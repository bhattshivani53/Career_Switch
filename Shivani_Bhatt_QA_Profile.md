# Shivani Bhatt — QA Learning Profile & Progress Record

> This document is a complete, factual record of Shivani Bhatt's QA training, skills, and real work output. It is intended for use by an AI agent generating a tailored CV or cover letter from a specific job description. Use the specifics — tool names, bug IDs, test case counts, techniques — when writing applications.

---

## Personal Details

- **Name:** Shivani Bhatt
- **Email:** bhattshivani53@gmail.com
- **Phone:** +44 7438 968 558
- **Location:** Aldershot, UK
- **Right to work in UK:** Yes (confirmed)
- **LinkedIn:** Not yet created
- **English:** IELTS Band 7.0 (CEFR C1)

---

## Career Background

### Current Role
**Healthcare Support Worker (Band 2)**
Royal Surrey County Hospital, Guildford, UK
September 2025 – Present

- Works within strict NHS clinical protocols — zero-error-tolerance documentation environment
- Documents patient observations and handover records to auditable standards
- Escalates clinical concerns using risk-based prioritisation under time pressure
- Collaborates within a multidisciplinary team (nurses, doctors, allied health professionals)
- QA transferable skills: protocol adherence, precise documentation, escalation triage, structured communication

### Volunteering
**Patient Companion Volunteer**
Frimley Park Hospital, Frimley, UK
May 2025 – Present

- Provides companionship and emotional support to hospital patients
- Accurately relays patient concerns to supervisors (precise information handover)
- Assists the dietetic department with nutritional feed distribution across wards

### Previous Experience (India)
**Dietetic Intern**
Lok Nayak Jai Prakash Hospital, New Delhi
December 2023 – March 2024

- Conducted structured patient assessments; maintained auditable dietary records
- Collaborated in multidisciplinary teams within strict clinical guidelines
- Presented evidence-based recommendations clearly to patients, families, and clinical staff

**Assistant Office Administrator**
Shishu Mangal School, New Delhi
September 2018 – April 2019

- Coordinated school events and administrative tasks
- Assisted teaching staff with documentation and presentation preparation

---

## Education

| Degree | Institution | Years | Grade |
|--------|-------------|-------|-------|
| MSc Dietetics and Food Service Management (M.Sc. DFSM) | IGNOU, New Delhi, India | 2021–2024 | 67.88% |
| Bachelor of Science | IGNOU, New Delhi, India | 2016–2019 | 60% |

**UK ENIC Equivalence:** MSc recognised at RQF Level 7 / SCQF Level 11 / CQFW Level 7 (UK Master's equivalent)

---

## Certifications

- Care Certificate (NHS)
- Level 2 Food Hygiene and Safety
- Certificate in Food and Nutrition
- NHS Allied Health Work Experience — Springpod (x2)
- IELTS Band 7.0 (CEFR C1 — English Language Proficiency)

---

## QA Training Summary

Shivani completed a structured 7-lesson QA curriculum (August 2025 – August 2026) using real tools: OWASP Juice Shop (deliberate-vulnerability web app) as the application under test, and YouTrack as the test management and bug tracking tool. All learning was grounded in practical exercises — no theoretical-only content.

**Mentor context:** Shivani's husband Khushal is a Senior QA Analyst who provided informal industry context throughout.

---

## QA Skills — Detailed

### Tools Used (Hands-on)

| Tool | What she did with it |
|------|----------------------|
| **YouTrack Test Manager** | Created test suites, wrote 15+ test cases with test steps/test data/expected results, executed test runs, marked pass/fail |
| **YouTrack Issues (Bug Tracking)** | Raised bugs with title, steps to reproduce, expected/actual results, severity, priority, screenshots, environment details; managed bug through lifecycle |
| **YouTrack Agile Board** | Moved work items through board columns (Backlog → In Progress → Ready for Testing → Done); wrote acceptance criteria on user stories |
| **Postman** | Sent GET and POST HTTP requests, read JSON response bodies, verified HTTP status codes, checked authentication token presence in response |
| **OWASP Juice Shop** | Used as primary test application — registration, login, search, product listing, basket, checkout features explored |

### Test Design Techniques (Practical)

**Equivalence Partitioning (EP)**
- Applied to Juice Shop registration password field
- Identified partitions: below minimum (< 5 chars, invalid), valid range (5–40 chars), above maximum (> 40 chars, invalid), empty (invalid), passwords not matching (invalid)
- Verified each partition's expected result against the real app
- Applied to email field: valid format, invalid format (no @), empty

**Boundary Value Analysis (BVA)**
- Applied to Juice Shop registration password minimum (5 chars)
- Tested: 4 chars (just below — INVALID), 5 chars (at boundary — VALID), 6 chars (just above — VALID)
- Applied to maximum (40 chars): 39 chars (VALID), 40 chars (VALID), 41 chars (INVALID — verified in live app, error shown: "Password must be 5-40 characters long")
- Documented all BVA test cases in YouTrack with specific test data values and expected results

**Decision Tables**
- Created decision table for Juice Shop login form
- Two conditions: email registered (Y/N), password correct (Y/N) → 4 combinations
- Observed that TC-02, TC-03, TC-04 all produce identical error ("Invalid email or password") — identified this as a deliberate security design feature
- Created decision table for Juice Shop registration (3 conditions: valid email, password length, passwords match) → 4 test cases mapped

### Testing Types Practised

- **Functional testing** — verified features work as specified
- **Negative testing** — tested invalid inputs, confirmed app correctly rejects them
- **Exploratory testing** — explored Juice Shop search feature across 5 scenarios before writing acceptance criteria
- **API testing** — direct backend testing via Postman without UI
- **Security testing** — identified SQL injection vulnerability
- **Regression awareness** — understands when regression testing is required

### Methodology

**Agile / Scrum:**
- Understands sprint cycle (Sprint Planning → Daily Standup → Sprint Review → Retrospective)
- Knows QA's role in each ceremony:
  - Planning: review user stories, flag ambiguous requirements
  - Standup: Yesterday/Today/Blockers format (practised)
  - Review: demonstrate tested features
  - Retrospective: raise process improvements
- Understands Definition of Done — QA is the final gate
- Knows Scrum roles: Product Owner, Scrum Master, Development Team (QA is part of dev team)
- Understands board columns: Backlog → Ready for Dev → In Progress → Ready for Testing → Done

**Acceptance Criteria:**
- Written in Given/When/Then (BDD) format
- Wrote 4 ACs for OJS-5 (Juice Shop search feature) on YouTrack board
- Understands ACs bridge requirements and test cases

---

## Real Work Output

### Bug Report: OJS-128 (SQL Injection — Critical)

**Summary:** SQL injection in login email field bypasses authentication and grants admin account access

**Full details:**
- **Type:** Bug
- **Severity:** Critical
- **Priority:** High
- **Status raised:** In Progress (on Agile board)
- **Steps to reproduce:**
  1. Navigate to http://192.168.0.202:9058/#/login
  2. In the email field, enter: `' OR 1=1--`
  3. Enter any value in the password field
  4. Click Log In
- **Expected result:** Login fails; error message displayed
- **Actual result:** Admin account access granted without valid credentials
- **Environment:** OWASP Juice Shop · Safari · macOS
- **Evidence:** 3 screenshots attached
- **OWASP reference:** SQL injection is #3 in OWASP Top 10 most critical web vulnerabilities

**Significance for job applications:** This is a Critical security vulnerability correctly identified, documented, and tracked to professional bug reporting standards. Most junior QA candidates have never raised a security bug. This is a differentiator.

### Test Cases Written in YouTrack Test Manager

**Lesson 02 — Registration feature (OJS-4)**
10 test cases covering: valid registration, empty fields, invalid email, password mismatch, duplicate email, SQL injection in registration, XSS attempt in name field, valid but edge-case inputs

**Lesson 06 — EP & BVA (Registration form)**

| ID | Title | Technique |
|----|-------|-----------|
| OJS-129 | EP — successful registration with valid email, password, security question | EP |
| OJS-135 | EP — registration unsuccessful if all fields are empty | EP |
| OJS-141 | EP — registration unsuccessful due to invalid email | EP |
| OJS-147 | BVA — password field validation (4 chars invalid, 5 chars valid, 9 chars valid, 41 chars invalid, 40 chars valid, 5 chars at boundary) | BVA |
| OJS-154 | EP — verify that password and repeat password fields must contain same values | EP |

OJS-147 contains 6 test steps, each with specific test data and expected behaviour, verified against the live application.

### Acceptance Criteria Written (OJS-5 — Search Feature)

**AC1:** Given the shopper is on the Juice Shop homepage / When shopper types text "apple" in the search field / Then the item which has that text (e.g. "Apple Juice") should appear AND items not containing "apple" should not be visible

**AC2:** Given the shopper is on the Juice Shop homepage / When shopper types a product name that does not exist / Then a no-results message should appear (not a validation error)

**AC3:** Given the shopper is on the Juice Shop homepage / When shopper submits an empty search / Then all products should be displayed

**AC4:** Given the shopper has typed in the search field / When shopper clears the search text / Then all products should be displayed again

### API Testing (Postman — Juice Shop)

| Request | Result |
|---------|--------|
| GET /api/Products | 200 OK — 46 products returned |
| GET /api/Products/1 | 200 OK — Apple Juice 100ml, £1.99 |
| GET /api/Products/9999 | 404 Not Found — resource does not exist |
| POST /rest/user/login (valid credentials) | 200 OK — auth token received in response body |
| POST /rest/user/login (wrong password) | 401 Unauthorized — "Invalid email or password" |
| GET /api/Users (no auth token) | 401 Unauthorized — expected, correct behaviour |

**Key understanding demonstrated:** 404 = resource doesn't exist (not an auth issue). 401 = not authenticated. 403 = authenticated but forbidden. Shivani can explain these distinctions correctly.

### Standup Practice (Completed Correctly)

Format: Yesterday / Today / Blockers — concise, specific, uses "completed" not "worked on"

Example completed: *"Yesterday I completed acceptance criteria for OJS-5. Today I will write test cases for OJS-5. There are no blockers."*

---

## Lessons Completed

| # | Topic | Status | Key Output |
|---|-------|--------|-----------|
| 01 | What QA Is (QA vs QC, SDLC, test types) | ✅ Complete | 4/4 quiz score |
| 02 | Writing Test Cases | ✅ Complete | 10 test cases in YouTrack |
| 03 | Bug Life Cycle | ✅ Complete | OJS-128 raised (Critical SQL injection) |
| 04 | Agile & Scrum | ✅ Complete | 4 ACs written, standup completed |
| 05 | API Testing with Postman | ✅ Complete | 6 API requests tested |
| 06 | Test Design Techniques (EP, BVA, DT) | ✅ Complete | 5 test cases using techniques |
| 07 | Interview Preparation | ✅ Complete | Model answers for 12 technical Qs |

---

## Terminology She Uses Correctly

- Test case anatomy: ID, title, preconditions, test data, steps, expected result, actual result, status
- Severity vs Priority: Severity = technical impact (set by QA); Priority = business urgency (set by PM)
- Bug life cycle states: New → Assigned → In Progress → Fixed → Retest → Closed / Reopened; also: Rejected, Deferred, Duplicate
- QA vs QC: QA = proactive/process; QC = reactive/product; Testing ⊂ QC
- Verification vs Validation: building the product right vs building the right product
- Smoke test: quick high-level check after a build before full testing
- Regression test: verifying existing features haven't broken after changes
- UAT: User Acceptance Testing
- Given/When/Then: BDD-style acceptance criteria format
- HTTP methods: GET (retrieve), POST (create), PUT (update), DELETE (remove)
- Status codes: 200 (OK), 201 (Created), 204 (No Content), 400 (Bad Request), 401 (Unauthorized), 403 (Forbidden), 404 (Not Found), 500 (Server Error)

---

## Key Differentiators for Job Applications

1. **Healthcare background + QA = rare combination** — in healthcare/health-tech roles, she understands the domain at a level no CS graduate can match. Protocol adherence, zero-error documentation, escalation — these are NHS competencies that map directly onto QA.

2. **Critical security bug raised** — OJS-128 is a SQL injection vulnerability documented to professional standard. Most junior QA candidates have never raised a security bug. OWASP Top 10 awareness is a bonus for any team.

3. **Real tools, real work** — not theoretical. Has used YouTrack, Postman, run test suites, tracked bugs through lifecycle, written ACs on a real Agile board.

4. **BDD alignment** — Given/When/Then format already in use. For roles mentioning BDD, Cucumber, or behaviour-driven development, this is directly relevant.

5. **API testing** — one of the most valued Junior QA skills. Has hands-on Postman experience, understands request/response anatomy, status codes, authentication flows.

---

## What She Has Not Yet Covered (Honest Gaps)

- **Test automation** — no Selenium, Playwright, Cypress, or any automation framework experience. All testing to date is manual. She is aware of automation and knows this is the next step.
- **CI/CD pipelines** — no hands-on experience with Jenkins, GitHub Actions, or similar.
- **Performance/load testing** — not covered.
- **ISTQB Foundation Level** — not yet taken. Considering it.
- **Database/SQL testing** — no hands-on experience beyond using SQL injection as an attack vector in testing.
- **Mobile testing** — not covered.
- **TDD (Test-Driven Development)** — understands the concept; no practice.

---

## How to Frame the Career Switch

**The core narrative:** Healthcare and QA share the same discipline — precise documentation, protocol adherence, escalation of critical issues, zero tolerance for errors that reach the end user. In NHS, the "user" is a patient. In software, the "user" is a customer. The stakes differ; the discipline does not.

**Suggested framing for any application:**
> "My healthcare career developed the same systematic rigour that quality assurance requires: following protocols precisely, documenting observations accurately, and escalating critical issues before they reach the patient. I've now applied that mindset directly to software testing — writing test cases, tracking bugs in YouTrack, and conducting API testing in Postman. I'm making a deliberate move into QA because it lets me do what I do best in a field I find genuinely interesting."

**For healthcare/health-tech roles specifically:**
> "As someone with an MSc in Dietetics and NHS experience, I understand what's at stake when software supports someone's health decisions. A bug in a health product isn't just a UX inconvenience — it can affect someone's access to care. That level of quality consciousness is what I bring."

---

## Application History

| Company | Role | Status |
|---------|------|--------|
| Posh Monkey Studios (Slough/London) | Junior QA Tester — Slots | Considering |
| Simplyhealth (Reading) | Junior Quality Engineer | Considering |

---

*Document generated: August 2026. All work output is real and verifiable — test cases and bugs are in YouTrack under the OWASP Juice Shop project. Portfolio repository: github.com/bhattshivani53/Career_Switch*
