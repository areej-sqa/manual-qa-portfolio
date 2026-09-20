# BUG-007 — Checkout Button Overlaps Content on Mobile View

## Bug ID
BUG-007

## Title
Checkout button overlaps the order summary on smaller mobile screen sizes.

## Environment
- Platform: Web — Mobile Responsive View
- Browser: Google Chrome
- Device: Mobile viewport
- Environment: Test / Staging
- Build: Sample Build 1.0

## Severity
Medium

## Priority
Medium

## Preconditions
- At least one product is available.
- Product has been added to the cart.
- User has reached the checkout page.

## Steps to Reproduce

1. Open the application in a mobile-sized viewport.
2. Add a product to the cart.
3. Navigate to the checkout page.
4. Scroll to the order summary section.
5. Observe the **Checkout/Place Order** button and surrounding content.

## Expected Result
The checkout button and order summary should be displayed without overlapping.

All prices, labels, controls, and order information should remain readable and accessible on the supported mobile screen size.

## Actual Result
The checkout button overlaps part of the order summary.

Some order information becomes partially hidden and difficult to read.

## Reproducibility
5/5 — Always

## Evidence
- Screenshot: Not included — sample portfolio report
- Screen recording: Not included — sample portfolio report

## Additional Notes
The issue should also be checked at different supported mobile widths and in both portrait and landscape orientation.

The layout should remain responsive when browser zoom or larger text settings are used.

> This is a fictional bug report created for portfolio demonstration purposes. No real customer, payment, or company data is included.
