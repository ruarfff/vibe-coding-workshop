# 🎸 Vibe Coding Workshop

An interactive workshop that teaches you how to build software with AI assistants — no prior coding experience required!

## Overview

In this workshop, you'll learn how to work alongside AI coding assistants (like Claude, Copilot, and others) to create software. Think of it like having a knowledgeable partner who can write code while you guide the direction. We'll also use [Beads](https://github.com/steveyegge/beads) — a simple tool that helps AI assistants remember what they're working on between sessions.

## Getting Started

### What You'll Need

- A web browser (Chrome, Firefox, or Safari work best)
- [Beads](https://github.com/steveyegge/beads) installed (we'll walk you through this!)
- Access to an AI coding assistant (Claude, GitHub Copilot, or similar)

### Viewing the Presentation

The simplest way: just double-click `slides/index.html` to open it in your browser.

Alternatively, if you have Python installed, you can run a local server (this ensures all features work correctly):

```bash
cd slides
python3 -m http.server 8000
```

Then open your browser and go to: http://localhost:8000

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

## What You'll Learn

1. **Introduction to AI-Assisted Building**
   - What is "vibe coding"? (Hint: it's about collaboration, not memorizing syntax!)
   - How AI assistants can help you create software

2. **Giving Your AI a Memory (Beads)**
   - Why AI assistants sometimes forget things
   - How Beads helps your AI remember tasks and context
   - Simple commands to track your project's progress

3. **Hands-on Practice**
   - Start a new project with your AI assistant
   - Work through multi-step tasks together
   - Pick up where you left off in future sessions

## Tools We Use

- **[impress.js](https://github.com/impress/impress.js)** - The engine behind our interactive presentation
- **[Beads](https://github.com/steveyegge/beads)** - A memory system that helps AI assistants track tasks and progress

## Contributing

This is a workshop project. Feel free to fork and adapt for your own workshops!

## License

MIT
