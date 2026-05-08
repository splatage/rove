# Browser and File Operations

The Browser is Rove's remote file surface for a selected host.

## Opening folders and files

- Tap a folder to open it.
- Tap a file to preview it in the Editor.
- Use the up-level button to move to the parent folder.
- Use path segments to jump back to earlier path levels.
- Use the home button when a remote home path is available.

## View controls

The Browser includes explicit presentation controls:

- List or grid view
- Sort mode
- Hidden-files toggle
- Grid tile size, including pinch-to-resize on supported layouts
- Refresh

Changing sort or view mode changes presentation only. It does not change remote files.

## Selection mode

Use selection mode for batch-safe actions. Selection actions include:

- Copy
- Cut / move
- Delete
- Download
- Clear selection

The file-operation clipboard is scoped to the current host. It does not silently cross hosts.

## Single item actions

For a selected file, actions can include:

- Preview
- Edit
- Rename
- Copy path
- Properties

For a selected folder, actions can include:

- Open
- Rename
- Copy path
- Properties

## Uploads and downloads

Rove uses explicit SFTP-style transfers. Uploads require choosing local files and a remote destination. Downloads require choosing a local destination.

Folder sync and automatic recursive directory transfer are not part of the current product contract. Archive handling should be explicit rather than automatic.

## Conflicts and destructive actions

File conflicts use explicit choices such as replace, skip, rename copy, or cancel. Destructive operations require confirmation. Rove should not silently overwrite, silently merge, or pretend a partial operation can be rolled back when it cannot.

## Properties

Properties can show details such as:

- Displayed path
- Canonical path
- Type
- Size
- Modified time
- Permissions
- Symlink target, when available
- Access/editability status
