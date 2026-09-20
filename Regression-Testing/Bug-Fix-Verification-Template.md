# Bug Fix Verification Template

## Purpose

This template demonstrates the process used to verify a resolved defect and perform targeted regression testing around the affected functionality.

Bug verification should confirm both that the original defect is fixed and that the change has not introduced problems in related workflows.

---

## Bug Information

- **Bug ID:** BUG-XXX
- **Bug Title:** Sample Bug Title
- **Build:** Sample Build 1.1
- **Environment:** Test / Staging
- **Tester:** QA Engineer
- **Verification Status:** Not Run

## Original Issue

Provide a short description of the original defect.

**Example:**

A user performing a specific action receives incorrect behavior instead of the expected result.

## Original Steps to Reproduce

1. Open the affected feature.
2. Perform the required setup.
3. Execute the action that previously caused the defect.
4. Observe the result.

## Expected Result

The application should complete the action according to the defined requirements without displaying incorrect behavior.

## Previous Actual Result

Describe the behavior that occurred before the fix.

## Fix Verification

| ID | Verification Check | Expected Result | Status | Evidence / Notes |
|---|---|---|---|---|
| BFV-001 | Reproduce the original bug steps | Original defect no longer occurs | Not Run | — |
| BFV-002 | Repeat the affected action | Behavior remains stable | Not Run | — |
| BFV-003 | Refresh and repeat the workflow | Fix remains effective | Not Run | — |
| BFV-004 | Logout/login and repeat where applicable | Correct behavior persists | Not Run | — |
| BFV-005 | Verify saved or updated data | Data remains correct | Not Run | — |

## Negative Testing

| ID | Verification Check | Expected Result | Status | Evidence / Notes |
|---|---|---|---|---|
| BFV-006 | Perform the action using invalid input | Validation works correctly | Not Run | — |
| BFV-007 | Repeat the action rapidly | No unintended duplicate behavior occurs | Not Run | — |
| BFV-008 | Interrupt the workflow where applicable | Application handles interruption safely | Not Run | — |

## Related Regression Testing

Identify functionality that could have been affected by the fix.

| ID | Related Area | Regression Check | Status | Evidence / Notes |
|---|---|---|---|---|
| BFV-009 | Related Workflow A | Verify existing functionality still works | Not Run | — |
| BFV-010 | Related Workflow B | Verify related data remains correct | Not Run | — |
| BFV-011 | Permissions | Verify authorization remains correct | Not Run | — |
| BFV-012 | API / Integration | Verify related backend or integration behavior | Not Run | — |
| BFV-013 | UI | Verify affected UI remains usable | Not Run | — |

## Cross-Browser / Device Verification

Where relevant, verify the fix across supported environments.

| Environment | Status | Notes |
|---|---|---|
| Chrome Desktop | Not Run | — |
| Firefox Desktop | Not Run | — |
| Edge Desktop | Not Run | — |
| Mobile Web | Not Run | — |

## Verification Result

Select the appropriate result after testing:

- **Passed** — Original issue is fixed and related regression checks pass.
- **Failed** — Original issue still occurs.
- **Reopened** — Fix is incomplete or the same defect remains reproducible.
- **Blocked** — Verification cannot be completed because of another issue or environment limitation.
- **Pending** — Additional information or testing is required.

## New Regression Issues

Document any new defects discovered while verifying the fix.

- **New Bug ID:** —
- **Description:** —
- **Severity:** —
- **Status:** —

## QA Notes

Add any observations, limitations, environment details, or follow-up requirements here.

## Final Verification Summary

After execution, summarize:

- Original defect status
- Fix verification result
- Related regression result
- New defects discovered
- Blocked or pending items
- Evidence collected

> This is a fictional bug-fix verification template created for portfolio demonstration purposes. No real employer, customer, or production information is included.
