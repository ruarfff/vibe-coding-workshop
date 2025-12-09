# Exercise 3: Snowflake SQL with AI Assistance

**Time:** 15 minutes
**Goal:** Generate SQL queries from natural language descriptions
**Requirements:** Snowflake access, AI assistant (ChatGPT, Copilot Chat, etc.)

---

## What You'll Learn

You don't need to know SQL to get insights from your data. By describing what you want in plain English, AI can generate the SQL queries for you.

**The AI handles the syntax. You bring the business knowledge.**

---

## How It Works

```
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│  You describe   │ ──▶  │   AI generates  │ ──▶  │   Run query in  │
│  business need  │      │   SQL query     │      │   Snowflake     │
└─────────────────┘      └─────────────────┘      └─────────────────┘
```

### The Workflow

1. **Share** your database schema with the AI
2. **Describe** what data you want in plain English
3. **Copy** the generated SQL query
4. **Run** it in Snowflake
5. **Iterate** if the results aren't quite right

---

## Getting Started

### Step 1: Open Your AI Assistant
Use :
- GitHub Copilot Chat <https://github.com/copilot>

### Step 2: Provide Schema Context
Share your database structure with the AI so it knows what tables and columns exist.

---

```sql
-- Example schema (replace with actual)
-- DATABASE: WORKSHOP_DB
-- SCHEMA: SAMPLE

-- CUSTOMERS table
CREATE TABLE CUSTOMERS (
    customer_id INT,
    name VARCHAR,
    email VARCHAR,
    region VARCHAR,
    created_at TIMESTAMP
);

-- ORDERS table
CREATE TABLE ORDERS (
    order_id INT,
    customer_id INT,
    order_date DATE,
    status VARCHAR,  -- 'pending', 'shipped', 'delivered', 'cancelled'
    total_amount DECIMAL(10,2)
);

```

---

## Your Task

### Step 1: Set Up the AI

Copy and paste this to start:

```
I'm working with a Snowflake database. Here's the schema:

[PASTE YOUR SCHEMA HERE]

I'll describe what data I want, and you'll generate SQL queries for me.
Keep queries simple and explain what each one does.
```

### Step 2: Ask Business Questions

Try these example prompts:

---

### Example Prompts

**Basic Queries:**
> "Show me the top 10 customers by total order amount"

> "List all orders from last month that are still pending"

**Filtering:**
> "Find customers who haven't placed an order in the last 90 days"

> "List orders over $1,000 that are still pending"

**Complex Analysis:**
> "Show me a breakdown of order status by month"

---

### Step 3: Run the Query

1. Copy the SQL query from the AI
2. Open Snowflake in your browser
3. Paste the query in the worksheet
4. Click **Run** or press Cmd/Ctrl + Enter
5. Review the results

### Step 4: Iterate

If results aren't quite right, tell the AI:

> "That's close, but I only want orders from the West region"

> "Add a column showing the percentage of total"

> "Make it a weekly breakdown instead of monthly"

> "Sort by date instead of amount"

---

## Handling Errors

When a query fails, copy the error message and send it to the AI:

> "I got this error when running the query:
>
> `SQL compilation error: Object 'CUSTOMERS' does not exist`
>
> Can you fix it?"

The AI will often:
- Correct table/column names
- Fix syntax issues
- Suggest alternatives

---

## Key Takeaways

1. **You don't need SQL expertise** — AI handles the syntax
2. **Business knowledge** — you know what questions to ask
3. **Iteration is normal** — refine until you get what you need
4. **Errors are conversation starters** — paste them back to the AI

---
