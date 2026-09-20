# CRM / SaaS Business Application Test Cases

## Scope
Domain-specific lead, contact, company, deal, pipeline, task, activity, ownership, team collaboration, import/export, audit trail, tenant isolation, and SaaS business workflow testing.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| CRM-001 | Create lead | 1. Open Leads<br>2. Click Add Lead<br>3. Enter valid data<br>4. Save | Fictional lead | Lead is created successfully | — | Not Run | High | — | Lead |
| CRM-002 | Required lead fields | 1. Open Add Lead<br>2. Leave required fields blank<br>3. Save | Missing data | Lead is not created and validation is displayed | — | Not Run | High | — | Validation |
| CRM-003 | Duplicate lead detection | 1. Create lead<br>2. Attempt another with configured duplicate-identifying data | Duplicate email | Duplicate is detected/handled according to requirements | — | Not Run | High | — | Data integrity |
| CRM-004 | Edit lead | 1. Open existing lead<br>2. Modify permitted fields<br>3. Save | Updated lead data | Correct lead is updated | — | Not Run | High | — | CRUD |
| CRM-005 | Delete lead | 1. Open lead<br>2. Delete<br>3. Confirm | Existing lead | Lead is deleted according to requirements | — | Not Run | High | — | CRUD |
| CRM-006 | Cancel lead deletion | 1. Select Delete<br>2. Cancel confirmation | Existing lead | Lead remains unchanged | — | Not Run | Medium | — | Negative |
| CRM-007 | Search lead | 1. Open Leads<br>2. Search known lead | Known lead | Correct matching lead is returned | — | Not Run | High | — | Search |
| CRM-008 | Filter leads | 1. Apply lead status/owner filter | Known criteria | Only matching leads are displayed | — | Not Run | Medium | — | Filter |
| CRM-009 | Assign lead owner | 1. Open lead<br>2. Select permitted owner<br>3. Save | Team member | Lead is assigned to selected user | — | Not Run | High | — | Ownership |
| CRM-010 | Reassign lead owner | 1. Open assigned lead<br>2. Select another owner<br>3. Save | New owner | Ownership changes correctly and follows notification/audit rules | — | Not Run | High | — | Ownership |
| CRM-011 | Restricted user assigns lead | 1. Login without assignment permission<br>2. Attempt owner change | Restricted user | Unauthorized reassignment is denied | — | Not Run | High | — | RBAC |
| CRM-012 | Convert lead to contact | 1. Open qualified lead<br>2. Select Convert<br>3. Confirm | Qualified lead | Contact is created and lead state updates according to requirements | — | Not Run | High | — | Workflow |
| CRM-013 | Lead conversion preserves data | 1. Create lead with known fields<br>2. Convert<br>3. Open resulting record | Known lead | Required mapped data is preserved correctly | — | Not Run | High | — | Data integrity |
| CRM-014 | Duplicate conversion prevention | 1. Convert lead<br>2. Attempt conversion again | Converted lead | Duplicate contact/deal creation is prevented | — | Not Run | High | — | Duplicate prevention |
| CRM-015 | Create contact | 1. Open Contacts<br>2. Add valid contact<br>3. Save | Fictional contact | Contact is created successfully | — | Not Run | High | — | Contact |
| CRM-016 | Update contact | 1. Open contact<br>2. Modify data<br>3. Save | Updated contact | Changes persist correctly | — | Not Run | High | — | Contact |
| CRM-017 | Link contact to company | 1. Open contact<br>2. Select company<br>3. Save | Existing company | Contact is associated with correct company | — | Not Run | High | — | Relationship |
| CRM-018 | Remove contact-company relationship | 1. Open linked contact<br>2. Remove association<br>3. Save | Existing relationship | Relationship is removed without incorrectly deleting records | — | Not Run | Medium | — | Relationship |
| CRM-019 | Create company/account | 1. Open Companies<br>2. Add valid organization<br>3. Save | Fictional company | Company record is created | — | Not Run | High | — | Company |
| CRM-020 | Company related contacts | 1. Link multiple contacts<br>2. Open company | Multiple contacts | Correct related contacts are displayed | — | Not Run | High | — | Relationship |
| CRM-021 | Create deal/opportunity | 1. Open Deals<br>2. Add valid deal<br>3. Save | Fictional deal | Deal is created in correct pipeline/stage | — | Not Run | High | — | Deal |
| CRM-022 | Deal amount validation | 1. Enter invalid deal amount<br>2. Save | Invalid amount | Invalid value is rejected according to business rules | — | Not Run | High | — | Validation |
| CRM-023 | Move deal between pipeline stages | 1. Open pipeline<br>2. Move deal to another permitted stage | Existing deal | Deal stage updates correctly | — | Not Run | High | — | Pipeline |
| CRM-024 | Pipeline stage restrictions | 1. Attempt invalid/restricted stage transition | Restricted transition | Transition follows configured workflow rules | — | Not Run | High | — | Business rules |
| CRM-025 | Mark deal as won | 1. Open deal<br>2. Mark Won<br>3. Save | Existing deal | Deal status, pipeline metrics and related workflow update correctly | — | Not Run | High | — | Workflow |
| CRM-026 | Mark deal as lost | 1. Open deal<br>2. Mark Lost<br>3. Enter required reason if applicable | Existing deal | Deal is marked lost and required data is stored | — | Not Run | High | — | Workflow |
| CRM-027 | Pipeline value calculation | 1. Create deals with known values<br>2. Review pipeline total | Known amounts | Pipeline totals follow configured calculation rules | — | Not Run | High | — | Calculation |
| CRM-028 | Dashboard after deal update | 1. Note dashboard metric<br>2. Update qualifying deal<br>3. Review dashboard | Known deal | Relevant CRM metrics update correctly | — | Not Run | High | — | Integration |
| CRM-029 | Create task for lead/contact | 1. Open record<br>2. Add task<br>3. Save | Fictional task | Task is created and linked to correct record | — | Not Run | High | — | Task |
| CRM-030 | Assign task | 1. Create/open task<br>2. Assign team member | Team member | Task is assigned to intended user | — | Not Run | High | — | Task |
| CRM-031 | Complete task | 1. Open assigned task<br>2. Mark Complete | Existing task | Completion status and applicable timestamp/user information are recorded | — | Not Run | High | — | Task |
| CRM-032 | Overdue task | 1. Create task with past due date according to test setup<br>2. Review task list | Overdue task | Task is identified/handled according to overdue rules | — | Not Run | Medium | — | Task |
| CRM-033 | Task reminder | 1. Create task with reminder<br>2. Reach reminder time | Upcoming task | Reminder is sent/displayed to intended user | — | Not Run | Medium | — | Notification |
| CRM-034 | Add activity/note | 1. Open CRM record<br>2. Add note/activity<br>3. Save | Fictional note | Activity is recorded under correct record | — | Not Run | High | — | Activity |
| CRM-035 | Activity timeline order | 1. Create multiple dated activities<br>2. Review timeline | Multiple activities | Activities appear in correct defined chronological order | — | Not Run | Medium | — | Timeline |
| CRM-036 | Edit activity permissions | 1. Login as restricted user<br>2. Attempt to modify protected activity | Restricted activity | Edit is denied according to permissions | — | Not Run | High | — | RBAC |
| CRM-037 | Email activity associated with correct contact | 1. Send/log test email through supported integration<br>2. Open contact timeline | Fictional email | Email activity is associated with intended contact | — | Not Run | High | — | Integration |
| CRM-038 | Import valid contacts | 1. Open Import<br>2. Upload valid test file<br>3. Map fields<br>4. Import | Fictional CSV | Valid contacts are imported correctly | — | Not Run | High | — | Import |
| CRM-039 | Import invalid rows | 1. Upload file containing valid and invalid rows<br>2. Run import | Mixed test data | Invalid rows are handled/reported according to requirements without falsely importing them | — | Not Run | High | — | Import |
| CRM-040 | Import duplicate contacts | 1. Import records matching existing contacts | Duplicate test records | Duplicate handling follows configured merge/skip/create rules | — | Not Run | High | — | Data integrity |
| CRM-041 | Import field mapping | 1. Upload file<br>2. Map source columns<br>3. Import | Test CSV | Imported values appear in intended CRM fields | — | Not Run | High | — | Import |
| CRM-042 | Export CRM records | 1. Open record list<br>2. Export | Fictional dataset | Export contains correct permitted records and fields | — | Not Run | Medium | — | Export |
| CRM-043 | Export respects filters | 1. Apply filters<br>2. Export | Filtered records | Export follows configured filtered-data behavior | — | Not Run | Medium | — | Export |
| CRM-044 | Restricted fields excluded from export | 1. Login as limited user<br>2. Export records | Restricted user | Unauthorized fields/data are not exposed | — | Not Run | High | — | Security-focused |
| CRM-045 | Bulk assign records | 1. Select multiple records<br>2. Assign new owner | Multiple records | Only selected records receive correct owner | — | Not Run | High | — | Bulk action |
| CRM-046 | Bulk status update | 1. Select multiple records<br>2. Change supported status | Multiple records | Selected records update correctly | — | Not Run | High | — | Bulk action |
| CRM-047 | Bulk delete records | 1. Select records<br>2. Delete<br>3. Confirm | Multiple records | Only intended records are deleted | — | Not Run | High | — | Bulk action |
| CRM-048 | Partial bulk-action failure | 1. Perform bulk action containing one restricted/invalid record | Mixed records | Results accurately identify successes/failures without false full-success state | — | Not Run | High | — | Error handling |
| CRM-049 | Custom field creation | 1. Login with configuration permission<br>2. Create supported custom field | Test field | Custom field is created and available in configured locations | — | Not Run | Medium | — | SaaS |
| CRM-050 | Custom field data persistence | 1. Enter value in custom field<br>2. Save<br>3. Reopen record | Test value | Custom-field value persists correctly | — | Not Run | High | — | SaaS |
| CRM-051 | Required custom field | 1. Configure/use required custom field<br>2. Attempt save without value | Blank field | Save follows configured required-field validation | — | Not Run | High | — | Validation |
| CRM-052 | User role permissions | 1. Login with limited CRM role<br>2. Attempt restricted operation | Limited role | Only permitted actions/features are available | — | Not Run | High | — | RBAC |
| CRM-053 | Record-level access | 1. Login as user with limited record scope<br>2. Attempt unrelated record access | Restricted record | Record-level permissions are enforced | — | Not Run | High | — | Authorization |
| CRM-054 | Cross-tenant data isolation | 1. Login under Organization A<br>2. Attempt Organization B record access | Two organizations | Organization B CRM data is not exposed | — | Not Run | High | — | SaaS/Security |
| CRM-055 | Role change while session active | 1. Login as User A<br>2. Change User A permissions from authorized admin session<br>3. Retry restricted action | Updated role | Access reflects updated permissions according to session rules | — | Not Run | High | — | RBAC |
| CRM-056 | Audit trail for record update | 1. Update supported record<br>2. Review history/audit log | Known change | Actor, change and timestamp are recorded according to audit requirements | — | Not Run | High | — | Audit |
| CRM-057 | Audit trail for ownership change | 1. Reassign record<br>2. Review audit/history | Ownership change | Ownership change is recorded accurately | — | Not Run | High | — | Audit |
| CRM-058 | Concurrent CRM record edits | 1. Open same record in two sessions<br>2. Save conflicting changes | Same record | Conflict follows defined concurrency rules without silent data corruption | — | Not Run | High | — | Concurrency |
| CRM-059 | Network failure while saving record | 1. Edit record<br>2. Cause request failure<br>3. Save | Updated data | Error is shown and false success is not displayed | — | Not Run | High | — | Error handling |
| CRM-060 | Rapid repeated record creation | 1. Complete create form<br>2. Rapidly click Save | Valid record | Unintended duplicate records are prevented | — | Not Run | High | — | Duplicate prevention |
| CRM-061 | Archived record | 1. Archive supported record<br>2. Review active list/search | Existing record | Archived record follows configured visibility/access rules | — | Not Run | Medium | — | Lifecycle |
| CRM-062 | Restore archived record | 1. Open archived records<br>2. Restore record | Archived record | Record returns to intended active state | — | Not Run | Medium | — | Lifecycle |
| CRM-063 | CRM notification recipient | 1. Trigger ownership/task/deal notification<br>2. Review recipients | Known event | Notification reaches intended users only | — | Not Run | High | — | Notification |
| CRM-064 | Deleted user with assigned records | 1. Assign records to test user<br>2. Deactivate/delete user according to supported flow | Test user | Assigned records follow configured reassignment/retention rules without unintended loss | — | Not Run | High | — | Edge case |
| CRM-065 | CRM across supported environments | 1. Test core CRM workflows across supported browsers/devices | Test accounts | Core workflows and data remain consistent | — | Not Run | Medium | — | Cross-platform |
