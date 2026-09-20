# File Upload and Error Handling Exploratory Testing Session

## Session ID
EXP-008

## Feature / Area
File Upload, Validation, Processing, and Failure Recovery

## Objective
Explore file-upload functionality to identify validation, usability, data-integrity, permission, error-handling, and recovery issues.

## Test Charter
Explore how the application handles valid, invalid, large, duplicate, interrupted, and unsupported file uploads.

Focus on file validation, upload progress, repeated actions, network failures, deletion, permissions, and recovery behavior.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Test Data
- Valid supported file
- Unsupported file type
- Empty file
- Large test file
- Duplicate file
- File with long filename
- File with special characters in filename
- Unicode filename

## Areas Explored

- File selection
- Drag and drop
- File-type validation
- File-size validation
- Upload progress
- Duplicate uploads
- Network interruption
- Retry behavior
- File preview
- File download
- File deletion
- File permissions
- Error messages

## Scenarios Tested

1. Upload a valid supported file.
2. Upload an unsupported file type.
3. Upload an empty file.
4. Upload a file at the allowed size limit.
5. Attempt to upload a file above the allowed size limit.
6. Upload the same file twice.
7. Upload multiple supported files where supported.
8. Select a file and cancel before uploading.
9. Upload using drag and drop.
10. Attempt an unsupported file using drag and drop.
11. Upload a file with a long filename.
12. Upload a file with spaces in its filename.
13. Upload a file with special characters in its filename.
14. Upload a file with a Unicode filename.
15. Rapidly click the Upload button.
16. Refresh the page while an upload is processing.
17. Disconnect the network during upload.
18. Restore the network and retry.
19. Verify a successfully uploaded file after page refresh.
20. Preview the uploaded file.
21. Download the uploaded file.
22. Compare the downloaded file with the original test file.
23. Delete an uploaded file.
24. Attempt to access the deleted file using its old link.
25. Attempt to access another user's private file.
26. Upload a file and logout.
27. Login again and verify expected file availability.
28. Observe validation and server-error messages.
29. Verify failed uploads do not create completed file records.
30. Test the upload interface at a mobile-sized viewport.

## Findings

### Finding 1 — Unsupported File Accepted
An unsupported file type is uploaded successfully instead of being rejected.

**Type:** Validation / File Handling  
**Status:** Potential Defect

### Finding 2 — Network Failure Recovery
When the network is interrupted during upload, the application displays an error and allows the user to retry after connectivity returns.

**Type:** Error Handling / Recovery  
**Status:** Working as expected

### Finding 3 — Duplicate Upload
Uploading the same file twice creates two separate file records without warning.

**Type:** Functional / Data Handling  
**Status:** Requires clarification

### Finding 4 — Deleted File Access
A deleted private file is no longer accessible through its previous link.

**Type:** File Access / Privacy  
**Status:** Working as expected

### Finding 5 — Long Filename
A very long filename causes text overflow in the uploaded-file list.

**Type:** UI / Edge Case  
**Status:** Potential Defect

## Defects Identified

Potential defects requiring further investigation or separate bug reports:

- Unsupported file types may be accepted by the upload feature.
- Long filenames may break the uploaded-file list layout.

Duplicate-file behavior should be confirmed against product requirements before final defect classification.

## Questions / Clarifications

- Which file formats are officially supported?
- What is the maximum allowed file size?
- Should duplicate files be allowed?
- Should interrupted uploads resume or restart?
- How long should deleted file links remain invalid or unavailable?

## Risks

- Incorrect file validation may allow unintended file formats.
- Failed uploads may leave incomplete records.
- Incorrect access controls may expose private files.
- Poor error recovery may require users to restart uploads.
- Long filenames may affect usability on smaller screens.

## Follow-Up Testing

Recommended follow-up testing:

- Verify file validation at API level.
- Test additional supported and unsupported formats.
- Test multiple simultaneous uploads.
- Test slower network conditions.
- Test file permissions across multiple users.
- Test additional browsers.
- Test mobile upload behavior.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered file validation, uploads, duplicate files, network interruptions, recovery, file access, deletion, downloads, and responsive behavior.

Potential file-validation and long-filename UI issues were identified, while network recovery and deleted-file access behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. Only safe fictional test files and data are referenced, and no real customer or company information is included.
