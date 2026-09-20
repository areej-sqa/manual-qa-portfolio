# SaaS Application Exploratory Testing Session

## Session ID
EXP-004

## Feature / Area
Workspace, User Management, Roles, and Business Records

## Objective
Explore a SaaS application's core business workflows to identify functional, permission, data-isolation, usability, integration, and state-management issues.

## Test Charter
Explore workspace management from the perspective of users with different roles.

Focus on user invitations, permissions, record ownership, CRUD operations, direct URL access, organization isolation, concurrent changes, and session behavior.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- Build: Sample Build 1.0

## Test Data
- Organization A
- Organization B
- Admin user
- Standard user
- Read-only user
- Invited user
- Sample business records
- Sample upload file

## Areas Explored

- Workspace management
- User invitations
- Roles and permissions
- Record creation
- Record editing
- Record deletion
- Search and filters
- Ownership
- Direct URL access
- Multi-tenant isolation
- Session handling
- Concurrent updates
- Audit history

## Scenarios Tested

1. Login as an administrator.
2. Create a new business record.
3. Edit the record.
4. Search for the record.
5. Filter records by status.
6. Invite a new user.
7. Accept the invitation.
8. Assign a standard user role.
9. Verify standard-user permissions.
10. Change the user to read-only access.
11. Attempt to edit a record as the read-only user.
12. Attempt to delete a record as the read-only user.
13. Copy a restricted record URL.
14. Open the URL while logged in as a restricted user.
15. Login to Organization A.
16. Attempt to access a record belonging to Organization B.
17. Search for Organization B's record from Organization A.
18. Change record ownership.
19. Remove a user who owns existing records.
20. Verify behavior of the user's existing records.
21. Open the same record in two browser tabs.
22. Edit the record from both tabs.
23. Save conflicting changes.
24. Archive a record.
25. Search for the archived record.
26. Restore the archived record.
27. Delete a record.
28. Attempt to open the deleted record using its old URL.
29. Change a user's role while that user has an active session.
30. Verify access after the role change.
31. Logout and attempt to reopen an authenticated URL.
32. Review audit history for record changes.

## Findings

### Finding 1 — Role Change Requires Refresh
A user's restricted action remains visible until the page is manually refreshed after their role is changed.

**Type:** Permissions / State Management  
**Status:** Requires further investigation

### Finding 2 — Direct URL Authorization
A read-only user cannot edit a restricted record by opening the edit URL directly.

**Type:** Authorization  
**Status:** Working as expected

### Finding 3 — Tenant Isolation
Records belonging to Organization B are not returned in Organization A's search results.

**Type:** Data Isolation  
**Status:** Working as expected

### Finding 4 — Concurrent Editing
When the same record is edited from two tabs, the last saved update silently overwrites the previous update.

**Type:** Data Integrity / Concurrency  
**Status:** Requires clarification

### Finding 5 — Audit History
Record creation and update actions are displayed with the correct user and timestamp.

**Type:** Audit Trail  
**Status:** Working as expected

## Defects Identified

Potential issues requiring further investigation:

- Permission-related UI does not update immediately after a role change.
- Concurrent edits may overwrite another user's changes without warning.

These findings should be confirmed against product requirements before final defect classification.

## Questions / Clarifications

- Should permission changes take effect immediately during an active session?
- Should users receive a warning when another user has modified the same record?
- What should happen to records owned by a removed user?
- Should archived records appear in global search?

## Risks

- Delayed permission updates may confuse users about their current access.
- Concurrent edits may result in lost business data.
- Incorrect tenant isolation could expose another organization's information.
- Ownership changes may affect workflows, notifications, or reporting.

## Follow-Up Testing

Recommended follow-up testing:

- Verify role changes at API level.
- Test tenant isolation through direct API requests.
- Test additional user-role combinations.
- Test simultaneous updates from separate devices.
- Verify ownership behavior after user removal.
- Test audit history for delete, archive, and restore actions.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered workspace management, user invitations, permissions, CRUD operations, ownership, multi-tenant isolation, concurrency, session behavior, and audit history.

Potential permission-state and concurrent-editing issues were identified, while direct URL authorization, tenant isolation, and audit tracking behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. No real customer, organization, company, or production data is included.
