# Shivani Bhatt — Junior QA Engineer Portfolio

**Career switch: NHS Healthcare → Software Quality Assurance**
Aldershot, UK · bhattshivani53@gmail.com

---

## About This Portfolio

This repository documents a structured, hands-on QA training programme completed between August 2025 and August 2026. All learning was done with real industry tools — no simulated exercises, no theoretical-only content.

**Tools used throughout:**
- **OWASP Juice Shop** — deliberately vulnerable web application used as the primary application under test
- **YouTrack** — test management, bug tracking, and Agile board
- **Postman** — REST API testing

---

## Completed Lessons

| # | Topic | Key Skill Developed |
|---|-------|---------------------|
| [01](lessons/0001-what-qa-is.html) | What QA Is | QA vs QC, SDLC, testing types, verification vs validation |
| [02](lessons/0002-writing-test-cases.html) | Writing Test Cases | Test case anatomy, pass/fail criteria, negative testing |
| [03](lessons/0003-bug-life-cycle.html) | Bug Life Cycle | Severity vs priority, defect states, professional bug reporting |
| [04](lessons/0004-agile-and-scrum.html) | Agile & Scrum | Sprint ceremonies, QA's role, acceptance criteria, standups |
| [05](lessons/0005-api-testing-postman.html) | API Testing with Postman | HTTP methods, status codes, REST API testing, JSON responses |
| [06](lessons/0006-test-design-techniques.html) | Test Design Techniques | Equivalence partitioning, boundary value analysis, decision tables |
| [07](lessons/0007-interview-preparation.html) | Interview Preparation | Technical Q&A, behavioural questions, mock interview, tools profile |

---

## Key Work Output

### Critical Security Bug: OJS-128

Identified, documented, and tracked a **Critical SQL injection vulnerability** in OWASP Juice Shop to professional bug reporting standards.

- **Technique:** Entered `' OR 1=1--` in the login email field
- **Result:** Admin account access granted without valid credentials — authentication fully bypassed
- **OWASP reference:** SQL injection is #3 in the OWASP Top 10 most critical web vulnerabilities
- **Documented with:** Title, steps to reproduce, expected vs actual results, severity, priority, environment, screenshots
- **Significance:** Most junior QA candidates have never raised a security bug

---

### Test Cases Written in YouTrack (15+)

**Lesson 02 — Registration feature (OJS-4):** 10 test cases covering valid registration, empty fields, invalid email format, password mismatch, duplicate email, SQL injection attempt, XSS attempt in name field.

**Lesson 06 — Test Design Techniques (OJS-129 to OJS-154):**

| ID | Technique | What Was Tested |
|----|-----------|----------------|
| OJS-129 | Equivalence Partitioning | Successful registration — valid email, password, security question |
| OJS-135 | Equivalence Partitioning | Registration fails when all fields are empty |
| OJS-141 | Equivalence Partitioning | Registration fails with invalid email format (no @) |
| OJS-147 | Boundary Value Analysis | Password field: 4 chars (invalid), 5 (valid), 6 (valid), 39 (valid), 40 (valid), 41 (invalid) |
| OJS-154 | Equivalence Partitioning | Password and repeat-password must match |

OJS-147 contains 6 test steps each with specific test data and expected behaviour, all verified against the live application.

---

### API Testing Results (Postman)

| Request | Status | Outcome |
|---------|--------|---------|
| GET /api/Products | 200 OK | 46 products returned |
| GET /api/Products/1 | 200 OK | Apple Juice 100ml, £1.99 |
| GET /api/Products/9999 | 404 Not Found | Resource does not exist |
| POST /rest/user/login (valid credentials) | 200 OK | Auth token received in response body |
| POST /rest/user/login (wrong password) | 401 Unauthorized | "Invalid email or password" |
| GET /api/Users (no auth token) | 401 Unauthorized | Correctly rejected unauthenticated request |

---

### Acceptance Criteria — Search Feature (OJS-5)

Written in Given/When/Then (BDD) format:

- **AC1:** Given the shopper is on the homepage / When they type "apple" in search / Then only products containing "apple" are shown
- **AC2:** Given the shopper types a product name that does not exist / When they submit / Then a no-results message appears (not a validation error)
- **AC3:** Given the shopper submits an empty search / When results load / Then all products are displayed
- **AC4:** Given the shopper clears the search field / When the field is empty / Then all products are displayed again

---

## Skills Acquired

| Area | Skills |
|------|--------|
| **Test Design** | Equivalence partitioning, boundary value analysis, decision tables |
| **Test Execution** | Functional, negative, exploratory, regression awareness |
| **Bug Reporting** | Full bug lifecycle, severity vs priority, professional defect documentation |
| **API Testing** | Postman, HTTP methods (GET/POST/PUT/DELETE), status codes, JSON response verification |
| **Security Testing** | SQL injection identification, OWASP Top 10 awareness |
| **Agile/Scrum** | Sprint ceremonies, Definition of Done, standup format, acceptance criteria |
| **BDD** | Given/When/Then acceptance criteria format |
| **Tools** | YouTrack (Test Manager + Issues + Agile Board), Postman |

---

## Learning Records

Detailed records of each lesson and milestone are in the [`learning-records/`](learning-records/) folder. These document not just what was covered but what was understood, corrected, and verified against the real application.

---

## Background: Why Healthcare → QA

The discipline is the same. Healthcare requires following protocols precisely, documenting observations accurately, and escalating critical issues before they reach the patient. Software QA requires exactly the same rigour — the "patient" is the end user.

| Healthcare Experience | QA Equivalent |
|----------------------|---------------|
| Clinical protocols | Test case execution |
| Adverse event reports | Bug reports |
| Escalating to senior nurse | Raising a Critical/High priority defect |
| Patient observation documentation | Test execution log |
| Discharge checklists | Smoke test / regression checklist |
| Zero-error documentation standard | Defect-free release gate |

Current role: **Healthcare Support Worker (Band 2), Royal Surrey County Hospital, Guildford** — a zero-error-tolerance documentation environment that maps directly onto QA discipline.

---

## Files in This Repository

| File/Folder | Contents |
|-------------|----------|
| [`lessons/`](lessons/) | 7 interactive HTML lesson files |
| [`learning-records/`](learning-records/) | 10 markdown records documenting progress and verified understanding |
| [`reference/qa-glossary.html`](reference/qa-glossary.html) | QA terminology reference |
| [`Shivani_Bhatt_QA_CV.docx`](Shivani_Bhatt_QA_CV.docx) | CV targeting Junior QA Engineer roles |
| [`Shivani_Bhatt_QA_Profile.md`](Shivani_Bhatt_QA_Profile.md) | Detailed skills and work output profile |
| [`RESOURCES.md`](RESOURCES.md) | Learning resources used throughout the programme |
