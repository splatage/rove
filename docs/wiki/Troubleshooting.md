# Troubleshooting

This page covers common Rove recovery paths.

## Connection will not open

Check:

- Host/address is correct
- Port is correct
- Username is correct
- Authentication method matches the server
- Password or private key is correct
- Network access to the server is available
- Host key trust has not changed unexpectedly

If Rove detects an authentication or trust-related problem, it may offer a recovery path to identity or trust settings for that host.

## Host key or fingerprint warning

Do not accept a changed host key automatically.

A host key warning can mean the server was rebuilt, the SSH endpoint changed, DNS points somewhere different, or something unsafe is happening. Verify the expected fingerprint through a trusted channel before accepting the change.

## Shell does not persist after disconnect

A normal interactive shell is tied to the active SSH transport.

For real remote shell persistence, configure the host to use GNU screen or tmux with a session name. That creates or reattaches to a remote session that can survive app disconnects when the remote session itself remains alive.

## Browser cannot open a folder

Check that the connected user has permission to read the folder. Try opening the parent folder or the remote home folder.

## Upload or download failed

Check:

- The connection is still live
- The remote folder is writable for uploads
- The local destination is available for downloads
- There is enough space on the target side
- Any conflict prompts were answered correctly

Failed transfer rows can be retried, cancelled, dismissed, or reviewed depending on their state.

## Editor opened read-only

A file may open read-only when Rove cannot safely prove it is editable, the file is too large, the file is not text-like, or the remote permissions do not allow writing.

Use Preview for read-only inspection. Use Edit only when the file is suitable and writable.

## Save failed in the Editor

Rove may offer:

- Retry
- Save as another remote file
- Export locally
- Cancel

If the remote file changed while you were editing, Rove asks before overwrite or reload.

## Account or entitlement problem

Open **Settings → Account / Access** and try:

- Refresh ownership
- Restore ownership
- Sign out and sign in again

Do not post account identifiers, purchase details, or entitlement details in public GitHub issues. Use private support.

## Public issue safety

When reporting a bug publicly, redact hostnames, usernames, paths, screenshots, logs, credentials, account details, and private infrastructure details.
