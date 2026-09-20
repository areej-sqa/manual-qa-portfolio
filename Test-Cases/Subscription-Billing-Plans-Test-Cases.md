# Subscription, Billing & Plans Test Cases

## Scope
Subscription lifecycle, free trials, upgrades, downgrades, renewals, cancellations, billing cycles, failed payments, invoices, plan permissions, pricing, and edge-case testing for SaaS applications.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| SUB-001 | Subscribe to paid plan | 1. Open Plans<br>2. Select paid plan<br>3. Enter valid payment details<br>4. Confirm | Valid plan + payment | Subscription is activated and correct plan is assigned | — | Not Run | High | — | Positive |
| SUB-002 | Correct plan price displayed | 1. Open pricing page<br>2. Select plan<br>3. Open checkout | Known plan | Price remains consistent across pricing and checkout | — | Not Run | High | — | Data accuracy |
| SUB-003 | Monthly billing plan | 1. Select monthly plan<br>2. Complete subscription | Monthly plan | Correct monthly billing cycle is applied | — | Not Run | High | — | Billing |
| SUB-004 | Annual billing plan | 1. Select annual plan<br>2. Complete subscription | Annual plan | Correct annual billing cycle is applied | — | Not Run | High | — | Billing |
| SUB-005 | Monthly/annual price switch | 1. Toggle billing frequency | Monthly / Annual | Displayed prices and billing labels update correctly | — | Not Run | Medium | — | UI |
| SUB-006 | Start free trial | 1. Select trial-eligible plan<br>2. Start trial | Eligible user | Trial activates with correct plan and duration | — | Not Run | High | — | Trial |
| SUB-007 | Trial expiration | 1. Start trial<br>2. Reach configured expiration | Trial account | Account transitions according to configured post-trial rules | — | Not Run | High | — | Trial |
| SUB-008 | Trial user subscribes before expiration | 1. Start trial<br>2. Purchase plan before trial ends | Trial user | Subscription transition and billing follow configured rules | — | Not Run | High | — | Trial |
| SUB-009 | Ineligible user attempts second trial | 1. Use account that already consumed trial<br>2. Attempt new trial | Existing user | Additional trial is allowed/blocked according to business rules | — | Not Run | High | — | Business rules |
| SUB-010 | Upgrade subscription | 1. Subscribe to lower plan<br>2. Select higher plan<br>3. Confirm upgrade | Basic → Pro | Plan upgrades according to configured billing/proration rules | — | Not Run | High | — | Upgrade |
| SUB-011 | Upgraded features available | 1. Upgrade plan<br>2. Access newly included feature | Higher plan | Features included in upgraded plan become accessible | — | Not Run | High | — | Authorization |
| SUB-012 | Upgrade pricing/proration | 1. Upgrade during billing cycle<br>2. Review charge/invoice | Mid-cycle upgrade | Charge/credit matches configured proration rules | — | Not Run | High | — | Billing |
| SUB-013 | Downgrade subscription | 1. Subscribe to higher plan<br>2. Select lower plan<br>3. Confirm | Pro → Basic | Downgrade is scheduled/applied according to requirements | — | Not Run | High | — | Downgrade |
| SUB-014 | Feature access after downgrade | 1. Downgrade plan<br>2. Reach effective downgrade time<br>3. Access premium feature | Lower plan | Features no longer included are restricted appropriately | — | Not Run | High | — | Authorization |
| SUB-015 | Existing data after downgrade | 1. Create premium-plan data<br>2. Downgrade<br>3. Review data | Premium data | Existing data follows defined downgrade/retention behavior | — | Not Run | High | — | Data integrity |
| SUB-016 | Cancel subscription | 1. Open Billing<br>2. Cancel subscription<br>3. Confirm | Active subscription | Cancellation is recorded according to requirements | — | Not Run | High | — | Cancellation |
| SUB-017 | Cancel cancellation flow | 1. Start cancellation<br>2. Cancel/close confirmation | Active subscription | Subscription remains active | — | Not Run | Medium | — | Negative |
| SUB-018 | Access until billing-period end | 1. Cancel subscription configured to end at period end<br>2. Use premium feature before end date | Cancelled subscription | Access remains available until configured expiration | — | Not Run | High | — | Cancellation |
| SUB-019 | Access after subscription expiration | 1. Let cancelled subscription expire<br>2. Attempt premium feature | Expired subscription | Premium access is removed according to plan rules | — | Not Run | High | — | Authorization |
| SUB-020 | Reactivate cancelled subscription | 1. Cancel subscription<br>2. Reactivate before expiration when supported | Cancelled subscription | Subscription returns to active state correctly | — | Not Run | High | — | Recovery |
| SUB-021 | Automatic renewal | 1. Maintain active subscription until renewal date | Active subscription | Renewal is processed according to configured billing rules | — | Not Run | High | — | Renewal |
| SUB-022 | Renewal payment succeeds | 1. Reach renewal with valid payment method | Valid payment | Subscription renews and new billing period is recorded | — | Not Run | High | — | Renewal |
| SUB-023 | Renewal payment fails | 1. Reach renewal using failing payment method | Declined payment | Subscription enters correct failed-payment/grace state | — | Not Run | High | — | Payment failure |
| SUB-024 | Retry failed renewal | 1. Cause renewal failure<br>2. Update/fix payment method<br>3. Retry | Valid replacement payment | Subscription recovers according to configured retry rules | — | Not Run | High | — | Recovery |
| SUB-025 | Grace period after failed payment | 1. Cause renewal failure<br>2. Check account during grace period | Failed renewal | Access follows configured grace-period rules | — | Not Run | High | — | Billing |
| SUB-026 | Subscription after repeated payment failures | 1. Allow configured retries to fail | Repeated failure | Subscription transitions to intended final state without incorrect access | — | Not Run | High | — | Billing |
| SUB-027 | Update payment method | 1. Open Billing<br>2. Add/select new payment method<br>3. Save | Valid payment method | New method is saved and used according to requirements | — | Not Run | High | — | Payment method |
| SUB-028 | Remove active/default payment method | 1. Attempt to remove default method | Default method | Application follows configured rules and prevents invalid billing state | — | Not Run | High | — | Edge case |
| SUB-029 | Expired payment method | 1. Use expired payment method for billing | Expired card | Appropriate billing/payment failure handling occurs | — | Not Run | High | — | Negative |
| SUB-030 | Invoice generated | 1. Complete successful subscription payment<br>2. Open billing history | Successful payment | Correct invoice/receipt is generated | — | Not Run | High | — | Invoice |
| SUB-031 | Invoice amount accuracy | 1. Complete payment<br>2. Review invoice | Known plan/charge | Invoice amount, discounts, taxes and total match transaction | — | Not Run | High | — | Data accuracy |
| SUB-032 | Download invoice | 1. Open billing history<br>2. Download invoice | Existing invoice | Correct invoice downloads successfully | — | Not Run | Medium | — | Invoice |
| SUB-033 | Billing history | 1. Perform subscription transactions<br>2. Open billing history | Multiple transactions | Transactions appear once with correct amounts, dates and statuses | — | Not Run | High | — | Data accuracy |
| SUB-034 | Valid subscription discount | 1. Select plan<br>2. Apply eligible discount<br>3. Subscribe | Valid discount | Correct discounted amount is charged | — | Not Run | High | — | Promotion |
| SUB-035 | Expired subscription discount | 1. Enter expired discount<br>2. Apply | Expired code | Discount is rejected | — | Not Run | Medium | — | Negative |
| SUB-036 | Subscription limits enforced | 1. Subscribe to limited plan<br>2. Reach configured usage/user/storage limit<br>3. Attempt additional action | Plan limit | Limit is enforced according to plan rules | — | Not Run | High | — | SaaS |
| SUB-037 | Upgrade after reaching plan limit | 1. Reach current plan limit<br>2. Upgrade<br>3. Retry action | Higher plan | Higher plan limits/features become available correctly | — | Not Run | High | — | SaaS |
| SUB-038 | Direct access to higher-plan feature | 1. Login on lower plan<br>2. Open premium feature URL directly | Lower plan | Premium feature remains restricted | — | Not Run | High | — | Security-focused |
| SUB-039 | Subscription associated with correct account | 1. Purchase plan as User A<br>2. Login as User B | Two accounts | Subscription and billing information remain associated with intended account | — | Not Run | High | — | Data isolation |
| SUB-040 | Cross-organization billing isolation | 1. Login under Organization A<br>2. Attempt to access Organization B billing data | Two organizations | Billing data from another organization is not exposed | — | Not Run | High | — | SaaS/Authorization |
| SUB-041 | Unauthorized user changes subscription | 1. Login without billing permission<br>2. Attempt upgrade/cancel | Restricted user | Subscription modification is denied | — | Not Run | High | — | RBAC |
| SUB-042 | Subscription status after refresh | 1. Change subscription<br>2. Refresh/reopen Billing | Updated subscription | Correct subscription status persists | — | Not Run | High | — | Persistence |
| SUB-043 | Duplicate subscription submission | 1. Start subscription<br>2. Rapidly click confirmation multiple times | Valid payment | Duplicate subscriptions/charges are prevented | — | Not Run | High | — | Duplicate prevention |
| SUB-044 | Network failure during subscription | 1. Submit subscription<br>2. Interrupt connection during processing | Valid payment | Final state is reconciled without duplicate charge/subscription | — | Not Run | High | — | Error handling |
| SUB-045 | Billing across supported environments | 1. Test core subscription flows across supported browsers/devices | Valid account | Billing and subscription functionality behaves consistently | — | Not Run | Medium | — | Cross-browser/device |
