# Functional Test Cases — PrestaShop Demo E-Commerce Platform

**Project:** Functional Testing of an E-Commerce Platform Using ISTQB Testing Principles  
**System Under Test (SUT):** [PrestaShop Demo](https://demo.prestashop.com/#/en/front)  
**Standard:** ISTQB CTFL — Test Analysis and Design Phase  
**Date:** 2026-03-14  
**Author:** QA Engineer  
**Total Test Cases:** 25  

---

## Requirements Reference

| Requirement ID | Requirement Description      |
| -------------- | ---------------------------- |
| REQ-01         | User Registration            |
| REQ-02         | User Login                   |
| REQ-03         | User Logout                  |
| REQ-04         | Product Browsing             |
| REQ-05         | Product Search               |
| REQ-06         | Product Details              |
| REQ-07         | Product Filtering            |
| REQ-08         | Add to Cart                  |
| REQ-09         | Update Cart                  |
| REQ-10         | Remove from Cart             |
| REQ-11         | Checkout Process             |

---

## TC-001 — Successful User Registration with Valid Data

| Field                 | Details                                                                                                                                                                                                                                                                      |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-001                                                                                                                                                                                                                                                                       |
| **Test Name**         | Successful User Registration with Valid Data                                                                                                                                                                                                                                 |
| **Description**       | Verify that a new user can successfully create an account on PrestaShop by providing all required personal information in valid format.                                                                                                                                       |
| **Reference Req. ID** | REQ-01                                                                                                                                                                                                                                                                       |
| **Priority**          | High                                                                                                                                                                                                                                                                         |
| **Preconditions**     | - The SUT is accessible at https://demo.prestashop.com/#/en/front  <br> - The user is not already logged in  <br> - The email address to be used does not already exist in the system                                                                                       |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - Network: stable internet connection  <br> - No active user session                                                                                                                                                           |
| **Test Data**         | Social title: Mr  <br> First name: John  <br> Last name: Doe  <br> Email: john.doe.test001@mailtest.com  <br> Password: SecurePass@123  <br> Birthdate: 01/15/1990                                                                                                           |
| **Test Steps**        | 1. Navigate to https://demo.prestashop.com/#/en/front  <br> 2. Click the **Sign in** link in the top navigation bar  <br> 3. Click **No account? Create one here** link  <br> 4. Select social title **Mr**  <br> 5. Enter first name, last name, email, and password from test data  <br> 6. Enter birthdate (optional)  <br> 7. Check **I agree to the terms and conditions**  <br> 8. Click the **SAVE** button |
| **Expected Result**   | - User account is created successfully  <br> - User is redirected to their account dashboard  <br> - A welcome message is displayed with the user's name  <br> - User is automatically logged in after registration                                                          |

---

## TC-002 — User Registration with Already Registered Email

| Field                 | Details                                                                                                                                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-002                                                                                                                                                                                                                                                |
| **Test Name**         | User Registration with Already Registered Email                                                                                                                                                                                                       |
| **Description**       | Verify that the system prevents registration when an email address that is already associated with an existing account is used.                                                                                                                        |
| **Reference Req. ID** | REQ-01                                                                                                                                                                                                                                                |
| **Priority**          | High                                                                                                                                                                                                                                                  |
| **Preconditions**     | - An account with email pub@prestashop.com already exists in the system  <br> - User is not logged in                                                                                                                                                 |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - Network: stable internet connection                                                                                                                                                                   |
| **Test Data**         | Social title: Mrs  <br> First name: Jane  <br> Last name: Smith  <br> Email: pub@prestashop.com (existing account)  <br> Password: AnotherPass@456                                                                                                    |
| **Test Steps**        | 1. Navigate to the homepage  <br> 2. Click **Sign in** → **No account? Create one here**  <br> 3. Fill in all required fields using test data  <br> 4. Check **I agree to the terms and conditions**  <br> 5. Click **SAVE**                          |
| **Expected Result**   | - Registration is rejected  <br> - An error message is displayed indicating the email is already in use (e.g., *"An account using this email address has already been registered."*)  <br> - User remains on the registration page                    |

---

## TC-003 — User Registration with Missing Required Fields

| Field                 | Details                                                                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-003                                                                                                                                                                              |
| **Test Name**         | User Registration with Missing Required Fields                                                                                                                                      |
| **Description**       | Verify that the registration form performs input validation and prevents submission when mandatory fields (first name, last name, email, password) are left empty.                  |
| **Reference Req. ID** | REQ-01                                                                                                                                                                              |
| **Priority**          | High                                                                                                                                                                                |
| **Preconditions**     | - User is on the registration page                                                                                                                                                  |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                             |
| **Test Data**         | First name: (empty)  <br> Last name: (empty)  <br> Email: (empty)  <br> Password: (empty)                                                                                          |
| **Test Steps**        | 1. Navigate to the registration page  <br> 2. Leave all required fields empty  <br> 3. Click **SAVE**                                                                               |
| **Expected Result**   | - Form submission is blocked  <br> - Validation error messages are displayed next to each required empty field (e.g., *"This field is required"*)  <br> - User remains on the page |

---

## TC-004 — Successful User Login with Valid Credentials

| Field                 | Details                                                                                                                                                                                                                                    |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-004                                                                                                                                                                                                                                     |
| **Test Name**         | Successful User Login with Valid Credentials                                                                                                                                                                                               |
| **Description**       | Verify that a registered user can successfully log in to the platform using a valid email address and password.                                                                                                                             |
| **Reference Req. ID** | REQ-02                                                                                                                                                                                                                                     |
| **Priority**          | High                                                                                                                                                                                                                                       |
| **Preconditions**     | - A valid account exists with the test credentials  <br> - User is not currently logged in                                                                                                                                                 |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - No active user session (cookies cleared or private window)                                                                                                                                 |
| **Test Data**         | Email: pub@prestashop.com  <br> Password: demo1234567890 (PrestaShop demo credentials)                                                                                                                                                     |
| **Test Steps**        | 1. Navigate to the homepage  <br> 2. Click the **Sign in** link  <br> 3. Enter email and password from test data  <br> 4. Click **SIGN IN**                                                                                                |
| **Expected Result**   | - User is authenticated successfully  <br> - User is redirected to their account dashboard  <br> - The top navigation bar displays the user's name (e.g., *"John Doe"*)  <br> - The **Sign in** link is replaced by the user's name link |

---

## TC-005 — User Login with Invalid Credentials

| Field                 | Details                                                                                                                                                                                                                              |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-005                                                                                                                                                                                                                               |
| **Test Name**         | User Login with Invalid Credentials                                                                                                                                                                                                  |
| **Description**       | Verify that the system rejects login attempts with an incorrect password and displays an appropriate error message without exposing security details.                                                                                  |
| **Reference Req. ID** | REQ-02                                                                                                                                                                                                                               |
| **Priority**          | High                                                                                                                                                                                                                                 |
| **Preconditions**     | - User is not logged in                                                                                                                                                                                                              |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                              |
| **Test Data**         | Email: pub@prestashop.com  <br> Password: WrongPassword!999                                                                                                                                                                          |
| **Test Steps**        | 1. Navigate to the Sign in page  <br> 2. Enter a valid registered email with an incorrect password  <br> 3. Click **SIGN IN**                                                                                                         |
| **Expected Result**   | - Authentication fails  <br> - An error message is displayed (e.g., *"Authentication failed."*)  <br> - User remains on the login page  <br> - No sensitive information (e.g., whether the email exists) is disclosed in the message |

---

## TC-006 — User Login with Empty Fields

| Field                 | Details                                                                                                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-006                                                                                                                                                                    |
| **Test Name**         | User Login with Empty Fields                                                                                                                                              |
| **Description**       | Verify that the login form performs client-side validation and prevents submission when either the email or password field is empty.                                       |
| **Reference Req. ID** | REQ-02                                                                                                                                                                    |
| **Priority**          | Medium                                                                                                                                                                    |
| **Preconditions**     | - User is on the Sign in page                                                                                                                                             |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                   |
| **Test Data**         | Email: (empty)  <br> Password: (empty)                                                                                                                                    |
| **Test Steps**        | 1. Navigate to the Sign in page  <br> 2. Leave email and password fields empty  <br> 3. Click **SIGN IN**                                                                  |
| **Expected Result**   | - Form submission is blocked  <br> - Required field validation messages are displayed (e.g., *"Please fill out this field"*)  <br> - User remains on the login page        |

---

## TC-007 — Successful User Logout

| Field                 | Details                                                                                                                                                                                                     |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-007                                                                                                                                                                                                      |
| **Test Name**         | Successful User Logout                                                                                                                                                                                      |
| **Description**       | Verify that a logged-in user can successfully end their session by logging out, and that they are redirected to the homepage with the session properly terminated.                                           |
| **Reference Req. ID** | REQ-03                                                                                                                                                                                                      |
| **Priority**          | High                                                                                                                                                                                                        |
| **Preconditions**     | - User is logged in with a valid account                                                                                                                                                                    |
| **Test Setup**        | - Active authenticated user session  <br> - Browser: latest stable Chrome/Firefox                                                                                                                           |
| **Test Data**         | N/A (uses existing authenticated session)                                                                                                                                                                   |
| **Test Steps**        | 1. Confirm user is logged in (name visible in top navigation)  <br> 2. Click on the user's name in the top navigation bar  <br> 3. Click **Sign out** from the dropdown menu                               |
| **Expected Result**   | - User session is terminated  <br> - User is redirected to the homepage or login page  <br> - The **Sign in** link is restored in the navigation  <br> - Navigating back does not restore the session (session cookie cleared) |

---

## TC-008 — Browse Products by Category

| Field                 | Details                                                                                                                                                                                                                                |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-008                                                                                                                                                                                                                                 |
| **Test Name**         | Browse Products by Category                                                                                                                                                                                                            |
| **Description**       | Verify that a user can navigate to a product category from the main navigation menu and view a list of products belonging to that category.                                                                                             |
| **Reference Req. ID** | REQ-04                                                                                                                                                                                                                                 |
| **Priority**          | High                                                                                                                                                                                                                                   |
| **Preconditions**     | - User is on the homepage  <br> - No login required (guest user)                                                                                                                                                                       |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                |
| **Test Data**         | Category: CLOTHES                                                                                                                                                                                                                      |
| **Test Steps**        | 1. Navigate to the homepage  <br> 2. Hover over **CLOTHES** in the main navigation menu  <br> 3. Click on a sub-category (e.g., **Men** or **Women**)                                                                                   |
| **Expected Result**   | - The category page loads with a title matching the selected category  <br> - A grid/list of product cards is displayed, each showing: product image, name, and price  <br> - The breadcrumb trail reflects the active category path |

---

## TC-009 — Browse Products Using Homepage Featured Section

| Field                 | Details                                                                                                                                                                                                            |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-009                                                                                                                                                                                                             |
| **Test Name**         | Browse Products Using Homepage Featured Section                                                                                                                                                                     |
| **Description**       | Verify that users can discover and browse products from the homepage's featured products and promotional banners.                                                                                                    |
| **Reference Req. ID** | REQ-04                                                                                                                                                                                                             |
| **Priority**          | Medium                                                                                                                                                                                                             |
| **Preconditions**     | - User is on the homepage                                                                                                                                                                                          |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                            |
| **Test Data**         | N/A                                                                                                                                                                                                                |
| **Test Steps**        | 1. Navigate to the homepage  <br> 2. Scroll down to the **Popular Products** or featured section  <br> 3. Click on any featured product card                                                                        |
| **Expected Result**   | - The product detail page for the selected product loads correctly  <br> - Product name, price, images, and attributes are visible  <br> - Breadcrumb accurately shows the product's position in the category tree |

---

## TC-010 — Search Products with a Valid Keyword

| Field                 | Details                                                                                                                                                                                                                                             |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-010                                                                                                                                                                                                                                              |
| **Test Name**         | Search Products with a Valid Keyword                                                                                                                                                                                                                 |
| **Description**       | Verify that the search functionality returns relevant product results when a user enters a known product keyword into the search bar.                                                                                                                 |
| **Reference Req. ID** | REQ-05                                                                                                                                                                                                                                              |
| **Priority**          | High                                                                                                                                                                                                                                                 |
| **Preconditions**     | - User is on any page of the site  <br> - The search bar is visible in the top navigation                                                                                                                                                           |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                             |
| **Test Data**         | Search keyword: "shirt"                                                                                                                                                                                                                             |
| **Test Steps**        | 1. Click on the search bar (magnifying glass icon) in the top right navigation  <br> 2. Type "shirt" into the search input  <br> 3. Press **Enter** or click the search button                                                                       |
| **Expected Result**   | - The search results page loads with the title **SEARCH RESULTS**  <br> - At least one product card is displayed  <br> - All displayed products are relevant to the keyword "shirt"  <br> - The number of results is shown (e.g., *"X products"*)   |

---

## TC-011 — Search Products with an Invalid Keyword

| Field                 | Details                                                                                                                                                                                                      |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-011                                                                                                                                                                                                       |
| **Test Name**         | Search Products with an Invalid/Non-Existent Keyword                                                                                                                                                         |
| **Description**       | Verify that the system handles search queries that yield no results gracefully, displaying an informative empty state message instead of an error.                                                            |
| **Reference Req. ID** | REQ-05                                                                                                                                                                                                       |
| **Priority**          | Medium                                                                                                                                                                                                       |
| **Preconditions**     | - User is on any page                                                                                                                                                                                        |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                      |
| **Test Data**         | Search keyword: "xyznonexistentproduct12345"                                                                                                                                                                 |
| **Test Steps**        | 1. Click the search bar  <br> 2. Enter "xyznonexistentproduct12345"  <br> 3. Press **Enter**                                                                                                                  |
| **Expected Result**   | - The search results page loads  <br> - No product cards are displayed  <br> - A user-friendly message is shown (e.g., *"No results were found for your search"*)  <br> - No application error is triggered |

---

## TC-012 — Search Autocomplete/Suggestions

| Field                 | Details                                                                                                                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-012                                                                                                                                                                                                                              |
| **Test Name**         | Search Autocomplete Suggestions on Keyword Input                                                                                                                                                                                    |
| **Description**       | Verify that the search bar displays real-time autocomplete suggestions as the user types a keyword, allowing quick product discovery.                                                                                                 |
| **Reference Req. ID** | REQ-05                                                                                                                                                                                                                              |
| **Priority**          | Medium                                                                                                                                                                                                                              |
| **Preconditions**     | - User is on the homepage or any page with the search bar visible                                                                                                                                                                   |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                             |
| **Test Data**         | Search keyword: "hum" (partial keyword for "Hummingbird")                                                                                                                                                                           |
| **Test Steps**        | 1. Click the search bar  <br> 2. Type "hum" slowly into the search input  <br> 3. Wait for autocomplete suggestions to appear                                                                                                        |
| **Expected Result**   | - A dropdown list of product suggestions appears below the search bar  <br> - Suggestions include products containing the letters "hum" (e.g., "Hummingbird printed t-shirt")  <br> - Clicking a suggestion navigates to that product page |

---

## TC-013 — View Product Details Page

| Field                 | Details                                                                                                                                                                                                                                                                                  |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-013                                                                                                                                                                                                                                                                                   |
| **Test Name**         | View Complete Product Details Page                                                                                                                                                                                                                                                       |
| **Description**       | Verify that the product detail page (PDP) displays all required product information including name, price, images, size options, color options, quantity field, and the Add to Cart button.                                                                                               |
| **Reference Req. ID** | REQ-06                                                                                                                                                                                                                                                                                   |
| **Priority**          | High                                                                                                                                                                                                                                                                                     |
| **Preconditions**     | - User is on the homepage or a category listing page                                                                                                                                                                                                                                     |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                                                                  |
| **Test Data**         | Product: "Hummingbird Printed T-Shirt" (from search or category)                                                                                                                                                                                                                         |
| **Test Steps**        | 1. Navigate to the Clothes > Men category  <br> 2. Click on the **Hummingbird Printed T-Shirt** product card  <br> 3. Inspect all page elements                                                                                                                                           |
| **Expected Result**   | - Product name is displayed prominently  <br> - At least one product image is shown  <br> - Price is visible (including discount if applicable)  <br> - Size dropdown (S, M, L, XL) is present and functional  <br> - Color swatches are displayed  <br> - Quantity input field is present  <br> - **ADD TO CART** button is enabled  <br> - Breadcrumb navigation is shown |

---

## TC-014 — View Product Image Gallery

| Field                 | Details                                                                                                                                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-014                                                                                                                                                                                                         |
| **Test Name**         | View and Navigate Product Image Gallery                                                                                                                                                                         |
| **Description**       | Verify that the product image gallery on the PDP allows users to view multiple product images by clicking thumbnails or arrows.                                                                                  |
| **Reference Req. ID** | REQ-06                                                                                                                                                                                                         |
| **Priority**          | Low                                                                                                                                                                                                            |
| **Preconditions**     | - User is on a product detail page with multiple images                                                                                                                                                         |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                         |
| **Test Data**         | Product: Any product with multiple images (e.g., Hummingbird Printed T-Shirt)                                                                                                                                   |
| **Test Steps**        | 1. Navigate to a product detail page  <br> 2. Click on a thumbnail image in the image gallery  <br> 3. Observe the main image change  <br> 4. If arrows are available, click the next/previous arrow           |
| **Expected Result**   | - Clicking a thumbnail changes the main displayed image  <br> - Gallery navigation (arrows or thumbnails) works without page reload  <br> - Images load fully without broken image icons                       |

---

## TC-015 — Filter Products by Size on Category Page

| Field                 | Details                                                                                                                                                                                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-015                                                                                                                                                                                                                                               |
| **Test Name**         | Filter Products by Size Attribute on Category Page                                                                                                                                                                                                   |
| **Description**       | Verify that the product filter panel on a category page allows users to narrow down displayed products by selecting a specific size attribute.                                                                                                         |
| **Reference Req. ID** | REQ-07                                                                                                                                                                                                                                               |
| **Priority**          | High                                                                                                                                                                                                                                                 |
| **Preconditions**     | - User is on a category page that has filterable products (e.g., Clothes)                                                                                                                                                                            |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                              |
| **Test Data**         | Category: Clothes  <br> Filter: Size = M                                                                                                                                                                                                             |
| **Test Steps**        | 1. Navigate to the **Clothes** category  <br> 2. Locate the **Filter by** sidebar on the left  <br> 3. Expand the **Size** filter section  <br> 4. Select size **M**                                                                                  |
| **Expected Result**   | - The product listing updates (or page reloads) to show only products available in size M  <br> - The active filter badge is shown (e.g., *"Size: M"*)  <br> - Products not available in size M are no longer displayed                              |

---

## TC-016 — Filter Products by Color on Category Page

| Field                 | Details                                                                                                                                                                                                      |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-016                                                                                                                                                                                                       |
| **Test Name**         | Filter Products by Color Attribute on Category Page                                                                                                                                                          |
| **Description**       | Verify that a user can filter products by color on the category listing page to narrow down the product selection.                                                                                            |
| **Reference Req. ID** | REQ-07                                                                                                                                                                                                       |
| **Priority**          | Medium                                                                                                                                                                                                       |
| **Preconditions**     | - User is on a category page with color-filterable products                                                                                                                                                  |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                      |
| **Test Data**         | Category: Clothes  <br> Filter: Color = Black                                                                                                                                                                |
| **Test Steps**        | 1. Navigate to the **Clothes** category  <br> 2. Locate the **Filter by** sidebar  <br> 3. Expand the **Color** filter section  <br> 4. Select the **Black** color swatch                                    |
| **Expected Result**   | - The product listing updates to only show products available in Black  <br> - An active filter indicator shows the selected color  <br> - Removing the filter restores the full product listing             |

---

## TC-017 — Sort Products by Price (Low to High)

| Field                 | Details                                                                                                                                                                                                                       |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-017                                                                                                                                                                                                                        |
| **Test Name**         | Sort Product Listing by Price Low to High                                                                                                                                                                                     |
| **Description**       | Verify that the sort dropdown on a category listing page correctly reorders products from lowest to highest price.                                                                                                              |
| **Reference Req. ID** | REQ-07                                                                                                                                                                                                                        |
| **Priority**          | Medium                                                                                                                                                                                                                        |
| **Preconditions**     | - User is on a category page with multiple products at different price points                                                                                                                                                  |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                       |
| **Test Data**         | Category: Clothes  <br> Sort option: Price, low to high                                                                                                                                                                       |
| **Test Steps**        | 1. Navigate to the **Clothes** category  <br> 2. Locate the **Sort by** dropdown at the top of the product listing  <br> 3. Select **Price, low to high**                                                                      |
| **Expected Result**   | - The product grid reorders with the cheapest products displayed first  <br> - The sort dropdown reflects the selected option  <br> - Product prices are in ascending order from first to last visible product card            |

---

## TC-018 — Add a Single Product to Cart

| Field                 | Details                                                                                                                                                                                                                                                           |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-018                                                                                                                                                                                                                                                            |
| **Test Name**         | Add a Single Product to Shopping Cart                                                                                                                                                                                                                             |
| **Description**       | Verify that a user can add a product to the shopping cart from the product detail page and that the cart icon and confirmation modal update correctly.                                                                                                             |
| **Reference Req. ID** | REQ-08                                                                                                                                                                                                                                                            |
| **Priority**          | High                                                                                                                                                                                                                                                              |
| **Preconditions**     | - User is on a product detail page  <br> - Cart is empty (or any state)                                                                                                                                                                                           |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                                           |
| **Test Data**         | Product: Hummingbird Printed T-Shirt  <br> Size: M  <br> Color: White  <br> Quantity: 1                                                                                                                                                                           |
| **Test Steps**        | 1. Navigate to the Hummingbird Printed T-Shirt product detail page  <br> 2. Select size **M**  <br> 3. Select color **White**  <br> 4. Set quantity to **1**  <br> 5. Click **ADD TO CART**                                                                         |
| **Expected Result**   | - A confirmation modal appears stating *"Product successfully added to your shopping cart"*  <br> - The modal displays product name, price, selected size/color, and quantity  <br> - The cart icon in the navigation updates to reflect the new item total count |

---

## TC-019 — Add Multiple Quantities of a Product to Cart

| Field                 | Details                                                                                                                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test Case ID**      | TC-019                                                                                                                                                                                                                   |
| **Test Name**         | Add Multiple Quantities of a Product to Shopping Cart                                                                                                                                                                    |
| **Description**       | Verify that a user can specify a quantity greater than 1 on the product detail page and that the cart correctly reflects the quantity and updated total price.                                                            |
| **Reference Req. ID** | REQ-08                                                                                                                                                                                                                   |
| **Priority**          | Medium                                                                                                                                                                                                                   |
| **Preconditions**     | - User is on a product detail page                                                                                                                                                                                       |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                  |
| **Test Data**         | Product: Hummingbird Printed T-Shirt  <br> Size: L  <br> Color: Black  <br> Quantity: 3                                                                                                                                   |
| **Test Steps**        | 1. Navigate to the product detail page  <br> 2. Select size and color  <br> 3. Set quantity field to **3** using the up arrow or by typing  <br> 4. Click **ADD TO CART**                                                 |
| **Expected Result**   | - Cart modal shows quantity as 3  <br> - Cart total equals unit price × 3  <br> - Cart icon reflects total quantity (3 or more if items already existed)                                                                  |

---

## TC-020 — Update Product Quantity in Cart

| Field                 | Details                                                                                                                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-020                                                                                                                                                                                                                              |
| **Test Name**         | Update Product Quantity in Shopping Cart                                                                                                                                                                                            |
| **Description**       | Verify that a user can change the quantity of an existing item in the shopping cart and that the order summary (subtotal, total) recalculates automatically.                                                                         |
| **Reference Req. ID** | REQ-09                                                                                                                                                                                                                              |
| **Priority**          | High                                                                                                                                                                                                                                |
| **Preconditions**     | - At least one item is already in the shopping cart  <br> - User has navigated to the cart page                                                                                                                                     |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - Cart pre-populated with 1 unit of Hummingbird Printed T-Shirt                                                                                                                       |
| **Test Data**         | New quantity: 2                                                                                                                                                                                                                     |
| **Test Steps**        | 1. Navigate to the shopping cart (click cart icon → **VIEW CART** or proceed)  <br> 2. Locate the quantity field for the existing product  <br> 3. Change the quantity from 1 to **2** using the up arrow or by direct input        |
| **Expected Result**   | - The cart line-item quantity updates to 2  <br> - The subtotal for that item is recalculated (unit price × 2)  <br> - The cart order summary total updates accordingly  <br> - No page error occurs during the update              |

---

## TC-021 — Remove a Product from Cart

| Field                 | Details                                                                                                                                                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-021                                                                                                                                                                                                                    |
| **Test Name**         | Remove a Product from Shopping Cart                                                                                                                                                                                       |
| **Description**       | Verify that a user can remove a product from the shopping cart using the delete (trash) icon and that the cart updates to reflect the removal.                                                                             |
| **Reference Req. ID** | REQ-10                                                                                                                                                                                                                    |
| **Priority**          | High                                                                                                                                                                                                                      |
| **Preconditions**     | - At least one item is in the shopping cart  <br> - User is on the cart page                                                                                                                                              |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - Cart pre-populated with 1 item                                                                                                                                            |
| **Test Data**         | Item to remove: any item in the cart                                                                                                                                                                                      |
| **Test Steps**        | 1. Navigate to the cart page  <br> 2. Locate the product to remove  <br> 3. Click the **trash can / delete icon** next to the product                                                                                      |
| **Expected Result**   | - The selected product is removed from the cart  <br> - The cart quantity counter in the navigation decreases  <br> - If the cart is now empty, an empty cart message is displayed (e.g., *"There are no more items in your cart"*) |

---

## TC-022 — Remove All Items from Cart (Empty Cart State)

| Field                 | Details                                                                                                                                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-022                                                                                                                                                                                               |
| **Test Name**         | Remove All Items — Verify Empty Cart State Display                                                                                                                                                   |
| **Description**       | Verify that when all items are removed from the cart, the system correctly displays an empty cart state with an appropriate message and no order summary.                                             |
| **Reference Req. ID** | REQ-10                                                                                                                                                                                               |
| **Priority**          | Medium                                                                                                                                                                                               |
| **Preconditions**     | - Cart contains exactly one item  <br> - User is on the cart page                                                                                                                                    |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                              |
| **Test Data**         | N/A                                                                                                                                                                                                  |
| **Test Steps**        | 1. Navigate to the cart page with one item  <br> 2. Click the trash icon to remove the last item  <br> 3. Observe the cart state                                                                      |
| **Expected Result**   | - Cart list is empty  <br> - A message is displayed indicating the cart is empty (e.g., *"There are no more items in your cart"*)  <br> - The cart icon in the navigation resets to 0 or disappears |

---

## TC-023 — Checkout as Guest User (Full Flow)

| Field                 | Details                                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-023                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Test Name**         | Full Guest Checkout Process — Personal Info to Order Confirmation                                                                                                                                                                                                                                                                                                                                        |
| **Description**       | Verify that an unregistered (guest) user can complete the full 4-step checkout process and receive an order confirmation.                                                                                                                                                                                                                                                                                 |
| **Reference Req. ID** | REQ-11                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Priority**          | High                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Preconditions**     | - Cart contains at least one item  <br> - User is not logged in                                                                                                                                                                                                                                                                                                                                          |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox  <br> - Cart pre-populated with Hummingbird Printed T-Shirt, size M, color White, qty 1                                                                                                                                                                                                                                                                          |
| **Test Data**         | First name: Alice  <br> Last name: Martin  <br> Email: alice.martin.guest@mailtest.com  <br> Address: 10 Example Street  <br> City: Paris  <br> Postcode: 75001  <br> Country: France  <br> Shipping: Standard Delivery  <br> Payment: Pay by check                                                                                                                                                        |
| **Test Steps**        | 1. Click **PROCEED TO CHECKOUT** from the cart  <br> 2. **Step 1 – Personal Info:** Select **Order as a guest**, fill in first name, last name, email; click **Continue**  <br> 3. **Step 2 – Addresses:** Fill in address fields; click **Continue**  <br> 4. **Step 3 – Shipping:** Select available shipping method; click **Continue**  <br> 5. **Step 4 – Payment:** Select **Pay by check**; click **Order with an obligation to pay** |
| **Expected Result**   | - Order is placed successfully  <br> - User is redirected to an order confirmation page  <br> - A unique order reference number is displayed  <br> - A summary of the order (items, total, delivery address) is shown                                                                                                                                                                                    |

---

## TC-024 — Checkout Address Validation

| Field                 | Details                                                                                                                                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-024                                                                                                                                                                                                    |
| **Test Name**         | Checkout — Address Step Validation with Missing Fields                                                                                                                                                    |
| **Description**       | Verify that the Addresses step of the checkout process validates required fields and prevents progression with missing mandatory address information.                                                       |
| **Reference Req. ID** | REQ-11                                                                                                                                                                                                    |
| **Priority**          | High                                                                                                                                                                                                      |
| **Preconditions**     | - User has passed Step 1 (Personal Information) of checkout  <br> - Cart contains at least one item                                                                                                       |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                   |
| **Test Data**         | Address line: (empty)  <br> City: (empty)  <br> Postcode: (empty)  <br> Country: France                                                                                                                   |
| **Test Steps**        | 1. Proceed to checkout and complete Step 1  <br> 2. On Step 2 (Addresses), leave **Address**, **City**, and **Postcode** fields empty  <br> 3. Click **Continue**                                          |
| **Expected Result**   | - Form submission is blocked  <br> - Validation error messages are shown next to each empty required field  <br> - User remains on the Addresses step  <br> - Checkout does not advance to Shipping step |

---

## TC-025 — Checkout Payment Selection and Order Placement

| Field                 | Details                                                                                                                                                                                                                                                                                     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test Case ID**      | TC-025                                                                                                                                                                                                                                                                                      |
| **Test Name**         | Checkout — Verify Payment Method Selection and Order Submission                                                                                                                                                                                                                             |
| **Description**       | Verify that the payment step presents available payment methods, allows the user to select one, and successfully submits the order to produce a confirmation page.                                                                                                                           |
| **Reference Req. ID** | REQ-11                                                                                                                                                                                                                                                                                      |
| **Priority**          | High                                                                                                                                                                                                                                                                                        |
| **Preconditions**     | - User has completed Steps 1, 2, and 3 of the checkout (Personal Info, Address, Shipping)  <br> - Cart has at least one item                                                                                                                                                                 |
| **Test Setup**        | - Browser: latest stable Chrome/Firefox                                                                                                                                                                                                                                                     |
| **Test Data**         | Payment method: Bank wire (bank transfer)                                                                                                                                                                                                                                                   |
| **Test Steps**        | 1. Complete Steps 1–3 of the checkout  <br> 2. On Step 4 (Payment), review the listed payment options (Bank wire / Pay by check)  <br> 3. Select **Bank wire**  <br> 4. Review the order summary on this page  <br> 5. Click **Order with an obligation to pay**                             |
| **Expected Result**   | - Order is submitted successfully  <br> - A confirmation page displays with the order reference number  <br> - The page acknowledges the chosen payment method (bank wire details if applicable)  <br> - A confirmation email notification is mentioned (even if the demo does not send one) |

---

*End of test cases. Total: 25 test cases covering REQ-01 through REQ-11.*
