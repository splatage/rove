# Remote Editor

The Editor is Rove's app-native remote text editor.

## Opening files

Open the Browser, select or tap a file, then choose preview or edit depending on the available action.

The Editor opens as a full-screen task surface and returns to the workspace when closed.

## Preview and edit modes

A file may open in preview or edit mode depending on file type, size, permissions, and the action you choose.

The Editor is conservative:

- Text files only
- No persistent local working copy
- No autosave by default
- No silent format-on-save
- No silent line-ending or encoding normalization

## Status bar

The Editor status bar can show information such as:

- Syntax mode
- Preview/read-only state
- Modified state
- Cursor line and column
- Line count
- Character count

## Saving

Rove uses a safe remote-save model where possible:

1. Re-check the remote file state.
2. Write the new content to a temporary remote file.
3. Replace the original file when the remote server/filesystem supports it.

If the safer path is unavailable, Rove warns before continuing with a weaker fallback.

## Remote change conflicts

If the remote file changed after you opened it, Rove warns before saving. You can cancel, reload the remote version, or explicitly overwrite.

Rove should not silently overwrite a changed remote file.

## Failed save recovery

If save fails, Rove offers explicit recovery choices such as:

- Retry
- Save as another remote file
- Export locally
- Cancel

Local export is an explicit recovery action, not an automatic hidden draft.

## Disconnected editing

If the connection is lost while editing, the current edits remain in memory while the Editor is open. You can export locally when saving to the remote host is not possible.
