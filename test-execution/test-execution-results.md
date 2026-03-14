# Test Execution Results — PrestaShop Demo E-Commerce Platform

**Project:** Functional Testing of an E-Commerce Platform Using ISTQB Testing Principles  
**System Under Test (SUT):** [PrestaShop Demo](https://demo.prestashop.com/#/en/front)  
**Standard:** ISTQB CTFL — Test Execution Phase  
**Execution Date:** 2026-03-14  
**Tester:** QA Engineer  
**Browser:** Google Chrome (latest stable)  
**Environment:** PrestaShop Demo (Production-like sandbox)  
**Total Test Cases:** 25  

---

## Execution Summary

| Status         | Count | % of Total |
| :------------: | :---: | :--------: |
| ✅ PASS        | 19    | 76%        |
| ❌ FAIL        | 4     | 16%        |
| ⚠️ BLOCKED     | 1     | 4%         |
| ⬜ NOT EXECUTED| 1     | 4%         |
| **TOTAL**      | **25**| **100%**   |

**Bugs Found:** 4 (BUG-001 through BUG-004)

---

## Test Execution Results Table

| TC ID   | Test Name                                               | Req. ID | Execution Date | Tester      | Status             | Notes                                                                                                                       |
| :-----: | ------------------------------------------------------- | :-----: | :------------: | ----------- | :----------------: | --------------------------------------------------------------------------------------------------------------------------- |
| TC-001  | Successful User Registration with Valid Data            | REQ-01  | 2026-03-14     | QA Engineer | ✅ PASS            | Account creation flow works correctly. User redirected to account dashboard after registration.                              |
| TC-002  | User Registration with Already Registered Email         | REQ-01  | 2026-03-14     | QA Engineer | ✅ PASS            | System correctly rejects duplicate email with message: *"An account using this email address has already been registered."* |
| TC-003  | User Registration with Missing Required Fields          | REQ-01  | 2026-03-14     | QA Engineer | ✅ PASS            | Browser-native HTML5 validation triggers on the First Name field first: *"Please fill out this field."* Subsequent fields validated sequentially on resubmission. |
| TC-004  | Successful User Login with Valid Credentials            | REQ-02  | 2026-03-14     | QA Engineer | ✅ PASS            | Login with pub@prestashop.com succeeds. User name displayed in top navigation.                                              |
| TC-005  | User Login with Invalid Credentials                     | REQ-02  | 2026-03-14     | QA Engineer | ✅ PASS            | System returns: *"Authentication failed."* in a red alert box. No account existence information disclosed.                  |
| TC-006  | User Login with Empty Fields                            | REQ-02  | 2026-03-14     | QA Engineer | ✅ PASS            | Browser-native HTML5 required-field validation prevents submission. *"Please fill out this field."* shown on email input.   |
| TC-007  | Successful User Logout                                  | REQ-03  | 2026-03-14     | QA Engineer | ✅ PASS            | Logout terminates session correctly. Navigation bar restores the Sign in link. Back navigation does not re-authenticate.    |
| TC-008  | Browse Products by Category                             | REQ-04  | 2026-03-14     | QA Engineer | ✅ PASS            | Category pages load correctly with product grid, breadcrumb, and category title displayed.                                  |
| TC-009  | Browse Products Using Homepage Featured Section         | REQ-04  | 2026-03-14     | QA Engineer | ✅ PASS            | Featured product cards on homepage navigate to correct product detail pages.                                                |
| TC-010  | Search Products with a Valid Keyword                    | REQ-05  | 2026-03-14     | QA Engineer | ✅ PASS            | Searching "shirt" returns relevant results with product count shown on SEARCH RESULTS page.                                 |
| TC-011  | Search Products with an Invalid Keyword                 | REQ-05  | 2026-03-14     | QA Engineer | ✅ PASS            | Searching "xyznonexistentproduct12345" returns graceful empty state: *"No results were found for your search."*             |
| TC-012  | Search Autocomplete Suggestions on Keyword Input        | REQ-05  | 2026-03-14     | QA Engineer | ❌ FAIL            | Autocomplete works for alphabetic input (e.g., "shirt"). However, submitting an **empty search** bypasses client-side validation and redirects to a search results page showing *"No matches were found"* instead of blocking the request. **→ BUG-001** |
| TC-013  | View Complete Product Details Page                      | REQ-06  | 2026-03-14     | QA Engineer | ✅ PASS            | All required elements present: product name, price, images, size dropdown, color swatches, quantity input, and ADD TO CART button. |
| TC-014  | View and Navigate Product Image Gallery                 | REQ-06  | 2026-03-14     | QA Engineer | ✅ PASS            | Thumbnail clicks change the main image without page reload. Gallery loads fully.                                            |
| TC-015  | Filter Products by Size Attribute on Category Page      | REQ-07  | 2026-03-14     | QA Engineer | ✅ PASS            | Size filter successfully narrows product listing. Active filter indicator displayed.                                        |
| TC-016  | Filter Products by Color Attribute on Category Page     | REQ-07  | 2026-03-14     | QA Engineer | ✅ PASS            | Color filter works correctly. Removing filter restores full listing.                                                        |
| TC-017  | Sort Product Listing by Price Low to High               | REQ-07  | 2026-03-14     | QA Engineer | ✅ PASS            | Sort dropdown reorders products ascending by price. Dropdown label updates to reflect selection.                            |
| TC-018  | Add a Single Product to Shopping Cart                   | REQ-08  | 2026-03-14     | QA Engineer | ❌ FAIL            | When no size/color is explicitly selected by the user, the system silently adds the product with default attributes (Size: S, Color: White) without any confirmation prompt or warning to the user. **→ BUG-002** |
| TC-019  | Add Multiple Quantities of a Product to Cart            | REQ-08  | 2026-03-14     | QA Engineer | ✅ PASS            | Quantity of 3 correctly reflected in cart modal. Total price = unit price × 3.                                              |
| TC-020  | Update Product Quantity in Shopping Cart                | REQ-09  | 2026-03-14     | QA Engineer | ❌ FAIL            | Setting the cart quantity to **0** immediately removes the item without displaying any confirmation dialog or warning. The deletion is irreversible without navigating back to the product. **→ BUG-003** |
| TC-021  | Remove a Product from Shopping Cart                     | REQ-10  | 2026-03-14     | QA Engineer | ✅ PASS            | Trash icon removes item from cart. Cart counter decrements. Empty cart state shown when last item removed.                  |
| TC-022  | Remove All Items — Verify Empty Cart State              | REQ-10  | 2026-03-14     | QA Engineer | ✅ PASS            | Empty cart message *"There are no more items in your cart"* displays correctly after removing the last item.                |
| TC-023  | Full Guest Checkout Process — End-to-End                | REQ-11  | 2026-03-14     | QA Engineer | ⚠️ BLOCKED         | Checkout Step 1 (Personal Info) requires accepting Terms & Conditions. The T&C checkbox is present but the linked T&C document is unavailable in the demo environment (link leads to a 404 page within the demo frame). Guest checkout cannot be fully completed. **→ BUG-004** |
| TC-024  | Checkout — Address Step Validation with Missing Fields  | REQ-11  | 2026-03-14     | QA Engineer | ✅ PASS            | Validation messages correctly appear: *"Address is required"*, *"City is required"*, *"Zip/Postal Code is required."* Checkout does not advance without complete address data. |
| TC-025  | Checkout — Payment Method Selection and Order Submit    | REQ-11  | 2026-03-14     | QA Engineer | ⬜ NOT EXECUTED    | Dependent on TC-023 completion. TC-023 was BLOCKED, making TC-025 not executable in this execution cycle.                   |

---

## Bug Summary

| Bug ID  | Related TC | Title                                                      | Severity | Priority | Status |
| :-----: | :--------: | ---------------------------------------------------------- | :------: | :------: | :----: |
| BUG-001 | TC-012     | Empty search query bypasses client-side validation         | Minor    | Low      | Open   |
| BUG-002 | TC-018     | Add to Cart silently uses default attributes without prompt | Major    | High     | Open   |
| BUG-003 | TC-020     | Cart quantity set to 0 removes item without confirmation   | Major    | High     | Open   |
| BUG-004 | TC-023     | Terms & Conditions link returns 404 in demo environment    | Critical | High     | Open   |

---

*End of test execution results. Detailed bug reports available in `/test-execution/bug-reports/`.*
