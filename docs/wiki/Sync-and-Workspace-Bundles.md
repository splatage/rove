# Sync and Workspace Bundles

Rove uses one canonical **WorkspaceBundle** format for portable workspace state.

The same bundle family supports:

- Local export
- Local import
- Backup
- Restore
- Personal sync
- Future trusted managed bundle apply

## What a workspace bundle can include

First-wave portable workspace state may include:

- Hosts
- Composer saved commands
- Composer variables
- Preferences
- AI provider/model defaults, without credentials
- Public keys and public-key metadata
- Other approved non-secret workspace configuration

## What a workspace bundle must not include

Bundles must exclude:

- Private keys
- Passwords
- Passphrases
- API keys
- AI credentials
- Clipboard contents
- Recent command history
- Live Runner state
- Terminal output
- Remote file contents
- Transient runtime-only UI state

Private keys remain local to the app/device.

## Import mode

Import is non-destructive.

Import may:

- Create missing records
- Update matching records

Import must not:

- Delete local records just because they are absent from the bundle
- Infer deletion from omission
- Silently clobber unrelated local state

Use import when you want to add or update workspace content without resetting the current workspace.

## Restore mode

Restore/reset is the destructive path.

Restore may create, update, and delete according to the reviewed restore plan. Rove shows a review before applying the plan and requires explicit confirmation for destructive restore behavior.

Use restore only when you intend to replace/reset local workspace state from the selected bundle or remote backup.

## Personal sync

Personal sync uses the same bundle substrate but with cloud storage and revision tracking.

Sync is a cloud-service feature. It requires active trial, active subscription, active Pro seat where supported, or another explicit cloud-service grant. Permanent Core ownership alone does not unlock sync.

## Push and pull

When remote sync is available:

- **Push** sends the current workspace bundle to the remote sync service.
- **Pull** retrieves the latest remote workspace state and prepares a local apply plan.

Pulling remote sync data is still reviewed before applying changes.

## Revision and hash model

The backend stores canonical bundle JSON with revision metadata and content hash. Revision/hash semantics are preferred over wall-clock timestamps for determining bundle state.

The app and backend should avoid exposing partially written remote revisions as current state.

## Public keys and provisioning

Public keys may be projected to the web/control plane so users or admins can copy them for server provisioning.

The web may display/copy public keys. It does not receive private keys and does not become the authority for key ownership.

## Sync versus ownership restore

Sync/restore affects workspace data.

Ownership restore affects commercial entitlements.

These are different actions and should not be confused.
