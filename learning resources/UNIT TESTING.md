# 🔬 GUIDED DEEP DIVE – PART 7.1

## UNIT TESTING (WHAT TO TEST, WHAT NOT TO TEST)

*(Tests are a safety net, not a second implementation)*

> **Senior rule:**
> Unit tests protect **behavior**, not lines of code.

---

## 1️⃣ MATERIAL-ANCHORED VIEW OF UNIT TESTING

![Image](https://global-uploads.webflow.com/619e15d781b21202de206fb5/628b0dca3e6eda9219d40a6a_The-Testing-Pyramid-Simplified-for-One-and-All-1280X720%20%281%29.jpg)

![Image](https://miro.medium.com/1%2ALBHxbUsmWv4A5b1bMqcpzA.jpeg)

![Image](https://dancerscode.com/content/2019/unit-test-diagram.png)

### 🔹 Material

* Functions / methods
* Input values
* Output values
* Side effects (state changes)
* Test assertions

These are **concrete, executable artifacts**.

---

### 🔹 Location

* Test code:

  * Separate test folders
* Runs in:

  * Test runtime (not production)
* Isolates:

  * One unit of logic at a time

Unit tests live **outside production code**, but reason about it precisely.

---

### 🔹 Transformation (What unit tests actually do)

**Without unit tests**

```
Change code → hope nothing broke
```

**With unit tests**

```
Change code → verify behavior unchanged
```

Transformation:

> **Fearful change → confident change**

---

## 2️⃣ WHAT SHOULD BE UNIT TESTED (SENIOR FILTER)

### ✅ Test these

* Pure business logic
* Decision branches
* Calculations
* State transitions

Example:

* “If salary > X, approval required”
* “Invalid input throws validation error”

---

### ❌ Do NOT unit test

* Framework behavior
* Getters / setters
* Simple data mapping
* External systems (DB, API calls)

Senior clarity:

> Test **your decisions**, not the framework’s.

---

## 3️⃣ ISOLATION IS NON-NEGOTIABLE

![Image](https://dancerscode.com/content/2019/unit-test-diagram.png)

![Image](https://www.softwaretestingmagazine.com/wp-content/uploads/testdouble1.jpg)

### 🔹 Material

* Mocks / stubs
* Fake inputs
* Controlled outputs

### 🔹 Transformation

```
Real dependencies → controlled test doubles
```

Why?

* Tests become fast
* Failures are meaningful
* Results are deterministic

---

## 4️⃣ COMMON UNIT TEST MISTAKES (REAL WORLD)

### ❌ Over-mocking

* Tests mirror implementation
* Fragile tests

### ❌ Under-mocking

* DB calls inside unit tests
* Slow, flaky tests

### ❌ Testing everything

* Huge test suite
* Low confidence

Senior instinct:

> Fewer meaningful tests beat many shallow tests.

---

## 5️⃣ NAMING & STRUCTURE (CLARITY BUILDER)

Good test names explain **behavior**:

```
shouldRejectApprovalWhenSalaryExceedsLimit()
```

Bad names explain **mechanics**:

```
testApproval1()
```

Senior habit:

> A test name should explain *why it exists*.

---

## 6️⃣ DAILY PRACTICE (25–35 MIN)

### ✍️ Write (Notebook / Excel)

Fill one row:

```
Skill: Unit Testing
Material: Inputs, outputs, assertions
Location: Test runtime
Transformation: Unverified logic → protected behavior
```

---

### 💻 Do (Laptop)

* Pick one service method
* Write 2–3 unit tests:

  * Normal case
  * Edge case
  * Failure case
* Mock all external dependencies

---

### 🎤 Say Aloud (Mobile)

Explain:

> “Why unit tests should not hit the database.”

If explanation is calm and reasoned → **Clear**.

---

## 7️⃣ LEARNING RESOURCES (MINIMAL & CORRECT)

Use only these **types**:

### 📘 Must-understand

* “What makes a good unit test”
* “Testing pyramid explained”
* “Mocks vs stubs vs fakes”

### 📘 Optional

* JUnit / PyTest basics (writing, not framework internals)

❌ Skip:

* Coverage obsession
* Testing private methods
* Framework-specific magic

---

## 8️⃣ INTERVIEW TRANSLATION (VERY STRONG SIGNAL)

If asked:

> “How do you approach unit testing?”

Senior answer:

> “I unit test business logic and decision paths, isolating external dependencies. Tests exist to protect behavior, not to maximize coverage.”

This signals:

* Practical testing mindset
* Low maintenance cost
* Production readiness

---

## 9️⃣ EXCEL UPDATE

In **Extended_Material_Anchored_Skill_Rebuild.xlsx**:

* Skill: Unit Testing
* Self Check: **Clear / Unclear**

---

## NEXT STEP (STRICT ORDER)

### ▶️ STEP 7.2 — **Integration Testing (API + DB Together)**

Next we will cover:

* Why integration tests are different
* What material they operate on
* How they complement unit tests

👉 Reply **“continue”** when ready.
