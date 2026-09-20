# Web Application Exploratory Testing Session

## Session ID
EXP-001

## Feature / Area
User Account and Profile Management

## Objective
Explore account and profile functionality to identify functional, validation, usability, session, and data-persistence issues that may not be covered by predefined test cases.

## Test Charter
Explore the complete user journey from login through profile editing, account settings, password management, and logout.

Focus on unexpected user behavior, invalid inputs, navigation changes, refresh behavior, session handling, and data persistence.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Test Data
- Valid test account
- Invalid login credentials
- Valid and invalid profile information
- Long text values
- Special characters
- Unicode characters
- Sample profile image

## Areas Explored

- Login
- Logout
- Profile
- Account settings
- Password change
- Form validation
- Navigation
- Session behavior
- Data persistence
- Profile image upload
- Responsive behavior

## Scenarios Tested

1. Login with valid credentials.
2. Login with an incorrect password.
3. Submit login form with empty fields.
4. Refresh the page after login.
5. Use browser Back after login.
6. Edit profile information.
7. Save valid profile changes.
8. Submit profile with required fields empty.
9. Enter long text into profile fields.
10. Enter special and Unicode characters.
11. Upload a valid profile image.
12. Attempt to upload an unsupported image format.
13. Refresh immediately after saving changes.
14. Open account settings in multiple browser tabs.
15. Update the same profile field from two tabs.
16. Change the account password.
17. Attempt to reuse the old password where restricted.
18. Verify session behavior after password change.
19. Navigate away with unsaved changes.
20. Logout and attempt to reopen an authenticated page using browser Back.
21. Open a previously authenticated URL after logout.
22. Resize the browser to a mobile-sized viewport.
23. Check buttons, fields, and navigation at smaller widths.
24. Test repeated clicks on Save.
25. Disconnect the network while saving profile changes.
26. Restore the network and retry the operation.

## Findings

### Finding 1 — Unsaved Changes Warning
No warning is displayed when navigating away after editing profile information without saving.

**Type:** Usability / Data Loss Risk  
**Status:** Observation

### Finding 2 — Multiple Save Clicks
The Save button remains enabled while the first update request is processing.

**Type:** Functional / Edge Case  
**Status:** Requires further investigation

### Finding 3 — Mobile Layout
A long email address causes minor layout overflow on a small mobile viewport.

**Type:** UI / Responsive  
**Status:** Observation

### Finding 4 — Logout Protection
Authenticated pages are no longer accessible after logout when revisited directly.

**Type:** Session / Authorization  
**Status:** Working as expected

### Finding 5 — Profile Persistence
Successfully saved profile changes remain available after page refresh and new login.

**Type:** Data Persistence  
**Status:** Working as expected

## Defects Identified

Potential defects requiring separate bug reports:

- Save button allows repeated submission while request is processing.
- Long account information may cause layout overflow on smaller screens.

These findings would require confirmation against product requirements before final defect classification.

## Questions / Clarifications

- Should users receive a warning before leaving a profile page with unsaved changes?
- Are duplicate profile update requests expected to be prevented?
- What is the officially supported minimum mobile viewport width?

## Risks

- Users may accidentally lose unsaved profile changes.
- Repeated submissions could cause unnecessary duplicate requests.
- Long user-generated content may affect responsive layouts.

## Follow-Up Testing

Recommended follow-up testing:

- Verify repeated Save requests at API level.
- Test profile editing in additional supported browsers.
- Test additional mobile screen sizes.
- Verify session invalidation after password change.
- Test concurrent profile updates from separate devices.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered authentication, profile management, validation, session behavior, navigation, persistence, responsive behavior, and error recovery.

Several observations were identified for further investigation, while core profile persistence and post-logout access behavior worked as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. The findings do not represent testing performed on a real company or customer application.
