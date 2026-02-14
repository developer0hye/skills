---
name: merge
description: Commit, push, create a PR, and merge it
disable-model-invocation: true
---

Perform commit, push, PR creation, and merge for the current branch:

1. Run `git status` (never use `-uall`), `git diff --cached`, and `git log --oneline -5` in parallel
2. Analyze all staged changes and draft a concise commit message (focus on "why", not "what")
3. Stage relevant untracked files if needed (prefer specific files over `git add -A`)
4. Commit using:
   - `git commit -s` (required for DCO)
   - HEREDOC format for the message
   - Append `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>`
5. Verify commit succeeded with `git status`
6. Push to remote with `git push -u origin HEAD`
7. Analyze ALL commits on this branch vs main using `git log main..HEAD` and `git diff main...HEAD`
8. Create a PR with `gh pr create` using:
   - Short title (under 70 chars)
   - Body in HEREDOC format:
     ```
     ## Summary
     <1-3 bullet points>

     ## Test plan
     <checklist>

     🤖 Generated with [Claude Code](https://claude.com/claude-code)
     ```
9. Show the PR URL to the user
10. Wait for CI checks to pass using `gh pr checks --watch` (timeout: 5 minutes)
11. Merge the PR with `gh pr merge --merge --delete-branch`
12. Confirm merge succeeded

Rules:
- Never commit to `main` branch — abort and warn if on main
- Never commit files that may contain secrets (.env, credentials, etc.)
- If there are no changes to commit, skip to PR creation if commits already exist
- If CI checks fail, stop and report the failure — do not force merge
- Ask the user for confirmation before merging
