# Test IDs Reference Guide

This document lists all `data-testid` attributes used in the application. Use these for reliable Cypress selectors.

## Login Page (`/login`)

- `email-input` - Email input field
- `password-input` - Password input field
- `login-button` - Login submit button

## Dashboard Page (`/dashboard`)

- `logout-button` - Logout button

## Products Page (`/products`)

- `search-input` - Product search input
- `filter-select` - Category filter dropdown
- `loading-indicator` - Loading state indicator
- `retry-button` - Retry button (on error)
- `product-{id}` - Product card container (e.g., `product-1`)
- `product-image-{id}` - Product image (e.g., `product-image-1`)
- `add-to-cart-{id}` - Add to cart button (e.g., `add-to-cart-1`)

## Users Page (`/users`)

- `loading-indicator` - Loading state indicator
- `retry-button` - Retry button (on error)
- `user-{id}` - User card container (e.g., `user-1`)
- `user-avatar-{id}` - User avatar/initial circle (e.g., `user-avatar-1`)
- `user-name-{id}` - User full name (e.g., `user-name-1`)
- `user-username-{id}` - Username (e.g., `user-username-1`)
- `user-email-{id}` - User email (e.g., `user-email-1`)
- `user-company-{id}` - Company name (e.g., `user-company-1`)
- `view-user-{id}` - View Profile button (e.g., `view-user-1`)
- `prev-page-button` - Previous page button
- `next-page-button` - Next page button
- `user-modal-overlay` - Modal backdrop/overlay
- `user-modal` - Modal container
- `close-modal-button` - Close modal button (×)
- `modal-user-name` - User name in modal
- `modal-username` - Username in modal
- `modal-email` - Email in modal
- `modal-phone` - Phone in modal
- `modal-website` - Website in modal
- `modal-address` - Address in modal
- `modal-company` - Company in modal

## Posts Page (`/posts`)

- `search-posts-input` - Search posts input
- `loading-posts` - Loading indicator for posts
- `post-title-{id}` - Post title (e.g., `post-title-1`)
- `post-body-{id}` - Post body/content (e.g., `post-body-1`)
- `load-comments-{id}` - Load Comments button (e.g., `load-comments-1`)
- `comment-{id}` - Comment container (e.g., `comment-1`)

## Contact Page (`/contact`)

- `contact-name` - Name input field
- `contact-email` - Email input field
- `contact-subject` - Subject input field
- `contact-message` - Message textarea
- `contact-submit` - Submit button

## Navigation

All pages have a navigation bar with links:
- Home (`/`)
- Login (`/login`)
- Dashboard (`/dashboard`)
- Products (`/products`)
- Users (`/users`)
- Posts (`/posts`)
- Contact (`/contact`)

## API Endpoints

### Internal APIs:
- `POST /api/login` - Login endpoint
- `POST /api/contact` - Contact form submission

### External APIs:
- `GET https://fakestoreapi.com/products` - Products data
- `GET https://jsonplaceholder.typicode.com/users` - Users data
- `GET https://jsonplaceholder.typicode.com/posts` - Posts data
- `GET https://jsonplaceholder.typicode.com/posts/{id}/comments` - Comments for a post

## Usage Tips:

1. **Dynamic IDs**: Use template literals in Cypress:
   ```javascript
   cy.get(`[data-testid="user-${userId}"]`)
   ```

2. **Partial Matches**: Use `contains` for partial matches:
   ```javascript
   cy.get('[data-testid^="product-"]') // All product cards
   ```

3. **Wait for Elements**: Always wait for elements to be visible:
   ```javascript
   cy.get('[data-testid="loading-indicator"]').should('not.exist')
   cy.get('[data-testid="product-1"]').should('be.visible')
   ```

4. **API Interception**: Use `cy.intercept()` to mock API calls:
   ```javascript
   cy.intercept('GET', 'https://fakestoreapi.com/products', {
     fixture: 'products.json'
   }).as('getProducts')
   ```

