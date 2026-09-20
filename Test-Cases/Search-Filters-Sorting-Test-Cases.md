# Search, Filters & Sorting Test Cases

## Scope
Positive, negative, validation, combined-filter, sorting, pagination, persistence, performance, and edge-case testing for search and discovery functionality.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| SEARCH-001 | Search with exact valid keyword | 1. Open Search<br>2. Enter exact keyword<br>3. Submit | Existing item name | Relevant matching results are displayed | — | Not Run | High | — | Positive |
| SEARCH-002 | Search with partial keyword | 1. Enter partial keyword<br>2. Search | Partial item name | Relevant partial matches are returned according to requirements | — | Not Run | High | — | Positive |
| SEARCH-003 | Search with no matching results | 1. Enter nonexistent keyword<br>2. Search | xyznonexistent123 | No-result state is displayed correctly | — | Not Run | High | — | Negative |
| SEARCH-004 | Empty search | 1. Leave search field blank<br>2. Submit | Blank | Application follows defined empty-search behavior | — | Not Run | Medium | — | Validation |
| SEARCH-005 | Leading/trailing spaces | 1. Enter keyword with spaces<br>2. Search | " laptop " | Spaces are handled correctly without affecting valid results | — | Not Run | Medium | — | Edge case |
| SEARCH-006 | Search case sensitivity | 1. Search lowercase term<br>2. Repeat uppercase | laptop / LAPTOP | Results follow defined case-sensitivity rules consistently | — | Not Run | Medium | — | Edge case |
| SEARCH-007 | Special characters | 1. Enter special characters<br>2. Search | @#$% | Input is handled safely and application remains stable | — | Not Run | Medium | — | Negative |
| SEARCH-008 | Very long search query | 1. Enter query near/exceeding supported limit<br>2. Search | Long text | Query is handled according to configured limits without breaking UI | — | Not Run | Medium | — | Boundary |
| SEARCH-009 | Numeric search | 1. Enter numeric searchable value<br>2. Search | 12345 | Correct results are returned when numeric searching is supported | — | Not Run | Medium | — | Positive |
| SEARCH-010 | Search by multiple words | 1. Enter multi-word query<br>2. Search | wireless headphones | Results match configured multi-word search behavior | — | Not Run | Medium | — | Search logic |
| SEARCH-011 | Typo/noisy search input | 1. Enter slightly misspelled query<br>2. Search | laptpo | Search follows configured typo/fuzzy-match behavior | — | Not Run | Low | — | Search logic |
| SEARCH-012 | Apply single filter | 1. Perform search/browse<br>2. Select one filter | Category A | Only results matching selected filter are displayed | — | Not Run | High | — | Filter |
| SEARCH-013 | Apply multiple filters | 1. Select Filter A<br>2. Select Filter B | Multiple filters | Results satisfy the configured combination of selected filters | — | Not Run | High | — | Combined filters |
| SEARCH-014 | Filter producing zero results | 1. Apply restrictive filter combination | No-match filters | Correct empty state is displayed | — | Not Run | Medium | — | Negative |
| SEARCH-015 | Remove one active filter | 1. Apply multiple filters<br>2. Remove one | Multiple filters | Removed filter no longer affects results while remaining filters stay applied | — | Not Run | High | — | Filter |
| SEARCH-016 | Clear all filters | 1. Apply filters<br>2. Click Clear/Reset | Active filters | All filters reset and result set updates correctly | — | Not Run | High | — | Filter |
| SEARCH-017 | Filter count/result count | 1. Apply filter<br>2. Compare displayed count/results | Active filter | Displayed result count is consistent with returned results | — | Not Run | Medium | — | Data accuracy |
| SEARCH-018 | Minimum range boundary | 1. Set filter to minimum supported value<br>2. Apply | Minimum value | Boundary is handled according to filter rules | — | Not Run | Medium | — | Boundary |
| SEARCH-019 | Maximum range boundary | 1. Set filter to maximum supported value<br>2. Apply | Maximum value | Boundary is handled according to filter rules | — | Not Run | Medium | — | Boundary |
| SEARCH-020 | Invalid range | 1. Set minimum greater than maximum when UI permits<br>2. Apply | Min 100 / Max 50 | Invalid range is prevented or validated appropriately | — | Not Run | Medium | — | Negative |
| SEARCH-021 | Sort ascending | 1. Search/browse results<br>2. Select ascending sort | Price/Name/Date | Results appear in correct ascending order | — | Not Run | High | — | Sorting |
| SEARCH-022 | Sort descending | 1. Select descending sort | Price/Name/Date | Results appear in correct descending order | — | Not Run | High | — | Sorting |
| SEARCH-023 | Sort with equal values | 1. Sort results containing equal primary values | Equal values | Results follow defined secondary/tie-breaking order | — | Not Run | Medium | — | Edge case |
| SEARCH-024 | Change sort with filters active | 1. Apply filters<br>2. Change sorting | Filter + sort | Filters remain applied and filtered results reorder correctly | — | Not Run | High | — | Integration |
| SEARCH-025 | Change filter with sorting active | 1. Apply sorting<br>2. Apply filter | Sort + filter | Sort remains correctly applied to updated result set | — | Not Run | High | — | Integration |
| SEARCH-026 | Pagination next page | 1. Search with enough results<br>2. Open next page | Multi-page results | Next set of results loads correctly | — | Not Run | High | — | Pagination |
| SEARCH-027 | Pagination previous page | 1. Navigate to page 2<br>2. Return to page 1 | Multi-page results | Previous results load correctly | — | Not Run | Medium | — | Pagination |
| SEARCH-028 | Last page | 1. Navigate to final page | Multi-page results | Final page displays remaining results without invalid extra page | — | Not Run | Medium | — | Boundary |
| SEARCH-029 | Duplicate results across pages | 1. Review multiple pages<br>2. Compare result identifiers | Multi-page results | Results are not unintentionally duplicated due to pagination | — | Not Run | High | — | Data integrity |
| SEARCH-030 | Infinite scroll | 1. Scroll to load more results repeatedly | Large result set | Additional results load correctly without unintended duplicates/skips | — | Not Run | High | — | If supported |
| SEARCH-031 | Search state after opening result and returning | 1. Search/apply filters<br>2. Open result<br>3. Navigate back | Active search state | Search/filter state is preserved according to requirements | — | Not Run | Medium | — | Navigation |
| SEARCH-032 | Search state after refresh | 1. Search/apply filters<br>2. Refresh page | Active search state | State follows defined persistence/URL behavior | — | Not Run | Medium | — | Persistence |
| SEARCH-033 | Share/bookmark filtered URL | 1. Apply filters<br>2. Copy URL<br>3. Open in new session | Filtered URL | Search state is restored when URL-based persistence is supported | — | Not Run | Medium | — | Deep link |
| SEARCH-034 | Search result opens correct record | 1. Search<br>2. Select result | Existing record | Correct detail page/record opens | — | Not Run | High | — | Navigation |
| SEARCH-035 | Deleted/unavailable record in results | 1. Search for record removed/unavailable according to test setup | Removed record | Stale/unavailable record follows product visibility rules | — | Not Run | High | — | Data consistency |
| SEARCH-036 | Newly created record becomes searchable | 1. Create record<br>2. Search for it after expected indexing period | New record | Record appears according to expected indexing/sync behavior | — | Not Run | High | — | Integration |
| SEARCH-037 | Updated searchable data | 1. Update record name/data<br>2. Search old and new values | Updated record | Search reflects updated data according to expected indexing behavior | — | Not Run | High | — | Data consistency |
| SEARCH-038 | Unauthorized result visibility | 1. Login as limited user<br>2. Search for restricted record | Restricted record | Unauthorized record/data is not exposed in search results | — | Not Run | High | — | Authorization |
| SEARCH-039 | Network failure during search | 1. Enter query<br>2. Submit while request fails | Valid query | Appropriate error/retry state is displayed and UI remains usable | — | Not Run | High | — | Error handling |
| SEARCH-040 | Rapid consecutive searches | 1. Search Term A<br>2. Immediately search Term B | Two queries | Latest intended search is displayed without stale-response overwrite | — | Not Run | High | — | Race condition |
| SEARCH-041 | Rapid filter changes | 1. Change filters repeatedly/quickly | Multiple filters | Final results match current selected filters | — | Not Run | Medium | — | Race condition |
| SEARCH-042 | Loading state | 1. Perform slower search/filter operation<br>2. Observe UI | Valid query | Appropriate loading state is shown without misleading stale data | — | Not Run | Medium | — | UI |
| SEARCH-043 | Search response time | 1. Perform representative searches<br>2. Observe response | Common queries | Results load within defined performance requirements | — | Not Run | Medium | — | Performance |
| SEARCH-044 | Search on mobile layout | 1. Open supported mobile viewport/device<br>2. Search and filter | Valid query | Search/filter controls remain usable and results display correctly | — | Not Run | Medium | — | Responsive |
| SEARCH-045 | Search across supported environments | 1. Repeat core search/filter/sort flow across supported environments | Valid queries | Functionality behaves consistently across supported browsers/devices | — | Not Run | Medium | — | Cross-browser/device |
