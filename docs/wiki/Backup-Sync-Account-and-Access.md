# Backup, Sync, Account, and Access

Rove includes account/access controls and workspace backup/sync tools.

## Account and access

Open **Settings → Account / Access** to review account and entitlement state.

This screen can show:

- Sign-in state
- Account label/provider
- Trusted device status
- Core local access
- Cloud-service access
- Sync access
- Paired web editor access
- Trial, Core ownership, subscription, and verification details where available

Available actions may include:

- Sign in with Google
- Sign out
- Start trial
- Buy Core once
- Subscribe
- Restore ownership
- Refresh ownership
- Manage subscription billing, when applicable
- Delete account, when available

## Trusted device

Rove may register the current device as a trusted device for account-backed access. The Account / Access screen shows trusted-device state and device-limit information where available.

## Workspace backup

Open **Settings → Workspace Backup** for local bundle and remote sync actions.

Local bundle actions include:

- Export current workspace bundle
- Review a local bundle import
- Review a local bundle restore
- Apply a reviewed import or restore plan

Rove reviews planned changes before applying them. Restore mode can delete local items and requires explicit confirmation.

## Remote sync

When remote sync is available, Workspace Backup can expose:

- Push current workspace
- Pull latest workspace
- Delete remote sync data

Remote deletion requires typed confirmation.

## Key resolution during import/restore

If an imported host uses key authentication and the private key is not available locally, Rove can prompt you to resolve that host to an existing local key.

Private keys are not treated as ordinary sync data. You must provision or import required private keys explicitly on each device.

## Account deletion

Account deletion is a private support/account action, not a public GitHub issue. Use the in-app account deletion flow or Jarsoft private support when available.
