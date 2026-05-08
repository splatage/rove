# Shell and Terminal

The Shell is Rove's real interactive terminal surface for the selected host.

## Opening the shell

Open a host workspace, then use the workspace switcher until the Shell surface is active. Rove starts the shell only when the host transport is live and the Shell surface is active.

## Keyboard and accessory row

On mobile, the Shell includes a terminal-specific input accessory row when the keyboard is visible. It provides quick access to:

- Ctrl
- Esc
- Tab
- Arrow keys
- Paste
- Copy selection, when text is selected

Paste is explicit and shows the clipboard text before inserting it.

## Text size

Pinch on the terminal to adjust terminal text size. Terminal text size is separate from the broader app display size.

## Selection mode

Long press in the terminal starts temporary selection mode. In selection mode you can:

- Copy selected text
- Clear selection
- Select all in the buffer
- Select the visible screen

Selection mode is explicit. It closes the terminal keyboard while active.

## Persistent terminal sessions

For durable remote shell continuity, configure the host to use GNU screen or tmux with a session name. Rove can then attach to the named remote session when the Shell starts.

Without screen or tmux, the shell is a normal interactive PTY tied to the active SSH transport.

## Boundaries

The Shell is manual. Browser actions do not silently insert paths or commands into the Shell. Saved commands and Runner execution belong to Composer, not the Shell surface.
