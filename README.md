# 🎸 Vibe Coding Workshop

An interactive workshop designed to teach developers about agentic coding workflows and best practices.

## Overview

This workshop teaches you how to effectively work with AI coding agents, leveraging tools like [Beads](https://github.com/steveyegge/beads) for issue tracking and memory management across coding sessions.

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari)
- [Beads](https://github.com/steveyegge/beads) CLI installed (`bd`)
- An AI coding agent (Claude Code, Copilot, etc.)

### Running the Presentation

Open the slides in your browser:

```bash
# Using a simple HTTP server
cd slides
python3 -m http.server 8000
# Then open http://localhost:8000 in your browser
```

Or simply open `slides/index.html` directly in your browser.

### Navigation

- **Arrow keys** or **Space**: Navigate between slides
- **Page Up/Down**: Navigate slides
- **Home**: Go to first slide
- **End**: Go to last slide
- **Esc** or **O**: Overview mode

## Project Structure

```
vibe-coding-workshop/
├── AGENTS.md           # Instructions for AI coding agents
├── README.md           # This file
├── .beads/             # Beads issue tracker database
├── slides/             # impress.js presentation
│   ├── index.html      # Main presentation file
│   └── css/            # Presentation styles
└── docs/               # Additional documentation (TBD)
```

## Workshop Content

1. **Introduction to Agentic Coding**
   - What is agentic coding?
   - Why use AI coding agents?

2. **Beads Issue Tracker**
   - Setting up Beads
   - Creating and managing issues
   - Dependency tracking
   - Agent workflows

3. **Hands-on Exercises**
   - Setting up a new project with Beads
   - Working with agents on multi-step tasks
   - Session continuity and context management

## Technologies Used

- **[impress.js](https://github.com/impress/impress.js)** - CSS3-powered presentation framework
- **[Beads](https://github.com/steveyegge/beads)** - AI-native issue tracker for coding agents

## Contributing

This is a workshop project. Feel free to fork and adapt for your own workshops!

## License

MIT
