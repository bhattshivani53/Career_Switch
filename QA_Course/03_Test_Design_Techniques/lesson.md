# Module 03 — Test Design Techniques

This module is one of the most practical. Writing great test cases is the core skill of a Junior QA.

---

## 1. What is a Test Case?

A test case is a documented set of steps that:
1. Sets up a starting condition
2. Performs specific actions
3. Verifies the expected result

Healthcare analogy: A test case is like a clinical procedure checklist. Steps are pre-defined, the expected outcome is known, and you document whether the actual outcome matched.

---

## 2. Anatomy of a Test Case

Every professional test case has these fields:

| Field | Description | Example |
|-------|-------------|---------|
| **Test Case ID** | Unique identifier | TC_LOGIN_001 |
| **Test Case Title** | Short summary | Verify login with valid credentials |
| **Module / Feature** | Which part of the app | Login |
| **Priority** | High / Medium / Low | High |
| **Preconditions** | What must be true before starting | User has a registered account |
| **Test Steps** | Numbered actions to perform | 1. Open login page 2. Enter email 3. Enter password 4. Click Login |
| **Test Data** | Specific values to use | Email: test@example.com, Password: Pass@123 |
| **Expected Result** | What SHOULD happen | User is redirected to the dashboard |
| **Actual Result** | What DID happen (filled during execution) | User redirected to dashboard |
| **Status** | Pass / Fail / Blocked / Skip | Pass |

---

## 3. How to THINK About Test Cases

Before writing a single test case, ask yourself:

1. **What is the feature supposed to do?** (Happy path)
2. **What should happen when inputs are invalid?** (Negative testing)
3. **What are the boundary conditions?** (Edge cases)
4. **What combinations of inputs exist?** (Equivalence partitioning)
5. **What if the user does something unexpected?** (Exploratory scenarios)

---

## 4. Test Design Techniques

These are systematic methods to GENERATE test cases efficiently. You don't need to test every possible combination — that's impossible. These techniques help you get maximum coverage with minimum tests.

---

### Technique 1: Equivalence Partitioning (EP)

**Principle:** Divide inputs into groups (partitions) where all values in a group behave the same way. Test ONE value from each group.

**Example:** Age field that accepts 18–65:
- Partition 1 (Invalid — too young): 0–17 → Test with: 17
- Partition 2 (Valid): 18–65 → Test with: 30
- Partition 3 (Invalid — too old): 66+ → Test with: 66

You only need 3 tests instead of testing every possible age.

**Healthcare analogy:** Blood pressure classification: Low (<90/60), Normal (90/60–120/80), High (>120/80). Testing one value from each category covers all behaviours.

---

### Technique 2: Boundary Value Analysis (BVA)

**Principle:** Bugs cluster at the EDGES of input ranges. Test the values just at, just below, and just above the boundaries.

**Example:** Same age field (18–65):
- Just below lower boundary: 17
- At lower boundary: 18
- Just above lower boundary: 19
- Just below upper boundary: 64
- At upper boundary: 65
- Just above upper boundary: 66

**Why?** Developers commonly write `if age > 18` instead of `if age >= 18` — BVA catches this off-by-one error.

BVA is always used WITH Equivalence Partitioning, not instead of it.

---

### Technique 3: Decision Table Testing

**Principle:** When behaviour depends on COMBINATIONS of conditions, map them all in a table.

**Example:** Online banking transfer requires:
- Balance sufficient: Yes/No
- Account verified: Yes/No
- Transfer limit not exceeded: Yes/No

| Condition | TC1 | TC2 | TC3 | TC4 | TC5 |
|-----------|-----|-----|-----|-----|-----|
| Balance sufficient | Y | Y | Y | N | N |
| Account verified | Y | Y | N | Y | N |
| Within limit | Y | N | Y | Y | Y |
| **Expected** | **Allow** | **Deny** | **Deny** | **Deny** | **Deny** |

This ensures you test all meaningful combinations.

---

### Technique 4: State Transition Testing

**Principle:** The system behaves differently depending on its current STATE. Map the states and transitions.

**Example:** Order status in a shopping app:
```
New Order → Confirmed → Shipped → Delivered → Closed
                ↓
            Cancelled
```

Test each valid transition AND test invalid transitions (e.g., can you cancel a "Delivered" order?).

**Healthcare analogy:** Patient journey: Admitted → Assessed → Treatment → Recovering → Discharged. Test both valid transitions and blocked ones (can a patient be discharged from "Admitted" without treatment?).

---

### Technique 5: Error Guessing

**Principle:** Use experience and intuition to guess where bugs are likely to hide. No formal method — just QA instinct.

Common places bugs hide:
- Empty inputs / null values
- Very long inputs (what's the max characters allowed?)
- Special characters in text fields (`<`, `>`, `&`, `'`, `"`, `;`)
- Negative numbers where positive expected
- Zero (dividing by zero, zero quantities)
- Duplicate records
- Fast clicking / double submitting
- Refreshing at a critical moment (payment confirmation)
- Going back in the browser during a multi-step form

---

## 5. Writing Good vs Bad Test Cases

### BAD Test Case
```
Title: Test login
Steps: 1. Login to the app
Expected: It works
```

### GOOD Test Case
```
Test Case ID: TC_LOGIN_001
Title: Verify successful login with valid registered email and password
Priority: High
Preconditions: User "testuser@gmail.com" has a registered, active account

Steps:
1. Navigate to https://app.example.com/login
2. Enter "testuser@gmail.com" in the Email field
3. Enter "ValidPass@123" in the Password field
4. Click the "Login" button

Expected Result:
- User is redirected to the Dashboard page
- User's name "Shivani" appears in the top-right header
- No error messages are displayed
```

The good test case is **atomic** (tests one thing), **reproducible** (anyone can follow it), **specific** (no ambiguity), and **verifiable** (clear pass/fail criteria).

---

## 6. Positive vs Negative Testing

| Type | Purpose | Example |
|------|---------|---------|
| **Positive** | Verify the happy path works | Login with correct credentials |
| **Negative** | Verify the system handles errors gracefully | Login with wrong password |

**Common mistake of junior QAs:** Only writing positive tests. Interviewers will probe this.

For every feature, you need BOTH. Rough ratio: 30–40% positive, 60–70% negative.

---

## 7. Test Coverage Checklist

When testing any feature, run through this mentally:

- [ ] Happy path (correct inputs, all conditions met)
- [ ] Empty / blank inputs
- [ ] Invalid format (letters in number field, etc.)
- [ ] Boundary values (min, max, min-1, max+1)
- [ ] Very long inputs
- [ ] Special characters
- [ ] Duplicate submission
- [ ] Concurrent access (two users doing same thing at once)
- [ ] Interrupted flows (close browser mid-way, network drops)
- [ ] Permission levels (can a regular user access admin functions?)

---

## Interview Questions for This Module

**Q1. What is the difference between Equivalence Partitioning and Boundary Value Analysis?**
> Equivalence Partitioning divides input data into groups where all values are expected to behave the same, and tests one representative value per group. Boundary Value Analysis specifically tests values at the edges of each partition — the minimum, maximum, and values just outside the valid range — because bugs most commonly occur at these boundaries. BVA is typically used in combination with EP.

**Q2. How many test cases would you write for a login form?**
> At minimum: Valid credentials (pass), invalid password (fail), invalid email format, non-existent email, empty email, empty password, both empty, SQL injection in email field, maximum character length, copy-pasted password, and session behaviour after login. That's roughly 10–15 test cases for login alone.

**Q3. What makes a good test case?**
> A good test case is atomic (tests one thing), clear (anyone can follow it without asking questions), specific (uses exact test data), reproducible (produces the same result every time), and has unambiguous pass/fail criteria.

**Q4. What is error guessing?**
> Error guessing is an informal technique where the tester uses experience and intuition to identify where bugs are likely to occur — empty fields, boundary values, special characters, concurrent operations, and so on. It complements formal techniques by catching edge cases that systematic methods might miss.

---

## Exercise — Write Real Test Cases

### Task 1: NHS App — Book an Appointment Feature
Write 10 test cases covering:
- At least 3 positive tests
- At least 5 negative tests
- At least 1 boundary value test
- At least 1 security-related test

Use the test case template from Section 2 above.

### Task 2: Apply BVA
A prescription quantity field accepts values between 1 and 99.
List all the values you would test using Boundary Value Analysis.

### Task 3: Decision Table
A pharmacy system dispenses medication if:
- Doctor has authorised the prescription: Yes/No
- Patient ID is verified: Yes/No
- Stock is available: Yes/No

Create a decision table and list all test cases needed.
