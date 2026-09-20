# Requirements Traceability Matrix (RTM)

## Purpose

The Requirements Traceability Matrix maps product requirements to test cases and defects.

It helps QA verify that requirements have appropriate test coverage and makes it easier to identify missing, failed, blocked, or incomplete testing.

---

## Project Information

- **Application:** Sample Web Application
- **Build:** Sample Build 1.0
- **Environment:** Test / Staging
- **Tester:** QA Engineer
- **Execution Status:** Not Run

## Status Values

- Pass
- Fail
- Blocked
- Not Run
- Not Applicable

---

## Requirements Traceability

| Requirement ID | Requirement | Test Case IDs | Test Status | Defect ID | Notes |
|---|---|---|---|---|---|
| REQ-001 | User can register using valid information | TC-SIGNUP-001, TC-SIGNUP-002 | Not Run | — | — |
| REQ-002 | User can login using valid credentials | TC-LOGIN-001 | Not Run | — | — |
| REQ-003 | Invalid login credentials are rejected | TC-LOGIN-002, TC-LOGIN-003 | Not Run | — | — |
| REQ-004 | User can reset a forgotten password | TC-RESET-001, TC-RESET-002 | Not Run | — | — |
| REQ-005 | Expired password reset links cannot be used | TC-RESET-003 | Not Run | — | — |
| REQ-006 | User can update profile information | TC-PROFILE-001, TC-PROFILE-002 | Not Run | — | — |
| REQ-007 | Restricted users cannot access admin functionality | TC-RBAC-001, TC-RBAC-002 | Not Run | — | — |
| REQ-008 | Users cannot access another user's private records | TC-RBAC-003 | Not Run | — | — |
| REQ-009 | Search returns relevant records | TC-SEARCH-001 | Not Run | — | — |
| REQ-010 | Users can filter search results | TC-SEARCH-002, TC-SEARCH-003 | Not Run | — | — |
| REQ-011 | Supported files can be uploaded | TC-FILE-001 | Not Run | — | — |
| REQ-012 | Unsupported file types are rejected | TC-FILE-002 | Not Run | — | — |
| REQ-013 | Required form fields are validated | TC-FORM-001, TC-FORM-002 | Not Run | — | — |
| REQ-014 | Expected events generate notifications | TC-NOTIF-001 | Not Run | — | — |
| REQ-015 | Notification preferences are respected | TC-NOTIF-002 | Not Run | — | — |
| REQ-016 | Valid payment completes successfully | TC-PAY-001 | Not Run | — | — |
| REQ-017 | Failed payments do not create successful orders | TC-PAY-002 | Not Run | — | — |
| REQ-018 | Duplicate payment submissions are prevented | TC-PAY-003 | Not Run | — | — |
| REQ-019 | Subscription upgrades update feature access | TC-SUB-001 | Not Run | — | — |
| REQ-020 | API endpoints enforce authentication | TC-API-001, TC-API-002 | Not Run | — | — |
| REQ-021 | API endpoints enforce authorization | TC-API-003 | Not Run | — | — |
| REQ-022 | External integrations synchronize expected data | TC-INT-001, TC-INT-002 | Not Run | — | — |
| REQ-023 | AI assistant uses available source information correctly | TC-AI-001, TC-AI-002 | Not Run | — | — |
| REQ-024 | AI citations reference valid available sources | TC-AI-003 | Not Run | — | — |
| REQ-025 | Critical workflows remain usable on mobile devices | TC-MOB-001, TC-MOB-002 | Not Run | — | — |

---

## Coverage Summary

| Metric | Result |
|---|---:|
| Total Requirements | 25 |
| Requirements with Test Coverage | 25 |
| Requirements Tested | 0 |
| Requirements Passed | 0 |
| Requirements Failed | 0 |
| Requirements Blocked | 0 |
| Requirements Not Run | 25 |

## Traceability Workflow

When testing is performed:

1. Review each requirement.
2. Confirm that appropriate test cases cover the requirement.
3. Execute the mapped test cases.
4. Update the test status.
5. Link any discovered defect to the affected requirement.
6. Add new test cases if a coverage gap is identified.
7. Recheck affected requirements after defect fixes.

## Coverage Gaps

Document requirements without sufficient test coverage.

| Requirement ID | Coverage Gap | Required Action |
|---|---|---|
| — | — | — |

## Failed Requirements

| Requirement ID | Failed Test Case | Defect ID | Status |
|---|---|---|---|
| — | — | — | — |

## Blocked Requirements

| Requirement ID | Blocking Reason | Dependency | Next Action |
|---|---|---|---|
| — | — | — | — |

## QA Notes

The RTM should be updated whenever:

- Requirements change
- New requirements are added
- Test cases are added or removed
- Defects affect requirement coverage
- Previously blocked functionality becomes available
- Regression coverage changes

> This is a fictional Requirements Traceability Matrix created for portfolio demonstration purposes. The requirement and test case identifiers are illustrative examples and do not represent confidential customer, employer, or production information.
