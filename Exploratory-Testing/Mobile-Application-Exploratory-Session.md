# Mobile Application Exploratory Testing Session

## Session ID
EXP-002

## Feature / Area
Mobile App Core User Journey and App Lifecycle

## Objective
Explore the mobile application to identify functional, usability, interruption, permission, network, state-management, and device-specific issues.

## Test Charter
Explore how the application behaves during normal usage and common mobile interruptions.

Focus on app backgrounding, screen locking, network changes, permissions, notifications, orientation changes, repeated actions, and data persistence.

## Environment
- Platform: Mobile Application
- Device: Android Test Device
- OS: Android
- Environment: Test / Staging
- Network: Wi-Fi and Mobile Data
- Build: Sample Build 1.0

## Test Data
- Valid test account
- Invalid credentials
- Sample form data
- Sample image
- Sample upload file
- Valid and invalid input values

## Areas Explored

- App launch
- Login
- Navigation
- Forms
- Background/foreground behavior
- Device lock/unlock
- Network changes
- Permissions
- File and image selection
- Notifications
- Orientation
- Session persistence
- Error recovery
- Logout

## Scenarios Tested

1. Launch the application normally.
2. Login with valid credentials.
3. Attempt login with invalid credentials.
4. Navigate between primary screens.
5. Enter data into a form.
6. Move the app to the background before submitting.
7. Return to the app and verify entered data.
8. Lock the device while completing a form.
9. Unlock the device and return to the app.
10. Switch from Wi-Fi to mobile data.
11. Disable the network during a request.
12. Restore the network and retry.
13. Rapidly tap the Submit button.
14. Deny camera permission.
15. Allow camera permission after previously denying it.
16. Change permission from device settings.
17. Upload an image from the gallery.
18. Cancel the image selection flow.
19. Receive a notification while using the app.
20. Open the application from a notification.
21. Move the app to the background for a longer duration.
22. Return and verify session state.
23. Rotate the device where orientation changes are supported.
24. Verify form data after orientation change.
25. Force-close and reopen the application.
26. Verify previously saved data after reopening.
27. Logout.
28. Reopen the application after logout.
29. Attempt to access previously authenticated content.
30. Repeat critical navigation after multiple app background/foreground cycles.

## Findings

### Finding 1 — Form Data Lost After Backgrounding
Entered but unsaved form information is cleared after the application is moved to the background and reopened.

**Type:** Functional / State Management  
**Status:** Potential Defect

### Finding 2 — Network Recovery
After the network is restored, the failed request can be retried successfully without restarting the application.

**Type:** Network / Recovery  
**Status:** Working as expected

### Finding 3 — Repeated Submission
The Submit button remains active while the request is processing and accepts multiple taps.

**Type:** Functional / Edge Case  
**Status:** Requires further investigation

### Finding 4 — Permission Handling
The application displays an appropriate message when camera permission is denied.

**Type:** Permission Handling  
**Status:** Working as expected

### Finding 5 — Session After Logout
Previously authenticated content cannot be reopened after logout.

**Type:** Session / Authorization  
**Status:** Working as expected

## Defects Identified

Potential defects requiring separate investigation or bug reports:

- Unsaved form data is lost after app backgrounding.
- Submit action may accept multiple taps while processing.

These findings should be confirmed against product requirements before final defect classification.

## Questions / Clarifications

- Should unsaved form data persist when the app is temporarily backgrounded?
- Should the Submit button become disabled while a request is processing?
- How long should an inactive mobile session remain valid?
- Which screen orientations are officially supported?

## Risks

- Users may lose entered information during common mobile interruptions.
- Repeated taps may create duplicate requests.
- Different device lifecycle behavior may produce inconsistent results across devices.

## Follow-Up Testing

Recommended follow-up testing:

- Test incoming phone-call interruption.
- Test low-storage conditions.
- Test additional Android versions.
- Test supported iOS devices.
- Test longer background durations.
- Test slow network conditions.
- Verify duplicate submissions at API level.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered core mobile workflows, app lifecycle behavior, permissions, network changes, interruptions, state persistence, and session handling.

Potential state-management and repeated-submission issues were identified for further investigation, while network recovery, permission handling, and logout protection behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. The findings do not represent testing performed on a real company or customer application.
