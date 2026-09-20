# Smoke Testing Checklist

## Purpose

This checklist provides a quick validation of critical application functionality after a new build or deployment.

Smoke testing is performed before detailed functional or regression testing to confirm that the build is stable enough for further QA.

## Test Information

- **Application:** Sample Web Application
- **Environment:** Test / Staging
- **Build:** Sample Build 1.0
- **Tester:** QA Engineer
- **Execution Status:** Not Run

## Status Values

- Pass
- Fail
- Blocked
- Not Run
- Not Applicable

---

## 1. Application Availability

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-001 | Application loads successfully | Not Run | — |
| SMK-002 | No unexpected server error appears on launch | Not Run | — |
| SMK-003 | Main navigation loads correctly | Not Run | — |
| SMK-004 | Critical pages are accessible | Not Run | — |

## 2. Authentication

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-005 | User can login with valid credentials | Not Run | — |
| SMK-006 | Invalid credentials are rejected | Not Run | — |
| SMK-007 | Authenticated user reaches the expected landing page | Not Run | — |
| SMK-008 | User can logout successfully | Not Run | — |
| SMK-009 | Protected pages cannot be accessed after logout | Not Run | — |

## 3. Core Navigation

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-010 | Dashboard loads successfully | Not Run | — |
| SMK-011 | Main menu links open expected pages | Not Run | — |
| SMK-012 | Browser Back and Forward do not break critical navigation | Not Run | — |
| SMK-013 | Page refresh does not cause unexpected application failure | Not Run | — |

## 4. Critical CRUD Workflow

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-014 | User can create a valid record | Not Run | — |
| SMK-015 | Created record appears in the expected location | Not Run | — |
| SMK-016 | User can open the created record | Not Run | — |
| SMK-017 | User can update the record | Not Run | — |
| SMK-018 | Updated data persists | Not Run | — |
| SMK-019 | User can delete or archive the test record | Not Run | — |

## 5. Search and Data

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-020 | Search functionality returns results | Not Run | — |
| SMK-021 | Critical data loads without unexpected errors | Not Run | — |
| SMK-022 | Basic filter functionality works | Not Run | — |

## 6. Forms

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-023 | Critical form loads successfully | Not Run | — |
| SMK-024 | Valid form submission succeeds | Not Run | — |
| SMK-025 | Required-field validation works | Not Run | — |
| SMK-026 | Successful submission displays expected confirmation | Not Run | — |

## 7. Roles and Permissions

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-027 | Authorized user can access required functionality | Not Run | — |
| SMK-028 | Restricted user cannot access protected functionality | Not Run | — |
| SMK-029 | Direct protected URL respects access permissions | Not Run | — |

## 8. Notifications

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-030 | Critical event triggers expected notification | Not Run | — |
| SMK-031 | Notification opens the correct destination | Not Run | — |

## 9. API and Integration Health

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-032 | Critical API request completes successfully | Not Run | — |
| SMK-033 | Application can retrieve required backend data | Not Run | — |
| SMK-034 | Critical external integration is available | Not Run | — |
| SMK-035 | Integration data appears in the expected application area | Not Run | — |

## 10. Payment / Subscription

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-036 | Checkout or subscription page loads successfully | Not Run | — |
| SMK-037 | Sandbox payment workflow can be initiated | Not Run | — |
| SMK-038 | Successful sandbox transaction produces expected result | Not Run | — |
| SMK-039 | Failed sandbox payment is handled correctly | Not Run | — |

## 11. Mobile / Responsive

| ID | Smoke Check | Status | Notes |
|---|---|---|---|
| SMK-040 | Application loads at mobile viewport | Not Run | — |
| SMK-041 | Main navigation remains usable | Not Run | — |
| SMK-042 | Critical forms remain usable | Not Run | — |
| SMK-043 | No major content overlap blocks critical actions | Not Run | — |

## Build Acceptance Criteria

The build can proceed to detailed testing when:

- Critical smoke scenarios pass.
- Login and logout are functional.
- Core business workflows are accessible.
- Critical APIs and integrations are operational.
- No blocker prevents further testing.
- No critical defect makes the build unusable.

## Build Rejection Criteria

The build should be returned for investigation when:

- Application cannot be accessed.
- Authentication is completely broken.
- Critical business workflow cannot be completed.
- Required backend services are unavailable.
- Critical data cannot be loaded.
- A blocker prevents meaningful regression testing.

## Smoke Test Summary

After execution, the tester should record:

- Total Scenarios
- Passed
- Failed
- Blocked
- Not Run
- Critical Defects
- Build Status
- Additional Notes

> This is a fictional smoke testing checklist created for portfolio demonstration purposes. Execution results should be recorded only after testing an actual authorized build.
