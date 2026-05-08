# Rove App Map

This page maps the current `splatage/rove-app` source tree into user-facing product areas.

## Product shape

The app is a Flutter project named `rove` with version `0.1.3+3`. It uses SSH/SFTP, terminal, secure storage, local notifications, file picking, in-app purchase, localization, code editing/highlighting, and scanner-related dependencies.

The master specification defines Rove as a mobile-first SSH workspace with Browser, Shell, Composer, and app-native remote Editor surfaces.

## Startup and app shell

Relevant source:

```text
lib/main.dart
lib/app/app.dart
lib/app/host_workspace_root_shell.dart
```

Responsibilities:

- Initialize Flutter and run `RoveApp`.
- Bootstrap stores and services.
- Load preferences, hosts, keys, trust, diagnostics, account session, entitlements, sync, transfers, notifications, and paired editor services.
- Show the Host chooser by default.
- Retain live host workspaces inside the app lifetime.
- Route paired editor mode into a locked paired screen.
- Gate core workspace access through entitlement state.

## Host chooser and host setup

Relevant source:

```text
lib/features/hosts/chooser/host_chooser_screen.dart
lib/features/hosts/new_host/new_host_screen.dart
lib/features/hosts/host_detail/
lib/features/hosts/identity/
lib/features/hosts/trust/
```

User-facing responsibilities:

- List saved hosts.
- Toggle list/grid view.
- Open a host workspace.
- Manage host details by long press.
- Add new hosts.
- Configure authentication, default path, terminal session mode, and advanced SSH behavior.
- Show live transfer and Runner activity badges.

## Workspace

Relevant source:

```text
lib/features/workspace/workspace_screen.dart
lib/features/workspace/workspace_controller.dart
```

User-facing responsibilities:

- Hold the current host workspace frame.
- Switch between Browser, Shell, and Composer.
- Track connection state.
- Handle reconnect, disconnect, and recovery settings.
- Coordinate transfers, Runner completions, pending imports, and artifact downloads.

## Browser

Relevant source:

```text
lib/features/browser/browser_surface.dart
lib/features/browser/browser_controller.dart
```

User-facing responsibilities:

- Browse remote folders.
- Open files or folders.
- Toggle list/grid view.
- Sort entries.
- Show or hide hidden files.
- Copy paths.
- Upload and download files.
- Use selection mode for batch actions.
- Rename, delete, copy, cut, paste, and show properties.
- Open files in the Editor.

## Shell

Relevant source:

```text
lib/features/shell/shell_surface.dart
lib/features/shell/shell_controller.dart
```

User-facing responsibilities:

- Present a real interactive terminal.
- Start the shell when the selected host is live and Shell is active.
- Provide a mobile terminal accessory row.
- Support terminal text selection and copy.
- Support terminal text-size pinch adjustment.
- Confirm clipboard paste before insertion.

## Composer and Runner

Relevant source:

```text
lib/features/composer/composer_surface.dart
lib/features/composer/composer_controller.dart
lib/features/composer/composer_library_gateway.dart
lib/domain/models/composer_saved_command.dart
lib/domain/models/runner_invocation.dart
```

User-facing responsibilities:

- Draft prepared commands.
- Save and manage reusable commands.
- Load host, shared, and group shared commands.
- Manage variables.
- Resolve previews.
- Use AI assistance when configured.
- Execute explicit Runner jobs.
- Show Runner output.
- Download declared Runner artifacts.

## Editor

Relevant source:

```text
lib/features/editor/editor_screen.dart
lib/features/editor/editor_controller.dart
lib/services/editor/
```

User-facing responsibilities:

- Open remote text files in preview or edit mode.
- Show syntax highlighting and line numbers.
- Track modified state and cursor position.
- Save through the remote save service.
- Detect remote changes.
- Warn before weaker save fallbacks.
- Offer retry, save-as-remote, and local export recovery.

## Settings

Relevant source:

```text
lib/features/settings/settings_home_screen.dart
lib/features/settings/app_preferences_screen.dart
lib/features/settings/key_manager/key_manager_screen.dart
lib/features/settings/sync_settings_screen.dart
lib/features/settings/entitlement_settings_screen.dart
lib/features/settings/advanced_settings_screen.dart
```

User-facing responsibilities:

- App preferences.
- Keys and identities.
- Account/access/entitlements.
- Workspace backup and sync.
- Advanced operational settings.

## Services and storage

Relevant source groups:

```text
lib/services/ssh/
lib/services/sftp/
lib/services/shell/
lib/services/transfers/
lib/services/editor/
lib/services/storage/
lib/services/keys/
lib/services/trust/
lib/services/account/
lib/services/entitlements/
lib/services/sync/
lib/services/notifications/
lib/services/paired_editor/
lib/services/ai/
```

Responsibilities:

- SSH transport and shell channels.
- SFTP browsing and transfers.
- Remote editor save/read behavior.
- Shared preferences and secure storage.
- Key import/generation/metadata.
- Host trust.
- Account sessions, entitlements, and purchase state.
- Workspace bundle export/import/sync.
- Notifications and foreground active-work handling.
- Paired web editor lifecycle.
- Composer AI provider abstraction.

## Product boundaries visible in the code and docs

- No hidden command execution.
- No silent Browser-to-Shell command insertion.
- No silent upload target selection.
- No automatic public diagnostic upload.
- No persistent local editor working copy.
- No silent destructive fallback.
- Private support and public support remain separate.
