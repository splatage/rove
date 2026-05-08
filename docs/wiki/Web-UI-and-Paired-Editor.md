# Web UI and Paired Editor

Rove's current user-facing web UI is centered on `/paired-editor`.

The same web shell supports two related areas:

- **Paired Device** — pair a browser session to the Rove app and edit permitted non-secret device/profile data.
- **Pro web shell** — access Web Library and User Management views when the signed-in account has cloud-service access.

## Access model

The web UI requires a Rove web session. In production, the web login is tied to an existing app-provisioned Rove account. The browser session uses an HttpOnly cookie and CSRF protection for state-changing requests.

The web UI is gated by cloud-service access. Cloud-service access can come from:

- Active trial
- Active subscription
- Future/implemented active Pro seat source where supported by the backend
- Separately implemented explicit cloud-service grant

Permanent Core ownership alone is local/device access only. Core-only users should see upgrade/subscribe messaging instead of Web Library, Sync, or Paired Web Editor access.

## Paired Device flow

The paired editor flow is short-lived and explicit:

1. Open the web UI on a computer/browser.
2. The browser creates a short-lived pairing session.
3. The browser displays a QR code and manual pairing code.
4. The Rove app scans or enters the code.
5. The app verifies the pairing session against the backend.
6. The user approves pairing on the phone.
7. The app enters locked paired mode after live runtime teardown succeeds.
8. The browser receives an encrypted snapshot from the app.

The backend relay is a short-lived rendezvous/exchange room. It relays encrypted messages and must not become the authority for app data.

## What the web editor can edit

The paired web editor is family-scoped. The browser edits one family at a time and requires Review / Confirm Save before writing to the device.

Approved families include:

- Commands
- Global variables
- Portable preferences
- Approved host metadata/host setup fields

After a successful family save, the browser waits for a fresh device snapshot before further editing.

## What the web editor must not do

The web UI must not:

- Execute commands
- Control Runner jobs
- Browse remote files
- Control SSH or SFTP sessions
- Access terminal output
- Access runner output
- Read private keys, passphrases, passwords, API keys, or AI credentials
- Mutate public-key records directly
- Perform global multi-family Save All
- Push edits to an unattended device

## Web Library without a paired device

When cloud-service access is available, the web shell may show Web Library and User Management views without a paired device snapshot.

Offline web-shell views may include:

- Host Templates
- Command Library
- Account status
- Devices
- Pro workspace / members
- Activity

Device-specific apply/copy actions remain disabled until a same-account paired-device snapshot is loaded.

## Host templates

Host Templates are safe setup drafts for hosts. They can include fields such as label, address, port, username mode/default, default remote path, safe auth preference, key setup mode, terminal preference, and provisioning notes.

Applying a host template to a paired device mutates only the Hosts working copy. It still requires Hosts Review / Confirm Save before the device is written.

## Command Library

The Web Command Library stores simple shared command records for Pro workspaces. These records are separate from full app saved-command records.

Copying a shared command to a paired device mutates only the Commands working copy. It still requires Commands Review / Confirm Save before the device is written.

## Public key provisioning

The web UI may display public-key summaries already published by the app for provisioning. The browser may copy public-key text or an `authorized_keys` line when available.

This does not expose private keys and does not SSH into or modify a target server.

## Security posture

The paired editor is designed to fail closed. Disconnect, expiry, revoke, invalid encrypted frames, backgrounding the app, or teardown failure clears browser working state and does not create stale recovery fragments.
