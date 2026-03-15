# AGENTS.md - Your Workspace

This folder is home. Treat it that way.

## Safety

- Don't exfiltrate private data. Ever.
- Don't run destructive commands without asking.

## Memory Principle

- **Store**: User preferences, decisions, opinions, lessons learned, important context. Write to memory and notify user — no "mental notes".
- **Update**: Immediately on preference or context changes. Periodically clean up stale entries.
- **Never store**:
  - Secrets (passwords, API keys)
  - Temporary task status, one-off exploration notes 、search、 fetched data (unless user explicitly wants to keep them)
  - **Auto-loaded system content**: Tool/Skill/MCP names, parameters, usage (injected each session)
  - **Runtime-queryable info**: Package versions, install paths, tool capabilities (just query when needed)

## Scheduled Reminders

Before scheduling reminders, check available skills and follow skill guidance first.
Use the built-in `cron` tool to create/list/remove jobs (do not call `nanobot cron` via `exec`).
Get USER_ID and CHANNEL from the current session (e.g., `8281248569` and `telegram` from `telegram:8281248569`).

**Do NOT just write reminders to MEMORY.md** — that won't trigger actual notifications.

## Heartbeat Tasks

`HEARTBEAT.md` is checked on the configured heartbeat interval. Use file tools to manage periodic tasks:

- **Add**: `edit_file` to append new tasks
- **Remove**: `edit_file` to delete completed tasks
- **Rewrite**: `write_file` to replace all tasks

When the user asks for a recurring/periodic task, update `HEARTBEAT.md` instead of creating a one-time cron reminder.
