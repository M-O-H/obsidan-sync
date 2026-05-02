### Stakeholder


Okay, here’s a single-line Product Requirements Document (PRD) for an e-commerce website, designed with a business stakeholder’s perspective, focusing on actionable requirements and clear acceptance criteria:**Product Requirements Document: E-Commerce Website**

**1. Product Overview:** This project aims to develop a user-friendly e-commerce website enabling customers to browse, purchase, and manage their orders, ultimately driving increased online sales and brand awareness for [Company Name].

**2. Objectives and Goals:**
*   Increase online sales by 20% within the first year.
*   Achieve a customer satisfaction score of 4.5 out of 5.
*   Reduce cart abandonment rate by 10%.
*   Establish a strong brand presence and customer loyalty.

**3. Key Features (Prioritized):**
*   **Must-Have:** Product Catalog & Search, Shopping Cart, Secure Checkout, User Account Management, Order Tracking.
*   **Should-Have:** Product Reviews & Ratings, Wishlist, Mobile Responsiveness, Payment Gateway Integration (Stripe, PayPal).
*   **Nice-to-Have:** Personalized Recommendations, Loyalty Program, Live Chat Support, Social Media Integration.

**4. Functional Requirements:**
*   Users must be able to browse products by category and subcategory.
*   Users must be able to search for products using keywords.
*   Users must be able to add products to a shopping cart.
*   Users must be able to proceed to a secure checkout process.
*   Users must be able to create and manage their accounts.
*   The system must accurately track order status and provide updates to users.
*   Admin users must be able to manage products, categories, and users.

**5. Non-Functional Requirements:**
*   **Performance:** Page load times should be under 3 seconds.  API response times under 500ms.
*   **Scalability:** The system must be able to handle 10,000 concurrent users.
*   **Security:**  All sensitive data (payment information, user credentials) must be encrypted using industry-standard protocols (SSL/TLS). PCI DSS compliance is required.
*   **Accessibility:** The website must adhere to WCAG 2.1 Level AA accessibility guidelines.
*   **Availability:**  The website should be available 99.9% of the time.

**6. Assumptions and Constraints:**
*   We will utilize a cloud-based hosting solution (AWS/Azure/Google Cloud).
*   Integration with existing CRM system will be prioritized after core e-commerce functionality is complete.
*   Budget: $50,000 - $100,000 (flexible based on scope).
*   Timeline: 6-9 months.


**7. Acceptance Criteria:**

*   **Product Catalog & Search:**
    *   Given a user navigates to the product catalog, When they browse by category, Then they should see a list of products within that category.
    *   Given a user enters a search term, When they submit the search, Then they should see a list of products matching that term.
*   **Shopping Cart:**
    *   Given a user adds a product to the cart, When they proceed to the cart, Then the product should be displayed with its quantity and price.
    *   Given a user modifies the quantity of a product in the cart, When they save the changes, Then the cart should be updated accordingly.
*   **Secure Checkout:**
    *   Given a user proceeds to checkout, When they enter their shipping and billing information, Then they should be presented with a secure payment gateway.
    *   Given a user completes the checkout process, Then they should receive an order confirmation email.
*   **User Account Management:**
    *   Given a user registers a new account, When they provide valid information, Then they should be able to log in to their account.
    *   Given a user logs in to their account, When they navigate to their profile, Then they should see their order history and account details.

**8. User Stories:**

*   **As a customer, I want to be able to easily search for products, so that I can quickly find what I’m looking for.** (High) - Acceptance Criteria: Search results are displayed within 3 seconds, and results are relevant to the search term.
*   **As a new customer, I want to be able to create an account quickly and easily, so that I can save my shipping and payment information.** (High) - Acceptance Criteria: Account creation form is intuitive and requires minimal information.
*   **As a returning customer, I want to be able to log in to my account, so that I can quickly access my order history.** (High) - Acceptance Criteria: Login process is seamless and secure.
*   **As a customer, I want to see product reviews and ratings, so that I can make informed purchasing decisions.** (Medium) - Acceptance Criteria: Reviews and ratings are displayed prominently on product pages.
*   **As a customer, I want to be able to track my order status, so that I know when to expect my delivery.** (High) - Acceptance Criteria: Order tracking information is readily available and updated in real-time.
*   **As a customer, I want the website to be responsive on my mobile device, so that I can browse and purchase products on the go.** (Medium) - Acceptance Criteria: Website layout adapts seamlessly to different screen sizes.
*   **As an administrator, I want to be able to add new products to the catalog, so that I can expand our product offerings.** (Medium) - Acceptance Criteria: Admin interface allows for easy product creation and management.



---

Would you like me to elaborate on any specific section or add more detail?

## Project Manager
You are an experienced technical Project Manager responsible for planning and delivering software projects.

Your job is to convert product requirements into an actionable execution plan for the development team.

Input:
You will receive a Product Requirements Document (PRD), user stories, and acceptance criteria.

---

Your tasks:

1. Project Breakdown
- Break the project into epics
- Break epics into tasks
- Clearly define deliverables for each task

1. Backlog Creation
- Create a prioritized product backlog
- Each item should include:
  - Title
  - Description
  - Priority (High / Medium / Low)
  - Estimated effort (Small / Medium / Large or story points)

1. Sprint Planning
- Organize tasks into 2–3 sprints
- Define sprint goals
- Assign tasks to each sprint

1. Timeline & Milestones
- Provide a rough timeline
- Define key milestones and delivery checkpoints

1. Risks & Dependencies
- Identify potential risks
- List dependencies between tasks
- Suggest mitigation strategies

1. Team Instructions
- Provide clear instructions for developers and QA
- Define what 'done' means (Definition of Done)

---

Rules:
- Be structured and concise
- Think like a real PM in a startup or agile team
- Avoid technical implementation details (focus on planning)
- Make everything actionable and execution-ready