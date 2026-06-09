# Module 02 — Types of Testing

---

## 1. The Two Big Categories

Every type of testing falls into one of two buckets:

| Category | Question | Examples |
|----------|----------|---------|
| **Functional Testing** | Does the software DO what it should? | Login works, payment processes, email sends |
| **Non-Functional Testing** | Does it work WELL ENOUGH? | Fast enough? Secure enough? Scales enough? |

---

## 2. Functional Testing Types

### Unit Testing
- Tests a single, isolated piece of code (one function or method)
- Done by **developers**, not QA
- You need to know this exists, but you won't write unit tests as a Junior QA

### Integration Testing
- Tests that multiple components work together correctly
- Example: The login module and the database module talk to each other correctly
- Healthcare analogy: Testing that the patient wristband scanner talks correctly to the patient record system

### System Testing
- Tests the entire application end-to-end
- This is where **manual QA** spends most of its time
- Example: A full user journey — register, login, book an appointment, receive confirmation email

### Regression Testing
- Re-runs previously passing tests after a code change
- Ensures a new feature hasn't broken existing features
- Very important: **roughly 70% of a QA's time** is regression testing
- Healthcare analogy: After updating the medication dispensing system, re-check that the existing prescriptions still process correctly

### Smoke Testing
- A quick "is it alive?" check after receiving a new build
- Covers only the most critical happy-path flows
- If smoke tests fail, the build is sent back to developers without further testing
- Healthcare analogy: Checking the defibrillator turns on and shows a heartbeat before starting a shift

### Sanity Testing
- Narrow testing after a specific bug fix
- Verifies the fix works AND hasn't broken closely related functionality
- Different from smoke: Smoke = broad/shallow. Sanity = narrow/deep.

### UAT (User Acceptance Testing)
- Done by **business stakeholders or real users**, not QA
- Final sign-off before release
- QA's role: Support UAT, manage the environment, help raise and track bugs

### Exploratory Testing
- Unscripted testing where the tester explores the application freely
- No predefined test cases — the tester uses their judgment and curiosity
- Great for finding bugs that scripted tests miss
- Healthcare analogy: A doctor doing a full patient assessment beyond the checklist because something "feels off"

### Re-testing (Confirmation Testing)
- After a bug is fixed, testers re-run the exact steps that caused the bug
- Different from regression: Regression checks broad impact; re-testing checks the specific fix

---

## 3. Non-Functional Testing Types

### Performance Testing
- Does the system perform well under various conditions?
- **Load Testing** — What happens with expected number of users?
- **Stress Testing** — What happens when pushed beyond limits?
- **Spike Testing** — What happens with sudden bursts of users?
- Healthcare analogy: How does the hospital's booking system cope when everyone books appointments at 8am?

### Security Testing
- Can the system be hacked or does it expose sensitive data?
- Checks for vulnerabilities like SQL injection, unauthorised access
- Especially important for healthcare IT (patient data protection — GDPR, NHS data standards)

### Usability Testing
- Is the system easy to use for the target audience?
- Healthcare analogy: Can an elderly patient navigate the NHS app without help?

### Accessibility Testing
- Can people with disabilities use the system?
- Screen readers, keyboard navigation, colour contrast
- Legal requirement in the UK (Equality Act 2010, WCAG 2.1 standards)

### Compatibility Testing
- Does it work across different browsers, devices, OS versions?
- Example: Does the checkout work on Chrome, Firefox, Safari, Edge?

### Localisation / Internationalisation Testing
- Does the app work in different languages, date formats, currencies?

---

## 4. Manual vs Automation Testing

| Aspect | Manual Testing | Automation Testing |
|--------|---------------|-------------------|
| Who | Human tester | A script/robot |
| Best for | Exploratory, usability, one-off tests | Regression, repetitive tests, large data sets |
| Speed | Slower | Much faster once set up |
| Cost | Lower upfront | Higher upfront (setup time) |
| Accuracy | Can miss things when tired | Consistent every run |
| Career stage | Where you START | Learn after 6–12 months manual experience |

**Interview tip:** "I am focused on building strong manual testing fundamentals first. I understand that automation is a multiplier — it amplifies good manual testing practices. I am actively learning Selenium/Python basics alongside my manual skills."

---

## 5. Black Box vs White Box vs Grey Box

| Type | Tester knows... | Focus |
|------|-----------------|-------|
| **Black Box** | Nothing about internal code | What the system does (inputs/outputs) |
| **White Box** | Full access to source code | How the code works internally |
| **Grey Box** | Partial knowledge | Mix of both |

**Junior QA does Black Box testing almost exclusively.** You test the UI, APIs, and behaviour — you don't need to read the code.

Healthcare analogy: Black box = testing a blood test machine by comparing its results against expected ranges (you don't know how it processes the sample internally).

---

## 6. The Testing Pyramid

Understanding this shows interviewers you "get" the big picture.

```
        /\
       /  \
      / UI \       ← Fewer, slower, expensive (E2E / Manual)
     /------\
    / API    \     ← Medium layer (Integration)
   /----------\
  / Unit Tests \   ← Most tests here — fast, cheap, isolated
 /--------------\
```

- The base (unit tests) should have the MOST coverage — developers do this
- Middle (API/integration) — QA and developers share this
- Top (UI/E2E) — QA owns this, but keep it lean because it's slow and brittle

---

## 7. Shift-Left Testing

Modern QA principle: **test earlier in the SDLC**, not just at the end.

- Old way: Dev finishes → throws it over the wall → QA tests → bugs found late
- Shift-left way: QA involved from requirements stage → bugs found and prevented early

This is why QA reviews requirements and designs — not just test code.

---

## Key Terms to Know Cold

- **Build** — A compiled, deployable version of the software for testing
- **Happy Path** — The expected, error-free flow through a feature
- **Negative Testing** — Testing what happens when inputs are wrong or users do unexpected things
- **Test Coverage** — What percentage of the application's functionality is covered by tests
- **Regression Suite** — The full set of tests run to check nothing is broken after a change
- **End-to-End (E2E) Testing** — Testing a complete user journey from start to finish

---

## Interview Questions for This Module

**Q1. What is the difference between smoke testing and sanity testing?**
> Smoke testing is broad and shallow — it checks the most critical functions after a new build to decide if it's worth testing further. Sanity testing is narrow and deep — it checks a specific area after a bug fix to confirm the fix works without breaking related functionality.

**Q2. What is regression testing and why is it important?**
> Regression testing re-runs previously passing tests after a code change to ensure new changes haven't broken existing functionality. It's critical because a fix in one area can unexpectedly break another — especially in large, interconnected systems.

**Q3. What is the difference between functional and non-functional testing?**
> Functional testing checks that the system does what it is supposed to do — correct behaviour, right outputs for given inputs. Non-functional testing checks how well the system does it — performance, security, usability, and accessibility.

**Q4. When would you choose manual testing over automation?**
> Manual testing is better for exploratory testing, usability testing, short-lived features, and cases where human judgment is needed. Automation is better for repetitive regression tests, large data sets, and anything that needs to run frequently. As a junior QA, most of my work will be manual.

**Q5. What is UAT and what is the QA engineer's role in it?**
> UAT is User Acceptance Testing — final testing done by business stakeholders or real users to confirm the system meets their needs. The QA engineer's role is to prepare the environment, assist users with test execution, and manage the defect tracking during UAT.

---

## Quick Quiz

1. Which type of testing checks that an existing feature still works after a new feature is added?
2. What is the difference between black box and white box testing?
3. Name 3 types of non-functional testing.
4. What is exploratory testing?
5. Where on the testing pyramid should there be the most tests, and why?

---

## Exercise

Pick the **NHS App** (or any app you use).

For each testing type below, write ONE specific test you would perform:
1. Smoke Test
2. Sanity Test (imagine a recent bug: "Login button was not working, now fixed")
3. Exploratory Test
4. Performance concern (describe a scenario that might slow the app)
5. Security concern (describe one potential vulnerability)
