# Module 01 — QA Fundamentals

---

## 1. What is Quality Assurance (QA)?

**Simple definition:** QA is the process of making sure a software product works correctly, meets requirements, and is fit for the end user.

Think of it like this: In your healthcare job, before a patient is discharged, a checklist is followed — medications reviewed, mobility assessed, follow-up booked. QA does the same for software before it is released to users.

**QA is NOT just "finding bugs."**
It is about:
- Preventing bugs from being introduced in the first place
- Building quality INTO the process, not just checking at the end
- Ensuring the software does what users actually need

---

## 2. QA vs QC vs Testing — The Three Are Different

This is one of the most common interview questions. Get this right.

| Term | Definition | Analogy |
|------|-----------|---------|
| **QA (Quality Assurance)** | Process-oriented. Focuses on *how* software is built. Sets standards and processes to prevent defects. | Setting infection-control protocols in a ward |
| **QC (Quality Control)** | Product-oriented. Checks the *output* to find defects. | Checking a medication dose before giving it to a patient |
| **Testing** | A subset of QC. Actually executing the software to find defects. | Physically testing that the call bell works |

**Key interview answer:** "QA is proactive — it prevents defects. QC is reactive — it detects defects. Testing is a subset of QC that involves actually running the software."

---

## 3. SDLC — Software Development Lifecycle

SDLC is the structured process by which software is planned, created, tested, and delivered.

```
Requirement Gathering
        ↓
System Design
        ↓
Development (Coding)
        ↓
Testing  ← THIS IS WHERE QA LIVES
        ↓
Deployment
        ↓
Maintenance
```

### The 6 Phases Explained

**Phase 1 — Requirement Gathering**
The business explains what the software should do. QA reads these requirements and asks: "Are they complete? Are they testable? Are they clear?"

**Phase 2 — System Design**
Architects decide how the system will be built. QA reviews designs for testability.

**Phase 3 — Development**
Developers write code. QA prepares test cases in parallel (don't wait for development to finish).

**Phase 4 — Testing**
QA executes test cases, finds bugs, reports them, and verifies fixes.

**Phase 5 — Deployment**
Software goes live. QA may do a final smoke test in production.

**Phase 6 — Maintenance**
Bugs found after release are fixed. QA retests fixes.

---

## 4. STLC — Software Testing Lifecycle

The STLC is the QA team's own mini-process within the SDLC.

```
Requirement Analysis → Test Planning → Test Case Development
                                              ↓
            Test Closure ← Test Cycle Closure ← Test Execution
```

| Phase | What QA Does |
|-------|-------------|
| **Requirement Analysis** | Read requirements, identify what to test, flag ambiguities |
| **Test Planning** | Define scope, approach, timeline, tools, resources |
| **Test Case Development** | Write test cases, prepare test data |
| **Test Environment Setup** | Set up devices, databases, test accounts |
| **Test Execution** | Run tests, log results, raise bugs |
| **Test Cycle Closure** | Analyse metrics, write test summary report |

---

## 5. Types of Software Testing (Big Picture)

```
Software Testing
├── Manual Testing (a human runs the tests)
│   ├── Functional Testing (does it DO the right thing?)
│   └── Non-Functional Testing (does it do it WELL?)
└── Automation Testing (scripts run the tests)
    ├── Unit Testing
    ├── Integration Testing
    └── End-to-End Testing
```

You will learn each of these in Module 02. For now, just understand the big picture.

---

## 6. Verification vs Validation

Another classic interview question.

| Term | Question it answers | Example |
|------|--------------------|---------| 
| **Verification** | "Are we building the product RIGHT?" — checking against specifications | Reviewing code against design documents |
| **Validation** | "Are we building the RIGHT product?" — checking against user needs | Having real users test the product |

Healthcare analogy: Verification = "Did I follow the protocol correctly?" Validation = "Did the protocol actually help the patient?"

---

## 7. Why QA Matters (for your interviews)

Companies invest in QA because:
1. **Cost** — fixing a bug after release costs 100x more than catching it during design
2. **Reputation** — one bad release can destroy user trust
3. **Safety** — in industries like healthcare IT, finance, aviation — bugs can kill people
4. **Compliance** — regulated industries must demonstrate testing was done

**Your angle in interviews:** "My healthcare background taught me that cutting corners on process has real consequences for real people. That mindset directly applies to QA."

---

## Key Terms to Know Cold

- **Defect / Bug** — When software does not behave as expected
- **Test Case** — A set of steps to verify a specific behaviour
- **Test Suite** — A collection of test cases
- **Test Plan** — A document describing what will be tested and how
- **Regression Testing** — Re-testing existing features after a change to ensure nothing broke
- **Smoke Testing** — A quick check that the basic functions work after a new build
- **Sanity Testing** — A narrow check after a bug fix to confirm the fix works
- **UAT (User Acceptance Testing)** — Final testing done by business users before release
- **Release / Build** — A version of the software given to QA for testing
- **Environment** — Where the software runs (Dev, QA/Test, Staging, Production)

---

## Interview Questions for This Module

**Q1. What is the difference between QA, QC, and Testing?**
> QA is process-focused and preventive — it sets up standards so defects don't occur. QC is product-focused and detective — it checks outputs for defects. Testing is a specific QC activity where the software is actually executed to find defects.

**Q2. What is SDLC and where does QA fit?**
> SDLC is the end-to-end process of building software — from requirements to maintenance. QA is involved at every phase: reviewing requirements, checking designs for testability, writing test cases during development, executing them after development, and maintaining regression suites post-release.

**Q3. What is STLC?**
> STLC is the QA team's own lifecycle within SDLC. It covers requirement analysis, test planning, test case development, environment setup, test execution, and closure. It ensures testing is systematic and documented.

**Q4. What is the difference between verification and validation?**
> Verification checks that we are building the product according to specifications. Validation checks that the product meets actual user needs. Verification happens during development; validation typically happens at the end.

**Q5. Why is early testing important?**
> The cost of fixing a defect increases exponentially the later it is found. A defect caught in requirements costs 1x to fix; the same defect caught post-production can cost 100x. Early testing also prevents defects from cascading into other parts of the system.

---

## Quick Quiz (Answer These Before Moving On)

1. What is the difference between QA and testing?
2. Name the 6 phases of SDLC.
3. What happens in the "Requirement Analysis" phase of STLC?
4. What is regression testing?
5. In healthcare terms — what is the QA equivalent of a "discharge checklist"?

Answers: See bottom of this file.

---

## Exercise

Take any app you use daily (NHS app, banking app, Amazon). Write down:
1. What are the **requirements** for ONE feature? (e.g., "The login page should accept email and password")
2. What could go **wrong** with that feature? (List 5 things)
3. How would you **verify** each one works correctly?

This is the mental model of a QA engineer.

---

## Quiz Answers

1. Testing is a specific activity of executing software to find defects. QA is the broader process of ensuring quality is built in throughout development — testing is just one tool within QA.
2. Requirement Gathering → Design → Development → Testing → Deployment → Maintenance
3. QA reads requirements, identifies what needs to be tested, highlights ambiguous or missing requirements.
4. Testing existing functionality after a code change to ensure nothing that previously worked has been broken.
5. A test checklist / test case — a set of steps to verify the patient/system is in the expected state before moving to the next phase.
