# Checkout & Payment Test Cases

## Scope
Positive, negative, validation, payment failure, retry, duplicate-payment, pricing, security-focused, and edge-case testing for e-commerce and SaaS checkout flows.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| PAY-001 | Successful checkout with valid payment | 1. Add item/plan<br>2. Open Checkout<br>3. Enter valid details<br>4. Pay | Valid payment data | Payment succeeds, order/subscription is created, and confirmation is displayed | — | Not Run | High | — | Positive |
| PAY-002 | Checkout with empty required fields | 1. Open Checkout<br>2. Leave required fields blank<br>3. Submit | Blank fields | Required-field validations are displayed and payment is not initiated | — | Not Run | High | — | Validation |
| PAY-003 | Invalid card number | 1. Enter invalid card number<br>2. Complete other fields<br>3. Pay | Invalid card | Payment is not completed and appropriate feedback is displayed | — | Not Run | High | — | Negative |
| PAY-004 | Expired card | 1. Enter expired card details<br>2. Pay | Expired card | Payment is rejected with appropriate feedback | — | Not Run | High | — | Negative |
| PAY-005 | Invalid expiry date | 1. Enter invalid expiry value<br>2. Submit | Invalid month/year | Validation is displayed and payment is prevented | — | Not Run | Medium | — | Validation |
| PAY-006 | Invalid CVV/security code | 1. Enter invalid CVV<br>2. Pay | Invalid CVV | Payment is rejected or validation is displayed according to payment-provider behavior | — | Not Run | High | — | Negative |
| PAY-007 | Declined payment | 1. Enter payment method configured to decline<br>2. Pay | Declined test payment | Order/subscription is not incorrectly marked paid and user receives appropriate feedback | — | Not Run | High | — | Payment failure |
| PAY-008 | Insufficient funds | 1. Attempt payment using supported insufficient-funds test scenario | Insufficient-funds test data | Payment failure is handled correctly without creating a paid order | — | Not Run | High | — | Payment failure |
| PAY-009 | Payment authentication required | 1. Checkout using payment requiring additional authentication<br>2. Complete authentication | Authentication-required payment | Authentication flow completes and payment status is updated correctly | — | Not Run | High | — | 3DS/Auth |
| PAY-010 | Payment authentication cancelled | 1. Start authentication-required payment<br>2. Cancel authentication | N/A | Payment is not marked successful and checkout provides appropriate feedback | — | Not Run | High | — | Negative |
| PAY-011 | User cancels payment | 1. Start payment<br>2. Cancel before completion | N/A | No successful charge/order is incorrectly recorded | — | Not Run | High | — | Negative |
| PAY-012 | Double-click Pay button | 1. Enter valid details<br>2. Rapidly click Pay multiple times | Valid payment | Only one intended payment/order is processed | — | Not Run | High | — | Duplicate prevention |
| PAY-013 | Refresh during payment processing | 1. Submit payment<br>2. Refresh while processing | Valid payment | Application safely resolves final payment state without duplicate charge | — | Not Run | High | — | Edge case |
| PAY-014 | Browser Back during payment | 1. Start checkout/payment<br>2. Press browser Back | N/A | Checkout remains consistent and duplicate/incorrect payment is not created | — | Not Run | High | — | Navigation |
| PAY-015 | Network failure before payment submission | 1. Complete checkout<br>2. Disconnect/fail request before submission | Valid payment | Error is handled and user is not incorrectly charged | — | Not Run | High | — | Error handling |
| PAY-016 | Network failure after payment submission | 1. Submit valid payment<br>2. Simulate connection loss while result is pending | Valid payment | Application reconciles payment state and avoids duplicate charging on retry | — | Not Run | High | — | Critical edge case |
| PAY-017 | Retry failed payment | 1. Cause payment failure<br>2. Retry with valid method | Failed then valid payment | Retry succeeds without duplicate order/charge | — | Not Run | High | — | Recovery |
| PAY-018 | Cart/order total calculation | 1. Add multiple products<br>2. Open Checkout | Multiple products | Subtotal and final total are calculated correctly | — | Not Run | High | — | E-commerce |
| PAY-019 | Quantity change updates total | 1. Change product quantity<br>2. Review checkout total | Quantity 1 → 2 | Price and total update correctly | — | Not Run | High | — | E-commerce |
| PAY-020 | Remove item during checkout | 1. Add multiple items<br>2. Remove one item | Multiple products | Removed item and totals update correctly | — | Not Run | Medium | — | E-commerce |
| PAY-021 | Valid discount/promo code | 1. Enter valid promo code<br>2. Apply | Valid code | Correct discount is applied to eligible items/order | — | Not Run | High | — | Promotion |
| PAY-022 | Invalid promo code | 1. Enter invalid code<br>2. Apply | Invalid code | Discount is not applied and appropriate feedback is displayed | — | Not Run | Medium | — | Negative |
| PAY-023 | Expired promo code | 1. Enter expired code<br>2. Apply | Expired code | Expired discount is rejected | — | Not Run | Medium | — | Negative |
| PAY-024 | Promo code eligibility rules | 1. Add ineligible item/order<br>2. Apply restricted code | Restricted code | Promotion follows configured eligibility rules | — | Not Run | High | — | Business rules |
| PAY-025 | Tax calculation | 1. Enter applicable billing/shipping details<br>2. Review total | Taxable location | Tax is calculated according to configured rules | — | Not Run | High | — | Calculation |
| PAY-026 | Shipping fee calculation | 1. Enter delivery address<br>2. Select shipping option | Valid address | Correct shipping fee is included in total | — | Not Run | High | — | E-commerce |
| PAY-027 | Currency displayed consistently | 1. Browse product/plan<br>2. Open checkout<br>3. Complete payment | Supported currency | Currency and charged amount remain consistent throughout the flow | — | Not Run | High | — | FinTech/E-commerce |
| PAY-028 | Price changes before checkout completion | 1. Add item<br>2. Change underlying price according to test setup<br>3. Continue checkout | Updated price | Application handles price change according to defined business rules | — | Not Run | High | — | Edge case |
| PAY-029 | Out-of-stock item at checkout | 1. Add available item<br>2. Make item unavailable according to test setup<br>3. Checkout | Out-of-stock product | Purchase is prevented or adjusted according to inventory rules | — | Not Run | High | — | E-commerce |
| PAY-030 | Successful order confirmation | 1. Complete successful payment | Valid payment | Correct order ID, amount, items/plan and status are displayed | — | Not Run | High | — | Positive |
| PAY-031 | Confirmation email/receipt | 1. Complete successful payment<br>2. Check email/receipt | Valid email | Correct confirmation/receipt is generated when supported | — | Not Run | High | — | Integration |
| PAY-032 | Failed payment does not generate paid receipt | 1. Cause payment failure<br>2. Check order/email history | Failed payment | No successful-payment receipt is generated | — | Not Run | High | — | Data integrity |
| PAY-033 | Order history after successful payment | 1. Complete payment<br>2. Open order/billing history | Successful order | Transaction appears once with correct details and status | — | Not Run | High | — | Integration |
| PAY-034 | Guest checkout | 1. Checkout without account when supported<br>2. Enter required details<br>3. Pay | Guest details | Guest purchase completes according to requirements | — | Not Run | Medium | — | E-commerce |
| PAY-035 | Saved payment method | 1. Login<br>2. Select saved method<br>3. Complete checkout | Saved method | Payment can be completed without exposing full sensitive payment data | — | Not Run | High | — | Security-focused |
| PAY-036 | Add new payment method | 1. Open payment methods<br>2. Add valid method<br>3. Save | Valid payment method | Method is added and represented safely according to requirements | — | Not Run | High | — | Payment method |
| PAY-037 | Remove saved payment method | 1. Open payment methods<br>2. Remove method<br>3. Confirm | Saved method | Method is removed according to requirements | — | Not Run | Medium | — | Payment method |
| PAY-038 | Unauthorized user accesses another user's order | 1. Login as User A<br>2. Attempt to access User B order | Another user's order ID | Access is denied and order/payment data is not exposed | — | Not Run | High | — | Authorization |
| PAY-039 | Sensitive payment data exposure | 1. Complete checkout<br>2. Inspect visible URL/loggable UI areas | Payment data | Full sensitive payment credentials are not exposed in URLs or inappropriate UI locations | — | Not Run | High | — | Security-focused |
| PAY-040 | Checkout across supported environments | 1. Complete checkout on supported browsers/devices | Valid payment | Checkout behaves consistently across supported environments | — | Not Run | Medium | — | Cross-browser/device |
