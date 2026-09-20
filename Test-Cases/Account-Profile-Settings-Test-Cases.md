# Account / Profile Settings Test Cases

## Scope
Positive, negative, validation, permissions, data persistence, security-focused, and edge-case testing for account and profile settings.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| SET-001 | View profile settings | 1. Login<br>2. Open Settings/Profile | N/A | Current profile information is displayed correctly | — | Not Run | High | — | Positive |
| SET-002 | Update valid profile information | 1. Open Profile Settings<br>2. Edit fields<br>3. Save | Valid profile data | Changes are saved and displayed correctly | — | Not Run | High | — | Positive |
| SET-003 | Save without making changes | 1. Open Settings<br>2. Click Save without editing | Existing data | No incorrect update or unexpected behavior occurs | — | Not Run | Low | — | Edge case |
| SET-004 | Required profile field left blank | 1. Clear required field<br>2. Click Save | Blank required field | Validation is displayed and invalid data is not saved | — | Not Run | High | — | Negative |
| SET-005 | Invalid email format | 1. Edit email<br>2. Enter invalid format<br>3. Save | user@ | Email validation is displayed | — | Not Run | High | — | Validation |
| SET-006 | Change email to already registered email | 1. Edit email<br>2. Enter email belonging to another account<br>3. Save | Existing email | Duplicate email is rejected according to requirements | — | Not Run | High | — | Negative |
| SET-007 | Email change verification | 1. Change email<br>2. Save<br>3. Check verification flow | New valid email | Email change follows configured verification requirements | — | Not Run | High | — | Integration |
| SET-008 | Maximum field length | 1. Enter value at maximum allowed length<br>2. Save | Boundary value | Valid boundary value is saved correctly | — | Not Run | Medium | — | Boundary |
| SET-009 | Exceed maximum field length | 1. Enter over-limit value<br>2. Save | Over-limit text | Input is restricted or appropriate validation is displayed | — | Not Run | Medium | — | Negative/Boundary |
| SET-010 | Supported special characters | 1. Enter supported characters in profile fields<br>2. Save | O'Connor / Anne-Marie | Supported characters are stored and displayed correctly | — | Not Run | Medium | — | Edge case |
| SET-011 | Upload valid profile image | 1. Select profile image<br>2. Upload/Save | Supported image | Image uploads and displays correctly | — | Not Run | Medium | — | File upload |
| SET-012 | Upload unsupported file type | 1. Select unsupported file<br>2. Upload | Unsupported file | Upload is rejected with appropriate feedback | — | Not Run | Medium | — | Negative |
| SET-013 | Upload oversized profile image | 1. Select file exceeding configured limit<br>2. Upload | Oversized image | File is rejected according to size requirements | — | Not Run | Medium | — | Boundary |
| SET-014 | Replace profile image | 1. Upload existing image<br>2. Upload different valid image | Valid image | New image replaces previous image correctly | — | Not Run | Medium | — | Positive |
| SET-015 | Remove profile image | 1. Click Remove/Delete image<br>2. Confirm if required | N/A | Image is removed and default state is displayed | — | Not Run | Low | — | Positive |
| SET-016 | Change password from Settings | 1. Open password settings<br>2. Enter required values<br>3. Save | Valid current/new password | Password changes successfully | — | Not Run | High | — | Security-focused |
| SET-017 | Incorrect current password | 1. Enter incorrect current password<br>2. Enter valid new password<br>3. Save | Incorrect current password | Password change is rejected | — | Not Run | High | — | Negative |
| SET-018 | New password violates policy | 1. Enter valid current password<br>2. Enter invalid new password<br>3. Save | Weak/invalid password | Password policy validation is displayed | — | Not Run | High | — | Validation |
| SET-019 | Notification preference toggle | 1. Change notification preference<br>2. Save<br>3. Reload page | Toggle ON/OFF | Selected preference persists correctly | — | Not Run | Medium | — | Persistence |
| SET-020 | Multiple preference changes | 1. Change multiple settings<br>2. Save<br>3. Reload | Multiple settings | All selected changes persist correctly | — | Not Run | Medium | — | Persistence |
| SET-021 | Cancel/discard profile edits | 1. Modify information<br>2. Cancel or navigate away according to UI | Modified data | Unsaved changes are handled according to requirements | — | Not Run | Medium | — | Navigation |
| SET-022 | Refresh after saved changes | 1. Update profile<br>2. Save<br>3. Refresh page | Updated data | Saved values remain correct after refresh | — | Not Run | High | — | Persistence |
| SET-023 | Settings persist after logout/login | 1. Change settings<br>2. Save<br>3. Logout<br>4. Login again | Updated settings | Saved settings remain associated with the account | — | Not Run | High | — | Persistence |
| SET-024 | Unauthorized access to another user's settings | 1. Attempt to access another user's settings/profile-edit endpoint or URL | Another user reference | Access is denied and no unauthorized data can be modified | — | Not Run | High | — | Authorization |
| SET-025 | Rapid repeated Save clicks | 1. Modify profile<br>2. Rapidly click Save multiple times | Valid update | Duplicate requests do not create inconsistent data | — | Not Run | Medium | — | Edge case |
| SET-026 | Network failure while saving | 1. Modify settings<br>2. Save while request fails | Valid update | Error/retry feedback is displayed and data remains consistent | — | Not Run | High | — | Error handling |
| SET-027 | Concurrent profile update | 1. Open account in two sessions<br>2. Modify same data in both<br>3. Save changes | Different values | Application handles conflicting updates according to defined behavior | — | Not Run | Medium | — | Edge case |
| SET-028 | Delete/deactivate account | 1. Open account management<br>2. Select Delete/Deactivate<br>3. Follow confirmation flow | Valid account | Account action follows defined confirmation and security requirements | — | Not Run | High | — | Account management |
| SET-029 | Cancel account deletion | 1. Start deletion flow<br>2. Cancel before confirmation | N/A | Account remains active and data is not deleted | — | Not Run | High | — | Negative |
| SET-030 | Settings across supported environments | 1. Update and verify settings on supported browsers/devices | Valid data | Settings function consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
