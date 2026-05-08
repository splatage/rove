# Composer and Runner

Composer is Rove's prepared-command workspace. It is separate from the live interactive Shell.

## What Composer is for

Use Composer to:

- Draft commands before using them
- Save reusable commands
- Organize host-specific and shared commands
- Work with variables and placeholders
- Preview resolved command text
- Run explicit Runner jobs
- Copy command text or Runner output
- Use bounded AI assistance where configured

## Composer versus Shell

The Shell is a manual interactive terminal. Composer is a command-preparation and Runner surface.

Composer does not silently execute commands. Running a command through Runner is an explicit action.

## Saved commands

Composer can save the current document as a reusable command. Saved command metadata can include details such as title, notes, execution profile, pinned state, and declared artifacts.

Saved commands can be copied, duplicated, pinned, deleted, or opened for editing depending on the command source and available services.

## Variables and placeholders

Composer supports variables and command token expansion. The product model keeps built-in placeholders and user variables separate.

General rule:

- Built-in contextual placeholders are app-owned.
- User-defined variables are explicit user assets.
- Unresolved required values should block execution rather than silently expanding to empty text.

## Runner

Runner executes a prepared command as an explicit job for the current host. Runner output stays associated with the invocation so it can be reviewed and copied.

Runner completions are visible in the workspace. Active Runner jobs may also appear as host activity in the Host chooser.

## Artifacts

Saved commands may declare expected artifacts. When a Runner job succeeds, Rove can present a download action for a declared artifact. Artifact downloads are explicit and use the transfer flow.

## AI assistance

Composer can expose AI assistance when a provider is configured. AI assistance is an assist layer for text; it should not silently mutate commands or execute anything. Applying, copying, or opening AI output is a user action.
