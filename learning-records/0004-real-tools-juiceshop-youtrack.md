# Real Tools Available — Juice Shop + YouTrack

Khushal (husband, Senior QA) has set up a full real-world QA environment on a home Unraid server:

**OWASP Juice Shop** — a deliberately vulnerable e-commerce web app, ideal for manual testing practice.
- URL: `http://192.168.0.202:9058`
- Features to test: Registration, Login, Product Search, Basket, Checkout, User Profile, Admin panel

**YouTrack** (JetBrains issue tracker + Test Manager)
- URL: `https://youtrack.kkunraid.com`
- Shivani's login: sbhatt / AqcJUm4rzpfjcB
- Project: "Juice Shop Testing" (OJS)
- Agile board columns: To Do → In Progress → Ready for Review → Ready for Testing → Verified → Blocked → To Release
- Test Manager extension: "OWASP Juice Shop" test repository already created

**Existing user stories on the board (To Do):**
- OJS-4: "As a new customer, I want to create an account so that I can buy juices."
- OJS-5: "As a shopper, I want to search for items so I can quickly find my favorite juices."
- OJS-6: "As a customer, I want to add a juice to my basket so I can purchase it later."

**Implications:** All lessons from here should use these real tools. Test cases go into YouTrack Test Manager (not just on paper). Bugs found should be raised as YouTrack issues on the Juice Shop Testing board. This gives her a real portfolio to talk about in interviews.
