# API Testing Test Cases

## Scope
Functional, CRUD, authentication, authorization, request validation, response validation, status codes, pagination, filtering, idempotency, rate limiting, error handling, data integrity, and security-focused API testing.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| API-001 | Valid GET request | 1. Send GET request to valid endpoint<br>2. Inspect response | Valid endpoint | Request succeeds with expected status code and response data | — | Not Run | High | — | Positive |
| API-002 | GET existing resource by ID | 1. Send GET with valid resource ID | Existing ID | Correct resource is returned | — | Not Run | High | — | CRUD |
| API-003 | GET nonexistent resource | 1. Send GET with nonexistent ID | Invalid/nonexistent ID | Appropriate not-found response is returned | — | Not Run | High | — | Negative |
| API-004 | Valid POST request | 1. Send POST with valid payload<br>2. Inspect response | Valid JSON payload | Resource is created successfully with expected response | — | Not Run | High | — | CRUD |
| API-005 | Verify POST-created data | 1. Create resource using POST<br>2. Retrieve it using GET | Valid payload | Retrieved resource matches successfully created data | — | Not Run | High | — | Data integrity |
| API-006 | POST missing required field | 1. Remove required field from payload<br>2. Send POST | Incomplete payload | Request is rejected with appropriate validation response | — | Not Run | High | — | Validation |
| API-007 | POST invalid field type | 1. Send incorrect data type in field | String instead of number | Request is rejected according to API validation rules | — | Not Run | High | — | Validation |
| API-008 | POST empty payload | 1. Send POST with empty body | `{}` | API returns appropriate validation/error response | — | Not Run | High | — | Negative |
| API-009 | POST duplicate unique value | 1. Create resource<br>2. Repeat with same unique value | Duplicate email/ID | Duplicate is handled according to API/business rules | — | Not Run | High | — | Data integrity |
| API-010 | Valid PUT request | 1. Send PUT for existing resource with valid payload | Existing ID + valid payload | Resource is updated according to PUT semantics | — | Not Run | High | — | CRUD |
| API-011 | Valid PATCH request | 1. Send PATCH for one supported field | Existing ID + partial payload | Requested field is updated without unintended changes | — | Not Run | High | — | CRUD |
| API-012 | Update nonexistent resource | 1. Send PUT/PATCH using nonexistent ID | Nonexistent ID | Appropriate not-found/error response is returned | — | Not Run | High | — | Negative |
| API-013 | Invalid update payload | 1. Send PUT/PATCH with invalid field value | Invalid payload | Update is rejected and existing data remains valid | — | Not Run | High | — | Validation |
| API-014 | Valid DELETE request | 1. Create/select resource<br>2. Send DELETE | Existing ID | Resource is deleted according to API requirements | — | Not Run | High | — | CRUD |
| API-015 | Verify deleted resource | 1. Delete resource<br>2. Send GET for same ID | Deleted ID | Resource is no longer retrievable according to deletion rules | — | Not Run | High | — | Data integrity |
| API-016 | Delete nonexistent resource | 1. Send DELETE for nonexistent ID | Nonexistent ID | API returns defined not-found/idempotent deletion response | — | Not Run | Medium | — | Negative |
| API-017 | Request without authentication | 1. Call protected endpoint without token | No token | Request is rejected with appropriate authentication response | — | Not Run | High | — | Authentication |
| API-018 | Request with valid token | 1. Authenticate<br>2. Call protected endpoint | Valid token | Request succeeds according to user's permissions | — | Not Run | High | — | Authentication |
| API-019 | Request with invalid token | 1. Call protected endpoint using invalid token | Invalid token | Request is rejected | — | Not Run | High | — | Authentication |
| API-020 | Request with expired token | 1. Use expired token on protected endpoint | Expired token | Request is rejected and authentication flow follows requirements | — | Not Run | High | — | Authentication |
| API-021 | Missing authorization header | 1. Remove Authorization header<br>2. Send protected request | N/A | API rejects unauthenticated request | — | Not Run | High | — | Authentication |
| API-022 | User accesses unauthorized resource | 1. Authenticate as User A<br>2. Request User B private resource | User B resource ID | Access is denied without exposing protected data | — | Not Run | High | — | Authorization |
| API-023 | Restricted role calls admin endpoint | 1. Authenticate as standard user<br>2. Call admin endpoint | Standard-user token | Request is denied according to RBAC rules | — | Not Run | High | — | RBAC |
| API-024 | Admin calls permitted endpoint | 1. Authenticate as Admin<br>2. Call admin endpoint | Admin token | Authorized request succeeds | — | Not Run | High | — | RBAC |
| API-025 | Cross-tenant resource access | 1. Authenticate under Tenant A<br>2. Request Tenant B resource | Cross-tenant ID | API denies access and does not expose Tenant B data | — | Not Run | High | — | SaaS/Security |
| API-026 | Invalid HTTP method | 1. Send unsupported HTTP method to endpoint | Unsupported method | API returns appropriate method-not-allowed/error response | — | Not Run | Medium | — | Negative |
| API-027 | Invalid endpoint | 1. Send request to nonexistent route | Invalid route | Appropriate not-found response is returned | — | Not Run | Medium | — | Negative |
| API-028 | Malformed JSON | 1. Send malformed JSON body | Invalid JSON | Request is rejected with appropriate client-error response | — | Not Run | High | — | Validation |
| API-029 | Unsupported Content-Type | 1. Send request with unsupported Content-Type | Invalid Content-Type | API rejects request according to requirements | — | Not Run | Medium | — | Headers |
| API-030 | Missing Content-Type | 1. Send body without required Content-Type header | Valid body | API follows defined header-validation behavior | — | Not Run | Medium | — | Headers |
| API-031 | Response Content-Type | 1. Send valid request<br>2. Inspect response headers | Valid request | Response uses expected Content-Type | — | Not Run | Medium | — | Response validation |
| API-032 | Response schema validation | 1. Send valid request<br>2. Validate response fields/types | Known schema | Response matches documented schema | — | Not Run | High | — | Contract |
| API-033 | Required response fields | 1. Send request<br>2. Inspect response | Valid request | Required response properties are present | — | Not Run | High | — | Contract |
| API-034 | Sensitive fields excluded | 1. Request user/resource data<br>2. Inspect response | Valid authenticated request | Passwords, secrets and unauthorized sensitive fields are not exposed | — | Not Run | High | — | Security-focused |
| API-035 | Correct success status code | 1. Perform successful API operation<br>2. Inspect status | Valid request | Correct documented 2xx status is returned | — | Not Run | High | — | Status code |
| API-036 | Correct validation error status | 1. Send invalid request<br>2. Inspect status | Invalid payload | Correct documented client-error status is returned | — | Not Run | High | — | Status code |
| API-037 | Error response structure | 1. Trigger validation/error response<br>2. Inspect body | Invalid request | Error response follows defined structure and contains useful non-sensitive information | — | Not Run | High | — | Error handling |
| API-038 | Internal error does not expose implementation details | 1. Trigger controlled server-error scenario<br>2. Inspect response | Controlled failure | Response does not expose sensitive stack traces/secrets | — | Not Run | High | — | Security-focused |
| API-039 | Pagination first page | 1. Request paginated endpoint with first-page parameters | page=1 | Correct first set of records and pagination metadata are returned | — | Not Run | Medium | — | Pagination |
| API-040 | Pagination next page | 1. Request page 1<br>2. Request page 2 | Multiple pages | Correct next set of records is returned | — | Not Run | Medium | — | Pagination |
| API-041 | Pagination last page | 1. Request final valid page | Last page | Remaining records and correct metadata are returned | — | Not Run | Medium | — | Boundary |
| API-042 | Invalid pagination value | 1. Send invalid page/limit value | page=-1 / limit=invalid | API handles invalid pagination according to requirements | — | Not Run | Medium | — | Validation |
| API-043 | Excessive page-size request | 1. Request page size above configured maximum | Large limit | API enforces configured maximum or rejects request appropriately | — | Not Run | Medium | — | Boundary |
| API-044 | Duplicate records across pages | 1. Retrieve consecutive pages<br>2. Compare resource IDs | Multiple pages | Pagination does not unintentionally duplicate records | — | Not Run | High | — | Data integrity |
| API-045 | API filtering | 1. Send request with valid filter | Known filter | Only records matching filter are returned | — | Not Run | High | — | Filtering |
| API-046 | Multiple API filters | 1. Send request with multiple filters | Multiple criteria | Response matches configured combined-filter logic | — | Not Run | High | — | Filtering |
| API-047 | API sorting ascending | 1. Request supported ascending sort | sort=asc | Records are returned in correct order | — | Not Run | Medium | — | Sorting |
| API-048 | API sorting descending | 1. Request supported descending sort | sort=desc | Records are returned in correct descending order | — | Not Run | Medium | — | Sorting |
| API-049 | Invalid filter parameter | 1. Send unsupported/invalid filter | Invalid filter | API handles invalid parameter according to contract | — | Not Run | Medium | — | Negative |
| API-050 | Unknown query parameter | 1. Add unsupported query parameter<br>2. Send request | unknown=value | API follows documented behavior without unintended effects | — | Not Run | Low | — | Edge case |
| API-051 | Minimum numeric boundary | 1. Send minimum allowed value | Minimum value | Valid minimum boundary is accepted | — | Not Run | Medium | — | Boundary |
| API-052 | Maximum numeric boundary | 1. Send maximum allowed value | Maximum value | Valid maximum boundary is accepted | — | Not Run | Medium | — | Boundary |
| API-053 | Value below minimum | 1. Send value below supported minimum | Below minimum | Request is rejected according to validation rules | — | Not Run | Medium | — | Boundary |
| API-054 | Value above maximum | 1. Send value above supported maximum | Above maximum | Request is rejected according to validation rules | — | Not Run | Medium | — | Boundary |
| API-055 | Null value handling | 1. Send null for supported/unsupported field | `"field": null` | Null value follows API schema/business rules | — | Not Run | Medium | — | Validation |
| API-056 | Empty string handling | 1. Send empty string in required field | `""` | Empty value is handled according to validation rules | — | Not Run | Medium | — | Validation |
| API-057 | Extra fields in request | 1. Add undocumented field to payload<br>2. Send request | Extra property | API follows documented handling of unknown fields | — | Not Run | Medium | — | Contract |
| API-058 | Repeated identical GET requests | 1. Send same GET request multiple times | Same request | Read-only requests do not create unintended data changes | — | Not Run | Medium | — | Idempotency |
| API-059 | Duplicate payment/order POST protection | 1. Send same transaction request repeatedly using supported idempotency mechanism | Same transaction | Duplicate processing is prevented according to API design | — | Not Run | High | — | Idempotency |
| API-060 | Idempotency key reuse | 1. Send transaction request with idempotency key<br>2. Repeat same request with same key | Same key | API does not unintentionally create duplicate transaction | — | Not Run | High | — | Payments |
| API-061 | Rate limit behavior | 1. Send requests up to configured limit<br>2. Exceed limit | Repeated requests | API enforces documented rate limits | — | Not Run | High | — | Rate limiting |
| API-062 | Rate-limit response headers | 1. Trigger/approach rate limit<br>2. Inspect headers | Repeated requests | Applicable rate-limit/retry information follows API contract | — | Not Run | Medium | — | Headers |
| API-063 | Retry after rate limit | 1. Trigger rate limit<br>2. Wait configured period<br>3. Retry | Valid request | Requests resume according to documented rate-limit behavior | — | Not Run | Medium | — | Recovery |
| API-064 | Request timeout | 1. Trigger/simulate slow downstream response | Valid request | Timeout is handled according to API contract without incorrect success | — | Not Run | High | — | Error handling |
| API-065 | Downstream service failure | 1. Trigger controlled dependency failure<br>2. Send request | Valid request | API returns appropriate failure response and preserves data consistency | — | Not Run | High | — | Integration |
| API-066 | Database/data persistence after POST | 1. Create resource<br>2. Retrieve it in a separate request | Valid payload | Successfully created data persists correctly | — | Not Run | High | — | Data integrity |
| API-067 | Failed request does not partially save data | 1. Send request designed to fail validation/transaction<br>2. Retrieve/check resource state | Invalid transaction | No unintended partial data is committed | — | Not Run | High | — | Data integrity |
| API-068 | Concurrent update requests | 1. Send two updates against same resource near-simultaneously | Same resource | Concurrency follows defined locking/version/conflict rules without silent corruption | — | Not Run | High | — | Concurrency |
| API-069 | Response time | 1. Send representative API requests<br>2. Measure response time | Common requests | Response time meets defined performance requirements | — | Not Run | Medium | — | Performance |
| API-070 | API version compatibility | 1. Call supported API version endpoint<br>2. Verify response | Supported API version | Endpoint behaves according to documented version contract | — | Not Run | Medium | — | Versioning |
