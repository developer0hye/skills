---
name: memory-save
description: Save current work context so it can be resumed in a new session
disable-model-invocation: true
---

Save the current work context to `.claude/memory/` in the project root so it can be resumed later with `/memory-load`.

1. Create the directory `.claude/memory/` in the project root if it doesn't exist
2. Ensure `.claude/memory/` is in `.gitignore` (add it if missing — session state should not be committed)
3. Analyze the current session and gather:
   - **Goal**: What the user is trying to accomplish
   - **Completed**: What has been done so far (commits, file changes, PRs created, etc.)
   - **In progress**: What is currently being worked on
   - **Remaining**: What still needs to be done
   - **Key paths**: Relevant file paths, worktree directories, branch names, PR URLs
   - **Decisions**: Important decisions or preferences the user expressed
   - **Blockers**: Any issues or blockers encountered
4. Write the context to `.claude/memory/<timestamp>.md` (format: `YYYYMMDD-HHMMSS.md`)
5. Update the symlink `.claude/memory/latest.md` to point to the new file:
   ```bash
   ln -sf <timestamp>.md .claude/memory/latest.md
   ```
6. Clean up old backups — keep only the **5 most recent** `.md` files (excluding the `latest.md` symlink). Delete older ones:
   ```bash
   ls -t .claude/memory/[0-9]*.md | tail -n +6 | xargs rm -f
   ```
7. Confirm to the user what was saved and how many backups exist

File format:

```markdown
# Work Context

**Saved**: <ISO 8601 timestamp>
**Project**: <project directory name>

## Goal
<What the user is trying to accomplish>

## Completed
- <List of completed items>

## In Progress
- <What is currently being worked on>

## Remaining
- <What still needs to be done>

## Key Paths
- **Branch**: <branch name>
- **Worktree**: <worktree path if applicable>
- **PR**: <PR URL if applicable>
- <Other relevant paths>

## Decisions
- <Important decisions or user preferences>

## Blockers
- <Any issues encountered, or "None">
```

Rules:
- Write in English
- Be concise but include enough detail for a fresh session to pick up the work
- Include exact file paths, branch names, and PR URLs — not vague references
