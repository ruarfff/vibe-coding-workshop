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
Use one of:
- ChatGPT (chat.openai.com)
- GitHub Copilot Chat (in VS Code or GitHub)
- Claude, Gemini, or another AI assistant

### Step 2: Provide Schema Context
Share your database structure with the AI so it knows what tables and columns exist.

---

## [PLACEHOLDER] Sample Database Schema

> **⚠️ Facilitator Note:** Replace this section with your actual Snowflake schema before the workshop.

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

-- PRODUCTS table
CREATE TABLE PRODUCTS (
    product_id INT,
    name VARCHAR,
    category VARCHAR,
    price DECIMAL(10,2)
);

-- ORDER_ITEMS table
CREATE TABLE ORDER_ITEMS (
    order_id INT,
    product_id INT,
    quantity INT,
    unit_price DECIMAL(10,2)
);
```

---

## Your Task (10 minutes)

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

> "How many customers do we have in each region?"

**Aggregation:**
> "What's our total revenue by month for 2024?"

> "Compare sales this quarter to the same quarter last year"

> "Show the average order value by region"

**Filtering:**
> "Find customers who haven't placed an order in the last 90 days"

> "Show products that have never been ordered"

> "List orders over $1,000 that are still pending"

**Complex Analysis:**
> "What are our best-selling products by quantity?"

> "Which customers have increased their spending compared to last year?"

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

## Tips for Success

### ✅ Do This

- **Provide the schema first** — AI can't guess your table names
- **Use business terms** — "customers" not "users" if that's your table
- **Be specific about time** — "last month" vs "last 30 days"
- **Ask for explanations** — "What does this query do?"

### ❌ Avoid This

- Don't assume the AI knows your data — provide context
- Don't run queries on production without reviewing them
- Don't ignore errors — paste them back to the AI

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

## [PLACEHOLDER] Hands-On Practice

> **⚠️ Facilitator Note:** Add specific exercises using your actual Snowflake environment.

### Exercise Ideas:

1. **Find Key Metrics**
   - Total orders this month
   - Number of active customers
   - Average order value

2. **Create a Report**
   - Monthly sales summary
   - Regional performance comparison
   - Top products by category

3. **Investigate a Question**
   - Why did sales drop in [month]?
   - Which customers are at risk of churning?
   - What products are trending up?

---

## Sample Conversation

**You:** "Show me total revenue by region for the last 12 months"

**AI:**
```sql
SELECT
    c.region,
    SUM(o.total_amount) as total_revenue
FROM ORDERS o
JOIN CUSTOMERS c ON o.customer_id = c.customer_id
WHERE o.order_date >= DATEADD(month, -12, CURRENT_DATE())
GROUP BY c.region
ORDER BY total_revenue DESC;
```

**You:** "Add a column showing the month so I can see the trend"

**AI:**
```sql
SELECT
    c.region,
    DATE_TRUNC('month', o.order_date) as month,
    SUM(o.total_amount) as total_revenue
FROM ORDERS o
JOIN CUSTOMERS c ON o.customer_id = c.customer_id
WHERE o.order_date >= DATEADD(month, -12, CURRENT_DATE())
GROUP BY c.region, DATE_TRUNC('month', o.order_date)
ORDER BY c.region, month;
```

**You:** "Perfect. Now add a percentage of total column"

---

## Key Takeaways

1. **You don't need SQL expertise** — AI handles the syntax
2. **Business knowledge is your superpower** — you know what questions to ask
3. **Iteration is normal** — refine until you get what you need
4. **Errors are conversation starters** — paste them back to the AI

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Query has wrong table names | Provide the exact schema to the AI |
| Results are empty | Check date ranges and filters |
| Query is too slow | Ask AI to optimize or add filters |
| Error message | Copy and paste the error to the AI |

---

## Next Steps

You've now seen how to:
- ✅ Build apps with Lovable.dev
- ✅ Create GitHub issues for AI implementation
- ✅ Generate SQL queries from natural language

**What will you build with AI next?**

[← Back to Workshop Outline](workshop-outline.md)
