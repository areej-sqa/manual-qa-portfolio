# Forgot / Reset Password Test Cases

## Scope
Positive, negative, validation, email, security-focused, session, and edge-case testing for forgot and reset password functionality.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| RESET-001 | Request reset with registered email | 1. Open Forgot Password<br>2. Enter registered email<br>3. Submit | Registered email | Reset request is accepted and reset instructions are sent according to requirements | — | Not Run | High | — | Positive |
| RESET-002 | Submit empty email field | 1. Open Forgot Password<br>2. Leave email blank<br>3. Submit | Blank | Required-field validation is displayed | — | Not Run | Medium | — | Validation |
| RESET-003 | Invalid email format | 1. Enter invalid email<br>2. Submit | user@ / user.com | Email format validation is displayed | — | Not Run | Medium | — | Negative |
| RESET-004 | Request reset for unregistered email | 1. Enter unregistered email<br>2. Submit | Unregistered email | Application follows defined behavior without exposing unnecessary account information | — | Not Run | High | — | Security-focused |
| RESET-005 | Leading/trailing spaces in email | 1. Enter registered email with spaces<br>2. Submit | " user@example.com " | Email is handled according to application requirements | — | Not Run | Medium | — | Edge case |
| RESET-006 | Reset email received | 1. Request password reset<br>2. Check inbox | Registered email | Reset email is delivered with correct instructions and reset action/link | — | Not Run | High | — | Email |
| RESET-007 | Reset email content | 1. Open reset email<br>2. Review sender, recipient and content | Reset email | Email contains correct user-facing information and no sensitive password data | — | Not Run | Medium | — | Email |
| RESET-008 | Valid reset link | 1. Request reset<br>2. Open received link | Valid reset link | User reaches the correct password reset flow | — | Not Run | High | — | Positive |
| RESET-009 | Expired reset link | 1. Open an expired reset link | Expired link | Reset is rejected and appropriate recovery/request-new-link option is provided | — | Not Run | High | — | Negative |
| RESET-010 | Invalid/tampered reset link | 1. Modify or use invalid reset token<br>2. Open link | Invalid token | Password reset is denied safely with appropriate feedback | — | Not Run | High | — | Security-focused |
| RESET-011 | Reuse reset link after successful reset | 1. Reset password successfully<br>2. Open same link again | Used reset link | Previously used reset link cannot reset the password again | — | Not Run | High | — | Security-focused |
| RESET-012 | New password meets policy | 1. Open valid reset link<br>2. Enter valid new password<br>3. Confirm password<br>4. Submit | Valid new password | Password is reset successfully | — | Not Run | High | — | Positive |
| RESET-013 | New password below minimum length | 1. Enter short password<br>2. Confirm<br>3. Submit | Short password | Password policy validation is displayed and reset is prevented | — | Not Run | High | — | Negative |
| RESET-014 | New password violates complexity rules | 1. Enter password that violates configured policy<br>2. Submit | Invalid password | Appropriate password-policy validation is displayed | — | Not Run | High | — | Validation |
| RESET-015 | Password confirmation mismatch | 1. Enter new password<br>2. Enter different confirmation<br>3. Submit | Different passwords | Reset is prevented and mismatch validation is displayed | — | Not Run | High | — | Negative |
| RESET-016 | Empty password fields | 1. Leave password fields blank<br>2. Submit | Blank | Required-field validations are displayed | — | Not Run | Medium | — | Validation |
| RESET-017 | Password masking | 1. Enter new password | Valid password | Password characters are masked | — | Not Run | Medium | — | UI |
| RESET-018 | Show/Hide new password | 1. Enter password<br>2. Toggle visibility | Valid password | Password visibility toggles without changing its value | — | Not Run | Medium | — | UI |
| RESET-019 | Login using new password | 1. Reset password successfully<br>2. Open Login<br>3. Login using new password | New password | Login succeeds with the new password | — | Not Run | High | — | Integration |
| RESET-020 | Login using old password after reset | 1. Reset password<br>2. Attempt login using old password | Old password | Old password no longer authenticates the user | — | Not Run | High | — | Security-focused |
| RESET-021 | Existing sessions after password reset | 1. Login on another session/device<br>2. Reset password<br>3. Check existing session | N/A | Existing sessions follow the application's defined security/session policy | — | Not Run | High | — | Session |
| RESET-022 | Multiple reset requests | 1. Request several reset emails<br>2. Inspect received links<br>3. Attempt reset | Multiple reset links | Multiple requests are handled according to token validity and security requirements | — | Not Run | High | — | Edge case |
| RESET-023 | Rapid repeated reset requests | 1. Submit Forgot Password repeatedly in a short period | Registered email | Application handles repeated requests safely according to configured limits | — | Not Run | Medium | — | Abuse/Edge case |
| RESET-024 | Network failure when requesting reset | 1. Enter registered email<br>2. Submit while request fails | Registered email | Appropriate error/retry feedback is displayed and application remains stable | — | Not Run | High | — | Error handling |
| RESET-025 | Network failure while saving new password | 1. Enter valid new password<br>2. Submit while request fails | Valid password | User receives appropriate feedback and password state remains consistent | — | Not Run | High | — | Error handling |
| RESET-026 | Refresh reset page | 1. Open valid reset link<br>2. Refresh page | Valid reset link | Reset flow remains secure and behaves according to token requirements | — | Not Run | Medium | — | Edge case |
| RESET-027 | Browser Back after successful reset | 1. Reset password successfully<br>2. Press browser Back | N/A | User cannot incorrectly repeat or restore completed reset state | — | Not Run | Medium | — | Navigation |
| RESET-028 | Sensitive information not exposed in URL | 1. Use reset flow<br>2. Inspect URLs | Reset flow | Password values and unnecessary sensitive information are not exposed in URL | — | Not Run | High | — | Security-focused |
| RESET-029 | Reset link associated with correct account | 1. Request reset for Account A<br>2. Open link<br>3. Reset password | Account A | Reset affects only the intended account | — | Not Run | High | — | Data integrity |
| RESET-030 | Reset flow across supported environments | 1. Perform reset flow on supported browsers/devices | Valid account | Reset flow works consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
