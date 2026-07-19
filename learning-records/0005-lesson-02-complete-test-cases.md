# Lesson 02 Complete — Test Cases in YouTrack

Shivani completed Lesson 02 by writing 10 test cases (beyond the required 8) for OJS-4 (Registration) in YouTrack Test Manager and executing them in a Test Run (OJS-68 "Lesson 2 Run"). Pass rate: 10/10 (100%).

**What she demonstrated:**
- Correct use of YouTrack Test Manager: suite → test cases → test run → execution → result marking
- Correct negative test coverage: empty email, duplicate email, invalid format, short password, password mismatch, no security question, all empty
- Initiative: went beyond the required number of tests

**What needs improvement (recorded for future sessions):**
- Duplicate test cases (OJS-8 and OJS-19 cover the same positive scenario)
- One test case too broad (OJS-14 "Verify that validations on Registration page are working")
- Inconsistent title style — some full sentences, some noun fragments; standardise on full action sentences

**Open question:** All tests marked Passed including negative ones. Need to confirm she understands that negative tests Pass when the app correctly rejects bad input (not that all inputs were accepted). Will verify in next session.

**Implications:** Ready for Lesson 03: Bug Life Cycle. She should also tidy up the duplicate/vague test cases in YouTrack.
