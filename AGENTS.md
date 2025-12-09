# Agent Instructions

This file provides guidance for AI coding agents working in this repository.

## Project Overview

This is a **Vibe Coding Workshop** project - an interactive workshop designed to teach developers about agentic coding workflows and best practices.

**Key Features:**
- impress.js-based presentation framework
- Teaches AI-assisted development workflows
- Uses beads (bd) for issue tracking

## Tech Stack

- **Slide Deck**: [impress.js](https://github.com/impress/impress.js) - CSS3 transforms/transitions-based presentation framework
- **Documentation**: Markdown files
- **Issue Tracking**: [Beads](https://github.com/steveyegge/beads) - AI-native issue tracker via `bd` CLI

## Workflow Guidelines

## Issue Tracking with bd (beads)

**IMPORTANT**: This project uses **bd (beads)** for ALL issue tracking. Do NOT use markdown TODOs, task lists, or other tracking methods.

### Why bd?

- Dependency-aware: Track blockers and relationships between issues
- Git-friendly: Auto-syncs to JSONL for version control
- Agent-optimized: JSON output, ready work detection, discovered-from links
- Prevents duplicate tracking systems and confusion

### Quick Start

**Check for ready work:**
```bash
bd ready --json
```

**Search and list issues:**
```bash
bd list --status open --priority 1 --json
bd show <id> --json
```

**Create new issues:**
```bash
bd create "Issue title" -t bug|feature|task -p 0-4 --json
bd create "Issue title" -p 1 --deps discovered-from:bd-123 --json
bd create "Subtask" --parent <epic-id> --json  # Hierarchical subtask (gets ID like epic-id.1)
```

**Claim and update:**
```bash
bd update bd-42 --status in_progress --json
bd update bd-42 --priority 1 --json
```

**Complete work:**
```bash
bd close bd-42 --reason "Completed" --json
```

**Sync changes (CRITICAL at end of session!):**
```bash
bd sync  # Force immediate export/commit/push
```

### Issue Types

- `bug` - Something broken
- `feature` - New functionality
- `task` - Work item (tests, docs, refactoring)
- `epic` - Large feature with subtasks
- `chore` - Maintenance (dependencies, tooling)

### Priorities

- `0` - Critical (security, data loss, broken builds)
- `1` - High (major features, important bugs)
- `2` - Medium (default, nice-to-have)
- `3` - Low (polish, optimization)
- `4` - Backlog (future ideas)

### Workflow for AI Agents

1. **Check ready work**: `bd ready` shows unblocked issues
2. **Claim your task**: `bd update <id> --status in_progress`
3. **Work on it**: Implement, test, document
4. **Discover new work?** Create linked issue:
   - `bd create "Found bug" -p 1 --deps discovered-from:<parent-id>`
5. **Complete**: `bd close <id> --reason "Done"`
6. **Commit together**: Always commit the `.beads/issues.jsonl` file together with the code changes so issue state stays in sync with code state

### Auto-Sync

bd automatically syncs with git:
- Exports to `.beads/issues.jsonl` after changes (5s debounce)
- Imports from JSONL when newer (e.g., after `git pull`)
- No manual export/import needed!

### CLI Help

Run `bd <command> --help` to see all available flags for any command.
For example: `bd create --help` shows `--parent`, `--deps`, `--assignee`, etc.

### Important Rules

- ✅ Use bd for ALL task tracking
- ✅ Always use `--json` flag for programmatic use
- ✅ Link discovered work with `discovered-from` dependencies
- ✅ Check `bd ready` before asking "what should I work on?"
- ✅ Run `bd <cmd> --help` to discover available flags
- ❌ Do NOT create markdown TODO lists
- ❌ Do NOT use external issue trackers
- ❌ Do NOT duplicate tracking systems

### Working with impress.js

- Slides are HTML-based using impress.js framework
- Each step/slide uses `<div class="step">` with data attributes for positioning
- Use `data-x`, `data-y`, `data-z` for 3D positioning
- Use `data-rotate-x`, `data-rotate-y`, `data-rotate-z` for rotation
- Use `data-scale` for zoom effects
- See [impress.js documentation](https://github.com/impress/impress.js/blob/master/DOCUMENTATION.md) for full API

### Code Quality

- Keep slides accessible and readable
- Use semantic HTML
- Test presentations in modern browsers (Chrome, Firefox recommended)

## Session Ending Protocol

Before ending any session:

1. **File/update issues for remaining work**
   - Create issues for discovered bugs, TODOs, and follow-up tasks
   - Close completed issues and update status for in-progress work

2. **Run quality gates (if applicable)**
   - Verify HTML is valid
   - Test presentation renders correctly

3. **Sync the issue tracker**
   - Run `bd sync` to ensure local and remote issues merge safely
   - Handle any git conflicts thoughtfully

4. **Verify clean state**
   - All changes committed and pushed
   - No untracked files remain

5. **Provide next session context**
   - Suggest next steps or provide formatted prompt for continuation

## Project Structure

```
vibe-coding-workshop/
├── AGENTS.md           # This file - agent instructions
├── README.md           # Project documentation
├── .beads/             # Beads issue tracker database
├── slides/             # impress.js presentation files
│   ├── index.html      # Main presentation
│   ├── css/            # Presentation styles
│   └── js/             # JavaScript (impress.js)
└── docs/               # Additional workshop documentation
```

## Resources

- [Beads Documentation](https://github.com/steveyegge/beads)
- [impress.js Documentation](https://github.com/impress/impress.js/blob/master/DOCUMENTATION.md)
- [impress.js Getting Started](https://github.com/impress/impress.js/blob/master/GettingStarted.md)
