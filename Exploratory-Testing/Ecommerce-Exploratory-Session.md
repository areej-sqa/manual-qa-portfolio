# E-commerce Exploratory Testing Session

## Session ID
EXP-003

## Feature / Area
Product Discovery, Cart, Checkout, and Payment

## Objective
Explore the complete e-commerce purchase journey to identify functional, pricing, validation, usability, payment, inventory, and data-integrity issues.

## Test Charter
Explore the customer journey from product discovery through order completion.

Focus on cart changes, pricing calculations, coupons, inventory, repeated actions, checkout validation, payment failures, browser navigation, and recovery behavior.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Payment Gateway: Sandbox
- Build: Sample Build 1.0

## Test Data
- Test customer account
- Guest user
- In-stock product
- Low-stock product
- Product with variants
- Valid coupon
- Invalid/expired coupon
- Test shipping address
- Sandbox payment method

## Areas Explored

- Product listing
- Product details
- Search
- Filters
- Product variants
- Cart
- Wishlist
- Coupons
- Shipping
- Checkout
- Payment
- Order confirmation
- Inventory
- Order history
- Error recovery

## Scenarios Tested

1. Browse available products.
2. Search for a product by name.
3. Apply multiple product filters.
4. Change sorting.
5. Open a product details page.
6. Select different product variants.
7. Add an in-stock product to the cart.
8. Add the same product again.
9. Increase and decrease quantity.
10. Enter quantity near the available stock limit.
11. Attempt to exceed available stock.
12. Remove a product from the cart.
13. Add a product to the wishlist.
14. Move a wishlist item to the cart.
15. Apply a valid coupon.
16. Apply an invalid coupon.
17. Apply an expired coupon.
18. Remove an applied coupon.
19. Verify subtotal after quantity changes.
20. Verify discount calculation.
21. Verify shipping charges.
22. Verify final order total.
23. Continue checkout with missing required information.
24. Enter an invalid shipping address.
25. Complete checkout information correctly.
26. Submit an invalid sandbox payment method.
27. Retry after a failed payment.
28. Submit a successful sandbox payment.
29. Rapidly click the Pay button multiple times.
30. Refresh the browser during payment processing.
31. Use browser Back during checkout.
32. Verify order confirmation after successful payment.
33. Verify the order appears in order history.
34. Verify inventory after successful purchase.
35. Open the application in a mobile-sized viewport.

## Findings

### Finding 1 — Duplicate Payment Submission
The Pay button remains enabled while payment is processing and accepts repeated clicks.

**Type:** Payment / Data Integrity  
**Status:** Potential Critical Defect

### Finding 2 — Cart Calculation
Cart subtotal updates correctly after product quantity is changed.

**Type:** Functional / Pricing  
**Status:** Working as expected

### Finding 3 — Invalid Coupon
An invalid coupon is rejected and an appropriate validation message is displayed.

**Type:** Validation  
**Status:** Working as expected

### Finding 4 — Checkout Navigation
Using browser Back after entering checkout information preserves some fields but clears others.

**Type:** State Management / Usability  
**Status:** Requires clarification

### Finding 5 — Mobile Checkout Layout
The order action area overlaps part of the order summary on a smaller mobile viewport.

**Type:** UI / Responsive  
**Status:** Potential Defect

## Defects Identified

Potential defects requiring separate bug reports:

- Payment action accepts repeated submissions while processing.
- Checkout layout overlaps important information on smaller mobile screens.

The inconsistent checkout data persistence should be confirmed against product requirements before being classified as a defect.

## Questions / Clarifications

- Should checkout information remain populated after browser Back navigation?
- Should the payment button become disabled immediately after submission?
- What is the minimum officially supported mobile viewport?
- How should inventory be reserved while payment is processing?

## Risks

- Duplicate payment requests may create duplicate charges or orders.
- Incorrect state handling may cause users to re-enter checkout information.
- Responsive layout issues may prevent users from reviewing important order information.
- Inventory changes during checkout may cause order inconsistencies.

## Follow-Up Testing

Recommended follow-up testing:

- Verify duplicate payment requests at API level.
- Test payment timeout behavior.
- Test simultaneous purchases of low-stock products.
- Test checkout in additional supported browsers.
- Test additional mobile screen sizes.
- Verify tax and shipping calculations with different addresses.
- Test guest checkout against registered-user checkout.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered product discovery, cart operations, pricing, coupons, checkout, payment, inventory, order creation, navigation, and responsive behavior.

Potential payment-submission and mobile-layout defects were identified, while core cart calculations and invalid-coupon handling worked as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. No real customer, payment, company, or production data is included.
