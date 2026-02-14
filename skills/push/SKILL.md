---
name: push
description: Commit staged changes and push to remote
disable-model-invocation: true
---

Perform commit and push for the current branch:

1. Run `git status` (never use `-uall`), `git diff --cached`, and `git log --oneline -5` in parallel
2. Analyze all staged changes and draft a concise commit message (focus on "why", not "what")
3. Stage relevant untracked files if needed (prefer specific files over `git add -A`)
4. Commit using:
   - `git commit -s` (required for DCO)
   - HEREDOC format for the message
   - Append `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>`
5. Verify commit succeeded with `git status`
6. Push to remote with `git push -u origin HEAD`

Rules:
- Never commit to `main` branch — abort and warn if on main
- Never commit files that may contain secrets (.env, credentials, etc.)
- If there are no changes to commit, inform the user and stop
