# BUG-006 — API Creates Duplicate Records When Request Is Retried

## Bug ID
BUG-006

## Title
API creates duplicate records when the same create request is retried after a timeout.

## Environment
- Platform: API
- Tool: Postman
- Environment: Test / Staging
- API Version: Sample v1
- Build: Sample Build 1.0

## Severity
High

## Priority
High

## Preconditions
- A valid test user exists.
- A valid authentication token is available.
- The user has permission to create the record.
- The create endpoint is available in the test environment.

## Steps to Reproduce

1. Send a valid POST request to create a new record.
2. Simulate a delayed response or client-side timeout after the request reaches the server.
3. Retry the same request using the same test data.
4. Send a GET request to retrieve the created records.
5. Review the returned records.

## Expected Result
The API should handle the retry according to its duplicate-prevention/idempotency requirements.

Only one intended record should exist when the retry represents the same operation.

## Actual Result
Two identical records are created from the original request and the retry.

Both records receive separate IDs even though they originated from the same intended operation.

## Reproducibility
5/5 — Always

## Evidence
- API request/response: Not included — sample portfolio report
- Postman screenshot: Not included — sample portfolio report
- Server logs: Not included — sample portfolio report

## Additional Notes
This issue can result in duplicate business records when users or clients retry requests after timeouts or uncertain network states.

The same behavior should be checked for other create or transaction endpoints where duplicate processing could affect data integrity.

> This is a fictional bug report created for portfolio demonstration purposes. No real API credentials, tokens, endpoints, customer data, or company information is included.
