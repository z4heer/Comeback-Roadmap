# 🔬 GUIDED DEEP DIVE – PART 7.2

## INTEGRATION TESTING (API + DB TOGETHER)

*(Proving the system works when parts are connected)*

> **Senior rule:**
> Unit tests protect **logic**.
> Integration tests protect **assumptions between components**.

---

## 1️⃣ MATERIAL-ANCHORED VIEW OF INTEGRATION TESTING

![Image](https://dancerscode.com/content/2019/integration-test-diagram-2.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/0%2Amcd_8jVDUqunnbJh)

![Image](https://global-uploads.webflow.com/619e15d781b21202de206fb5/628b0dca3e6eda9219d40a6a_The-Testing-Pyramid-Simplified-for-One-and-All-1280X720%20%281%29.jpg)

### 🔹 Material

* HTTP requests
* Serialized payloads (JSON)
* Database schema & rows
* Transactions
* Real configurations (test-safe)

These are **real system materials**, not mocks.

---

### 🔹 Location

* Test runtime
* Application runtime (same code paths as prod)
* Test database (isolated)

Integration tests live **between unit tests and production**.

---

### 🔹 Transformation (What integration tests really do)

**Without integration tests**

```
Unit tests pass → deploy → surprises
```

**With integration tests**

```
Components connected → verified end-to-end behavior
```

Transformation:

> **Assumptions → verified interactions**

---

## 2️⃣ WHAT INTEGRATION TESTS SHOULD COVER

### ✅ Test these

* API → Service → DB flow
* Serialization/deserialization
* Transaction boundaries
* Repository queries
* Error mapping (4xx/5xx)

These catch:

* Mapping errors
* Wrong SQL
* Missing config
* Transaction issues

---

### ❌ Do NOT test

* Every edge case (unit tests do that)
* External third-party APIs (mock or stub)
* UI rendering

Senior filter:

> Integration tests focus on **connections**, not logic.

---

## 3️⃣ TEST DATABASE STRATEGY (PRACTICAL)

![Image](https://dancerscode.com/content/2019/integration-test-diagram.png)

![Image](https://cdn.document360.io/6ef8bcc1-6489-4486-9ad1-83acff7e5df0/Images/Documentation/image-1699278588569.png)

### Options (in increasing realism)

1. In-memory DB (fast, limited realism)
2. Local DB (more realistic)
3. Containerized DB (most realistic)

Senior guidance:

> Use the **simplest option that catches real issues**.

---

## 4️⃣ DATA MANAGEMENT IN INTEGRATION TESTS

### 🔹 Material

* Test data
* Transactions
* Cleanup logic

### Strategies

* Wrap each test in a transaction and rollback
* Reset DB between tests
* Use known seed data

Senior habit:

> Tests must be **repeatable and isolated**.

---

## 5️⃣ COMMON INTEGRATION TEST FAILURES

### ❌ Tests depend on execution order

### ❌ Tests share mutable state

### ❌ Tests assume existing data

### ❌ Tests are slow and brittle

Senior fix:

> Control data explicitly. Reset aggressively.

---

## 6️⃣ DAILY PRACTICE (30–40 MIN)

### ✍️ Write (Notebook / Excel)

Fill one row:

```
Skill: Integration Testing
Material: HTTP requests, DB rows, transactions
Location: Test runtime + app runtime + test DB
Transformation: Untested component interaction → verified system flow
```

---

### 💻 Do (Laptop)

* Write **one** integration test:

  * Call API endpoint
  * Insert/read from DB
  * Verify response + DB state
* Ensure DB is clean after test

---

### 🎤 Say Aloud (Mobile)

Explain:

> “Why unit tests passing doesn’t guarantee the system works.”

If explanation is calm and grounded → **Clear**.

---

## 7️⃣ LEARNING RESOURCES (MINIMAL & CORRECT)

Use only these **types**:

### 📘 Must-understand

* “Unit vs Integration testing”
* “Test pyramid explained simply”
* “Why integration tests fail”

### 📘 Optional

* Transaction rollback in tests (conceptual)

❌ Skip:

* Full end-to-end UI testing
* Heavy test frameworks

---

## 8️⃣ INTERVIEW TRANSLATION (STRONG SIGNAL)

If asked:

> “How do you ensure components work together?”

Senior answer:

> “I use integration tests to verify API-to-database flows and configuration assumptions. Unit tests alone can’t catch those issues.”

This signals:

* Systems thinking
* Practical quality mindset
* Low-risk delivery

---

## 9️⃣ EXCEL UPDATE

In **Extended_Material_Anchored_Skill_Rebuild.xlsx**:

* Skill: Integration Testing
* Self Check: **Clear / Unclear**

---

## NEXT STEP (STRICT ORDER)

### ▶️ STEP 7.3 — **Regression Thinking (What Might Break If This Changes?)**

Next we’ll cover:

* Regression as a mindset
* Change impact analysis
* Why seniors fear *unintended consequences*, not change itself

👉 Reply **“continue”** when ready.
