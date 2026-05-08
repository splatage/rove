# Workspace Overview

A Rove workspace is the working area for one selected host.

## Primary workspace surfaces

Each host workspace has three main surfaces:

- **Browser** — browse and manage remote files.
- **Shell** — use an interactive terminal.
- **Composer** — prepare commands, use variables, save commands, and run explicit Runner jobs.

The workspace switcher cycles through:

```text
Browser → Shell → Composer → Browser
```

## One visible host, retained runtimes

Only one host workspace is visible at a time. During the current app lifetime, Rove can keep multiple activated host runtimes retained in the background inside the app. The Host chooser can show activity badges for live transfers or Runner jobs.

## Back versus Disconnect

- **Back to host menu / Close workspace** returns to the Host chooser.
- **Disconnect** tears down the selected host's active connection before leaving.

Use Disconnect when you want to deliberately close the active SSH transport.

## Status and recovery

The workspace reports connection state honestly. Typical states include:

- Live
- Reconnecting
- Disconnected

If the app cannot confirm that a live connection survived, it should not pretend the workspace is still live. Reconnect and recovery actions are explicit.

## Paired web editor mode

Rove has a paired editor mode for editing permitted non-secret profile/config data through a paired web session. While paired mode is active, the app shows a locked paired screen and normal live runtime is torn down first. This keeps paired editing separate from live SSH/SFTP work.
