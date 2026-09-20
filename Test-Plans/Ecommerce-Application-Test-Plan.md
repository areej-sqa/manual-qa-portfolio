# E-commerce Application Test Plan

## 1. Introduction

This test plan defines the QA approach for testing a sample e-commerce application.

The purpose is to validate the complete customer journey from product discovery through checkout, payment, order creation, and post-purchase activities.

## 2. Objectives

The main objectives are to:

- Validate critical shopping workflows.
- Verify product, cart, wishlist, and checkout functionality.
- Validate payment processing and failure handling.
- Verify pricing, discounts, taxes, and shipping calculations.
- Validate order creation and order history.
- Identify functional, UI, integration, and data integrity defects.
- Perform regression testing before release.

## 3. In Scope

The following areas are included:

- User registration and login
- Product listing
- Product details
- Product search
- Filters and sorting
- Product variants
- Inventory availability
- Shopping cart
- Wishlist
- Coupons and discounts
- Shipping address
- Billing address
- Shipping methods
- Checkout
- Payment methods
- Payment success and failure
- Order confirmation
- Order history
- Order cancellation
- Refund-related workflows
- Email notifications
- Mobile responsive behavior
- Third-party integrations
- Error handling
- Regression and smoke testing

## 4. Out of Scope

The following activities are excluded unless specifically requested:

- Real financial transactions
- Production payment testing
- Warehouse physical operations
- Courier infrastructure testing
- Source code review
- Production penetration testing
- Large-scale performance and load testing

## 5. Test Strategy

Testing will combine structured test cases with exploratory testing.

Coverage will include:

- Positive scenarios
- Negative scenarios
- Boundary conditions
- Edge cases
- End-to-end purchase workflows
- Payment failure scenarios
- Duplicate-submission scenarios
- Inventory scenarios
- Integration scenarios
- Error and recovery scenarios

## 6. Test Types

The following testing types may be performed:

- Functional Testing
- Smoke Testing
- Regression Testing
- Exploratory Testing
- UI Testing
- Responsive Testing
- Cross-Browser Testing
- Integration Testing
- API Testing
- Payment Testing
- Negative Testing
- Boundary Testing
- UAT Support

## 7. Critical E-commerce Workflows

Priority should be given to:

1. Product search and discovery.
2. Product selection and variants.
3. Add to cart.
4. Cart quantity and price updates.
5. Coupon application.
6. Checkout.
7. Shipping calculation.
8. Payment submission.
9. Order creation.
10. Order confirmation.
11. Order history.
12. Cancellation and refund workflows where supported.

## 8. Payment Testing

Payment testing should use approved test or sandbox payment methods.

Testing should verify:

- Successful payment
- Declined payment
- Invalid payment details
- Expired card
- Insufficient funds response where supported
- Payment timeout
- Payment cancellation
- Duplicate payment prevention
- Multiple clicks on payment button
- Browser refresh during payment
- Back navigation during payment
- Payment gateway error
- Successful payment with delayed response
- Correct order creation after payment
- No order creation after confirmed failed payment
- Correct payment status displayed to the user

No real card or customer financial information should be stored in portfolio documentation.

## 9. Pricing and Calculation Testing

Testing should verify:

- Product price
- Quantity calculation
- Subtotal
- Discounts
- Coupon rules
- Shipping charges
- Taxes
- Final total
- Currency display
- Rounding behavior

The final amount displayed before payment should match the amount submitted for payment.

## 10. Inventory Testing

Testing should verify:

- In-stock products
- Out-of-stock products
- Low-stock products
- Quantity limits
- Inventory changes during checkout
- Multiple users attempting to purchase limited inventory
- Product becoming unavailable after being added to cart

## 11. Test Environment

Example test environment:

- Environment: QA / Staging
- Desktop OS: Windows 11
- Primary Browser: Google Chrome
- Additional Browsers: Microsoft Edge and Mozilla Firefox
- Mobile Coverage: Supported Android and iOS browsers
- Payment Gateway: Sandbox / Test Mode
- API Tool: Postman

## 12. Test Data

Test data may include:

- Test customer accounts
- Guest checkout data
- Products with different prices
- Products with variants
- In-stock and out-of-stock products
- Valid and invalid coupons
- Test shipping addresses
- Sandbox payment methods
- Different user roles
- Sample orders

Real customer or payment information should not be used.

## 13. Entry Criteria

Testing can begin when:

- Test environment is available.
- Required build is deployed.
- Product catalog contains test data.
- Checkout is accessible.
- Sandbox payment gateway is configured.
- Required test accounts are available.
- Core requirements or acceptance criteria are available.

## 14. Exit Criteria

Testing may be considered complete when:

- Critical purchase workflows have been validated.
- High-priority test cases have been executed.
- Payment success and failure scenarios have been tested.
- Pricing and order totals have been validated.
- No unresolved release-blocking defects remain unless formally accepted.
- Critical resolved defects have been retested.
- Required regression testing is complete.
- Known issues are documented.

## 15. Defect Management

Defects should include:

- Clear title
- Environment
- Preconditions
- Steps to reproduce
- Expected result
- Actual result
- Severity
- Priority
- Reproducibility
- Supporting evidence where available

Payment and order defects should clearly identify whether the issue affects payment status, order status, inventory, or customer-visible information.

## 16. Test Deliverables

QA deliverables may include:

- E-commerce Test Plan
- Test Cases
- Bug Reports
- Payment Testing Results
- Exploratory Testing Notes
- Regression Checklist
- Test Execution Results
- QA Summary Report

## 17. Risks and Mitigation

### Payment Gateway Dependency
**Risk:** Payment provider issues may block checkout testing.

**Mitigation:** Use sandbox payment methods and document provider-related blockers separately.

### Inventory Changes
**Risk:** Shared test data may change during execution.

**Mitigation:** Use controlled test products where possible and verify inventory before executing dependent cases.

### Pricing Configuration
**Risk:** Incorrect configuration may affect multiple calculations.

**Mitigation:** Validate subtotal, discounts, shipping, taxes, and final totals independently.

### Third-Party Dependency
**Risk:** Shipping, tax, email, or payment services may become unavailable.

**Mitigation:** Document affected scenarios and retest after service restoration.

## 18. Test Completion and Reporting

At the end of the testing cycle, QA should document:

- Testing scope completed
- Checkout and payment results
- Passed and failed scenarios
- Blocked or pending scenarios
- Open defects
- Resolved and retested defects
- Known limitations
- Release-related QA risks

> This is a fictional test plan created for portfolio demonstration purposes. No real customer, payment, company, or production data is included.
