# Keys, Identities, and Trust

Rove separates host connection settings, private keys, and host trust decisions.

## Key Manager

Open **Settings → Keys / Identities** to manage keys.

The Key Manager can:

- Import a private key from the system picker
- Import a private key by explicit local path
- Generate a new key
- Rename a key
- Delete an unused key
- View key details
- Copy the public key
- Show whether a passphrase is stored

## Generated keys

Generated keys support:

- Ed25519 with fixed 256-bit strength
- RSA with selectable 2048, 3072, or 4096-bit strength

Private keys are stored in device secure storage.

## Importing keys

When importing a key, provide:

- Local file or path
- Display label
- Optional passphrase

Imported keys can then be selected when creating or editing a host that uses private-key authentication.

## Deleting keys

Rove prevents deletion of a key while it is still assigned to one or more hosts. Remove or change those host assignments first.

## Public keys

Key details include the public key where available. Use **Copy public key** when you need to paste it into a server's `authorized_keys` file.

## Host trust

Host trust is host-scoped. If a connection problem looks related to a host key or fingerprint, Rove can route you to trust recovery for that host.

Do not accept a changed host key unless you understand why it changed. A changed host key can indicate a rebuilt server, a changed SSH endpoint, or a security problem.
