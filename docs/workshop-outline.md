# Vibe Coding Workshop — Facilitator Guide

**Duration:** 90 minutes
**Audience:** Non-developers who want to leverage AI for software creation
**Prerequisites:** GitHub account, Lovable.dev account, Snowflake access

---

## Workshop Overview

This workshop introduces non-developers to "vibe coding" — the practice of building software through natural language conversations with AI. Participants will complete three hands-on exercises without writing any code or setting up development environments.

### Learning Objectives

By the end of this workshop, participants will:

1. Understand what vibe coding is and its key principles
2. Know how to work effectively with LLM Coding Agents
3. Build a simple app using Lovable.dev
4. Create GitHub issues that GitHub Copilot implements automatically
5. Use LLMs to generate SQL queries from natural language

---

## Agenda

| Time | Section | Duration |
|------|---------|----------|
| 0:00 | Opening & What is Vibe Coding | 10 min |
| 0:10 | AI Knowledge & Limitations | 10 min |
| 0:20 | The Future of AI Agents | 5 min |
| 0:25 | **Exercise 1: Lovable.dev** | 20 min |
| 0:45 | **Exercise 2: GitHub Copilot** | 25 min |
| 1:10 | **Exercise 3: Snowflake SQL** | 15 min |
| 1:25 | Closing & Q&A | 5 min |

---

## Section 1: Opening & What is Vibe Coding (10 min)

### Slides: title → ai-mistakes

### Talking Points

**What is Vibe Coding?**
- Term coined by Andrej Karpathy (OpenAI co-founder, former Tesla AI lead) in February 2025
- The idea: describe what you want in plain English, let AI write the code
- "Fully give in to the vibes, embrace exponentials, forget the code exists"

**Conversation, Not Commands**
- Vibe coding is a dialogue, not a specification document
- You don't need perfect prompts — iterate and refine
- Problem-solving conversations are messy but productive
- AI tolerates your typos, vague descriptions, and changes of mind

**AI Makes Mistakes**
- Set expectations: AI will get things wrong
- This is normal and expected — not a failure
- Each correction teaches the AI what you actually want
- The goal is iteration, not perfection on the first try

---

## Section 2: AI Knowledge & Limitations (10 min)

### Slides: ai-knowledge → errors

### Talking Points

**What AI Knows**
- Trained on vast amounts of internet content
- Knows programming languages, frameworks, tools, patterns
- Has seen millions of examples of working code
- Like having access to every Stack Overflow answer ever written

**The Mind-Reading Problem**
- AI can't guess what's in your head
- Being specific saves time (but don't over-optimize prompts)
- AI defaults to "appearing helpful" — may claim success prematurely
- Defaults to bare-minimum implementations unless you ask for more

**Quality Checklist (from "Vibe Coding" by Kim & Yegge)**

1. **Count your babies** — Verify every requested component was actually delivered
2. **Check for cardboard muffins** — Look beyond "it works" to check if implementation is real
3. **Demand excellence explicitly** — Specify quality standards; you get what you ask for
4. **Clean as you go** — Include cleanup in every request; AI will leave messes otherwise
5. **Trust but verify** — Working code can hide deeper problems

**Handling Errors**
- Copy/paste error messages directly to the AI
- Take screenshots of visual problems
- Describe expected vs actual behavior
- Don't try to debug yourself — let AI help

---

## Section 3: The Future of AI Agents (5 min)

### Slides: future

### Talking Points

**Where This Is Going**
- **Async remote agents:** AI works on your tasks overnight, you review in the morning
- **Clusters of agents:** Multiple AIs collaborating on different parts of a project
- **Supervisor agents:** AI orchestrating and managing other AIs
- **Agent meshes:** Networks of specialized AIs for different domains

**The Takeaway**
- We're at the very beginning of this technology
- Skills learned today will become more powerful as tools improve
- The ability to work with AI is a career superpower

---

## Section 4: Exercise 1 — Lovable.dev (20 min)

### Slides: exercise1-intro → exercise1-ideas

### Setup (2 min)
1. Direct participants to [lovable.dev](https://lovable.dev)
2. Have them create a free account if they haven't already
3. Click "Create new project"

### Activity (15 min)
- Participants describe an app idea in plain English
- Watch AI build the app in real-time
- Iterate by adding features or making changes

### App Ideas for Inspiration
- Personal to-do list with categories
- Birthday reminder app for friends & family
- Simple expense tracker
- Habit tracker with streaks
- Recipe collection organizer
- Weather dashboard

### Facilitation Tips
- Encourage simple ideas first
- Remind them: "You can always add more features"
- If stuck, suggest: "A to-do list is always a good start"
- Help troubleshoot any account/login issues

### Wrap-up (3 min)
- Ask 2-3 volunteers to share what they built
- Highlight: "You just built an app without writing code!"

---

## Section 5: Exercise 2 — GitHub Copilot (25 min)

### Slides: exercise2-intro → exercise2-examples

### Context
Participants will use GitHub's Copilot feature that implements issues automatically. When you assign an issue to `@copilot`, it:
1. Creates a new branch
2. Implements the requested changes
3. Opens a pull request for review

### Setup (5 min)
1. Navigate to the workshop repository (provide URL)
2. Ensure participants can access it
3. Walk through the repository structure briefly

### Activity (15 min)
- Each participant creates 1-2 GitHub issues
- Assign issues to `@copilot`
- Wait for implementation (2-5 minutes typically)
- Review the pull request

### Example Issues (ready to copy)

**Easy:**
> **Title:** Add a footer with copyright text
>
> Add a footer component that appears at the bottom of every page with:
> - Copyright text: "© 2025 [Company Name]"
> - The footer should be styled consistently with the rest of the app

**Medium:**
> **Title:** Add a navigation header with page links
>
> Create a navigation bar at the top of all pages with:
> - Links to "Home" and "About" pages
> - Highlight the currently active page
> - Use existing design system components

**Advanced:**
> **Title:** Add a loading spinner to the search
>
> When a user submits a search:
> - Show a loading spinner while waiting for results
> - Disable the search button during loading
> - Only show results after loading completes

### Facilitation Tips
- Start with simple issues (footer, button color change)
- Remind participants: "Write like you're explaining to a colleague"
- If Copilot gets confused, help them refine the issue description
- Point out the "Files changed" tab in the PR

### Wrap-up (5 min)
- Review one or two PRs together as a group
- Discuss: "What was different about your expectations vs. what Copilot delivered?"
- Reinforce the "trust but verify" principle

---

## Section 6: Exercise 3 — Snowflake SQL (15 min)

### Slides: exercise3-intro → exercise3-hands-on

### Context
Participants will use an AI assistant (ChatGPT, Copilot Chat, etc.) to generate Snowflake SQL queries from natural language descriptions.

### Setup (2 min)
- Open the AI assistant of choice
- Optionally provide schema context to the AI

### Activity (10 min)

**Step 1: Describe the schema**
```
I'm working with a Snowflake database that has these tables:
[PLACEHOLDER: Add your actual schema here]
```

**Step 2: Ask business questions**
- "Show me the top 10 customers by revenue this quarter"
- "Find all orders from last month that are still pending"
- "Compare sales by region for 2024 vs 2023"

**Step 3: Iterate**
- "Actually, filter that to just the West region"
- "Add a column showing the percentage of total"
- "Make it a weekly breakdown instead of monthly"

### Example Prompts

| Business Question | What AI Generates |
|-------------------|-------------------|
| "Show me top customers" | SELECT with ORDER BY and LIMIT |
| "Compare this year to last" | Query with date filtering and aggregation |
| "Find pending items" | WHERE clause with status filtering |

### Facilitation Tips
- Emphasize: "You're describing the business question, not the technical query"
- If queries don't work, show how to paste errors back to the AI
- Demonstrate iteration: "Now add a filter for..."

### Wrap-up (3 min)
- Key insight: "You can get data insights without learning SQL"
- The AI handles syntax; you bring business knowledge

---

## Section 7: Closing & Q&A (5 min)

### Slides: takeaways → closing

### Key Takeaways

1. **Vibe coding is a conversation** — Iterate, don't perfect
2. **AI makes mistakes** — That's expected and okay
3. **Be specific about what you want** — AI can't read minds
4. **Trust but verify** — Always review the output
5. **You don't need to code** — These tools are for everyone

### Resources to Share
- [Lovable.dev](https://lovable.dev)
- [GitHub Copilot](https://github.com/features/copilot)
- ["Vibe Coding" book by Gene Kim & Steve Yegge](https://www.amazon.com/dp/B0F41Y3YMM)

### Questions
- Open floor for Q&A
- If time permits, demonstrate one more quick example

### Follow-up
- Provide contact info for questions after the workshop
- Share link to this documentation
- Encourage participants to practice with their own projects

---

## Troubleshooting

### Common Issues

| Problem | Solution |
|---------|----------|
| Lovable.dev won't load | Try incognito mode, check ad blockers |
| GitHub issue not picked up | Verify `@copilot` is spelled correctly in assignees |
| Copilot PR takes too long | Normally 2-5 min; check GitHub Actions for status |
| SQL query has errors | Paste the error back to the AI and ask it to fix |

### Technical Requirements
- Modern browser (Chrome, Firefox, Safari, Edge)
- Stable internet connection
- GitHub account with repo access
- Snowflake access (for Exercise 3)

---

## Appendix: Slide Reference

| Slide ID | Section | Content |
|----------|---------|---------|
| title | Opening | Workshop title and tagline |
| intro | Opening | Learning objectives |
| what-is-vibe | Opening | Definition of vibe coding |
| conversation | Opening | Conversation not commands |
| ai-mistakes | Opening | AI makes mistakes and that's okay |
| ai-knowledge | AI Limits | What AI knows |
| ai-limits | AI Limits | Cannot read minds |
| quality-checklist | AI Limits | Kim/Yegge quality checklist |
| trust-verify | AI Limits | Trust but verify |
| errors | AI Limits | Handling errors |
| future | Future | Async agents, meshes, supervisors |
| exercise1-intro | Lovable | Exercise 1 introduction |
| exercise1-ideas | Lovable | App ideas |
| exercise2-intro | Copilot | Exercise 2 introduction |
| exercise2-workflow | Copilot | How it works |
| exercise2-examples | Copilot | Example issues |
| exercise3-intro | Snowflake | Exercise 3 introduction |
| exercise3-examples | Snowflake | Example prompts |
| exercise3-hands-on | Snowflake | Hands-on (placeholder) |
| takeaways | Closing | Key takeaways |
| closing | Closing | Q&A and resources |
