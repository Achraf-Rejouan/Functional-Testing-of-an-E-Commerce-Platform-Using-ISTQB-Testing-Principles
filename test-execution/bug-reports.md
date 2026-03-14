# Bug Reports — PrestaShop Demo E-Commerce Platform

**Project:** Functional Testing of an E-Commerce Platform Using ISTQB Testing Principles  
**Standard:** ISTQB CTFL — Test Execution Phase  
**Execution Date:** 2026-03-14  
**Tester:** QA Engineer  
**Environment:** PrestaShop Demo · Chrome (latest stable)  

---

## Bug Summary Table

| Bug ID  | Title                                                        | Related TC | Severity | Priority | Status |
| :-----: | ------------------------------------------------------------ | :--------: | :------: | :------: | :----: |
| [BUG-001](bug-reports/BUG-001.md) | Empty search query bypasses client-side validation and redirects instead of blocking | TC-012 | Minor    | Low      | 🔴 Open |
| [BUG-002](bug-reports/BUG-002.md) | Add to Cart silently applies default size/color without prompting user to confirm attribute selection | TC-018 | Major    | High     | 🔴 Open |
| [BUG-003](bug-reports/BUG-003.md) | Cart quantity set to 0 immediately removes item without confirmation dialog | TC-020 | Major    | High     | 🔴 Open |
| [BUG-004](bug-reports/BUG-004.md) | Terms & Conditions link returns 404 during Guest Checkout, blocking order placement | TC-023 | Critical | High     | 🔴 Open |

---

## Bug Statistics

| Severity | Count |
| :------: | :---: |
| Critical | 1     |
| Major    | 2     |
| Minor    | 1     |
| **Total**| **4** |

| Priority | Count |
| :------: | :---: |
| High     | 3     |
| Low      | 1     |
| **Total**| **4** |

---

## Feature Area Distribution

| Feature Area      | Bugs Found | Bug IDs             |
| ----------------- | :--------: | ------------------- |
| Search            | 1          | BUG-001             |
| Add to Cart       | 1          | BUG-002             |
| Cart Management   | 1          | BUG-003             |
| Checkout Process  | 1          | BUG-004             |

---

*Detailed bug reports are available in the `bug-reports/` folder.*
