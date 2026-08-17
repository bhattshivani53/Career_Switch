# Lesson 05 Complete — API Testing with Postman

Shivani completed Lesson 05 covering REST APIs, HTTP methods, status codes, and Postman using the Juice Shop API.

**Demonstrated correctly:**
- GET /api/Products — identified 46 products, status 200 OK
- GET /api/Products/1 — correctly identified Apple Juice 100ml, £1.99
- GET /api/Products/9999 — correctly identified 404 Not Found
- POST /rest/user/login (valid) — status 200, located auth token in response body
- POST /rest/user/login (wrong password) — status 401, read error message "Invalid email or password"
- GET /api/Users (unauthenticated) — status 401, correctly assessed as expected behaviour

**Teaching moment recorded:**
- Task 2 reasoning error: Shivani attributed 404 to "I did not enter email/password" — incorrect. 404 = resource does not exist (product ID 9999 not in DB). Authentication failures produce 401/403, not 404. These are completely separate concepts. Corrected in feedback.
- 404 vs 401 vs 403 distinction is a common interview question area — needs reinforcement.

**Strong performance:**
- Correctly identified that 401 on GET /api/Users matched expectation (no bug)
- Located the JWT token in the POST login response without prompting
- Completed all 6 tasks independently with Postman

**Implications:** Ready for Lesson 06: Test Design Techniques (Equivalence Partitioning, Boundary Value Analysis, Decision Tables). These are ISTQB-tested concepts and appear directly in Junior QA interviews. Will ground them in the Juice Shop registration and search features.
