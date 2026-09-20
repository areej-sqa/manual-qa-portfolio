# File Upload & Document Management Test Cases

## Scope
Positive, negative, validation, file type/size, multiple upload, download, preview, deletion, permissions, security-focused, and error-handling test cases.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| FILE-001 | Upload supported file | 1. Click Upload<br>2. Select supported file<br>3. Confirm upload | Valid PDF/JPG/DOCX | File uploads successfully and appears in the expected location | — | Not Run | High | — | Positive |
| FILE-002 | Upload unsupported file type | 1. Click Upload<br>2. Select unsupported file | Unsupported extension | Upload is rejected with appropriate feedback | — | Not Run | High | — | Negative |
| FILE-003 | Upload file at maximum allowed size | 1. Select file at configured size limit<br>2. Upload | Max-size file | File uploads successfully if it meets the allowed limit | — | Not Run | Medium | — | Boundary |
| FILE-004 | Upload oversized file | 1. Select file exceeding configured limit<br>2. Upload | Oversized file | Upload is rejected with appropriate size validation | — | Not Run | High | — | Boundary |
| FILE-005 | Upload zero-byte/empty file | 1. Select empty file<br>2. Upload | 0-byte file | File is handled according to validation requirements | — | Not Run | Medium | — | Negative |
| FILE-006 | File with long filename | 1. Select file with very long name<br>2. Upload | Long filename | Filename is handled without breaking UI or storage behavior | — | Not Run | Medium | — | Boundary |
| FILE-007 | Filename with spaces | 1. Upload file containing spaces in name | QA Test Report.pdf | File uploads and filename displays correctly | — | Not Run | Low | — | Edge case |
| FILE-008 | Filename with supported special characters | 1. Upload file with supported characters in name | report-(final)_01.pdf | File is handled correctly according to filename rules | — | Not Run | Medium | — | Edge case |
| FILE-009 | Duplicate filename | 1. Upload file<br>2. Upload another file with same name | Same filename | Duplicate is handled according to overwrite/version/rename requirements | — | Not Run | Medium | — | Edge case |
| FILE-010 | Multiple file upload | 1. Select multiple valid files<br>2. Upload | Multiple supported files | All valid files upload correctly when multiple upload is supported | — | Not Run | High | — | Positive |
| FILE-011 | Mixed valid and invalid files | 1. Select supported and unsupported files together<br>2. Upload | PDF + invalid file | Files are handled according to defined partial/batch validation behavior | — | Not Run | High | — | Negative |
| FILE-012 | Drag-and-drop upload | 1. Drag valid file into upload area | Valid file | File is accepted and uploaded correctly when drag-and-drop is supported | — | Not Run | Medium | — | UI |
| FILE-013 | Cancel file selection | 1. Click Upload<br>2. Cancel file picker | N/A | No file is uploaded and page state remains unchanged | — | Not Run | Low | — | Negative |
| FILE-014 | Cancel upload in progress | 1. Start large upload<br>2. Cancel when supported | Large file | Upload stops and incomplete file is not incorrectly saved | — | Not Run | Medium | — | Edge case |
| FILE-015 | Network failure during upload | 1. Start upload<br>2. Interrupt network | Valid file | Appropriate failure/retry feedback is displayed and partial file is handled safely | — | Not Run | High | — | Error handling |
| FILE-016 | Retry failed upload | 1. Cause upload failure<br>2. Restore connection<br>3. Retry | Valid file | Retry completes without unintended duplicate files | — | Not Run | High | — | Recovery |
| FILE-017 | Rapid repeated Upload clicks | 1. Select file<br>2. Rapidly trigger upload multiple times | Valid file | Duplicate unintended uploads are prevented | — | Not Run | Medium | — | Edge case |
| FILE-018 | Upload progress indicator | 1. Upload sufficiently large file<br>2. Observe UI | Large valid file | Progress/loading state accurately represents upload status when supported | — | Not Run | Medium | — | UI |
| FILE-019 | Preview uploaded image | 1. Upload image<br>2. Open Preview | Valid JPG/PNG | Correct image is displayed | — | Not Run | Medium | — | Preview |
| FILE-020 | Preview uploaded PDF/document | 1. Upload supported document<br>2. Open Preview | Valid PDF | Correct document is previewed when preview is supported | — | Not Run | Medium | — | Preview |
| FILE-021 | Download uploaded file | 1. Upload file<br>2. Click Download | Valid file | Correct file downloads without corruption | — | Not Run | High | — | Download |
| FILE-022 | Downloaded file integrity | 1. Upload known file<br>2. Download it<br>3. Compare/open file | Known file | Downloaded content matches the stored file | — | Not Run | High | — | Data integrity |
| FILE-023 | Rename document | 1. Upload file<br>2. Rename it<br>3. Save | New filename | Updated name is saved and displayed correctly | — | Not Run | Medium | — | Document management |
| FILE-024 | Delete document | 1. Upload file<br>2. Delete it<br>3. Confirm | Existing file | File is removed according to requirements | — | Not Run | High | — | Positive |
| FILE-025 | Cancel file deletion | 1. Select Delete<br>2. Cancel confirmation | Existing file | File remains available and unchanged | — | Not Run | Medium | — | Negative |
| FILE-026 | Refresh after upload | 1. Upload file<br>2. Refresh page | Valid file | Successfully uploaded file remains available | — | Not Run | High | — | Persistence |
| FILE-027 | File associated with correct record | 1. Upload file to Record A<br>2. Open Record B | File + records | File appears only under the intended record according to requirements | — | Not Run | High | — | Data integrity |
| FILE-028 | Unauthorized user views private file | 1. Login as unauthorized user<br>2. Attempt to open private file | Private file | Access is denied and file content is not exposed | — | Not Run | High | — | Authorization |
| FILE-029 | Unauthorized user downloads private file | 1. Attempt direct/private download without permission | Private file URL/reference | Download is denied | — | Not Run | High | — | Security-focused |
| FILE-030 | Unauthorized user deletes file | 1. Login as limited user<br>2. Attempt deletion | Restricted file | Delete action is denied | — | Not Run | High | — | Authorization |
| FILE-031 | Direct file URL after logout | 1. Login and access private file<br>2. Logout<br>3. Reopen file URL | Private file URL | Authentication/authorization requirements remain enforced | — | Not Run | High | — | Security-focused |
| FILE-032 | File extension/content mismatch | 1. Use controlled test file whose extension does not match its content type<br>2. Upload | Test file | Application validates files according to security/product requirements | — | Not Run | High | — | Security-focused |
| FILE-033 | Potentially unsafe upload type | 1. Attempt upload of file type prohibited by product policy | Prohibited test file | File is rejected according to upload security rules | — | Not Run | High | — | Security-focused |
| FILE-034 | File version replacement | 1. Upload document<br>2. Replace/update it with newer version | Version 1 + Version 2 | Correct version is available according to versioning requirements | — | Not Run | Medium | — | Document management |
| FILE-035 | File metadata | 1. Upload file<br>2. Review metadata | Known file | Filename, type, size, uploader/date and other supported metadata are correct | — | Not Run | Medium | — | Data accuracy |
| FILE-036 | Search uploaded document | 1. Upload file<br>2. Search by filename | Existing filename | Correct file appears when document search is supported | — | Not Run | Medium | — | Integration |
| FILE-037 | Deleted file absent from search/list | 1. Delete file<br>2. Search/reload list | Deleted filename | Deleted file no longer appears according to deletion rules | — | Not Run | Medium | — | Data consistency |
| FILE-038 | Upload from mobile device | 1. Open upload on supported mobile device<br>2. Select file/photo<br>3. Upload | Supported mobile file | Upload completes correctly | — | Not Run | Medium | — | Mobile |
| FILE-039 | Upload across supported browsers | 1. Repeat core upload flow across supported browsers | Valid file | Upload behaves consistently across supported browsers | — | Not Run | Medium | — | Cross-browser |
| FILE-040 | Storage/service failure | 1. Attempt upload while storage service failure is simulated | Valid file | User receives appropriate error and application does not report false success | — | Not Run | High | — | Integration/Error handling |
