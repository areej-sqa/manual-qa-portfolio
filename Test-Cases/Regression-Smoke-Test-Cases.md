# Regression & Smoke Test Cases

## Scope
Reusable smoke and regression test cases for validating critical application functionality after deployments, bug fixes, configuration changes, releases, and major feature updates.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| REG-001 | Application launches successfully | 1. Open application | N/A | Application loads without critical errors | — | Not Run | High | — | Smoke |
| REG-002 | Homepage/dashboard loads | 1. Login if required<br>2. Open main page/dashboard | Test account | Main page loads with expected core content | — | Not Run | High | — | Smoke |
| REG-003 | User login | 1. Open Login<br>2. Enter valid credentials<br>3. Submit | Valid test account | User logs in successfully | — | Not Run | High | — | Smoke |
| REG-004 | Invalid login | 1. Enter invalid credentials<br>2. Submit | Invalid password | Login is rejected appropriately | — | Not Run | High | — | Regression |
| REG-005 | User logout | 1. Login<br>2. Logout | Test account | Session ends and protected content becomes inaccessible | — | Not Run | High | — | Smoke |
| REG-006 | Forgot password flow | 1. Open Forgot Password<br>2. Submit registered test email | Fictional email | Reset flow starts according to requirements | — | Not Run | High | — | Regression |
| REG-007 | User registration | 1. Open Signup<br>2. Enter valid unique data<br>3. Submit | Fictional user | Account is created according to registration requirements | — | Not Run | High | — | Smoke |
| REG-008 | Protected page access | 1. Logout<br>2. Open protected URL | Protected URL | Unauthorized access is denied | — | Not Run | High | — | Regression |
| REG-009 | Primary navigation | 1. Login<br>2. Open each critical navigation item | N/A | Each item opens intended page without critical errors | — | Not Run | High | — | Smoke |
| REG-010 | Browser Back/Forward navigation | 1. Navigate between core pages<br>2. Use Back/Forward | N/A | Navigation behaves correctly without invalid application state | — | Not Run | Medium | — | Regression |
| REG-011 | Create core record | 1. Open primary record module<br>2. Enter valid data<br>3. Save | Fictional record | Record is created successfully | — | Not Run | High | — | Smoke |
| REG-012 | View created record | 1. Create record<br>2. Open it | Known record | Correct saved information is displayed | — | Not Run | High | — | Smoke |
| REG-013 | Edit core record | 1. Open existing record<br>2. Modify permitted field<br>3. Save | Updated data | Changes persist correctly | — | Not Run | High | — | Smoke |
| REG-014 | Delete core record | 1. Open test record<br>2. Delete<br>3. Confirm | Disposable test record | Record is removed according to requirements | — | Not Run | High | — | Regression |
| REG-015 | Required-field validation | 1. Open core form<br>2. Leave required field blank<br>3. Submit | Missing required data | Submission is prevented and validation appears | — | Not Run | High | — | Regression |
| REG-016 | Cancel form | 1. Open create/edit form<br>2. Enter changes<br>3. Cancel | Test data | Unsaved changes follow configured cancel behavior | — | Not Run | Medium | — | Regression |
| REG-017 | Search core records | 1. Open search<br>2. Search known record | Known keyword | Correct matching result is returned | — | Not Run | High | — | Smoke |
| REG-018 | Search with no results | 1. Search nonexistent value | Unique nonexistent text | Correct empty/no-results state is displayed | — | Not Run | Medium | — | Regression |
| REG-019 | Apply common filter | 1. Open record list<br>2. Apply filter | Known criteria | Only matching records are displayed | — | Not Run | High | — | Regression |
| REG-020 | Clear filters | 1. Apply filter<br>2. Clear filters | N/A | Default/unfiltered dataset is restored | — | Not Run | Medium | — | Regression |
| REG-021 | Sort table/list | 1. Open sortable list<br>2. Sort supported column | Known dataset | Records appear in correct order | — | Not Run | Medium | — | Regression |
| REG-022 | Pagination | 1. Open dataset spanning multiple pages<br>2. Navigate pages | Large test dataset | Correct records load without unexpected duplication/missing entries | — | Not Run | Medium | — | Regression |
| REG-023 | Dashboard key metric accuracy | 1. Open dashboard<br>2. Compare metric with known test data | Known dataset | Metric reflects correct data according to requirements | — | Not Run | High | — | Regression |
| REG-024 | Dashboard updates after record creation | 1. Note relevant metric<br>2. Create qualifying record<br>3. Refresh/review dashboard | Test record | Related dashboard data updates correctly | — | Not Run | High | — | Integration |
| REG-025 | User profile loads | 1. Login<br>2. Open Profile | Test account | Correct profile information is displayed | — | Not Run | Medium | — | Smoke |
| REG-026 | Update profile | 1. Open Profile<br>2. Change permitted value<br>3. Save | Fictional profile data | Updated value persists | — | Not Run | Medium | — | Regression |
| REG-027 | Settings persist | 1. Change supported setting<br>2. Save<br>3. Refresh/re-login | Test setting | Saved preference remains according to requirements | — | Not Run | Medium | — | Regression |
| REG-028 | Role-based navigation | 1. Login using different test roles<br>2. Compare permitted navigation | Admin and standard user | Each role sees only permitted functionality | — | Not Run | High | — | RBAC |
| REG-029 | Restricted direct URL | 1. Login as restricted user<br>2. Open restricted URL | Restricted role | Access is denied | — | Not Run | High | — | RBAC |
| REG-030 | File upload | 1. Open supported upload feature<br>2. Upload valid test file | Safe supported file | File uploads and associates with correct record | — | Not Run | High | — | Regression |
| REG-031 | File download | 1. Open existing test attachment<br>2. Download | Test file | Correct file downloads successfully | — | Not Run | Medium | — | Regression |
| REG-032 | Notification generation | 1. Trigger event that creates notification<br>2. Review intended recipient | Test event | Correct notification is generated | — | Not Run | High | — | Integration |
| REG-033 | Transactional email | 1. Trigger supported email event<br>2. Check test inbox | Fictional recipient | Expected email is generated with correct core information | — | Not Run | High | — | Integration |
| REG-034 | Deep link from notification/email | 1. Open generated notification/email<br>2. Select action link | Test link | Correct destination opens according to authentication rules | — | Not Run | High | — | Integration |
| REG-035 | Add item to cart | 1. Open available product<br>2. Add to cart | Test product | Correct item is added | — | Not Run | High | — | E-commerce smoke |
| REG-036 | Cart total | 1. Add known products/quantities<br>2. Open cart | Known prices | Cart total is calculated correctly | — | Not Run | High | — | E-commerce |
| REG-037 | Checkout | 1. Add item<br>2. Open checkout<br>3. Enter valid test details | Test order | Checkout proceeds successfully to expected stage | — | Not Run | High | — | E-commerce smoke |
| REG-038 | Successful test payment | 1. Complete checkout using supported test payment method | Test payment | Payment/order state updates correctly | — | Not Run | High | — | Payment |
| REG-039 | Failed test payment | 1. Use provider test scenario configured to fail | Failed test payment | Failure is handled without false paid status | — | Not Run | High | — | Payment |
| REG-040 | Duplicate payment prevention | 1. Submit payment<br>2. Rapidly trigger payment action repeatedly | Test transaction | Unintended duplicate payment/order is prevented | — | Not Run | High | — | Payment |
| REG-041 | API health/core request | 1. Send valid request to critical test endpoint | Valid request | Expected success response and data are returned | — | Not Run | High | — | API smoke |
| REG-042 | Protected API endpoint | 1. Call protected endpoint without authentication | Protected endpoint | Request is rejected | — | Not Run | High | — | API |
| REG-043 | Third-party integration | 1. Trigger critical integration action<br>2. Review result | Test integration | Integration completes according to requirements | — | Not Run | High | — | Integration |
| REG-044 | Data synchronization | 1. Create/update test source record<br>2. Trigger/wait for sync<br>3. Check destination | Fictional record | Intended data synchronizes correctly | — | Not Run | High | — | Integration |
| REG-045 | Mobile app launch | 1. Install/open supported mobile build | Test device | App launches without critical failure | — | Not Run | High | — | Mobile smoke |
| REG-046 | Mobile login | 1. Open app<br>2. Enter valid credentials<br>3. Login | Test account | User reaches expected authenticated screen | — | Not Run | High | — | Mobile smoke |
| REG-047 | Mobile background/foreground | 1. Open authenticated app<br>2. Background<br>3. Return | Test account | App resumes with valid expected state | — | Not Run | High | — | Mobile |
| REG-048 | Mobile network recovery | 1. Use core feature<br>2. Disconnect network<br>3. Restore network | Test device | Application handles loss/recovery without incorrect data state | — | Not Run | High | — | Mobile |
| REG-049 | Critical page on supported browsers | 1. Open critical flows on supported browsers | Test account | Core functionality behaves consistently | — | Not Run | High | — | Cross-browser |
| REG-050 | Responsive critical workflow | 1. Test core workflow on supported viewport sizes | Desktop/mobile viewport | Workflow remains usable and functional | — | Not Run | Medium | — | Responsive |
| REG-051 | Existing data after deployment | 1. Open known pre-release test records after deployment | Known records | Existing data remains available and accurate | — | Not Run | High | — | Deployment |
| REG-052 | Newly created data after deployment | 1. Create new record after deployment<br>2. Reopen it | Test record | New data saves and retrieves correctly | — | Not Run | High | — | Deployment |
| REG-053 | Database-backed update persists after refresh | 1. Modify supported record<br>2. Refresh/re-login | Updated record | Saved changes remain correct | — | Not Run | High | — | Data integrity |
| REG-054 | Fixed bug retest | 1. Reproduce original reported steps after fix | Bug-specific test data | Previously reported issue no longer occurs | — | Not Run | High | — | Retest |
| REG-055 | Related functionality after bug fix | 1. Identify functions related to fixed area<br>2. Execute relevant regression cases | Related test data | Fix does not break related functionality | — | Not Run | High | — | Regression |
| REG-056 | Loading state | 1. Trigger data-loading action | Test dataset | Appropriate loading state appears and resolves correctly | — | Not Run | Medium | — | UI |
| REG-057 | Network error handling | 1. Start supported action<br>2. Cause controlled network failure | Test data | Error is handled without false success or unintended data corruption | — | Not Run | High | — | Error handling |
| REG-058 | Refresh during core workflow | 1. Start supported workflow<br>2. Refresh at defined step | Test workflow | Application follows expected state/recovery behavior | — | Not Run | Medium | — | Edge case |
| REG-059 | Rapid repeated submission | 1. Complete core form<br>2. Rapidly click Submit/Save | Valid data | Unintended duplicate records/actions are prevented | — | Not Run | High | — | Edge case |
| REG-060 | Critical end-to-end workflow | 1. Login<br>2. Create/use primary record<br>3. Complete key business action<br>4. Verify resulting state | Fictional test data | Full critical business workflow completes successfully with correct final data | — | Not Run | High | — | E2E / Smoke |
