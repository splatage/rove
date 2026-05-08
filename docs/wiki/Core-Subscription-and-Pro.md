# Core, Subscription, and Pro

Rove uses a clear commercial model:

- **Trial** lets users evaluate the full product temporarily.
- **Core** is a one-time purchase for permanent local/device access.
- **Subscription** adds cloud-service features and grants Core access while active.
- **Pro** is the shared workspace / seat-based layer built on the subscription family.

## Trial

The trial is account-backed and backend-authoritative. It is not a store-managed Core purchase trial.

While active, trial access temporarily includes:

- Core local/device access
- Cloud-service access
- Sync
- Paired Web Editor / web shell access

When trial ends, Core local/device access ends unless the user owns Core or has an active subscription. Cloud-service access ends unless the user has an active subscription or another explicit cloud-service grant.

## Core

Core is the one-time unlock for the complete local/device Rove workbench.

Core includes local/device functionality such as:

- SSH terminal
- SFTP browser
- Composer
- Runner
- App-native remote editor
- Local command library
- Local variables
- Local preferences
- Local hosts
- Local import/export bundle use
- Local artifact handling
- Local BYOK AI support where configured

Core does not include ongoing backend/cloud services such as:

- Workspace sync
- Cloud backup/restore storage
- Paired Web Editor access
- Web Library
- Managed cloud profiles
- Future backend convenience services

Permanent Core ownership survives subscription cancellation.

## Subscription

The subscription is optional recurring access to the cloud-service version of Rove.

While active, the subscription grants:

- Core local/device access while subscribed
- Cloud-service access
- Sync access
- Paired Web Editor / web shell access
- Hosted continuity features such as workspace backup/restore and revisioned bundle storage where implemented

A user may subscribe whether or not they already own Core.

If subscription ends:

- A Core owner falls back to permanent Core local/device access.
- A non-Core owner loses Core access unless another entitlement source applies.
- Cloud-service features end unless another cloud-service entitlement source applies.

## Restore ownership versus restore workspace

Rove keeps these separate:

- **Restore ownership** restores commercial entitlements such as Core or subscription access.
- **Restore workspace backup** restores workspace data from a bundle or remote sync source.

Restoring ownership does not restore hosts, commands, variables, keys, or workspace content by itself.

## Store product mapping

Recommended store mapping:

- Core: one-time product / non-consumable purchase
- Subscription monthly: recurring subscription
- Subscription annual: recurring subscription

Recommended product identifiers from the contract are:

```text
rove.core.unlock
rove.subscription.monthly
rove.subscription.annual
```

## Pro

Pro is the customer-facing shared workspace and seat-based subscription layer.

Pro is not a shared login. Each member keeps:

- Their own Rove account
- Their own app session
- Their own trusted devices
- Their own device-local private keys

A Pro workspace can support shared assets such as:

- Host Templates
- Command Library
- Members and roles
- Seat assignment
- Public-key provisioning visibility
- Activity/audit views

## Pro seats

A Pro seat is a derived entitlement source. When active and valid, a seat may contribute:

- Core local/device access
- Cloud-service access

Seat assignment does not delete or control a member's local app data. Revoking a seat removes the seat-derived entitlement source, and the user falls back to any personal trial, Core, subscription, or admin-grant source they still have.

## Pro boundaries

Pro does not mean:

- Shared login
- Owner access to member private keys
- Unattended member-device editing
- Push edits to another user's app
- Browser control of SSH/SFTP or Runner
- Billing-provider mutation from the Pro web shell

Cross-account paired editing, where supported later, must be short-lived, code-based, member-entered, member-approved, and family-scoped.
