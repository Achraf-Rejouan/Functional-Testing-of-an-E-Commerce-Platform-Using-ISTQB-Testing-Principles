# Bidirectional Requirements Traceability Matrix
## PrestaShop Demo — Functional Testing

**Project:** Functional Testing of an E-Commerce Platform Using ISTQB Testing Principles  
**Standard:** ISTQB CTFL — Test Analysis and Design Phase  
**Date:** 2026-03-14  
**Author:** QA Engineer  

---

## Part 1 — Requirements → Test Cases (Forward Traceability)

*This view ensures every requirement has corresponding test coverage.*

| Requirement ID | Requirement Description | Priority | Test Case IDs                     | # TCs |
| :------------: | ----------------------- | :------: | --------------------------------- | :---: |
| REQ-01         | User Registration       | High     | TC-001, TC-002, TC-003            | 3     |
| REQ-02         | User Login              | High     | TC-004, TC-005, TC-006            | 3     |
| REQ-03         | User Logout             | High     | TC-007                            | 1     |
| REQ-04         | Product Browsing        | High     | TC-008, TC-009                    | 2     |
| REQ-05         | Product Search          | High     | TC-010, TC-011, TC-012            | 3     |
| REQ-06         | Product Details         | High     | TC-013, TC-014                    | 2     |
| REQ-07         | Product Filtering       | Medium   | TC-015, TC-016, TC-017            | 3     |
| REQ-08         | Add to Cart             | High     | TC-018, TC-019                    | 2     |
| REQ-09         | Update Cart             | High     | TC-020                            | 1     |
| REQ-10         | Remove from Cart        | High     | TC-021, TC-022                    | 2     |
| REQ-11         | Checkout Process        | High     | TC-023, TC-024, TC-025            | 3     |

**Total Requirements:** 11  
**Total Test Cases:** 25  
**Requirements without test coverage:** 0 ✅  

---

## Part 2 — Test Cases → Requirements (Backward Traceability)

*This view ensures every test case is linked to a valid requirement.*

| Test Case ID | Test Case Name                                         | Mapped Requirement ID | Requirement Description |
| :----------: | ------------------------------------------------------ | :-------------------: | ----------------------- |
| TC-001       | Successful User Registration with Valid Data           | REQ-01                | User Registration       |
| TC-002       | User Registration with Already Registered Email        | REQ-01                | User Registration       |
| TC-003       | User Registration with Missing Required Fields         | REQ-01                | User Registration       |
| TC-004       | Successful User Login with Valid Credentials           | REQ-02                | User Login              |
| TC-005       | User Login with Invalid Credentials                    | REQ-02                | User Login              |
| TC-006       | User Login with Empty Fields                           | REQ-02                | User Login              |
| TC-007       | Successful User Logout                                 | REQ-03                | User Logout             |
| TC-008       | Browse Products by Category                            | REQ-04                | Product Browsing        |
| TC-009       | Browse Products Using Homepage Featured Section        | REQ-04                | Product Browsing        |
| TC-010       | Search Products with a Valid Keyword                   | REQ-05                | Product Search          |
| TC-011       | Search Products with an Invalid Keyword                | REQ-05                | Product Search          |
| TC-012       | Search Autocomplete Suggestions on Keyword Input       | REQ-05                | Product Search          |
| TC-013       | View Complete Product Details Page                     | REQ-06                | Product Details         |
| TC-014       | View and Navigate Product Image Gallery                | REQ-06                | Product Details         |
| TC-015       | Filter Products by Size Attribute on Category Page     | REQ-07                | Product Filtering       |
| TC-016       | Filter Products by Color Attribute on Category Page    | REQ-07                | Product Filtering       |
| TC-017       | Sort Product Listing by Price Low to High              | REQ-07                | Product Filtering       |
| TC-018       | Add a Single Product to Shopping Cart                  | REQ-08                | Add to Cart             |
| TC-019       | Add Multiple Quantities of a Product to Cart           | REQ-08                | Add to Cart             |
| TC-020       | Update Product Quantity in Shopping Cart               | REQ-09                | Update Cart             |
| TC-021       | Remove a Product from Shopping Cart                    | REQ-10                | Remove from Cart        |
| TC-022       | Remove All Items — Verify Empty Cart State Display     | REQ-10                | Remove from Cart        |
| TC-023       | Full Guest Checkout Process — Personal Info to Order   | REQ-11                | Checkout Process        |
| TC-024       | Checkout — Address Step Validation with Missing Fields | REQ-11                | Checkout Process        |
| TC-025       | Checkout — Payment Method Selection and Order Submit   | REQ-11                | Checkout Process        |

**Test cases without a valid requirement mapping:** 0 ✅  

---

## Part 3 — Coverage Summary

| Feature Area       | Requirements Covered | Test Cases | Coverage Status |
| ------------------ | :------------------: | :--------: | :-------------: |
| Account Features   | REQ-01, REQ-02, REQ-03 | 7        | ✅ Covered      |
| Product Features   | REQ-04, REQ-05, REQ-06, REQ-07 | 10 | ✅ Covered |
| Shopping Features  | REQ-08, REQ-09, REQ-10, REQ-11 | 8  | ✅ Covered |
| **TOTAL**          | **11**               | **25**     | **✅ 100%**     |

---

## Part 4 — Test Priority Distribution

| Priority | Test Cases                                            | Count |
| :------: | ----------------------------------------------------- | :---: |
| High     | TC-001, TC-002, TC-003, TC-004, TC-005, TC-007, TC-008, TC-010, TC-013, TC-015, TC-018, TC-020, TC-021, TC-023, TC-024, TC-025 | 16 |
| Medium   | TC-006, TC-009, TC-011, TC-012, TC-016, TC-017, TC-019, TC-022 | 8  |
| Low      | TC-014                                                | 1     |
| **Total**| —                                                     | **25**|

---

*Bidirectional traceability ensures:*  
- **(Forward)** All requirements have at least one test case → No gaps in test coverage  
- **(Backward)** All test cases map to a requirement → No orphan or out-of-scope tests
