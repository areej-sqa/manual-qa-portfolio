# Forms & Validation Test Cases

## Scope
Positive, negative, required-field, input-format, boundary, conditional-field, submission, duplicate prevention, data persistence, and error-handling testing for web/mobile forms.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| FORM-001 | Submit form with valid data | 1. Complete all required fields with valid data<br>2. Submit | Valid data | Form submits successfully and data is saved correctly | — | Not Run | High | — | Positive |
| FORM-002 | Submit completely empty form | 1. Leave all fields blank<br>2. Submit | Blank | Required-field validations are displayed and form is not submitted | — | Not Run | High | — | Negative |
| FORM-003 | Leave one required field blank | 1. Complete form except one required field<br>2. Submit | Missing required value | Validation identifies the missing required field | — | Not Run | High | — | Validation |
| FORM-004 | Optional field left blank | 1. Complete required fields<br>2. Leave optional field blank<br>3. Submit | Valid required data | Form submits successfully | — | Not Run | Medium | — | Positive |
| FORM-005 | Invalid email format | 1. Enter invalid email<br>2. Submit | user@ / user.com | Email validation is displayed | — | Not Run | High | — | Validation |
| FORM-006 | Valid email formats | 1. Enter supported valid email<br>2. Submit | user.name+test@example.com | Valid email is accepted | — | Not Run | Medium | — | Positive |
| FORM-007 | Invalid phone number | 1. Enter invalid phone number<br>2. Submit | Invalid phone | Appropriate validation is displayed | — | Not Run | Medium | — | Negative |
| FORM-008 | Valid phone format | 1. Enter supported phone format<br>2. Submit | Valid phone | Phone number is accepted according to requirements | — | Not Run | Medium | — | Positive |
| FORM-009 | Minimum character boundary | 1. Enter exactly minimum allowed characters<br>2. Submit | Minimum-length value | Boundary value is accepted | — | Not Run | Medium | — | Boundary |
| FORM-010 | Below minimum character limit | 1. Enter fewer than minimum characters<br>2. Submit | Under-limit value | Validation is displayed | — | Not Run | Medium | — | Boundary |
| FORM-011 | Maximum character boundary | 1. Enter exactly maximum allowed characters<br>2. Submit | Maximum-length value | Boundary value is accepted | — | Not Run | Medium | — | Boundary |
| FORM-012 | Exceed maximum character limit | 1. Enter more than allowed characters<br>2. Submit | Over-limit value | Input is restricted or validation is displayed | — | Not Run | Medium | — | Boundary |
| FORM-013 | Leading/trailing spaces | 1. Enter value with leading/trailing spaces<br>2. Submit | " Test User " | Whitespace is handled according to field requirements | — | Not Run | Medium | — | Edge case |
| FORM-014 | Multiple internal spaces | 1. Enter text containing multiple spaces<br>2. Submit | Test  User | Input is stored/displayed according to requirements | — | Not Run | Low | — | Edge case |
| FORM-015 | Supported special characters | 1. Enter supported special characters<br>2. Submit | O'Connor / Anne-Marie | Valid characters are accepted and stored correctly | — | Not Run | Medium | — | Edge case |
| FORM-016 | Unicode/non-English characters | 1. Enter supported Unicode text<br>2. Submit | Multilingual text | Characters are stored and displayed correctly | — | Not Run | Medium | — | Internationalization |
| FORM-017 | Numeric field accepts valid number | 1. Enter valid numeric value<br>2. Submit | 100 | Value is accepted and stored correctly | — | Not Run | Medium | — | Positive |
| FORM-018 | Letters entered in numeric field | 1. Enter letters in numeric field<br>2. Submit | abc | Invalid input is prevented or validated | — | Not Run | Medium | — | Negative |
| FORM-019 | Negative number | 1. Enter negative value in applicable field<br>2. Submit | -10 | Value is accepted/rejected according to business rules | — | Not Run | Medium | — | Boundary |
| FORM-020 | Decimal value | 1. Enter decimal value<br>2. Submit | 10.50 | Decimal handling follows field requirements | — | Not Run | Medium | — | Boundary |
| FORM-021 | Date field with valid date | 1. Select/enter valid date<br>2. Submit | Valid date | Date is accepted and saved correctly | — | Not Run | Medium | — | Positive |
| FORM-022 | Invalid date | 1. Enter invalid date when manual entry is supported<br>2. Submit | Invalid date | Invalid date is rejected | — | Not Run | Medium | — | Negative |
| FORM-023 | Past/future date restriction | 1. Enter date outside allowed range<br>2. Submit | Restricted date | Business-rule validation is displayed | — | Not Run | High | — | Business rules |
| FORM-024 | Dropdown selection | 1. Open dropdown<br>2. Select option<br>3. Submit | Valid option | Selected value is saved correctly | — | Not Run | Medium | — | UI |
| FORM-025 | Required dropdown left unselected | 1. Leave required dropdown at default/no selection<br>2. Submit | No selection | Required validation is displayed | — | Not Run | Medium | — | Validation |
| FORM-026 | Checkbox selection | 1. Select checkbox<br>2. Submit | Selected | Checkbox value is saved correctly | — | Not Run | Medium | — | UI |
| FORM-027 | Radio-button selection | 1. Select option<br>2. Submit | Valid option | Correct option is saved | — | Not Run | Medium | — | UI |
| FORM-028 | Conditional field appears | 1. Select value that triggers conditional field | Trigger option | Correct dependent field appears | — | Not Run | High | — | Dynamic form |
| FORM-029 | Conditional field disappears | 1. Trigger conditional field<br>2. Change parent selection | Different option | Conditional field hides and stale value is handled correctly | — | Not Run | High | — | Dynamic form |
| FORM-030 | Conditional required validation | 1. Trigger required dependent field<br>2. Leave it blank<br>3. Submit | Blank dependent field | Required validation is applied only when applicable | — | Not Run | High | — | Dynamic form |
| FORM-031 | Form retains data after validation error | 1. Complete form<br>2. Make one field invalid<br>3. Submit | Mixed valid/invalid data | Valid entered data is not unexpectedly cleared | — | Not Run | High | — | Usability |
| FORM-032 | Error message clears after correction | 1. Trigger validation error<br>2. Correct value | Corrected data | Error state/message updates appropriately | — | Not Run | Medium | — | Validation |
| FORM-033 | Multiple validation errors | 1. Enter invalid values in multiple fields<br>2. Submit | Multiple invalid values | Applicable errors are displayed clearly | — | Not Run | High | — | Negative |
| FORM-034 | Double-click Submit | 1. Complete valid form<br>2. Rapidly click Submit multiple times | Valid data | Only one intended record/action is created | — | Not Run | High | — | Duplicate prevention |
| FORM-035 | Press Enter to submit | 1. Complete form<br>2. Press Enter where supported | Valid data | Form follows defined keyboard submission behavior | — | Not Run | Medium | — | Keyboard |
| FORM-036 | Cancel form | 1. Enter data<br>2. Click Cancel | Unsaved data | Form closes/navigates according to requirements without unintended save | — | Not Run | Medium | — | Negative |
| FORM-037 | Navigate away with unsaved changes | 1. Modify form<br>2. Navigate away | Unsaved data | Unsaved-change behavior follows requirements | — | Not Run | Medium | — | Navigation |
| FORM-038 | Refresh with unsaved data | 1. Enter data<br>2. Refresh page | Unsaved data | Form follows defined data-retention behavior | — | Not Run | Low | — | Edge case |
| FORM-039 | Edit existing record | 1. Open existing record<br>2. Modify fields<br>3. Save | Updated data | Changes are saved to the correct record | — | Not Run | High | — | CRUD |
| FORM-040 | Saved data persists after refresh | 1. Submit valid form<br>2. Refresh/reopen record | Saved data | Saved values remain correct | — | Not Run | High | — | Persistence |
| FORM-041 | Network failure during submission | 1. Complete valid form<br>2. Submit while request fails | Valid data | Appropriate error/retry feedback is shown and false success is not displayed | — | Not Run | High | — | Error handling |
| FORM-042 | Retry after failed submission | 1. Cause submission failure<br>2. Restore connection<br>3. Retry | Valid data | Form submits once without unintended duplicate record | — | Not Run | High | — | Recovery |
| FORM-043 | Unauthorized form submission | 1. Login as user without required permission<br>2. Attempt submission | Restricted user | Unauthorized action is denied | — | Not Run | High | — | Authorization |
| FORM-044 | Form data associated with correct user/record | 1. Submit form for Record A<br>2. Inspect Record B | Known records | Submitted data is associated only with intended record/user | — | Not Run | High | — | Data integrity |
| FORM-045 | Form across supported environments | 1. Complete core form flow across supported browsers/devices | Valid data | Form behaves consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
