# E-commerce Product, Cart & Wishlist Test Cases

## Scope
Product listing/detail, variants, pricing, inventory, cart, quantity, wishlist, guest/authenticated behavior, persistence, data integrity, and edge-case testing for e-commerce applications.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| ECOM-001 | Product listing loads | 1. Open product listing page | Existing products | Eligible products are displayed correctly | — | Not Run | High | — | Product |
| ECOM-002 | Product information accuracy | 1. Open product listing/detail<br>2. Review information | Known product | Name, price, image and other displayed information match product data | — | Not Run | High | — | Data accuracy |
| ECOM-003 | Open product details | 1. Click product from listing | Existing product | Correct product detail page opens | — | Not Run | High | — | Navigation |
| ECOM-004 | Product image gallery | 1. Open product<br>2. Navigate through images | Product with multiple images | Correct images load and gallery controls work | — | Not Run | Medium | — | UI |
| ECOM-005 | Product without image | 1. Open product configured without image | No-image product | Defined placeholder/fallback behavior is displayed | — | Not Run | Medium | — | Edge case |
| ECOM-006 | Product price accuracy | 1. Open product page<br>2. Compare displayed price with configured price | Known product | Correct price and currency are displayed | — | Not Run | High | — | Data accuracy |
| ECOM-007 | Discounted product price | 1. Open discounted product | Discounted product | Original/discounted prices follow configured pricing rules | — | Not Run | High | — | Pricing |
| ECOM-008 | Select product variant | 1. Open product<br>2. Select variant | Size/Color | Correct variant is selected and related data updates | — | Not Run | High | — | Variant |
| ECOM-009 | Variant-specific price | 1. Select different variants<br>2. Compare price | Multiple variants | Price updates according to selected variant | — | Not Run | High | — | Pricing |
| ECOM-010 | Variant-specific inventory | 1. Select available variant<br>2. Select unavailable variant | Multiple variants | Availability accurately reflects selected variant | — | Not Run | High | — | Inventory |
| ECOM-011 | Add product to cart | 1. Open product<br>2. Click Add to Cart | Available product | Correct product is added to cart | — | Not Run | High | — | Cart |
| ECOM-012 | Add selected variant to cart | 1. Select variant<br>2. Add to Cart | Selected variant | Cart contains the exact selected variant | — | Not Run | High | — | Cart |
| ECOM-013 | Required variant not selected | 1. Open variant product<br>2. Do not select required option<br>3. Add to Cart | N/A | Add is prevented and appropriate selection feedback is displayed | — | Not Run | High | — | Validation |
| ECOM-014 | Add multiple different products | 1. Add Product A<br>2. Add Product B<br>3. Open cart | Two products | Both products appear correctly | — | Not Run | High | — | Cart |
| ECOM-015 | Add same product multiple times | 1. Add same product repeatedly | Same product | Cart quantity/line-item behavior follows requirements | — | Not Run | High | — | Cart |
| ECOM-016 | Cart badge/count | 1. Add/remove items<br>2. Observe cart count | Multiple items | Cart count follows defined item/quantity counting rules | — | Not Run | Medium | — | UI |
| ECOM-017 | Increase cart quantity | 1. Add product<br>2. Increase quantity | Quantity 1 → 2 | Quantity and totals update correctly | — | Not Run | High | — | Cart |
| ECOM-018 | Decrease cart quantity | 1. Add multiple quantity<br>2. Decrease quantity | Quantity 2 → 1 | Quantity and totals update correctly | — | Not Run | High | — | Cart |
| ECOM-019 | Quantity below minimum | 1. Attempt quantity below supported minimum | 0 / negative | Invalid quantity is prevented or handled according to requirements | — | Not Run | Medium | — | Boundary |
| ECOM-020 | Quantity above available stock | 1. Add product<br>2. Attempt quantity greater than stock | Stock + 1 | User cannot purchase more than permitted inventory | — | Not Run | High | — | Inventory |
| ECOM-021 | Quantity maximum boundary | 1. Set quantity to configured maximum | Maximum quantity | Maximum permitted quantity is handled correctly | — | Not Run | Medium | — | Boundary |
| ECOM-022 | Remove item from cart | 1. Add product<br>2. Remove it | Existing cart item | Product is removed and totals update correctly | — | Not Run | High | — | Cart |
| ECOM-023 | Empty cart state | 1. Remove all cart items | Empty cart | Correct empty-cart state is displayed | — | Not Run | Medium | — | Empty state |
| ECOM-024 | Cart subtotal | 1. Add products with known prices/quantities<br>2. Review subtotal | Known products | Subtotal equals correct sum of cart items | — | Not Run | High | — | Calculation |
| ECOM-025 | Cart updates after product price change | 1. Add product<br>2. Change product price according to test setup<br>3. Reopen cart | Updated price | Cart follows configured price-change rules and clearly reflects payable amount | — | Not Run | High | — | Pricing |
| ECOM-026 | Product becomes out of stock while in cart | 1. Add product<br>2. Make product unavailable according to test setup<br>3. Open cart/checkout | Out-of-stock item | User is prevented from incorrectly purchasing unavailable inventory | — | Not Run | High | — | Inventory |
| ECOM-027 | Product deleted while in cart | 1. Add product<br>2. Remove product from catalog according to test setup<br>3. Reopen cart | Deleted product | Stale cart item is handled gracefully according to requirements | — | Not Run | High | — | Edge case |
| ECOM-028 | Cart persists after refresh | 1. Add products<br>2. Refresh | Cart items | Cart state persists according to requirements | — | Not Run | High | — | Persistence |
| ECOM-029 | Cart persists after re-login | 1. Login<br>2. Add product<br>3. Logout<br>4. Login again | Registered user | Saved cart follows account persistence requirements | — | Not Run | Medium | — | Persistence |
| ECOM-030 | Guest cart behavior after login | 1. Add item as guest<br>2. Login | Guest cart + account | Guest/account carts are merged/replaced according to defined business rules without unintended data loss | — | Not Run | High | — | Integration |
| ECOM-031 | Add product to wishlist | 1. Open product<br>2. Click Add to Wishlist | Existing product | Product is added to user's wishlist | — | Not Run | High | — | Wishlist |
| ECOM-032 | Remove product from wishlist | 1. Open wishlist<br>2. Remove product | Wishlisted product | Product is removed successfully | — | Not Run | Medium | — | Wishlist |
| ECOM-033 | Duplicate wishlist addition | 1. Add same product to wishlist repeatedly | Same product | Unintended duplicate wishlist entries are prevented | — | Not Run | Medium | — | Data integrity |
| ECOM-034 | Wishlist persists after re-login | 1. Add product to wishlist<br>2. Logout<br>3. Login | Registered user | Wishlist remains associated with correct account | — | Not Run | High | — | Persistence |
| ECOM-035 | Move wishlist item to cart | 1. Add item to wishlist<br>2. Select Move/Add to Cart | Available product | Correct product/variant is added to cart | — | Not Run | High | — | Integration |
| ECOM-036 | Out-of-stock wishlist item | 1. Wishlist product<br>2. Make it unavailable according to test setup<br>3. Open wishlist | Out-of-stock product | Current availability is displayed and invalid purchase is prevented | — | Not Run | High | — | Inventory |
| ECOM-037 | Wishlist privacy | 1. Login as User B<br>2. Attempt to access User A private wishlist | User A wishlist | Private wishlist data is not exposed | — | Not Run | High | — | Authorization |
| ECOM-038 | Cart isolation between users | 1. Add cart items as User A<br>2. Login as User B | Two accounts | User B does not receive User A's private cart data | — | Not Run | High | — | Data isolation |
| ECOM-039 | Product unavailable by direct URL | 1. Open direct URL of hidden/unavailable product | Unavailable product URL | Product visibility/purchase behavior follows configured rules | — | Not Run | High | — | Authorization/Business rules |
| ECOM-040 | Rapid Add to Cart clicks | 1. Open product<br>2. Rapidly click Add to Cart | Available product | Quantity/items follow intended behavior without unintended duplicates | — | Not Run | High | — | Edge case |
| ECOM-041 | Network failure while adding to cart | 1. Click Add to Cart while request fails | Available product | Error is shown and UI does not falsely indicate successful addition | — | Not Run | High | — | Error handling |
| ECOM-042 | Network failure while updating quantity | 1. Change cart quantity while request fails | Existing cart item | Error is handled and displayed quantity remains consistent with saved state | — | Not Run | High | — | Error handling |
| ECOM-043 | Product reviews display | 1. Open product with reviews | Reviewed product | Eligible reviews/ratings display correctly when supported | — | Not Run | Medium | — | Reviews |
| ECOM-044 | Submit product review | 1. Open eligible purchased/product review flow<br>2. Enter rating/review<br>3. Submit | Valid review | Review is submitted according to moderation/eligibility rules | — | Not Run | Medium | — | Reviews |
| ECOM-045 | Unauthorized review submission | 1. Attempt review without required eligibility | Ineligible user | Review submission follows configured eligibility rules | — | Not Run | Medium | — | Authorization |
| ECOM-046 | Product share/deep link | 1. Copy/share product URL<br>2. Open in new session | Product URL | Correct product/variant state opens according to deep-link requirements | — | Not Run | Medium | — | Navigation |
| ECOM-047 | Cart currency consistency | 1. Add products<br>2. Open cart<br>3. Continue toward checkout | Known currency | Currency and prices remain consistent through cart flow | — | Not Run | High | — | Data accuracy |
| ECOM-048 | Product inventory after successful purchase | 1. Note stock<br>2. Complete purchase<br>3. Recheck stock | Known inventory | Inventory updates according to completed-order rules | — | Not Run | High | — | Integration |
| ECOM-049 | Failed payment does not incorrectly reduce inventory | 1. Note stock<br>2. Attempt checkout with failed payment<br>3. Recheck inventory | Failed payment | Inventory follows configured reservation/release rules and is not incorrectly permanently reduced | — | Not Run | High | — | Integration |
| ECOM-050 | Product/cart/wishlist across supported environments | 1. Test core flows across supported browsers/devices | Valid products | Core e-commerce functionality behaves consistently | — | Not Run | Medium | — | Cross-browser/device |
