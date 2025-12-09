# Agent Instructions

This file provides guidance for AI coding agents working in this repository.

## Project Overview

This is a **Vibe Coding Workshop** project - an interactive workshop designed to teach developers about agentic coding workflows and best practices.

## Tech Stack

- **Slide Deck**: [impress.js](https://github.com/impress/impress.js) - CSS3 transforms/transitions-based presentation framework
- **Documentation**: Markdown files
- **Issue Tracking**: [Beads](https://github.com/steveyegge/beads) - AI-native issue tracker via `bd` CLI

## Before Starting Work

**BEFORE ANYTHING ELSE**: Run `bd onboard` and follow the instructions.

## Workflow Guidelines

### Issue Tracking with Beads

- Use `bd` for all issue tracking instead of markdown-based plans
- Run `bd ready` to find work with no blockers
- Create issues for discovered bugs/tasks with `bd create`
- Link discovered work to parent issues with `bd dep add <new-id> <parent-id> --type discovered-from`
- Update issue status as you work: `bd update <issue-id> --status in_progress`
- Close completed issues: `bd close <issue-id> --reason "Completed"`

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
