# BUG-001 — Duplicate Payment Created When Pay Button Is Clicked Multiple Times

## Bug ID
BUG-001

## Title
Duplicate payment is created when the user clicks the Pay button multiple times during payment processing.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Severity
Critical

## Priority
High

## Preconditions
- User is logged in.
- A product is available for purchase.
- User has added the product to the cart.
- User has reached the checkout page.
- A valid test payment method is available.

## Steps to Reproduce

1. Add a product to the cart.
2. Proceed to checkout.
3. Enter valid checkout information.
4. Enter a valid test payment method.
5. Click the **Pay** button multiple times quickly before payment processing completes.
6. Wait for the transaction to finish.
7. Check the order and payment history.

## Expected Result
The Pay button should become disabled after the first submission, and only one payment and one order should be created.

## Actual Result
Multiple payment requests are processed, resulting in duplicate charges and duplicate orders for the same checkout attempt.

## Reproducibility
5/5 — Always

## Evidence
- Screen recording: Not included — sample portfolio report
- Screenshot: Not included — sample portfolio report
- Payment logs: Not included — sample portfolio report

## Additional Notes
The application should prevent duplicate payment submissions while the first payment request is being processed. Server-side duplicate protection should also ensure that repeated requests do not create multiple payments or orders.

> This is a fictional bug report created for portfolio demonstration purposes. No real customer, payment, or company data is included.
