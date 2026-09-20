# BUG-004 — Unsupported File Type Can Be Uploaded Successfully

## Bug ID
BUG-004

## Title
Application allows users to upload a file type that is not included in the supported file formats.

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
- User is logged in.
- User has permission to upload files.
- The upload feature accepts only specific supported file types.
- A safe unsupported test file is available.

## Steps to Reproduce

1. Login with a valid test account.
2. Navigate to the file upload section.
3. Click **Upload File**.
4. Select a safe file with an unsupported file type.
5. Click **Upload**.
6. Observe the upload result.
7. Refresh the page and review the uploaded files.

## Expected Result
The application should reject the unsupported file and display a clear validation message explaining which file types are allowed.

No file record should be created.

## Actual Result
The unsupported file is uploaded successfully and appears in the user's uploaded files.

The application does not display any file-type validation error.

## Reproducibility
5/5 — Always

## Evidence
- Screenshot: Not included — sample portfolio report
- Screen recording: Not included — sample portfolio report
- Test file: Not included — sample portfolio report

## Additional Notes
File type restrictions should be validated according to the application's upload requirements and should not rely only on the file selection interface.

The same validation should also be checked for drag-and-drop uploads and other upload entry points.

> This is a fictional bug report created for portfolio demonstration purposes. Only safe fictional test data is referenced and no real company or customer data is included.
