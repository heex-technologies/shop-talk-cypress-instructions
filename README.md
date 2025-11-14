# QA Engineer Cypress Assessment

## Product Overview
ShopTalk is a community-based e-commerce platform that combines product purchasing with a user exchange space. The goal is to create an informed shopping experience where customers can get answers to their questions before, during, and after purchase.

### Product's Objectives

- Reduce cart abandonment rate and increase purchase confidence by allowing users to help each other through an integrated forum.
- Create an engaged community around products.

### Target Personas

- **Hesitant buyer**: needs reassurance before purchase, has questions about products.
- **Expert customer**: enjoys sharing their experience, helps others, brand loyal.
- **Quick buyer**: wants to buy fast without friction, occasionally consults reviews.

## Application Overview

**Application Name:** ShopTalk

**Application URL:** https://shop-talk.heex.io/

You will be testing the live, deployed application. You do NOT need access to the source code.

This application uses real external APIs:
- **FakeStoreAPI** (https://fakestoreapi.com/products) - Products page
- **JSONPlaceholder** (https://jsonplaceholder.typicode.com/) - Users, Posts and Comments

### Test Credentials

- **Email:** `admin@test.com`
- **Password:** `password123`

### Reference Documents

- **TEST_IDS_REFERENCE.md** - Contains all available `data-testid` attributes
- Use these for reliable element selection in your tests
- You can inspect the DOM in your browser to verify these selectors exist

### Important Notes

- ShopTalk uses real external APIs (FakeStoreAPI, JSONPlaceholder)
- You can mock API responses for reliable, fast tests
- Network calls may be slow - mocking is the recommended approach
- All pages are accessible without authentication except `/dashboard`

---

## Testing Tasks

### Task 1: Navigation and Basic Page Verification
Write Cypress tests that verify:
- All navigation links are present and functional on the home page
- Home page loads correctly and displays the main heading
- Navigation links navigate to correct pages

---

### Task 2: Login Form Validation and Authentication
Write comprehensive tests for the login form:
- Empty form submission validation
- Invalid email format validation
- Password too short validation
- Valid credentials submission and redirect to dashboard
- User email is displayed on dashboard
- Logout functionality and redirect back to login

---

### Task 3: API Testing - Products Page
Write tests for the Products page that verify:
- API call is made to FakeStoreAPI (https://fakestoreapi.com/products)
- Products load and display correctly after API response
- Loading indicator appears while fetching
- Search functionality works on fetched data
- Filter dropdown (All/Electronics/Jewelery/etc.) works correctly
- Error handling when API fails (mock a failed API response)

---

### Task 4: API Testing - Users Page with Pagination
Write tests for the Users page that verify:
- API call is made to JSONPlaceholder API (https://jsonplaceholder.typicode.com/users)
- Users are displayed correctly
- Pagination buttons work (Previous/Next) - note: pagination is client-side
- Page number updates correctly
- Disabled state of pagination buttons (first/last page)
- Users are paginated correctly (6 per page)

---

### Task 5: Protected Routes and Error Handling
Create tests that verify:
- Unauthenticated users are redirected from dashboard to login
- Direct URL access to dashboard without login redirects to login
- Login with incorrect credentials shows appropriate error

---

### Task 6: Test Organization and Best Practices
Organize your tests to demonstrate:
- Proper use of custom commands (at least one custom command)
- Test data management (use fixtures or constants)
- Clear test structure and organization

---

### Optional Bonus Tasks

#### Bonus 1: Contact Form Testing
Write tests for the contact form that verify:
- Form submission with valid data
- Success message appears
- API error handling

#### Bonus 2: Posts Page with Nested API Calls
Write tests for the Posts page that verify:
- Initial API call fetches posts
- Clicking "Load Comments" triggers a second API call
- Comments are displayed after API response

---

## Additional Notes

- Focus on completing the core 6 tasks.
- Bonus tasks are optional and can be attempted if you have time.
- Quality over quantity - well-written, maintainable tests are preferred.

---

## Expected Deliverables

Please provide:
1. Complete Cypress test suite (all test files)
2. `cypress.config.js` configuration file
3. Any custom commands or utilities (`cypress/support/commands.ts`)
4. README with setup instructions (how to run the tests)
5. Brief explanation of test strategy (optional but preferred)
6. Test fixtures or mock data (if used)

### Submission Format

- GitHub repository link
- Or Zip file containing the entire Cypress project folder
- Or any format that allows us to review and run the tests

---

## Tips

- Focus on code quality and best practices
- Write maintainable, scalable tests
- Use appropriate selectors
- Mock API calls for reliable tests
- Organize your tests logically
- Add comments where helpful
- Be prepared to discuss your approach and decisions

Good luck!

