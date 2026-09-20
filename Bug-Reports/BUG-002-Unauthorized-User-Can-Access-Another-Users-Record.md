# BUG-002 — Unauthorized User Can Access Another User's Private Record

## Bug ID
BUG-002

## Title
User can access another user's private record by changing the record ID in the URL.

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
- Two test users exist: User A and User B.
- Both users have separate private records.
- User A is logged in.
- User A does not have permission to access User B's records.

## Steps to Reproduce

1. Login as **User A**.
2. Open one of User A's private records.
3. Note the record URL.
4. Replace the record ID in the URL with the ID of a private record belonging to **User B**.
5. Press Enter.
6. Observe the displayed record.

## Expected Result
The application should verify authorization before returning the record. User A should receive an access-denied or appropriate unavailable response and no information belonging to User B should be exposed.

## Actual Result
User B's private record is displayed to User A after the record ID is changed in the URL.

## Reproducibility
5/5 — Always

## Evidence
- Screen recording: Not included — sample portfolio report
- Screenshot: Not included — sample portfolio report
- Network response: Not included — sample portfolio report

## Additional Notes
Hiding records in the user interface is not sufficient. Authorization should also be enforced when the record is requested directly.

This issue may expose private user information to unauthorized users and should be investigated across other record types and API endpoints that use direct resource identifiers.

> This is a fictional bug report created for portfolio demonstration purposes. No real user, customer, company, or production data is included.
