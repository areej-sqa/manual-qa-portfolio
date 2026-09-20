# FinTech / Banking Application Test Cases

## Scope
Domain-specific account, balance, money transfer, beneficiary, transaction, payment, OTP, limits, statements, authorization, data integrity, and financial security test cases using fictional test data only.

> These are fictional portfolio test cases and do not contain real financial, banking, card, or customer information.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| FIN-001 | Account dashboard displays correct balance | 1. Login<br>2. Open account dashboard<br>3. Compare with known test balance | Fictional account | Displayed balance matches expected account balance | — | Not Run | High | — | Data accuracy |
| FIN-002 | Available and current balance | 1. Open account details<br>2. Review balances | Known test account | Available/current balances follow configured financial rules | — | Not Run | High | — | Data accuracy |
| FIN-003 | Account transaction history | 1. Open transaction history | Account with known transactions | Correct transactions, amounts, dates and statuses are displayed | — | Not Run | High | — | Transactions |
| FIN-004 | Transaction detail view | 1. Select known transaction | Fictional transaction | Correct transaction details are displayed | — | Not Run | High | — | Transactions |
| FIN-005 | Unauthorized account access | 1. Login as User A<br>2. Attempt to access User B account | User B account reference | Access is denied and financial data is not exposed | — | Not Run | High | — | Authorization |
| FIN-006 | Add valid beneficiary | 1. Open beneficiaries<br>2. Enter valid fictional details<br>3. Confirm | Fictional beneficiary | Beneficiary is added according to verification requirements | — | Not Run | High | — | Beneficiary |
| FIN-007 | Beneficiary required-field validation | 1. Leave required field blank<br>2. Submit | Incomplete data | Beneficiary is not created and validation is displayed | — | Not Run | High | — | Validation |
| FIN-008 | Invalid beneficiary account details | 1. Enter invalid account information<br>2. Submit | Invalid fictional account | Invalid beneficiary details are rejected according to requirements | — | Not Run | High | — | Negative |
| FIN-009 | Duplicate beneficiary | 1. Add beneficiary<br>2. Attempt to add same beneficiary again | Duplicate test data | Duplicate is handled according to business rules | — | Not Run | Medium | — | Data integrity |
| FIN-010 | Delete beneficiary | 1. Open beneficiary<br>2. Delete<br>3. Confirm | Existing beneficiary | Beneficiary is removed successfully according to requirements | — | Not Run | Medium | — | Beneficiary |
| FIN-011 | Transfer valid amount | 1. Select source account<br>2. Select beneficiary<br>3. Enter valid amount<br>4. Confirm | Valid amount | Transfer succeeds and correct transaction is created | — | Not Run | High | — | Transfer |
| FIN-012 | Transfer zero amount | 1. Enter 0 as transfer amount<br>2. Submit | 0 | Transfer is prevented with appropriate validation | — | Not Run | High | — | Boundary |
| FIN-013 | Transfer negative amount | 1. Enter negative amount when input permits<br>2. Submit | -100 | Invalid transfer is prevented | — | Not Run | High | — | Boundary |
| FIN-014 | Transfer amount above available balance | 1. Enter amount exceeding available balance<br>2. Submit | Balance + amount | Transfer is rejected according to insufficient-funds rules | — | Not Run | High | — | Negative |
| FIN-015 | Transfer minimum amount boundary | 1. Enter configured minimum transfer amount<br>2. Submit | Minimum amount | Valid minimum amount is handled correctly | — | Not Run | Medium | — | Boundary |
| FIN-016 | Transfer above transaction limit | 1. Enter amount exceeding configured transaction limit<br>2. Submit | Over-limit amount | Transfer is blocked or additional required flow is applied | — | Not Run | High | — | Limits |
| FIN-017 | Daily transfer limit | 1. Perform transfers up to daily limit<br>2. Attempt another transfer | Daily limit exceeded | Configured daily limit is enforced | — | Not Run | High | — | Limits |
| FIN-018 | Decimal amount handling | 1. Enter supported decimal amount<br>2. Submit | 100.50 | Amount is processed with correct currency precision | — | Not Run | High | — | Calculation |
| FIN-019 | Excess decimal precision | 1. Enter amount with more decimal places than currency supports | 100.555 | Amount is rejected/rounded according to documented financial rules | — | Not Run | High | — | Boundary |
| FIN-020 | Transfer fee calculation | 1. Create transfer requiring fee<br>2. Review summary | Known fee scenario | Correct fee and total debit are displayed | — | Not Run | High | — | Calculation |
| FIN-021 | Transfer confirmation details | 1. Prepare transfer<br>2. Review confirmation before final submission | Known transfer | Source, beneficiary, amount, fee and total are correct | — | Not Run | High | — | Data accuracy |
| FIN-022 | Cancel transfer before confirmation | 1. Prepare transfer<br>2. Cancel before final confirmation | Valid transfer | No transfer/debit is created | — | Not Run | High | — | Negative |
| FIN-023 | Successful transfer updates balance | 1. Note balance<br>2. Complete transfer<br>3. Recheck balance | Known amount | Balance reflects successful transfer and applicable fees correctly | — | Not Run | High | — | Data integrity |
| FIN-024 | Failed transfer does not incorrectly debit balance | 1. Note balance<br>2. Cause transfer failure<br>3. Recheck balance | Failed transaction | Account is not incorrectly permanently debited | — | Not Run | High | — | Critical |
| FIN-025 | Duplicate transfer prevention | 1. Submit transfer<br>2. Rapidly trigger confirmation multiple times | Valid transfer | Only intended transaction is processed | — | Not Run | High | — | Duplicate prevention |
| FIN-026 | Network failure during transfer | 1. Submit transfer<br>2. Interrupt network while processing | Valid transfer | Final transaction state is reconciled without duplicate debit | — | Not Run | High | — | Error handling |
| FIN-027 | Retry after uncertain transfer state | 1. Interrupt response after submission<br>2. Restore network<br>3. Check/retry according to flow | Valid transfer | User can determine transaction status without accidentally duplicating payment | — | Not Run | High | — | Idempotency |
| FIN-028 | OTP sent for protected transaction | 1. Initiate transaction requiring OTP | Fictional account | OTP is sent through configured channel | — | Not Run | High | — | Authentication |
| FIN-029 | Valid OTP | 1. Initiate protected transaction<br>2. Enter valid OTP | Valid test OTP | Verification succeeds and transaction continues | — | Not Run | High | — | Authentication |
| FIN-030 | Invalid OTP | 1. Enter incorrect OTP | Invalid OTP | Verification fails and transaction is not authorized | — | Not Run | High | — | Negative |
| FIN-031 | Expired OTP | 1. Request OTP<br>2. Wait until expiration<br>3. Submit | Expired OTP | OTP is rejected | — | Not Run | High | — | Security-focused |
| FIN-032 | OTP reuse | 1. Successfully use OTP<br>2. Attempt to reuse it | Used OTP | Reuse is rejected according to requirements | — | Not Run | High | — | Security-focused |
| FIN-033 | OTP attempt limit | 1. Enter incorrect OTP repeatedly | Invalid OTP | Configured attempt/lockout controls are enforced | — | Not Run | High | — | Security-focused |
| FIN-034 | Resend OTP | 1. Request OTP<br>2. Select Resend | Test account | New OTP follows configured resend/expiration rules | — | Not Run | High | — | Authentication |
| FIN-035 | Transaction status pending | 1. Initiate transaction configured for delayed processing<br>2. Open history | Pending transaction | Transaction is clearly shown as pending and not falsely marked completed | — | Not Run | High | — | Transaction state |
| FIN-036 | Pending transaction becomes successful | 1. Create pending transaction<br>2. Complete processing<br>3. Refresh history | Pending transaction | Status transitions to successful exactly as intended | — | Not Run | High | — | Integration |
| FIN-037 | Pending transaction becomes failed | 1. Create pending transaction<br>2. Cause downstream failure<br>3. Refresh | Pending transaction | Final failed status and balance handling are correct | — | Not Run | High | — | Integration |
| FIN-038 | Transaction reference uniqueness | 1. Perform multiple transactions<br>2. Compare references | Multiple transactions | Transactions receive appropriate unique references | — | Not Run | High | — | Data integrity |
| FIN-039 | Transaction receipt | 1. Complete successful transaction<br>2. Open receipt | Successful transaction | Receipt contains correct non-sensitive transaction information | — | Not Run | Medium | — | Receipt |
| FIN-040 | Download account statement | 1. Select supported statement period<br>2. Download | Fictional account | Correct statement is generated/downloaded | — | Not Run | High | — | Statement |
| FIN-041 | Statement transaction accuracy | 1. Download statement<br>2. Compare known transactions | Known test transactions | Statement values and transaction records match account history | — | Not Run | High | — | Data accuracy |
| FIN-042 | Statement date range | 1. Select specific period<br>2. Generate statement | Known date range | Statement contains transactions for correct period according to rules | — | Not Run | High | — | Date filtering |
| FIN-043 | Unauthorized statement download | 1. Login as unauthorized user<br>2. Attempt another user's statement | Restricted account | Download is denied | — | Not Run | High | — | Privacy |
| FIN-044 | Sensitive account number masking | 1. Open account/transaction screens | Fictional account | Sensitive account identifiers are masked according to requirements | — | Not Run | High | — | Security-focused |
| FIN-045 | Sensitive card/payment information masking | 1. Open supported card/payment screen | Fictional test data | Sensitive payment details are not unnecessarily exposed | — | Not Run | High | — | Security-focused |
| FIN-046 | Session timeout | 1. Login<br>2. Remain inactive until configured timeout<br>3. Attempt protected action | Test account | Session expires and reauthentication is required | — | Not Run | High | — | Security-focused |
| FIN-047 | Browser Back after logout | 1. View financial data<br>2. Logout<br>3. Press Back | Protected page | Previously authenticated financial information is not accessible | — | Not Run | High | — | Security-focused |
| FIN-048 | Concurrent balance-changing transactions | 1. Submit supported transactions concurrently against same test balance | Fictional account | Transactions follow defined concurrency rules without incorrect balance calculations | — | Not Run | High | — | Concurrency |
| FIN-049 | Audit trail for financial action | 1. Perform supported financial/account action<br>2. Review audit/history when available | Known action | Required action, actor, timestamp and status information are recorded | — | Not Run | High | — | Audit |
| FIN-050 | FinTech flows across supported environments | 1. Test core account/transaction flows across supported browsers/devices | Fictional account | Core functionality and financial data remain consistent across supported environments | — | Not Run | Medium | — | Cross-platform |
