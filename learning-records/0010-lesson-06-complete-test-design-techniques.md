# Lesson 06 Complete — Test Design Techniques

Shivani completed Lesson 06 covering Equivalence Partitioning, Boundary Value Analysis, and Decision Tables, applied to the OWASP Juice Shop registration and login forms.

**Demonstrated correctly:**
- Identified all EP partitions for email field (valid, invalid format, empty) with correct expected outcomes and exact error message text
- Identified all EP partitions for password field unprompted — including the maximum boundary (5-40 chars), which was not given in the hint
- Correctly described BVA for minimum boundary: 4 chars (invalid), 5 chars (valid), 6 chars (valid)
- Completed decision table for login with all 4 combinations and specific error message text ("Invalid email or password"), not just "Fail"
- Wrote OJS-147 with 6 test steps covering valid, below-min, above-max, at-min, and at-max — with specific test data values and correct expected behaviours
- Step 5 in OJS-147 ("12345" at 5-char boundary → no error) is textbook BVA

**Teaching moments recorded:**
- BVA confusion (recurring): Initially stated 6 chars should produce "password is too long" — corrected with number line explanation. Second attempt used a 50+ char string labelled as "just above minimum" — corrected again. Concept now understood by end of lesson.
- OJS-135 mislabelled "EP+BVA" — empty fields is EP only. No boundary to test on an empty value.
- OJS-147 Step 6: test data for "at maximum" appears to be longer than 40 chars. Expected result says "no error" which may be incorrect if the max is enforced. Flagged — needs verification in app.
- Terminology: uses "threshold" instead of "boundary" — acceptable but "boundary" is the industry-standard ISTQB term.

**Progression on recurring issue:**
- "Validation error" vs "no results" — no recurrence this lesson. Using "error message" correctly.
- BVA concept: took 3 rounds of correction but final understanding is solid. Core confusion was thinking "just above minimum" = error. Now resolved.

**Implications:** Ready for Lesson 07. Options:
1. Test Planning and Test Strategy — how to write a test plan, coverage, risk-based testing
2. SQL Injection and Security Testing basics — she raised OJS-128; build on that
3. Interview preparation and mock Q&A — consolidate lessons 1-6 into interview-ready answers
Recommend Lesson 07 = Interview Prep & Mock Q&A as she is approaching the 6-8 week target and all core technical skills are covered.
