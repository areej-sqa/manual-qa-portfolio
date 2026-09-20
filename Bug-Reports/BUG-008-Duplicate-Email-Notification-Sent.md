# BUG-008 — Duplicate Email Notification Sent for a Single Event

## Bug ID
BUG-008

## Title
User receives duplicate email notifications when a single event is triggered.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Email Provider: Test Email Service
- Build: Sample Build 1.0

## Severity
Medium

## Priority
High

## Preconditions
- User is logged in.
- User has a verified test email address.
- Email notifications are enabled.
- An action that triggers an email notification is available.

## Steps to Reproduce

1. Login with a valid test account.
2. Confirm that email notifications are enabled.
3. Perform an action that should generate one email notification.
4. Wait for the notification to be processed.
5. Open the test email inbox.
6. Review the emails received for the event.

## Expected Result
Only one email notification should be generated and delivered for the single event.

## Actual Result
Two identical email notifications are received for the same event.

Both emails contain the same subject, content, and event information.

## Reproducibility
4/5 — Frequently

## Evidence
- Email screenshots: Not included — sample portfolio report
- Screen recording: Not included — sample portfolio report
- Email/provider logs: Not included — sample portfolio report

## Additional Notes
The issue may be caused by duplicate event processing, repeated notification jobs, or retry handling.

The event should be processed idempotently so that retries or duplicate events do not result in unintended duplicate notifications.

The same behavior should also be checked for push and in-app notifications where applicable.

> This is a fictional bug report created for portfolio demonstration purposes. No real email addresses, customer information, or company data is included.
