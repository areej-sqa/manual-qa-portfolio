# BUG-003 — Expired Password Reset Link Still Allows Password Change

## Bug ID
BUG-003

## Title
Expired password reset link still allows the user to set a new password.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Severity
High

## Priority
High

## Preconditions
- A registered test user exists.
- The user has access to the test email inbox.
- Password reset functionality is enabled.
- The reset link has a configured expiration period.

## Steps to Reproduce

1. Open the login page.
2. Click **Forgot Password**.
3. Enter the registered test email address.
4. Submit the password reset request.
5. Open the password reset email.
6. Wait until the reset link has passed its configured expiration time.
7. Open the expired reset link.
8. Enter a new valid password.
9. Confirm the new password.
10. Submit the form.
11. Attempt to login using the new password.

## Expected Result
The expired password reset link should be rejected. The user should be informed that the link has expired and should be required to request a new password reset link.

The account password should remain unchanged.

## Actual Result
The expired reset link remains valid and allows the user to successfully change the account password.

The user can then login using the newly created password.

## Reproducibility
5/5 — Always

## Evidence
- Screen recording: Not included — sample portfolio report
- Screenshot: Not included — sample portfolio report
- Reset email: Not included — sample portfolio report

## Additional Notes
Password reset tokens should become invalid after their configured expiration period.

The same flow should also be checked for previously used reset links to confirm that a successfully used token cannot be reused.

> This is a fictional bug report created for portfolio demonstration purposes. No real account, email, credential, or company data is included.
