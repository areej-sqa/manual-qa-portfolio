# Signup / Registration Test Cases

## Scope
Positive, negative, validation, verification, security-focused, and edge-case testing for user registration.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| SIGNUP-001 | Register with valid details | 1. Open Signup page<br>2. Enter valid required details<br>3. Submit form | Valid name, email, password | Account is created successfully and expected post-registration flow starts | — | Not Run | High | — | Positive |
| SIGNUP-002 | Submit empty signup form | 1. Leave all fields blank<br>2. Click Signup | Blank fields | Required-field validations are displayed | — | Not Run | High | — | Validation |
| SIGNUP-003 | Register with already registered email | 1. Enter an existing user's email<br>2. Complete remaining fields<br>3. Submit | Existing email | Duplicate account is not created and appropriate feedback is displayed | — | Not Run | High | — | Negative |
| SIGNUP-004 | Invalid email format | 1. Enter invalid email<br>2. Complete remaining fields<br>3. Submit | user@ / user.com | Email format validation is displayed | — | Not Run | Medium | — | Validation |
| SIGNUP-005 | Email with leading/trailing spaces | 1. Enter email with spaces<br>2. Complete form<br>3. Submit | " user@example.com " | Email is handled according to application requirements without creating incorrect duplicate data | — | Not Run | Medium | — | Edge case |
| SIGNUP-006 | Email case handling | 1. Enter email using uppercase/mixed case<br>2. Complete form<br>3. Submit | User@Example.COM | Email casing is handled consistently according to application requirements | — | Not Run | Medium | — | Edge case |
| SIGNUP-007 | Password below minimum length | 1. Enter password shorter than allowed<br>2. Submit form | Short password | Password policy validation is displayed and registration is prevented | — | Not Run | High | — | Negative |
| SIGNUP-008 | Password meeting requirements | 1. Enter a password satisfying configured rules<br>2. Complete form<br>3. Submit | Valid password | Password is accepted | — | Not Run | High | — | Positive |
| SIGNUP-009 | Password violates complexity rules | 1. Enter password missing required complexity<br>2. Submit | Password violating configured policy | Appropriate password validation is displayed | — | Not Run | High | — | Validation |
| SIGNUP-010 | Password and confirmation do not match | 1. Enter password<br>2. Enter different confirmation password<br>3. Submit | Two different passwords | Registration is prevented and mismatch validation is displayed | — | Not Run | High | — | Negative |
| SIGNUP-011 | Password masking | 1. Enter password and confirmation | Valid password | Sensitive password characters are masked | — | Not Run | Medium | — | UI |
| SIGNUP-012 | Show/Hide password | 1. Enter password<br>2. Toggle password visibility | Valid password | Visibility changes correctly without altering the password | — | Not Run | Medium | — | UI |
| SIGNUP-013 | Minimum field-length boundary | 1. Enter values at configured minimum lengths<br>2. Submit | Boundary values | Valid boundary values are accepted | — | Not Run | Medium | — | Boundary |
| SIGNUP-014 | Maximum field-length boundary | 1. Enter values at configured maximum lengths<br>2. Submit | Boundary values | Valid maximum values are accepted without UI/data issues | — | Not Run | Medium | — | Boundary |
| SIGNUP-015 | Exceed maximum field length | 1. Enter value exceeding allowed limit<br>2. Submit | Over-limit value | Input is restricted or appropriate validation is displayed | — | Not Run | Medium | — | Negative/Boundary |
| SIGNUP-016 | Special characters in name field | 1. Enter supported special characters in name<br>2. Complete form<br>3. Submit | Example: O'Connor / Anne-Marie | Valid names are handled according to requirements | — | Not Run | Medium | — | Edge case |
| SIGNUP-017 | Email verification sent | 1. Register using valid email<br>2. Check inbox | Valid accessible email | Verification email is sent when email verification is required | — | Not Run | High | — | Email |
| SIGNUP-018 | Valid email verification link | 1. Register<br>2. Open verification email<br>3. Click verification link | Valid verification link | Account/email is verified successfully | — | Not Run | High | — | Verification |
| SIGNUP-019 | Expired verification link | 1. Open an expired verification link | Expired link | Verification is rejected and appropriate recovery/resend option is provided | — | Not Run | High | — | Negative |
| SIGNUP-020 | Reuse verification link | 1. Verify account<br>2. Open the same link again | Previously used link | Application handles reused link safely without corrupting account state | — | Not Run | Medium | — | Edge case |
| SIGNUP-021 | Resend verification email | 1. Request another verification email | Registered unverified email | New verification email is sent according to configured rules | — | Not Run | Medium | — | Verification |
| SIGNUP-022 | Rapid repeated Signup clicks | 1. Complete valid form<br>2. Rapidly click Signup multiple times | Valid registration data | Only one account/request is processed as intended | — | Not Run | High | — | Edge case |
| SIGNUP-023 | Network failure during registration | 1. Complete valid form<br>2. Submit while request fails | Valid registration data | Appropriate error/retry feedback is shown and duplicate/partial account creation is avoided | — | Not Run | High | — | Error handling |
| SIGNUP-024 | Terms acceptance required | 1. Complete form<br>2. Leave required Terms checkbox unchecked<br>3. Submit | Valid registration data | Registration is prevented when mandatory consent has not been provided | — | Not Run | High | — | Validation |
| SIGNUP-025 | Terms/privacy links | 1. Open Terms and Privacy links from Signup page | N/A | Correct pages/documents open and Signup data is not unexpectedly lost | — | Not Run | Medium | — | Navigation |
| SIGNUP-026 | Refresh during registration | 1. Partially complete Signup form<br>2. Refresh page | Partial form data | Application follows defined data-retention behavior and remains stable | — | Not Run | Low | — | Edge case |
| SIGNUP-027 | Browser Back during registration | 1. Enter Signup data<br>2. Navigate away/back | Partial form data | Application behaves consistently without unintended account creation | — | Not Run | Low | — | Navigation |
| SIGNUP-028 | Successful signup cannot create duplicate on refresh | 1. Complete registration successfully<br>2. Refresh/revisit completion flow | Valid registration data | Duplicate account is not created | — | Not Run | High | — | Data integrity |
| SIGNUP-029 | Sensitive password not exposed in URL | 1. Complete registration<br>2. Submit<br>3. Inspect URL | Valid registration data | Password and other sensitive authentication data are not exposed in URL | — | Not Run | High | — | Security-focused |
| SIGNUP-030 | Signup across supported browsers/devices | 1. Complete valid signup on supported environments | Valid registration data | Registration works consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
