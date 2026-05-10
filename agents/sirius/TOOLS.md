# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

## GitHub MCP Server (via mcporter)

Sirius has access to GitHub via the `mcporter` MCP bridge. Use `mcporter call github.<tool>` to invoke.

### Allowed (read-only) tools:
- `github.search_repositories` — search repos
- `github.search_issues` — search issues/PRs across repos
- `github.search_code` — search code
- `github.search_users` — search users
- `github.get_file_contents` — read a file from a repo
- `github.get_issue` — get issue details
- `github.get_pull_request` — get PR details
- `github.get_pull_request_files` — list files in a PR
- `github.get_pull_request_status` — CI/check status on a PR
- `github.get_pull_request_comments` — PR comments
- `github.get_pull_request_reviews` — PR reviews
- `github.list_issues` — list issues in a repo
- `github.list_pull_requests` — list PRs in a repo
- `github.list_commits` — list commits

### FORBIDDEN (write) tools — never call these:
- `github.create_or_update_file`
- `github.create_repository`
- `github.create_issue`
- `github.create_pull_request`
- `github.create_pull_request_review`
- `github.create_branch`
- `github.push_files`
- `github.fork_repository`
- `github.merge_pull_request`
- `github.update_issue`
- `github.update_pull_request_branch`
- `github.add_issue_comment`

---

## Disabled Tools

### Browser (disabled)
The `browser` tool is **disabled** on this VM. Never call `browser navigate`, `browser snapshot`, or any browser action. Chromium is not installed and will not be reinstalled — it caused repeated OOM crashes on this 8GB Tencent VM.

For URL fetching, use `web_fetch`. For web search, use `web_search` (Brave Search API).

---

Add whatever helps you do your job. This is your cheat sheet.
