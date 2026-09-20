# Roles & Permissions (RBAC) Test Cases

## Scope
Positive, negative, authorization, role-based access control, privilege, session, and security-focused testing for applications with multiple user roles.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| RBAC-001 | User can access permitted module | 1. Login as standard user<br>2. Open permitted module | Standard User | Module opens successfully | — | Not Run | High | — | Positive |
| RBAC-002 | User cannot access restricted module | 1. Login as standard user<br>2. Attempt to open admin-only module | Standard User | Access is denied and restricted content is not exposed | — | Not Run | High | — | Negative |
| RBAC-003 | Admin can access admin module | 1. Login as Admin<br>2. Open admin module | Admin | Admin module is accessible | — | Not Run | High | — | Positive |
| RBAC-004 | Restricted navigation item hidden | 1. Login as limited user<br>2. Inspect navigation | Limited User | Unauthorized menu/options are hidden or disabled according to requirements | — | Not Run | High | — | UI/Authorization |
| RBAC-005 | Direct URL access to restricted page | 1. Login as limited user<br>2. Enter restricted URL directly | Restricted URL | Server/application denies unauthorized access | — | Not Run | High | — | Security-focused |
| RBAC-006 | Restricted API/action through UI manipulation | 1. Login as limited user<br>2. Attempt restricted action by modifying accessible request/action | Limited User | Authorization is enforced server-side and action is rejected | — | Not Run | High | — | Security-focused |
| RBAC-007 | Read-only user views permitted data | 1. Login as read-only user<br>2. Open permitted record | Read-only User | User can view authorized data | — | Not Run | High | — | Positive |
| RBAC-008 | Read-only user attempts edit | 1. Login as read-only user<br>2. Attempt to modify record | Read-only User | Edit is unavailable or request is rejected | — | Not Run | High | — | Negative |
| RBAC-009 | Read-only user attempts delete | 1. Login as read-only user<br>2. Attempt delete action | Read-only User | Delete is unavailable or denied | — | Not Run | High | — | Negative |
| RBAC-010 | Editor can update permitted record | 1. Login as Editor<br>2. Modify permitted record<br>3. Save | Editor | Authorized update succeeds | — | Not Run | High | — | Positive |
| RBAC-011 | User cannot view another user's private data | 1. Login as User A<br>2. Attempt to access User B's private record | User B record ID | Access is denied and private data is not exposed | — | Not Run | High | — | Data isolation |
| RBAC-012 | User cannot modify another user's data | 1. Login as User A<br>2. Attempt update on User B's record | User B record ID | Unauthorized modification is rejected | — | Not Run | High | — | Security-focused |
| RBAC-013 | User cannot delete another user's data | 1. Login as User A<br>2. Attempt deletion of User B's record | User B record ID | Unauthorized deletion is rejected | — | Not Run | High | — | Security-focused |
| RBAC-014 | Admin assigns role | 1. Login as authorized Admin<br>2. Open user management<br>3. Assign role<br>4. Save | User + Role | Role is assigned successfully | — | Not Run | High | — | Admin |
| RBAC-015 | Unauthorized user attempts role assignment | 1. Login without role-management permission<br>2. Attempt to assign role | Standard User | Role assignment is denied | — | Not Run | High | — | Privilege escalation |
| RBAC-016 | Role change takes effect | 1. Change user's role<br>2. Refresh/re-login as required<br>3. Verify permissions | Updated Role | User receives permissions defined for the new role | — | Not Run | High | — | Integration |
| RBAC-017 | Removed permission no longer works | 1. Remove user's permission<br>2. Attempt previously allowed action | Updated permissions | Removed action is no longer permitted | — | Not Run | High | — | Authorization |
| RBAC-018 | Role downgrade during active session | 1. Login as privileged user<br>2. Downgrade role from another admin session<br>3. Attempt privileged action | Role downgrade | Application applies updated authorization according to defined session behavior | — | Not Run | High | — | Session |
| RBAC-019 | Role upgrade during active session | 1. Login as limited user<br>2. Upgrade role<br>3. Verify new access | Role upgrade | New permissions become available according to defined session behavior | — | Not Run | Medium | — | Session |
| RBAC-020 | Disabled user access | 1. Disable user account<br>2. Attempt login/access | Disabled User | Disabled user cannot gain unauthorized access | — | Not Run | High | — | Security-focused |
| RBAC-021 | Existing session after account disabled | 1. Login as user<br>2. Disable account from Admin session<br>3. Attempt protected action in existing session | Disabled User | Existing session follows defined security policy and unauthorized actions are prevented | — | Not Run | High | — | Session |
| RBAC-022 | Multi-role user permissions | 1. Assign multiple supported roles<br>2. Login<br>3. Verify allowed actions | Multiple Roles | Effective permissions match configured role-combination rules | — | Not Run | High | — | Edge case |
| RBAC-023 | Same action with different roles | 1. Perform action as Admin<br>2. Repeat as Editor<br>3. Repeat as Viewer | Admin / Editor / Viewer | Each role receives only its configured level of access | — | Not Run | High | — | Role comparison |
| RBAC-024 | Restricted action hidden but endpoint still protected | 1. Confirm restricted button is hidden<br>2. Attempt equivalent request directly | Limited User | Backend still rejects unauthorized request | — | Not Run | High | — | Security-focused |
| RBAC-025 | Organization/tenant data isolation | 1. Login under Organization A<br>2. Attempt to access Organization B data | Cross-tenant record | Data belonging to another tenant is inaccessible | — | Not Run | High | — | SaaS/Multi-tenant |
| RBAC-026 | Admin from one organization cannot manage another organization | 1. Login as Organization A Admin<br>2. Attempt to manage Organization B user | Cross-tenant user | Cross-organization management is denied | — | Not Run | High | — | SaaS/Multi-tenant |
| RBAC-027 | Permission persists after logout/login | 1. Update role/permission<br>2. Logout<br>3. Login again | Updated role | Correct permissions remain applied | — | Not Run | High | — | Persistence |
| RBAC-028 | Deleted role assigned to existing user | 1. Delete/deactivate role according to supported flow<br>2. Check affected user | Assigned role | Application handles affected users safely according to requirements | — | Not Run | Medium | — | Edge case |
| RBAC-029 | Unauthorized bulk action | 1. Login as limited user<br>2. Attempt restricted bulk update/delete | Multiple records | Unauthorized bulk action is rejected without partial changes | — | Not Run | High | — | Security-focused |
| RBAC-030 | Audit trail for permission changes | 1. Change user role/permission<br>2. Open audit/history view | Role change | Change is recorded with required audit information when audit logging is supported | — | Not Run | Medium | — | Audit |
