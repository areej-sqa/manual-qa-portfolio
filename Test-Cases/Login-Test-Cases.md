# Login Test Cases

## Scope
Functional, negative, validation, session, security-focused, and cross-platform test cases for a standard web/mobile login feature.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| LOGIN-001 | Login with valid credentials | 1. Open Login page<br>2. Enter valid email<br>3. Enter valid password<br>4. Click Login | Valid email + password | User logs in successfully and is redirected to the authorized area | — | Not Run | High | — | — |
| LOGIN-002 | Login with incorrect password | 1. Enter valid email<br>2. Enter incorrect password<br>3. Click Login | Valid email + invalid password | Login is rejected and an appropriate error message is displayed | — | Not Run | High | — | Negative |
| LOGIN-003 | Login with unregistered email | 1. Enter unregistered email<br>2. Enter password<br>3. Click Login | Unregistered email + password | Login is rejected with an appropriate error message | — | Not Run | High | — | Negative |
| LOGIN-004 | Submit empty login form | 1. Leave all fields blank<br>2. Click Login | Blank fields | Required-field validations are displayed | — | Not Run | High | — | Validation |
| LOGIN-005 | Email field left blank | 1. Leave email blank<br>2. Enter password<br>3. Click Login | Blank email + valid password | Email required validation is displayed | — | Not Run | Medium | — | Validation |
| LOGIN-006 | Password field left blank | 1. Enter email<br>2. Leave password blank<br>3. Click Login | Valid email + blank password | Password required validation is displayed | — | Not Run | Medium | — | Validation |
| LOGIN-007 | Invalid email format | 1. Enter invalid email<br>2. Enter password<br>3. Click Login | user@ / user.com | Email format validation is displayed | — | Not Run | Medium | — | Negative |
| LOGIN-008 | Password masking | 1. Enter password | Valid password | Password characters are masked | — | Not Run | Medium | — | UI |
| LOGIN-009 | Show/Hide password | 1. Enter password<br>2. Click visibility control<br>3. Click it again | Valid password | Password visibility toggles correctly without changing the entered value | — | Not Run | Medium | — | UI |
| LOGIN-010 | Submit login using Enter key | 1. Enter valid credentials<br>2. Press Enter | Valid credentials | Login form is submitted successfully | — | Not Run | Medium | — | — |
| LOGIN-011 | Leading/trailing spaces in email | 1. Enter valid email with leading/trailing spaces<br>2. Enter password<br>3. Click Login | " user@example.com " | Application handles leading/trailing spaces according to requirements | — | Not Run | Medium | — | Edge case |
| LOGIN-012 | Email case handling | 1. Enter registered email using different casing<br>2. Enter password<br>3. Click Login | USER@EXAMPLE.COM | Email casing is handled according to application requirements | — | Not Run | Medium | — | Edge case |
| LOGIN-013 | Multiple failed login attempts | 1. Enter valid email with incorrect password repeatedly<br>2. Submit each attempt | Valid email + incorrect password | Configured failed-attempt or account-lockout behavior is applied | — | Not Run | High | — | Security-focused |
| LOGIN-014 | Login with disabled/locked account | 1. Enter credentials for disabled/locked account<br>2. Click Login | Locked account credentials | Access is denied with appropriate feedback | — | Not Run | High | — | Negative |
| LOGIN-015 | Login with unverified account | 1. Enter credentials for unverified account<br>2. Click Login | Unverified account credentials | Defined verification flow is followed and unauthorized access is prevented | — | Not Run | High | — | Negative |
| LOGIN-016 | Remember Me | 1. Select Remember Me<br>2. Login<br>3. Close browser/app<br>4. Reopen | Valid credentials | Session persists according to Remember Me requirements | — | Not Run | Medium | — | Session |
| LOGIN-017 | Access protected page after logout | 1. Login<br>2. Logout<br>3. Attempt to open protected page | Protected URL | Protected content cannot be accessed after logout | — | Not Run | High | — | Security-focused |
| LOGIN-018 | Browser Back after logout | 1. Login<br>2. Logout<br>3. Press browser Back | N/A | Previously authenticated content is not accessible | — | Not Run | High | — | Security-focused |
| LOGIN-019 | Direct protected URL while logged out | 1. Logout<br>2. Enter a protected URL directly | Protected URL | User is redirected to login or access is denied | — | Not Run | High | — | Authorization |
| LOGIN-020 | Session expiration | 1. Login<br>2. Remain inactive until session expires<br>3. Perform a protected action | N/A | User is required to authenticate again according to session rules | — | Not Run | High | — | Session |
| LOGIN-021 | Redirect after authentication | 1. While logged out, open protected URL<br>2. Login when redirected | Valid credentials | User is redirected appropriately after successful authentication | — | Not Run | Medium | — | — |
| LOGIN-022 | Rapid/double Login submission | 1. Enter valid credentials<br>2. Rapidly click Login multiple times | Valid credentials | Duplicate requests do not cause incorrect behavior | — | Not Run | Medium | — | Edge case |
| LOGIN-023 | Network failure during login | 1. Enter valid credentials<br>2. Submit while network request fails | Valid credentials | Appropriate error/retry feedback is displayed and application remains stable | — | Not Run | High | — | Error handling |
| LOGIN-024 | Login across supported environments | 1. Perform valid login on supported browsers/devices | Valid credentials | Login works consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
| LOGIN-025 | Sensitive credentials not exposed in URL | 1. Enter credentials<br>2. Submit login<br>3. Inspect browser URL | Valid credentials | Password and sensitive authentication data are not exposed in the URL | — | Not Run | High | — | Security-focused |
