# Dashboard, Tables & Data Management Test Cases

## Scope
Dashboard metrics, widgets, tables, CRUD operations, pagination, sorting, filtering, bulk actions, data accuracy, permissions, refresh, and error-handling testing for SaaS and business applications.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| DASH-001 | Dashboard loads successfully | 1. Login<br>2. Open Dashboard | Valid user | Dashboard loads without errors and expected widgets are displayed | — | Not Run | High | — | Smoke |
| DASH-002 | Dashboard metrics accuracy | 1. Note known underlying records<br>2. Open Dashboard<br>3. Compare metrics | Known dataset | Dashboard metrics match underlying data | — | Not Run | High | — | Data accuracy |
| DASH-003 | Dashboard after new record creation | 1. Note current metric<br>2. Create qualifying record<br>3. Return to Dashboard | New record | Relevant metric/widget updates according to requirements | — | Not Run | High | — | Integration |
| DASH-004 | Dashboard after record deletion | 1. Note current metric<br>2. Delete qualifying record<br>3. Check Dashboard | Existing record | Relevant metric updates correctly | — | Not Run | High | — | Integration |
| DASH-005 | Dashboard empty state | 1. Login with account containing no applicable data<br>2. Open Dashboard | Empty account | Correct empty state is displayed without broken widgets | — | Not Run | Medium | — | Empty state |
| DASH-006 | Dashboard widget navigation | 1. Click dashboard widget/link | Existing data | Correct corresponding page/list opens | — | Not Run | Medium | — | Navigation |
| DASH-007 | Dashboard date-range filter | 1. Select date range<br>2. Review metrics | Known date range | Dashboard displays data belonging to selected period | — | Not Run | High | — | Filter |
| DASH-008 | Dashboard refresh | 1. Change underlying data<br>2. Refresh Dashboard | Updated data | Latest expected data is displayed | — | Not Run | High | — | Data freshness |
| DASH-009 | Dashboard loading state | 1. Open Dashboard under slower response conditions | N/A | Appropriate loading state is displayed | — | Not Run | Medium | — | UI |
| DASH-010 | Dashboard service failure | 1. Open Dashboard while data request fails | N/A | Appropriate error/retry state is shown without false data | — | Not Run | High | — | Error handling |
| TABLE-001 | Table loads records | 1. Open records page | Existing records | Table displays expected records | — | Not Run | High | — | Positive |
| TABLE-002 | Table empty state | 1. Open table with no records | Empty dataset | Correct empty state is displayed | — | Not Run | Medium | — | Empty state |
| TABLE-003 | Table column data accuracy | 1. Open table<br>2. Compare row with source record | Known record | Values appear under correct columns and match source data | — | Not Run | High | — | Data accuracy |
| TABLE-004 | Sort table ascending | 1. Click sortable column<br>2. Select/trigger ascending order | Multiple records | Records appear in correct ascending order | — | Not Run | Medium | — | Sorting |
| TABLE-005 | Sort table descending | 1. Trigger descending order | Multiple records | Records appear in correct descending order | — | Not Run | Medium | — | Sorting |
| TABLE-006 | Filter table | 1. Apply supported filter | Known filter | Only matching records are displayed | — | Not Run | High | — | Filter |
| TABLE-007 | Search table | 1. Enter known record value in search | Existing record | Matching record is returned | — | Not Run | High | — | Search |
| TABLE-008 | Search table with no result | 1. Search nonexistent value | xyz123nonexistent | Correct no-results state is displayed | — | Not Run | Medium | — | Negative |
| TABLE-009 | Combined table filters | 1. Apply multiple filters | Multiple criteria | Results satisfy selected filter combination | — | Not Run | High | — | Combined filters |
| TABLE-010 | Clear table filters | 1. Apply filters<br>2. Clear filters | Active filters | Filters reset and full eligible dataset returns | — | Not Run | Medium | — | Filter |
| TABLE-011 | Table pagination next page | 1. Open multi-page table<br>2. Click Next | Large dataset | Next page displays correct records | — | Not Run | Medium | — | Pagination |
| TABLE-012 | Table pagination previous page | 1. Open page 2<br>2. Click Previous | Large dataset | Previous page displays correctly | — | Not Run | Medium | — | Pagination |
| TABLE-013 | Change rows per page | 1. Change page-size setting | 10 → 25 | Number of displayed rows follows selected setting | — | Not Run | Medium | — | Pagination |
| TABLE-014 | No duplicate records across pages | 1. Review IDs across multiple pages | Large dataset | Records are not unintentionally duplicated | — | Not Run | High | — | Data integrity |
| TABLE-015 | Open record from table | 1. Click a row/record action | Existing record | Correct record details open | — | Not Run | High | — | Navigation |
| DATA-001 | Create new record | 1. Click Add/Create<br>2. Enter valid data<br>3. Save | Valid record | One new record is created successfully | — | Not Run | High | — | CRUD |
| DATA-002 | New record appears in list | 1. Create record<br>2. Return to table/list | New record | Newly created record appears according to refresh/sync requirements | — | Not Run | High | — | CRUD |
| DATA-003 | View record details | 1. Open existing record | Existing record | Correct complete record data is displayed | — | Not Run | High | — | CRUD |
| DATA-004 | Edit existing record | 1. Open record<br>2. Edit value<br>3. Save | Updated value | Correct record is updated | — | Not Run | High | — | CRUD |
| DATA-005 | Edited data updates table | 1. Edit record<br>2. Return to table | Updated record | Updated value appears correctly in list/table | — | Not Run | High | — | Data consistency |
| DATA-006 | Delete record | 1. Select existing record<br>2. Delete<br>3. Confirm | Existing record | Record is deleted according to requirements | — | Not Run | High | — | CRUD |
| DATA-007 | Cancel record deletion | 1. Select Delete<br>2. Cancel confirmation | Existing record | Record remains unchanged | — | Not Run | Medium | — | Negative |
| DATA-008 | Deleted record removed from list | 1. Delete record<br>2. Refresh/search list | Deleted record | Deleted record no longer appears according to deletion rules | — | Not Run | High | — | Data consistency |
| DATA-009 | Duplicate record handling | 1. Create record<br>2. Attempt duplicate according to unique-field rules | Duplicate data | Duplicate is handled according to business requirements | — | Not Run | High | — | Validation |
| DATA-010 | Bulk selection | 1. Select multiple records | Multiple records | Intended records are selected accurately | — | Not Run | Medium | — | Bulk action |
| DATA-011 | Select all records | 1. Use Select All | Multiple records | Correct applicable records are selected according to page/global rules | — | Not Run | Medium | — | Bulk action |
| DATA-012 | Bulk update | 1. Select multiple records<br>2. Apply supported bulk update | Multiple records | Only selected records are updated correctly | — | Not Run | High | — | Bulk action |
| DATA-013 | Bulk delete | 1. Select multiple records<br>2. Delete<br>3. Confirm | Multiple records | Selected records are deleted without affecting unselected records | — | Not Run | High | — | Bulk action |
| DATA-014 | Cancel bulk delete | 1. Select records<br>2. Start delete<br>3. Cancel | Multiple records | No selected records are deleted | — | Not Run | High | — | Negative |
| DATA-015 | Partial bulk-action failure | 1. Perform bulk action where one record cannot be processed | Mixed records | Application reports results accurately and does not falsely show full success | — | Not Run | High | — | Error handling |
| DATA-016 | Unauthorized record access | 1. Login as restricted user<br>2. Attempt to open restricted record | Restricted record | Access is denied and data is not exposed | — | Not Run | High | — | Authorization |
| DATA-017 | Unauthorized record edit | 1. Login without edit permission<br>2. Attempt update | Restricted user | Update is denied | — | Not Run | High | — | Authorization |
| DATA-018 | Unauthorized record deletion | 1. Login without delete permission<br>2. Attempt delete | Restricted user | Delete is denied | — | Not Run | High | — | Authorization |
| DATA-019 | Concurrent record update | 1. Open same record in two sessions<br>2. Update from Session A<br>3. Update from Session B | Same record | Concurrent edits follow defined conflict-handling rules without silent data corruption | — | Not Run | High | — | Concurrency |
| DATA-020 | Rapid repeated Save clicks | 1. Edit/create record<br>2. Rapidly click Save | Valid data | Only intended save operation occurs and duplicate records are avoided | — | Not Run | High | — | Duplicate prevention |
| DATA-021 | Network failure while saving | 1. Modify record<br>2. Save while request fails | Updated data | Error is displayed and false success is not shown | — | Not Run | High | — | Error handling |
| DATA-022 | Data persists after re-login | 1. Create/update record<br>2. Logout<br>3. Login again | Saved record | Successfully saved data remains correct | — | Not Run | High | — | Persistence |
| DATA-023 | Export table data | 1. Apply intended filters if applicable<br>2. Export | Existing dataset | Export contains correct permitted records and fields | — | Not Run | Medium | — | Export |
| DATA-024 | Export respects active filters | 1. Apply filter<br>2. Export | Filtered dataset | Export follows defined filtered-data behavior | — | Not Run | Medium | — | Export |
| DATA-025 | Restricted data excluded from export | 1. Login as limited user<br>2. Export data | Restricted user | Export does not expose unauthorized records/fields | — | Not Run | High | — | Security-focused |
| DASH-011 | Dashboard on mobile layout | 1. Open Dashboard on supported mobile viewport/device | Valid account | Widgets remain readable and usable | — | Not Run | Medium | — | Responsive |
| DASH-012 | Dashboard/table across supported environments | 1. Test core flows across supported browsers/devices | Valid account | Core functionality behaves consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
