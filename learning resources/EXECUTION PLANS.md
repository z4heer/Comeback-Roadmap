# 🔬 GUIDED DEEP DIVE – PART 3.2

## EXECUTION PLANS & QUERY OPTIMIZER

*(How the database actually decides what to do)*

> **Senior rule:**
> SQL tells the database **what you want**,
> the optimizer decides **how it will get it**.

---

## 1️⃣ MATERIAL-ANCHORED VIEW OF EXECUTION PLANS

![Image](https://vladmihalcea.com/wp-content/uploads/2018/05/StatementLifeCycle.png)

![Image](https://docs.oracle.com/cd/E15586_01/server.1111/e16638/img/pfgrf184.gif)

![Image](https://dev.mysql.com/doc/workbench/en/images/wb-visual-explain-example-sakila.png)

### 🔹 Material

* SQL text
* Table statistics (row counts, data distribution)
* Index structures
* Estimated row counts
* Cost numbers (abstract but comparative)

These are **real inputs** used by the DB engine.

---

### 🔹 Location

* Inside the **database optimizer**
* Runs **before** query execution
* Uses metadata + statistics stored in DB

The optimizer lives **inside the DB**, not your app.

---

### 🔹 Transformation

**Before**

```
SQL statement (declarative)
```

**During**

```
Parse SQL
→ generate multiple possible plans
→ estimate cost of each
→ choose cheapest plan
```

**After**

```
One chosen execution plan
```

👉 This transformation explains **why the same SQL can behave differently**.

---

## 2️⃣ WHY INDEXES ARE SOMETIMES IGNORED (KEY INSIGHT)

Common reasons:

### 🔹 Low selectivity

* Index does not filter enough rows
* Full scan is cheaper

### 🔹 Outdated statistics

* Optimizer makes wrong assumptions

### 🔹 Small tables

* Scanning everything is faster than index traversal

### 🔹 Function on indexed column

```sql
WHERE LOWER(name) = 'john'
```

Index can’t be used efficiently.

👉 This is **optimizer logic**, not a bug.

---

## 3️⃣ COST IS RELATIVE, NOT ABSOLUTE

### 🔹 Material

* Estimated IO
* Estimated CPU
* Estimated rows

Cost values:

* Are **not milliseconds**
* Are **relative numbers** used for comparison

Senior habit:

> Compare plans, not numbers.

---

## 4️⃣ JOIN ORDER & JOIN METHODS (HIGH IMPACT)

![Image](https://www.kdnuggets.com/wp-content/uploads/ferrer_essential_guide_sql_execution_order_6.png)

![Image](https://miro.medium.com/1%2AhmMO-pnq6pd-dADrj6Pggg.png)

### 🔹 Join Methods

* Nested Loop
* Hash Join
* Merge Join

### 🔹 Transformation

Different join strategies change:

* Memory usage
* IO pattern
* Performance drastically

Senior awareness:

> Join order + join method often matters more than indexes.

---

## 5️⃣ WHY “IT WORKED YESTERDAY” FAILS TODAY

Execution plans can change due to:

* Data growth
* Data skew
* Statistics refresh
* Parameter values

Same SQL + different data = **different plan**.

This is normal DB behavior.

---

## 6️⃣ DAILY PRACTICE (30–40 MIN)

### ✍️ Write (Notebook / Excel)

Fill one row:

```
Skill: Execution Plans
Material: SQL, statistics, indexes
Location: Database optimizer
Transformation: SQL → chosen execution strategy
```

---

### 💻 Do (Laptop)

1. Run a query
2. Check execution plan
3. Add/remove index
4. Re-check plan
5. Observe:

   * Scan vs index
   * Join order

Do **not** optimize yet. Observe only.

---

### 🎤 Say Aloud (Mobile)

Explain:

> “Why the database sometimes ignores an index.”

If you can explain without blaming the DB → **Clear**.

---

## 7️⃣ LEARNING RESOURCES (MINIMAL & CORRECT)

Use only these **types**:

### 📘 Must-understand

* “How SQL query optimizers work”
* “What EXPLAIN actually shows”
* “Why cost-based optimizers exist”

### 📘 Practical

* Basic `EXPLAIN`
* Basic `EXPLAIN ANALYZE`

❌ Skip:

* Vendor-specific optimizer hints
* Forced index usage

Those are **advanced and risky**.

---

## 8️⃣ INTERVIEW TRANSLATION (VERY STRONG SIGNAL)

If asked:

> “How do you optimize a slow query?”

Senior answer:

> “I first look at the execution plan to see how the optimizer is accessing data. Indexes help only if the plan actually uses them.”

That answer signals:

* Experience
* Calm reasoning
* No guesswork

---

## 9️⃣ EXCEL UPDATE

In **Extended_Material_Anchored_Skill_Rebuild.xlsx**:

* Skill: Execution Plans
* Self Check: **Clear / Unclear**

---

## NEXT STEP (STRICT ORDER)

### ▶️ STEP 3.3 — **Transactions & Isolation Levels**

We will cover:

* What a transaction really protects
* Locks as physical material
* Isolation levels without theory overload
* Why deadlocks happen

👉 Reply **“continue”** when ready.
