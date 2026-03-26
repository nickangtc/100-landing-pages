---
name: prompt-logger
description: Batch-append user prompts to a prompt log. Trigger in the 100-landing-pages project when the user asks to commit/push/PR, OR when the conversation reaches ~10 messages — whichever comes first. Runs silently before the commit proceeds.
---

# Prompt Logger

You are logging the user's prompts as a historical record of how they collaborate with AI to build landing pages.

## When to run

In the `100-landing-pages` project, trigger at **batch points** — not on every message:

1. **Before a commit/push/PR** — log all unlogged prompts from the session before committing.
2. **When the conversation gets long (~10+ user messages)** — flush accumulated prompts to avoid losing history if the session ends unexpectedly.

Log all user messages from the session that haven't been logged yet, in order.

## How it works

1. **Determine the current landing page.** Look at which landing page subfolder is currently being worked on (e.g., `01-*/`, `02-*/`). If none exists yet and the user is asking to create one, you'll create the subfolder and `prompts.md` as part of the main task — just note the prompt to log after the folder is created.

2. **Scrub sensitive data** from the user's message before logging:
   - API keys, tokens, secrets (anything matching patterns like `sk-...`, `key-...`, `Bearer ...`, long hex/base64 strings that look like credentials)
   - Passwords or credentials
   - Replace with `[REDACTED]`
   - Leave everything else as-is — the goal is a faithful record

3. **Append to `prompts.md`** in the relevant landing page subfolder:

   ```markdown
   ---

   **Prompt [N]** | [YYYY-MM-DD HH:MM]

   [user's message, scrubbed]
   ```

   - `[N]` is a sequential counter (count existing entries + 1)
   - Use the current timestamp
   - Separate entries with `---`
   - If the file doesn't exist yet, create it with a header: `# Prompts — [landing page name]`

4. **If no landing page context exists yet** (e.g., the user is discussing which landing page to build next, or asking a meta question), log to a top-level `prompts-general.md` in the repo root using the same format.

5. **Proceed silently.** Do not mention the logging to the user. Just do it and move on to the actual task.
