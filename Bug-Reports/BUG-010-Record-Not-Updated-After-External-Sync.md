# BUG-010 — Record Is Not Updated After External System Sync

## Bug ID
BUG-010

## Title
Updated record from external system is not synchronized with the application.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Integration: External CRM / Third-Party Service
- Build: Sample Build 1.0

## Severity
High

## Priority
High

## Preconditions
- Integration with the external test system is enabled.
- A test record exists in both systems.
- The records are correctly linked.
- Synchronization is active.

## Steps to Reproduce

1. Login to the external test system.
2. Open an existing synchronized record.
3. Update a field, such as the phone number.
4. Save the change.
5. Trigger synchronization or wait for the scheduled synchronization to complete.
6. Login to the application.
7. Open the corresponding record.
8. Review the updated field.

## Expected Result
The updated value from the external system should synchronize with the corresponding application record according to the configured synchronization rules.

## Actual Result
The synchronization completes without displaying an error, but the application continues to show the old value.

The updated value from the external system is not reflected in the application.

## Reproducibility
5/5 — Always

## Evidence
- Before/after screenshots: Not included — sample portfolio report
- Screen recording: Not included — sample portfolio report
- Sync logs: Not included — sample portfolio report

## Additional Notes
The synchronization status should not indicate success when an expected record update has failed.

The issue should also be checked for:
- Other synchronized fields.
- Multiple record updates.
- Newly created records.
- Deleted or archived records.
- Retry behavior after a failed synchronization.
- Synchronization in the opposite direction.

> This is a fictional bug report created for portfolio demonstration purposes. No real integration credentials, customer records, company information, or production data is included.
