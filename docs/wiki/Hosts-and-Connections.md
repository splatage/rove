# Hosts and Connections

Hosts are the saved remote systems you connect to from Rove.

## Host chooser

The Host chooser is the app entry point. It lists your saved hosts and shows live activity such as active transfers or Runner jobs.

Actions:

- Tap a host to open or reconnect its workspace.
- Long press a host to manage it.
- Use the view toggle to switch between list and grid.
- Use **New host** to add another host.

Pinned hosts appear first. Other hosts are ordered by recent use.

## New host fields

The basic host setup screen includes:

- Label
- Host / address
- Port
- Username
- Authentication method
- Password or selected private key
- Default remote path
- Terminal session mode
- Terminal session name, when using a persistent terminal session

## Authentication methods

Rove supports password authentication and private-key authentication. Passwords are stored through secure storage. Private keys are managed through the Key Manager.

## Terminal session modes

A host can use:

- No persistent terminal session
- GNU screen
- tmux

When screen or tmux is configured, Rove can reattach to the named remote session when starting the shell. This is the durable remote-side shell persistence model. The app does not pretend a shell stayed alive if the remote session did not.

## Advanced SSH settings

Advanced host setup exposes SSH-style options such as address family, connection timeout, keepalive/reliability controls, reconnect window, reconnect attempts, TCP keepalive, and identity behavior.

## Live workspace behavior

Rove may retain live host workspaces during the current app lifetime. Returning to the host chooser or closing the workspace does not necessarily disconnect the host. Use **Disconnect** when you want to tear down that host's active transport.
