# BUG-005 — Form Data Is Lost After Mobile App Is Backgrounded

## Bug ID
BUG-005

## Title
Entered form data is cleared when the mobile app is moved to the background and reopened.

## Environment
- Platform: Mobile App
- Device: Android Test Device
- OS: Android
- Environment: Test / Staging
- Build: Sample Build 1.0
- Network: Wi-Fi

## Severity
Medium

## Priority
High

## Preconditions
- User is logged in.
- User has access to a form containing multiple input fields.
- The application is running normally.

## Steps to Reproduce

1. Open the mobile application.
2. Login with a valid test account.
3. Navigate to the form.
4. Enter valid information into multiple fields.
5. Do not submit the form.
6. Move the application to the background.
7. Wait approximately 10 seconds.
8. Return to the application.
9. Observe the form.

## Expected Result
The application should return the user to the form and preserve the entered data according to the expected app-state behavior.

## Actual Result
The application returns to the form, but all previously entered data is cleared.

The user must enter the information again.

## Reproducibility
4/5 — Frequently

## Evidence
- Screen recording: Not included — sample portfolio report
- Screenshot: Not included — sample portfolio report
- Device logs: Not included — sample portfolio report

## Additional Notes
This issue may cause significant inconvenience on longer forms and increases the risk of users abandoning the workflow.

The behavior should also be checked when:
- The device is locked and unlocked.
- A phone call interrupts the application.
- The user switches between multiple applications.
- The app remains in the background for different durations.

> This is a fictional bug report created for portfolio demonstration purposes. No real user, customer, or company data is included.
