# Exercise 2: GitHub Copilot for Non-Developers

**Time:** 25 minutes
**Goal:** Create GitHub issues that AI automatically implements
**Requirements:** GitHub account, access to workshop repository

---

## What You'll Learn

GitHub Copilot can do more than help developers write code — it can implement entire features from a simple issue description. You write a GitHub Issue, assign it to Copilot, and it:

1. Creates a new branch
2. Implements the changes
3. Opens a Pull Request for review

**No coding. No terminal. No development environment.**

---

## How It Works

```
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│   You write a   │ ──▶  │  Copilot reads  │ ──▶  │  Pull Request   │
│  GitHub Issue   │      │  and implements │      │  ready to merge │
└─────────────────┘      └─────────────────┘      └─────────────────┘
```

### The Workflow

1. **Open** the repository on GitHub
2. **Create** a new Issue describing what you want
3. **Assign** the issue to `@copilot`
4. **Wait** 2-5 minutes for implementation
5. **Review** the Pull Request it creates

---

## Getting Started (5 minutes)

### Step 1: Access the Repository
Go to: `https://github.com/ch-robinson-internal/Workshop.Ruairi.UI`

### Step 2: Navigate to Issues
Click the **Issues** tab at the top of the repository

### Step 3: Create a New Issue
Click the green **New Issue** button

---

## Writing Effective Issues

### The Formula

A good issue has three parts:

1. **Title** — Clear, action-oriented summary
2. **What** — Describe the feature or change
3. **Details** — Specific requirements (optional but helpful)

### Example Structure

```markdown
## What I Want
[Describe the feature in plain English]

## Requirements
- [Specific requirement 1]
- [Specific requirement 2]
- [Specific requirement 3]

## Additional Context
[Any helpful information for the AI]
```

---

## 8 Example Issues (Ready to Use!)

Copy these directly or use them as inspiration:

---

### Issue 1: Add a Navigation Header (Easy)

**Title:** Add a navigation bar to the top of all pages

**Description:**
```markdown
## What I Want
Create a navigation header component that appears at the top of every page.

## Requirements
- Show the app logo/avatar on the left
- Add navigation links to "Home" and "Fetch Example" pages
- Highlight the currently active page
- Use EDS components where possible
```

---

### Issue 2: Add a Footer (Easy)

**Title:** Add a footer to the bottom of all pages

**Description:**
```markdown
## What I Want
Create a footer component that displays at the bottom of every page.

## Requirements
- Show copyright text: "© 2025 C.H. Robinson"
- Add links to "Privacy Policy" and "Terms of Service" (can be placeholder # links)
- The footer should stick to the bottom of the viewport
```

---

### Issue 3: Create an About Page (Medium)

**Title:** Add a new "About" page with team information

**Description:**
```markdown
## What I Want
Create a new route `/about` with an About page.

## Requirements
- Add a heading "About This App"
- Include a brief description paragraph about the workshop app
- Show a section with 3-4 team member cards (can use placeholder names/roles)
- Add a link to this page from the Home page
- Use EDS Typography and layout components
```

---

### Issue 4: Improve Search Results Display (Medium)

**Title:** Display city search results in a formatted card instead of raw JSON

**Description:**
```markdown
## What I Want
In the FetchExample page, improve how search results are displayed.

## Requirements
- Instead of raw JSON in a `<pre>` tag, show results in a nice card format
- Display: City name prominently, State/Province, Country
- Show any other relevant fields from the API response
- Use EDS Card or Paper components for styling
```

---

### Issue 5: Add Loading State (Medium)

**Title:** Show a loading spinner while city search is in progress

**Description:**
```markdown
## What I Want
Improve the user experience when searching for cities.

## Requirements
- Show a loading spinner/indicator while waiting for results
- Disable the search button while loading
- Only show results after loading completes
- Use an EDS or MUI loading component
```

---

### Issue 6: Add Search History (Advanced)

**Title:** Display recent search history on the Fetch Example page

**Description:**
```markdown
## What I Want
Keep track of recent searches so users can quickly re-search.

## Requirements
- Store the last 5 city searches in component state
- Display them as clickable chips/tags below the search box
- When clicked, auto-populate the search field with that city name
- Show "Recent searches:" label above the list
- Add a "Clear history" button
```

---

### Issue 7: Add Dark Mode Toggle (Advanced)

**Title:** Add a button to toggle between light and dark mode

**Description:**
```markdown
## What I Want
Allow users to switch between light and dark themes.

## Requirements
- Add a toggle button (sun/moon icon) in the header
- Theme preference should apply to all pages
- Use the EDS theme provider's dark mode capabilities
- Consider persisting the preference in localStorage
```

---

### Issue 8: Add a Contact Form (Advanced)

**Title:** Create a Contact Us page with a feedback form

**Description:**
```markdown
## What I Want
Create a new `/contact` route with a contact form.

## Requirements
- Include fields: Name (required), Email (required with validation), Message textarea (required)
- Add a Submit button
- Show a success message after form submission (no actual backend needed)
- Use proper form validation with EDS form components
- Add a link to this page from the Home page navigation
```

---

## Your Task (15 minutes)

### Step 1: Choose 1-2 Issues
Pick from the examples above or create your own

### Step 2: Create the Issue
1. Click **New Issue**
2. Add the **Title**
3. Paste or write the **Description**
4. In the right sidebar, click **Assignees** and type `copilot`
5. Click **Submit new issue**

### Step 3: Wait for Implementation
- Copilot typically takes 2-5 minutes
- You'll see a comment on the issue when it starts working
- A Pull Request link will appear when it's done

### Step 4: Review the Pull Request
1. Click the PR link in the issue
2. Go to the **Files changed** tab
3. Review what Copilot implemented
4. Check if it matches your requirements

---

## Tips for Success

### ✅ Do This

- **Be specific** — "Add a blue button" is better than "add a button"
- **List requirements** — Bullet points help the AI understand each piece
- **Describe behavior** — "When clicked, show a success message"
- **Reference existing patterns** — "Use the same style as the Home page"

### ❌ Avoid This

- Don't be too vague — "Make it better" won't help
- Don't assume context — Describe what you want explicitly
- Don't forget to assign — The issue won't be picked up without `@copilot`

---

## Reviewing Pull Requests

When Copilot opens a PR, check:

| What to Check | How to Check |
|---------------|--------------|
| **Files changed** | Click "Files changed" tab |
| **Code quality** | Look for obvious issues (even without coding knowledge) |
| **Completeness** | Did it address all your requirements? |
| **Tests** | Did it add or update tests? |

### If Something's Wrong

Add a comment on the PR:
> "This is close, but the button should be green instead of blue. Can you fix that?"

Copilot will update the PR based on your feedback.

---

## Discussion Questions

After the exercise, consider:

1. How accurate was Copilot's implementation?
2. What would you have done differently in your issue description?
3. Where could you use this in your actual work?
4. What surprised you about the process?

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Issue not picked up | Check that `@copilot` is in the Assignees field |
| Taking too long (>10 min) | Check the Actions tab for any errors |
| Implementation is wrong | Add a comment with corrections, or close and create a new issue |
| Can't find the PR | Look in the Pull Requests tab, or check the issue for a link |

---

## Next Steps

Now that you've seen AI implement features from issues:

- **Exercise 3:** Snowflake SQL — generate database queries from natural language

[← Back to Workshop Outline](workshop-outline.md)
