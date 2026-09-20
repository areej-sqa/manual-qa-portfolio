# Subscription and Billing Exploratory Testing Session

## Session ID
EXP-010

## Feature / Area
Subscription Plans, Trials, Upgrades, Downgrades, and Billing

## Objective
Explore subscription and billing functionality to identify issues involving plan access, payment status, feature restrictions, upgrades, downgrades, cancellations, renewals, and account state.

## Test Charter
Explore the complete subscription lifecycle using sandbox payment methods.

Focus on plan changes, feature access, billing status, payment failures, repeated actions, cancellation, expiration, and data consistency.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Payment Gateway: Sandbox
- Build: Sample Build 1.0

## Test Data
- Free-plan test account
- Trial account
- Paid-plan test account
- Sandbox payment method
- Valid test card
- Declined test card
- Different subscription plans

## Areas Explored

- Free plan
- Trial
- Paid subscription
- Upgrade
- Downgrade
- Cancellation
- Renewal
- Payment failure
- Feature restrictions
- Billing status
- Subscription persistence
- Repeated submissions

## Scenarios Tested

1. Create a free-plan account.
2. Verify free-plan feature restrictions.
3. Start a trial.
4. Verify trial features become available.
5. Upgrade from free to a paid plan.
6. Complete payment using a valid sandbox method.
7. Verify paid features become available.
8. Refresh the page after upgrading.
9. Logout and login again.
10. Verify the subscription remains active.
11. Attempt to upgrade using a declined payment method.
12. Verify paid features are not incorrectly enabled after failed payment.
13. Retry payment with a valid test method.
14. Rapidly click the subscription confirmation button.
15. Verify duplicate subscriptions or charges are not created.
16. Upgrade from one paid plan to another.
17. Verify feature access after the upgrade.
18. Downgrade to a lower plan.
19. Verify downgrade timing according to product rules.
20. Verify restricted features after downgrade.
21. Cancel the subscription.
22. Verify cancellation status.
23. Verify access during any remaining paid period.
24. Verify behavior after subscription expiration.
25. Attempt to access a paid feature after expiration.
26. Renew or reactivate the subscription where supported.
27. Verify feature access after reactivation.
28. Update the payment method.
29. Verify billing information reflects the update.
30. Simulate a renewal payment failure.
31. Verify subscription state after failed renewal.
32. Open the billing page in multiple browser tabs.
33. Perform a plan change in one tab.
34. Verify the other tab reflects the updated state after refresh.
35. Review subscription history or invoices where supported.

## Findings

### Finding 1 — Failed Payment Handling
A declined sandbox payment does not activate paid features.

**Type:** Payment / Subscription  
**Status:** Working as expected

### Finding 2 — Repeated Subscription Submission
The confirmation button remains enabled while the subscription request is processing.

**Type:** Payment / Edge Case  
**Status:** Requires further investigation

### Finding 3 — Subscription Persistence
The upgraded subscription remains correctly active after logout and login.

**Type:** Data Persistence  
**Status:** Working as expected

### Finding 4 — Downgrade Messaging
The application changes the displayed plan immediately after a downgrade request, although the higher plan remains active until the end of the billing period.

**Type:** UI / Subscription State  
**Status:** Potential Defect

### Finding 5 — Expired Subscription Access
Paid-only functionality becomes unavailable after the test subscription expires.

**Type:** Authorization / Subscription  
**Status:** Working as expected

## Defects Identified

Potential issues requiring further investigation:

- Subscription confirmation may accept repeated submissions while processing.
- Downgrade UI may display a plan state that does not match the user's current feature access.

These findings should be confirmed against subscription and billing requirements before final defect classification.

## Questions / Clarifications

- When should a downgrade become effective?
- Should plan labels show the current plan or the scheduled next plan?
- What is the expected grace-period behavior after a failed renewal?
- Should the subscription button become disabled immediately after submission?
- How should unused trial time behave after upgrading?

## Risks

- Incorrect subscription state may provide unauthorized feature access.
- Duplicate submissions may create duplicate billing operations.
- Incorrect downgrade messaging may confuse users.
- Failed renewal handling may incorrectly enable or disable features.
- Billing and application states may become inconsistent.

## Follow-Up Testing

Recommended follow-up testing:

- Verify subscription state through the API.
- Test duplicate payment protection.
- Test trial expiration.
- Test failed renewal recovery.
- Test multiple upgrade and downgrade combinations.
- Verify invoices and billing history.
- Test subscription webhooks where applicable.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered free plans, trials, paid subscriptions, upgrades, downgrades, payment failures, cancellations, renewals, expiration, and feature access.

Potential repeated-submission and downgrade-state issues were identified, while failed-payment handling, subscription persistence, and expired-plan restrictions behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. No real payment details, customer information, company data, or production transactions are included.
