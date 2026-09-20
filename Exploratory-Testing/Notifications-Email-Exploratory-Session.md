# Notifications and Email Exploratory Testing Session

## Session ID
EXP-009

## Feature / Area
Email, In-App Notifications, Preferences, and Delivery

## Objective
Explore notification functionality to identify issues involving delivery, duplicate notifications, preferences, recipients, content, links, timing, and state synchronization.

## Test Charter
Explore how notifications behave when different user actions occur.

Focus on notification delivery, duplicate prevention, preference changes, correct recipients, deep links, read/unread state, retries, and account changes.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Email: Test Email Account
- Build: Sample Build 1.0

## Test Data
- Valid test user
- Second test user
- Test email address
- Enabled notification preferences
- Disabled notification preferences
- Sample records and events

## Areas Explored

- Email notifications
- In-app notifications
- Notification preferences
- Read/unread state
- Notification links
- Duplicate prevention
- Recipient validation
- Delivery timing
- Retry behavior
- Account changes

## Scenarios Tested

1. Trigger an event that should generate an email.
2. Verify the email is received.
3. Verify the email subject.
4. Verify the email content.
5. Verify the correct recipient receives the email.
6. Click the action link in the email.
7. Verify the link opens the correct record.
8. Trigger an in-app notification.
9. Verify the notification appears.
10. Open the notification.
11. Verify read/unread state changes.
12. Mark a notification as unread where supported.
13. Trigger the same event once and check for duplicate notifications.
14. Trigger multiple different events.
15. Disable email notifications.
16. Trigger an email-related event.
17. Verify the disabled email is not delivered.
18. Re-enable email notifications.
19. Trigger another event.
20. Verify delivery resumes.
21. Disable one notification category while leaving others enabled.
22. Verify category-specific preferences.
23. Change the account email address.
24. Trigger a new notification.
25. Verify the notification is sent according to the updated account configuration.
26. Remove a user's access to a record.
27. Trigger an event related to that record.
28. Verify the removed user does not receive restricted information.
29. Open an old notification after its referenced record is deleted.
30. Refresh the notification page.
31. Login from another session and compare notification state.
32. Trigger several notifications rapidly.
33. Verify ordering.
34. Test a notification containing long content.
35. Check the notification interface at a mobile-sized viewport.

## Findings

### Finding 1 — Duplicate Email
A single event generates two identical email notifications.

**Type:** Notification / Duplicate Processing  
**Status:** Potential Defect

### Finding 2 — Notification Preferences
Disabling email notifications prevents new email delivery while in-app notifications continue according to the configured preferences.

**Type:** Preferences  
**Status:** Working as expected

### Finding 3 — Deep Link
The notification action link opens the correct associated record.

**Type:** Navigation / Integration  
**Status:** Working as expected

### Finding 4 — Deleted Record
Opening an old notification for a deleted record displays an appropriate unavailable message instead of an unexpected error.

**Type:** Error Handling  
**Status:** Working as expected

### Finding 5 — Multi-Session Read State
A notification marked as read in one session remains unread in another session until the page is refreshed.

**Type:** State Synchronization  
**Status:** Requires further investigation

## Defects Identified

Potential issues requiring further investigation or separate bug reports:

- A single event may generate duplicate email notifications.
- Notification read state may not update immediately across active sessions.

These findings should be confirmed against product requirements before final defect classification.

## Questions / Clarifications

- How quickly should notification state synchronize across sessions?
- Are notification retries expected after temporary delivery failures?
- Which notification types should remain available after the referenced record is deleted?
- Should notification preference changes take effect immediately?

## Risks

- Duplicate notifications may confuse or annoy users.
- Incorrect recipients could expose private information.
- Broken notification links may prevent users from completing important actions.
- Incorrect preference handling may send unwanted communications.
- Synchronization issues may produce inconsistent notification states.

## Follow-Up Testing

Recommended follow-up testing:

- Verify duplicate notification events at API or job level.
- Test email delivery failures and retries.
- Test notification preferences across multiple categories.
- Test role and permission changes.
- Test notification behavior after account deactivation.
- Test additional browsers and mobile devices.
- Verify push notifications where supported.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered email and in-app notifications, preferences, recipients, deep links, duplicate prevention, read state, account changes, and error handling.

Potential duplicate-delivery and multi-session synchronization issues were identified, while preference handling, deep links, and deleted-record handling behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. No real email addresses, customer information, company data, or production systems are included.
