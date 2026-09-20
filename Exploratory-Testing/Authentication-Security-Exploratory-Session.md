# Authentication and Security-Focused Exploratory Testing Session

## Session ID
EXP-007

## Feature / Area
Authentication, Password Reset, Sessions, and Access Control

## Objective
Explore authentication and account-security workflows to identify functional security issues involving login, password reset, sessions, authorization, account state, and direct access to protected resources.

## Test Charter
Explore how the application protects user accounts and authenticated functionality.

Focus on invalid authentication attempts, password reset behavior, session invalidation, direct URL access, multiple sessions, role changes, and unauthorized resource access.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Test Data
- Valid test user
- Second test user
- Admin test user
- Restricted test user
- Valid and invalid credentials
- Password reset test email
- Private test records

## Areas Explored

- Login
- Failed authentication
- Password reset
- Reset-token behavior
- Password change
- Logout
- Session expiration
- Multiple sessions
- Direct URL access
- Role-based access
- Record ownership
- Disabled accounts

## Scenarios Tested

1. Login with valid credentials.
2. Login with an incorrect password.
3. Submit repeated incorrect passwords.
4. Submit empty login fields.
5. Request a password reset for a registered test account.
6. Request a reset for an unregistered email.
7. Open a valid password reset link.
8. Attempt to reuse a successfully used reset link.
9. Attempt to use an expired reset link.
10. Request multiple password reset links.
11. Verify behavior of older reset links.
12. Change the account password.
13. Attempt login using the old password.
14. Login using the new password.
15. Logout and use browser Back.
16. Open a protected URL after logout.
17. Copy a private record URL.
18. Attempt to open it as another test user.
19. Change the record ID in the URL to another user's record.
20. Attempt a restricted action as a standard user.
21. Attempt the same action through its direct URL.
22. Open the account in two browser sessions.
23. Logout from one session.
24. Check the second session according to expected session rules.
25. Change the user's role during an active session.
26. Verify restricted functionality after the role change.
27. Disable a test account.
28. Attempt login with the disabled account.
29. Attempt to reuse an existing authenticated session for the disabled account.
30. Verify that error messages do not expose unnecessary account information.

## Findings

### Finding 1 — Expired Reset Link
An expired password reset link still allows the test user to set a new password.

**Type:** Authentication / Account Security  
**Status:** Potential Defect

### Finding 2 — Unauthorized Record Access
Changing a record identifier in the URL allows User A to view a private record belonging to User B.

**Type:** Authorization / Privacy  
**Status:** Potential Critical Defect

### Finding 3 — Post-Logout Access
Protected pages cannot be reopened after logout using their direct URLs.

**Type:** Session Management  
**Status:** Working as expected

### Finding 4 — Invalid Login
Incorrect credentials are rejected without exposing sensitive account information.

**Type:** Authentication  
**Status:** Working as expected

### Finding 5 — Role Change
Restricted functionality remains visible until the user refreshes the page after a role change.

**Type:** Authorization / State Management  
**Status:** Requires further investigation

## Defects Identified

Potential defects requiring separate bug reports:

- Expired password reset token remains usable.
- A user may access another user's private record by modifying the record identifier.

The role-change behavior should be confirmed against session and permission requirements before final defect classification.

## Questions / Clarifications

- What is the configured password reset token expiration period?
- Should requesting a new reset link invalidate all previous reset links?
- Should role changes take effect immediately in active sessions?
- Should disabling an account invalidate all existing sessions?
- What is the expected session duration?

## Risks

- Invalid reset-token handling may weaken account protection.
- Missing resource-level authorization may expose private user information.
- Delayed permission updates may allow users to see outdated actions.
- Incorrect session invalidation may allow access after account changes.

## Follow-Up Testing

Recommended follow-up testing:

- Verify authorization at API level.
- Test additional private resource types.
- Test reset-token reuse.
- Test multiple password reset requests.
- Verify session behavior after password changes.
- Verify session behavior after account deactivation.
- Test role changes across multiple active sessions.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered authentication, password reset, session management, direct URL access, resource authorization, role changes, and account state.

Potential reset-token and resource-authorization defects were identified, while invalid-login handling and post-logout protection behaved as expected in this fictional sample session.

> This is a fictional security-focused exploratory testing session created for portfolio demonstration purposes. It represents functional QA validation rather than penetration testing and contains no real credentials, customer information, or company data.
