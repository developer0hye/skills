---
name: memory-load
description: Load the last saved work context and resume where you left off
disable-model-invocation: true
---

Load the most recent work context from `.claude/memory/` in the project root and resume the work.

1. Resolve `.claude/memory/latest.md` (symlink → actual timestamped file)
   - If the file or directory doesn't exist, inform the user that no saved context was found and suggest using `/memory-save` first, then stop
2. Read the file and display a summary to the user:
   - When it was saved (highlight if older than 24 hours)
   - Goal
   - What was completed
   - What remains to be done
3. Verify the saved state is still valid:
   - Check if the branch still exists (`git branch --list <branch>`)
   - Check if the worktree directory still exists (`test -d <path>`)
   - Check if the PR is still open (if applicable, using `gh pr view`)
   - Report any discrepancies to the user
4. Ask the user: "Resume this work?" before proceeding
5. If confirmed, continue working on the remaining tasks from where the previous session left off

If multiple memories exist and the user wants an older one:
- List available memories: `ls -lt .claude/memory/[0-9]*.md`
- Let the user pick which one to load

Rules:
- Always verify paths and branches before assuming they still exist
- If the worktree was removed, offer to recreate it
- If the branch was deleted (e.g., after a PR merge), inform the user the task may already be complete
- Do not blindly execute — understand the context first, then act
