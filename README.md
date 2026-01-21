# Manual Software Testing

## In the beginning, let's know the difference between Software vs. Web App vs. Mobile App

**Software** refers to any program that runs on a computer or device to perform tasks. It can be **installed locally** (like Microsoft Word or Photoshop) or run **on servers/cloud**.

**Web app** is a *type* of software that runs **in a web browser** (e.g., Gmail, Trello, Google Docs). It works on both **desktop and mobile browsers**, so no installation is needed.

**Mobile app** is a *type* of software* designed for **smartphones or tablets**, downloaded and installed through app stores (e.g., WhatsApp, Instagram, Spotify).

### Key Differences

| Feature | Software | Web App | Mobile App |
|----------|-----------|----------|-------------|
| **Access** | Installed on OS | Runs in browser (desktop & mobile) | Installed via App Store/Play Store |
| **Platform** | OS-specific (Windows, macOS, etc.) | Cross-platform | Platform-specific (iOS, Android) |
| **Updates** | Manual or automatic install | Instant (on server) | Via store updates |
| **Offline Use** | Often yes | Usually no (unless PWA) | Often yes |
| **Performance** | High, uses local resources | Depends on internet and server | Optimized for mobile hardware |
| **Installation** | Required | Not required | Required |
| **User Interface** | Desktop-oriented | Browser-based | Touchscreen-optimized |

In short:  
- **Software** runs on computers.  
- **Web apps** run in browsers on both desktop and mobile.  
- **Mobile apps** run directly on mobile devices.  
All are software but just built for different environments.

---

Welcome! This repository contains categorized checklists to support web app testing, QA, and documentation.
The following "Index" lists all main testing modules and their sub-sections for quick navigation.

### **1** [Functional Testing](#functional-testing)
- [Search Functionality](#search-functionality)
- [URL Field Validation](#url-field-validation)
- [Form Submissions (with and without required data)](#form-submissions-with-and-without-required-data)
- [Redirects & Navigation](#redirects--navigation)
- [Session Timeout](#session-timeout)
- [Pagination & Sorting](#pagination--sorting)
### **2** [Authentication & User Management](#authentication--user-management)
- [Login Module](#login-module)
- [Login Page (UI/UX, validation, redirects)](#login-page-uiux-validation-redirects)
- [Registration/Sign Up](#registrationsign-up)
- [Forgot Password](#forgot-password)
- [OTP Verification](#otp-verification)
- [CAPTCHA](#captcha)
- [Email Field Validation](#email-field-validation)
- [Mobile Number Field Validation](#mobile-number-field-validation)
- [Error Messages](#error-messages)
### **3** [File & Data Handling](#file-and-data-handling)
- [Upload File/Image (formats, size limits, validation)](#upload-file--image-formats-size-limits-validation)
- [Reports Downloads (PDF, CSV, Excel, etc.)](#reports-downloads-pdf-csv-excel-etc)
### **4** [eCommerce & Transactions](#ecommerce-and-transactions)
- [Product Selection](#product-selection)
- [Cart Button & Cart Summary](#cart-button--cart-summary)
- [Quantity Update](#quantity-update)
- [Payment Gateway Integration](#payment-gateway-integration)
- [Order Confirmation](#order-confirmation)
- [Invoice Generation](#invoice-generation)
### **5** [System & Integration](#system--integration)
- [API Integration Validation](#api-integration-validation)
- [Database Validation (data saved correctly)](#database-validation-data-saved-correctly)
- [Third-Party Service Responses (e.g., OTP, Payment APIs)](#third-party-service-responses-eg-otp-payment-apis)
### **6** [Performance & Security](#performance-and-security)
- 1) [Load Testing (page performance under traffic)](#1-load-testing-page-performance-under-traffic)
- 2) [Stress Testing](#2-stress-testing)
- 3) [Input Validation — SQL Injection (SQLi) & Cross-Site Scripting (XSS)](#3-input-validation--sql-injection-sqli--cross-site-scripting-xss)
- 4) [Password Encryption](#4-password-encryption)
- 5) [Session Management (logout, session expiration)](#5-session-management-logout-session-expiration)
- [Operational & Testing Best Practices](#operational--testing-best-practices)

## **7** [Compatibility & Accessibility](#compatibility--accessibility)
- 1. [Browser Compatibility (Chrome, Firefox, Safari, Edge)](#1-browser-compatibility-chrome-firefox-safari-edge)
- 2. [Mobile Responsiveness](#2-mobile-responsiveness)
- 3. [Accessibility (Keyboard navigation, ARIA labels)](#3-accessibility-keyboard-navigation-aria-labels)

## **8** [UI/UX & Design](#uiux-design)
- [Header Section](#header-section)
- [Footer Section](#footer-section)
- [Buttons (Primary, Secondary, Disabled states)](#buttons-primary-secondary-disabled-states)
- [Radio Buttons](#radio-buttons)
- [Checkboxes](#checkboxes)
- [Dropdown Menus](#dropdown-menus)
- [Tooltips](#tooltips)
- [Hyperlinks](#hyperlinks)
- [Delete Button](#delete-button)
- [GUI](#gui)

---

# Functional Testing

## Search Functionality

### **1. Field Presence & UI Verification**

- [ ]  Verify the **search field is visible**, properly aligned, and responsive.
- [ ]  Verify **placeholder text** is present in the search box.
- [ ]  Verify **placeholder text grammar and spelling** are correct.
- [ ]  Verify a **search icon** is visible within or beside the field.
- [ ]  Verify **cursor focus** appears when clicking the search icon or field.

### **2. Search Behavior**

- [ ]  Verify **valid keyword search** returns accurate results.
- [ ]  Verify pressing **Enter key** triggers the search successfully.
- [ ]  Verify clicking the **search button/icon** triggers the search successfully.
- [ ]  Verify the user can **paste keywords** into the field using the mouse (right-click → Paste).

### **3. Invalid & Blank Inputs**

- [ ]  Verify **invalid keywords** display a proper *“No results found”* or similar message.
- [ ]  Verify **blank input** displays a proper error or empty state message.

### **4. Performance & Loading**

- [ ]  Measure and verify **response time** for generating search results.
- [ ]  Verify a **loader/spinner** appears when results take noticeable time to load.

### **5. Search Results Verification**

- [ ]  Verify **results are displayed in correct order** (relevance, date, or defined criteria).
- [ ]  Verify **pagination** appears if results span multiple pages.
- [ ]  Verify **pagination controls** (Next, Previous, specific page numbers) work properly.

### **6. Suggestions & Autocomplete**

- [ ]  Verify **search suggestions** appear as the user types (if feature exists).
- [ ]  Verify **auto-suggestions** display relevant or popular queries.
- [ ]  Verify **max/min character limits** for keyword input are enforced correctly.
- [ ]  Verify **related keywords** are displayed below search results (if implemented).

### **7. Dynamic Content & Indexing**

- [ ]  Verify that **newly added content/items/tools** are searchable using related keywords.

## URL Field Validation

### **1. Field Accessibility & Input**

- [ ]  Verify the URL input field is clickable and gains focus.
- [ ]  Verify the user can type URLs manually in the field.
- [ ]  Verify pasting a URL using **keyboard shortcut (Ctrl+V)** works.
- [ ]  Verify pasting a URL using **mouse right-click → Paste** works.
- [ ]  After pasting a valid URL and pressing **Enter**, the process should start.

### **2. Valid URL Formats**

- [ ]  Check with a valid HTTPS URL (e.g., `https://onlinetestcase.com/radio-buttontest-cases/`).
- [ ]  Check with a valid HTTP URL.
- [ ]  Validate URLs with various TLDs/extensions (`.in`, `.be`, `.xyz`, `.site`, etc.).
- [ ]  Verify URLs with **maximum allowed length** are accepted.
- [ ]  Verify URLs with **minimum valid length** are accepted.

### **3. Whitespace Handling**

- [ ]  Leading spaces in the URL should be **ignored**.
- [ ]  Trailing spaces should be **trimmed**.
- [ ]  URLs containing **spaces within** should be rejected or sanitized with a clear error.

### **4. Missing or Partial URLs**

- [ ]  Input only domain name without protocol (`example.com`).
- [ ]  Input URL missing TLD (`https://example`).
- [ ]  Input only site name without dot (`example`).
- [ ]  Input only extension (`https://www.com`).
- [ ]  Leave field blank and click the button — should show *“No URL found!”* or equivalent error.

### **5. Special Cases & Encoded URLs**

- [ ]  Verify valid IP address input (e.g., `https://192.168.1.1`).
- [ ]  Verify URL containing **parameters** (e.g., `?id=123&ref=abc`).
- [ ]  Verify **encoded URLs** (e.g., `%20` or `%2F` sequences).
- [ ]  Verify URLs with **forward slashes variations** (extra or missing `/`).
- [ ]  Verify URLs containing **special characters** (e.g., `#`, `@`, `?`, `&`).
- [ ]  Verify **anchor URLs** (e.g., `https://example.com/#section`).

### **6. Error Handling**

- [ ]  Ensure an error appears for **blank** or **space-only** input.
- [ ]  Ensure invalid URLs trigger a clear **error message**.
- [ ]  Verify that pressing Enter or clicking the button does **not** proceed for invalid input.

## Form Submissions (with and without required data)

### **1. Field Presence & Basic Functionality**

- [ ]  Verify all **form fields** are visible, labeled correctly, and properly aligned.
- [ ]  Verify all **required fields** are marked with an asterisk (*) or suitable indicator.
- [ ]  Verify users can **enter data** manually in each input field.
- [ ]  Verify users can **paste** data into input fields.
- [ ]  Verify form can be submitted using **both mouse click** and **Enter key** (if applicable).

### **2. Submitting with Required Data**

- [ ]  Verify the form **submits successfully** when all required fields are filled correctly.
- [ ]  Verify the **success message or confirmation** appears after valid submission.
- [ ]  Verify the **data is saved or processed correctly** in the backend/database.
- [ ]  Verify user is **redirected or notified** as per design (e.g., thank-you page, dashboard).
- [ ]  Verify form **clears or resets** after successful submission if applicable.

### **3. Submitting Without Required Data**

- [ ]  Verify submitting the form **without required fields** displays proper validation messages.
- [ ]  Verify **error messages** appear beside or below the missing fields.
- [ ]  Verify error messages have **clear and correct grammar**.
- [ ]  Verify form **does not submit or reload** when required data is missing.
- [ ]  Verify **highlighting or focus** appears on the empty required fields.

### **4. Validation Checks**

- [ ]  Verify **field-specific validation** (e.g., email, URL, phone number, numeric, date).
- [ ]  Verify **invalid format** input triggers a proper error message.
- [ ]  Verify **min/max character limits** are enforced on text fields.
- [ ]  Verify **dropdowns**, **checkboxes**, and **radio buttons** must have valid selections before submission.
- [ ]  Verify **special characters** or **SQL injections** are handled safely (no crash or data exposure).

### **5. User Experience**

- [ ]  Verify **auto-focus** moves to the next field or first invalid field when pressing Enter or Tab.
- [ ]  Verify **form reset button** clears all input fields if present.
- [ ]  Verify **loading indicator** or **disabled button** appears during submission.
- [ ]  Verify **duplicate submissions** are prevented (e.g., double-click protection).

### **6. Edge & System Behavior**

- [ ]  Verify submission behavior when **session expires** before submitting.
- [ ]  Verify submission behavior with **slow or unstable network connection**.
- [ ]  Verify form handles **empty optional fields** correctly (no validation error).
- [ ]  Verify **server-side validation** prevents submission even if client-side validation is bypassed.

## Redirects & Navigation

### **1. General Navigation**

- [ ]  Verify all **navigation links, buttons, and menus** are visible and clickable.
- [ ]  Verify clicking any navigation element **takes the user to the correct page**.
- [ ]  Verify all **URLs update correctly** in the browser address bar after navigation.
- [ ]  Verify **browser Back and Forward buttons** work properly for all navigations.
- [ ]  Verify user can **refresh the page** without errors or session loss (if expected).

### **2. Redirects**

- [ ]  Verify **HTTP redirects (301/302)** occur correctly for outdated or moved URLs.
- [ ]  Verify redirects use **secure protocol (HTTPS)** when available.
- [ ]  Verify redirect behavior when accessing **restricted pages** without authentication (e.g., redirected to login).
- [ ]  Verify after successful login, the user is redirected **back to the intended page**.
- [ ]  Verify redirects do **not form loops** (no infinite redirect or multiple hops).
- [ ]  Verify **temporary redirects** return to the previous state if reloaded (e.g., after password reset).
- [ ]  Verify **external links** open in a new tab (if designed to).

### **3. Navigation Accuracy**

- [ ]  Verify **main menu items** navigate to their respective pages.
- [ ]  Verify **submenus or dropdowns** open and link correctly.
- [ ]  Verify **breadcrumb navigation** (if present) accurately reflects the current path.
- [ ]  Verify **logo click** redirects to the homepage.
- [ ]  Verify **footer links** navigate to correct sections (e.g., Terms, Privacy Policy, Contact).

### **4. User State & Access Control**

- [ ]  Verify authenticated users cannot access **login or signup pages** again unless logged out.
- [ ]  Verify unauthorized users cannot access **protected routes** (redirects to login or 403 page).
- [ ]  Verify logged-out users are properly **redirected after session timeout**.
- [ ]  Verify **role-based redirects** (e.g., admin vs user dashboards) function correctly.

### **5. Performance & UX**

- [ ]  Verify **page load time** after navigation or redirect is within acceptable limits.
- [ ]  Verify **loading indicators or transitions** appear smoothly between navigations.
- [ ]  Verify **active navigation state** (highlight, underline, etc.) reflects the current page.
- [ ]  Verify **no broken links or 404 errors** exist in any navigation path.

## Session Timeout

### **1. Session Configuration & Duration**

- [ ]  Verify that the **default session timeout duration** matches the defined requirement (e.g., 15 or 30 minutes).
- [ ]  Verify the session timer **starts from the last user interaction** (not from login time).
- [ ]  Verify **no unexpected logouts** occur before the timeout duration expires.

### **2. Idle Session Behavior**

- [ ]  Verify that when the user stays **idle beyond the timeout period**, the session expires automatically.
- [ ]  Verify the system **logs the user out** and redirects to the **login page** after timeout.
- [ ]  Verify an appropriate **timeout notification message** appears (e.g., “Your session has expired. Please log in again.”).
- [ ]  Verify user data is **not lost or exposed** after timeout (e.g., cached sensitive data cleared).

### **3. Warning & Countdown (If Applicable)**

- [ ]  Verify that a **session timeout warning popup** appears before the session expires.
- [ ]  Verify the **countdown timer** (if available) accurately reflects the remaining time.
- [ ]  Verify clicking **“Stay Logged In”** or any user action resets the session timer.
- [ ]  Verify **no background activity** extends the session unless it’s user-initiated.

### **4. Post-Timeout Behavior**

- [ ]  Verify attempting any **action after timeout** redirects the user to the login page.
- [ ]  Verify **browser refresh** after timeout also redirects to login.
- [ ]  Verify that after re-login, the user is **redirected to the correct intended page** or homepage as per design.
- [ ]  Verify **session cookies or tokens** are invalidated after timeout (cannot be reused).

### **5. Security & Edge Cases**

- [ ]  Verify **session timeout** functions consistently across browsers and tabs.
- [ ]  Verify **session tokens** are securely regenerated upon re-login.
- [ ]  Verify **multiple logins** on different browsers/devices handle timeouts independently.
- [ ]  Verify **inactivity timeout** behaves correctly even if user keeps the tab open but inactive.
- [ ]  Verify **sensitive actions** (e.g., profile edit, payment) are blocked post-timeout until re-authenticated.

## Pagination & Sorting

### **1. Pagination Display & Navigation**

- [ ]  Verify **pagination controls** (Next, Previous, First, Last, page numbers) are visible and properly aligned.
- [ ]  Verify **default page** loads correctly (usually page 1).
- [ ]  Verify clicking **Next** navigates to the next set of results.
- [ ]  Verify clicking **Previous** navigates to the prior set of results.
- [ ]  Verify **First and Last** page buttons work as expected.
- [ ]  Verify **specific page numbers** can be clicked to navigate directly.
- [ ]  Verify **active page number** is highlighted or styled differently.
- [ ]  Verify **pagination state** persists after refresh or returning from detail view (if applicable).
- [ ]  Verify pagination still functions correctly after performing a **search or filter action**.

### **2. Result Count & Boundaries**

- [ ]  Verify the correct **number of items per page** is displayed (as per requirement, e.g., 10, 20, 50).
- [ ]  Verify **total result count** and **page count** are displayed correctly.
- [ ]  Verify pagination handles **last page** gracefully (no empty result pages).
- [ ]  Verify behavior when there are **no results** (pagination should be hidden or disabled).
- [ ]  Verify behavior when results **exactly match the page limit** (no unnecessary extra page).

### **3. Sorting Functionality**

- [ ]  Verify **sorting options** (e.g., A–Z, Date, Price) are visible and selectable.
- [ ]  Verify sorting works correctly for **text, numeric, and date fields**.
- [ ]  Verify sorting **order toggles** correctly between ascending and descending.
- [ ]  Verify sorted results remain **consistent across pages**.
- [ ]  Verify **sorting + pagination** together work seamlessly (page change does not reset sorting).
- [ ]  Verify sorting resets when **filters or new searches** are applied (if designed to).
- [ ]  Verify **default sorting order** is applied when the page first loads.

### **4. Usability & Edge Cases**

- [ ]  Verify **loader or transition indicator** appears when changing pages or sorting.
- [ ]  Verify pagination is **accessible via keyboard (Tab, Enter)**.
- [ ]  Verify pagination and sorting are **responsive** on mobile and different screen sizes.
- [ ]  Verify **invalid page number entries** (manual URL edits) redirect or handle gracefully.
- [ ]  Verify **sorting and pagination preferences** persist during the session (if applicable).

---

[^        back to top        ^](#manual-software-testing)

# Authentication & User Management

## Login Module

### **1. Field Behavior & UI**

- [ ]  Verify that credentials remain in the fields after selecting “Remember Me” and revisiting the login page.
- [ ]  Verify the password is masked (encrypted) while typing.
- [ ]  Verify that an “eye” icon exists in the password field to toggle visibility.
- [ ]  Verify that clicking the “eye” icon correctly shows/hides the password.
- [ ]  Verify proper line spacing for password fields on macOS.
- [ ]  Verify the login form layout and spacing meet design specifications.

### **2. Valid Login Scenarios**

- [ ]  Verify login with correct credentials redirects the user to the dashboard.
- [ ]  Verify login by pressing **Enter** works as expected.
- [ ]  Verify login by clicking the **Login** button works as expected.
- [ ]  Verify email verification is required before accessing the dashboard.
- [ ]  Verify all form elements are accessible using the **Tab** key.

### **3. Error Handling**

- [ ]  Verify an error message appears when only the email is entered.
- [ ]  Verify an error message appears when only the password is entered.
- [ ]  Verify an error message appears for invalid credentials.
- [ ]  Verify an error message appears for invalid email format.
- [ ]  Verify the text, grammar, and spelling of all error messages.
- [ ]  Verify invalid login attempts do not cause infinite loading.

### **4. Security**

- [ ]  Verify CAPTCHA is present to prevent bot attacks.
- [ ]  Verify brute-force protection limits repeated failed login attempts.
- [ ]  Verify SQL injection prevention on the login form.
- [ ]  Verify session timeout after inactivity (user cannot stay logged in indefinitely).
- [ ]  Verify rate limiting is applied on login attempts.

### **5. Session Management**

- [ ]  Verify the logged-in user remains authenticated after closing and reopening the browser (if “Remember Me” is enabled).
- [ ]  Verify the session expires correctly after the timeout period.
- [ ]  Verify that clicking the browser **Back** button after login does not log the user out.
- [ ]  Verify that copying the dashboard URL and opening it in a new tab redirects unauthenticated users to the login page.

### **6. Social & Third-Party Login**

- [ ]  Verify Google and other social login options function correctly in both normal and private browser modes.
- [ ]  Verify that after successful social login, all features work as expected.
- [ ]  Verify that post-login, elements like “Sign Up” or “Try Now” are hidden.

## **Login Page (UI/UX, validation, redirects)**

### **1. Page Rendering & Navigation**

- [ ]  Verify the login page appears correctly after clicking on a **Login** link or button.
- [ ]  Verify that the **page title** of the login screen is displayed correctly.
- [ ]  Verify that the **login page loads without visual or layout issues**.

### **2. Element Presence**

- [ ]  Verify that all required login fields and elements are present:
    - Username / Email field
    - Password field
    - Login button
    - Remember Me checkbox
    - Forgot Password link
    - Social login buttons (if applicable)

### **3. UI Design & Layout**

- [ ]  Verify alignment and positioning of all elements on the login page.
- [ ]  Verify that the size, color, font, and style of UI elements match design specifications.
- [ ]  Verify that the login page layout is consistent across major browsers.
- [ ]  Verify that the login page is **responsive** and adapts properly to different screen sizes and devices.

### **4. Usability & Accessibility**

- [ ]  Verify that the **cursor is automatically placed** in the username/email field when the page loads.
- [ ]  Verify that the **Remember Me** checkbox is clickable and can also be toggled by clicking on its label text.
- [ ]  Verify that when the **Remember Me** checkbox is selected, it appears visually checked.

## **Registration/Sign Up**

### **1. Form Elements & Layout**

- [ ]  Verify all registration-related fields are present on the registration form.
- [ ]  Verify example or dummy placeholder text is shown in each field to guide the user.
- [ ]  Verify spelling and grammar for all text and labels on the registration page.
- [ ]  Verify users can navigate through all form fields using the **Tab** key.

### **2. Field Validations**

- [ ]  Verify that clicking **Submit** with blank inputs shows validation error messages.
- [ ]  Verify that required fields not filled in display appropriate validation errors.
- [ ]  Verify that entering blank spaces in fields and clicking **Register** shows an error message.
- [ ]  Verify that all possible validations are handled on the **client-side** when possible.

### **3. Password Rules & Behavior**

- [ ]  Verify password validation:
    - Minimum 8 and maximum 16 characters.
    - At least one uppercase letter.
    - At least one number.
    - At least one special character.
- [ ]  Verify that passwords entered are masked (displayed as asterisks `**`).
- [ ]  Verify password and confirm password fields have an **eye icon** for visibility toggle.
- [ ]  Verify that clicking the eye icon correctly shows/hides passwords in both fields.
- [ ]  Verify validation ensures **password** and **confirm password** fields match.

### **4. Email Validation & Behavior**

- [ ]  Verify that only valid email formats are accepted during registration.
- [ ]  Verify that registering with an already registered email address shows an appropriate error.
- [ ]  Verify that adding a plus sign (e.g., `useractual+1@gmail.com`) to an existing email is treated as the same unique email and not a new account.

### **5. CAPTCHA & Security**

- [ ]  Verify CAPTCHA is present (visible or hidden) to prevent bot registrations.
- [ ]  Verify password data is protected and encrypted.

### **6. Email Verification**

- [ ]  Verify that an email verification link is sent successfully after registration.
- [ ]  Verify that the user cannot access protected features or dashboards before verifying their email.
- [ ]  Verify the user is informed to check the spam folder if the email is not found in the inbox.
- [ ]  Verify that a **Resend Link** option is available for users who did not receive the verification email.
- [ ]  Verify that the resend link becomes disabled or limited (e.g., after 5 attempts).

### **7. Form Behavior**

- [ ]  Verify that user-entered data remains in the fields if validation fails (client-side validation).
- [ ]  Verify users can successfully register using valid credentials.
- [ ]  Verify consistent form behavior and no data loss when switching between registration and other pages.

## **Forgot Password**

### **1. Link & Navigation**

- [ ]  Verify that a **“Forgot Password”** link is present on the login screen.
- [ ]  Verify that clicking the **“Forgot Password”** link opens the **Forgot Password** page.
- [ ]  Verify that the heading displayed on the Forgot Password screen is “Forgot Password”.

### **2. Form Elements**

- [ ]  Verify that an **Email** field is present on the Forgot Password page.
- [ ]  Verify that a **Submit** button is present on the page.
- [ ]  Verify that the **entire button area** is clickable, not just the text.

### **3. Field Validations**

- [ ]  Verify that the email field has **proper email format validation**.
- [ ]  Verify an error message appears when submitting without entering an email.
- [ ]  Verify an error message appears when entering **spaces only** and clicking Submit.
- [ ]  Verify an error message appears when entering an **unregistered email address**.
- [ ]  Verify that the error message for unregistered emails is **clear and meaningful**.

### **4. Email Delivery & Content**

- [ ]  Verify that a **confirmation message** (e.g., “Check your email to recover your password”) is displayed after entering a registered email and clicking Submit.
- [ ]  Verify that the user receives a **password reset email** after submitting a valid email.
- [ ]  Verify that the reset email is received from [**info@sitename.com**](mailto:info@sitename.com).
- [ ]  Verify that the **subject** of the email is “Your New Password”.
- [ ]  Verify that the email arrives in the **Inbox**, not the Spam folder.

### **5. Reset Link & Security**

- [ ]  Verify that the password reset link **expires after a certain time** (as per specification).
- [ ]  Verify that the reset link becomes **disabled after multiple clicks** or use attempts.
- [ ]  Verify that password reset actions are properly stored and logged in the **database**.

### **6. Password Update Behavior**

- [ ]  Verify that after resetting the password, the user is **logged out from all browsers and devices**.
- [ ]  Verify that the user can log in **successfully with the new password**, not the old one.
- [ ]  Verify that a message prompts the user to **change the temporary password** if a temporary one is sent via email.

## **OTP Verification**

### **1. OTP Generation**

- [ ]  Verify that a valid and correct OTP is generated.
- [ ]  Verify that the OTP is valid for **one-time use only**.
- [ ]  Verify that the number of OTPs generated does not exceed the required limit.
- [ ]  Verify that the number of OTPs generated is not less than required.

### **2. OTP Delivery**

- [ ]  Verify that the OTP is **sent successfully** to the user.
- [ ]  Verify that the OTP is received **within the expected time** via email.
- [ ]  Verify that the OTP is received **within the expected time** via SMS/mobile.
- [ ]  Verify that the application can **auto-fetch OTP** from messages (if applicable).
- [ ]  Verify that users can **manually enter** the OTP if auto-fetch is not supported.

### **3. OTP Validation**

- [ ]  Verify that entering a **valid OTP** is accepted successfully.
- [ ]  Verify that an **informational message** (e.g., “OTP verified successfully”) is displayed for valid OTPs.
- [ ]  Verify that an **error message** appears when entering an **invalid OTP**.
- [ ]  Verify that the **error message text** for invalid OTP is correct and user-friendly.
- [ ]  Verify that the OTP **expires** after the allowed time duration.
- [ ]  Verify that the system **does not accept expired OTPs**.

### **4. OTP Resend & Rate Limiting**

- [ ]  Verify that the user can request a **new OTP** by clicking the **Resend Code** button or link.
- [ ]  Verify that a new OTP is sent successfully when the user requests again.
- [ ]  Verify that multiple resend requests are **limited** (e.g., maximum five attempts).
- [ ]  Verify that the user is **temporarily blocked** if resending OTP repeatedly beyond the allowed limit.

### **5. OTP Format & Security**

- [ ]  Verify whether the OTP is **case-sensitive** (if alphanumeric).
- [ ]  Verify whether the OTP format is **numeric** or **alphanumeric**, as per specifications.

## **CAPTCHA**

### **1. Loading & Timeout**

- [ ]  Verify the **time taken for CAPTCHA** to load on the webpage.
- [ ]  Verify the **timeout duration** after which CAPTCHA becomes unchecked or expires.
- [ ]  Verify that CAPTCHA does not show an **invalid error** when tested on **slow internet** connections.

### **2. Behavior & Validation**

- [ ]  Verify that when CAPTCHA is solved and **Submit** is clicked twice, it does not trigger an invalid CAPTCHA error.
- [ ]  Verify that a **new CAPTCHA** appears on each **page reload**.
- [ ]  Verify that the **webpage accepts a valid CAPTCHA** entry.
- [ ]  Verify that a **new CAPTCHA is generated** when the user enters an incorrect CAPTCHA.

### **3. Error Handling**

- [ ]  Verify an **error message** appears if the CAPTCHA is **not filled** before submitting.
- [ ]  Verify an **error message** appears if the CAPTCHA is **incorrectly filled**.
- [ ]  Verify an **error message** appears if the CAPTCHA is **partly filled**.
- [ ]  Verify an **error message** appears when the **CAPTCHA times out**.
- [ ]  Verify that **error messages are meaningful and clear**.

### **4. Security & Rate Limiting**

- [ ]  Verify that the **user IP is blocked** after exceeding the allowed number of invalid CAPTCHA attempts.
- [ ]  Verify that CAPTCHA is **displayed on all required web pages**.

### **5. UI/UX & Accessibility**

- [ ]  Verify that the CAPTCHA is **properly aligned** with other page elements.
- [ ]  Verify CAPTCHA behavior and visibility when **ad blockers** are enabled.
- [ ]  Verify that CAPTCHA **functions correctly even with ad blockers active**.
- [ ]  Verify that the user can **request a new CAPTCHA** without reloading the page (if feature supported).
- [ ]  Verify whether an **audio CAPTCHA option** is available (as per accessibility or requirement).

## **Email Field Validation**

### 1. Design Test Cases

- [ ]  Verify the email field is present on the page.
- [ ]  Verify whether label text is shown with the email field or not.
- [ ]  Verify the label text is aligned properly with the email field.
- [ ]  Verify the placeholder text in the email field is added and descriptive.

### 2. Functional Test Cases

- [ ]  Verify the email address field is accessible when clicked.
- [ ]  Check that users can type an email in the field.
- [ ]  Verify that the user can paste an email address using keyboard keys (`Ctrl + V`).
- [ ]  Verify that the user can paste an email address using the mouse (right-click → paste).
- [ ]  Verify that proper validation is implemented for the email field.
- [ ]  Verify an appropriate error message is shown when the user enters an invalid email address.

### 3. Positive Test Cases

- [ ]  Validate the email field by entering a valid email address (e.g., `abc@gmail.com`).
- [ ]  Verify the email address must contain the `@` symbol.
- [ ]  Verify that the field accepts emails containing a plus sign (`+`) in the address.
- [ ]  Verify that an email address must contain a valid domain (e.g., `abc@gmail.com`).
- [ ]  Ensure there is at least one dot (`.`) in the email address.
- [ ]  Verify that an email with a subdomain (e.g., `abc@mail.company.com`) is accepted.
- [ ]  Check that an email address can have up to two dots in case of subdomains.
- [ ]  Verify that special characters (allowed by RFC standards) are accepted.
- [ ]  Verify that numbers within the email address are valid.
- [ ]  Verify that an email address can contain an IP address (e.g., `user@[192.168.1.1]`).
- [ ]  Verify that emails with square brackets are handled correctly if allowed.
- [ ]  Verify that emails containing quotes (`" "`) are accepted if valid.
- [ ]  Verify that emails containing dashes () or underscores (`_`) are considered valid.

## **Mobile Number Field Validation**

### 1. Field Appearance & UI Behavior

- [ ]  Verify that the mobile number field displays the accepted format as placeholder text for user guidance.
- [ ]  Verify whether country flags are shown beside the mobile number field.
- [ ]  Verify that the corresponding country code is displayed along with the flag.
- [ ]  Verify that the mobile number field layout and alignment are consistent with other input fields.

### 2. Input Handling

- [ ]  Verify that the field accepts a valid mobile number.
- [ ]  Verify that the field rejects alphabets when entered.
- [ ]  Verify that the field rejects special characters when entered.
- [ ]  Verify the system behavior when fewer digits than required are entered.
- [ ]  Verify the system behavior when more digits than allowed are entered.
- [ ]  Verify whether the field accepts spaces between digits as per requirements.
- [ ]  Verify that blank input triggers an appropriate error message.
- [ ]  Verify that entering only spaces triggers an appropriate error message.

### 3. Data Interaction & Validation

- [ ]  Verify that the user can copy and paste a mobile number into the field.
- [ ]  Verify that the correct number is stored in the database after clicking **Save** or **Next**.
- [ ]  Verify that pressing **Enter** after input also saves the mobile number.

### 4. Error & Feedback Messages

- [ ]  Verify that proper validation messages appear for invalid, incomplete, or excessive digits.
- [ ]  Verify that error messages are clearly worded and easy to understand.

## **Error Messages**

### 1. Content Quality

- [ ]  Verify spelling in all error messages is correct.
- [ ]  Verify grammar in all error messages is correct.
- [ ]  Verify error messages are concise, clear, and easily understood.
- [ ]  Verify error messages do not blame the user and are politely worded.
- [ ]  Verify error messages include actionable instructions so the user knows next steps.
- [ ]  Verify consistency of phrasing and terminology across all error messages.

### 2. Tone & Style

- [ ]  Verify a consistent casing style is used for error messages (sentence case / Title Case / UPPERCASE) as per spec.
- [ ]  Verify tone is friendly and non-accusatory.
- [ ]  Verify use of punctuation and capitalization follows style guidelines.

### 3. Display & Visuals

- [ ]  Verify error message position is correctly aligned relative to the related field or component.
- [ ]  Verify color usage follows design rules (e.g., red for errors, blue/green for info/confirmation).
- [ ]  Verify the size, font, and contrast of error text meet accessibility and design specs.
- [ ]  Verify the error icon (if any) is displayed and aligned with the message.
- [ ]  Verify the duration an error message is shown matches the spec (sticky vs. auto-dismiss).

### 4. Behavior & Interaction

- [ ]  Verify error message for blank input is shown when required fields are empty.
- [ ]  Verify user can still interact with the form/app after an error appears (no UI freeze).
- [ ]  Verify error messages clear or update appropriately once the user fixes the issue.
- [ ]  Verify clicking or focusing the related field brings attention to the error and allows correction.
- [ ]  Verify that long error messages wrap or truncate properly without breaking the layout.

### 5. Validation-Specific Errors

- [ ]  Verify error message for invalid email format is shown and meaningful.
- [ ]  Verify error message for invalid URL is shown and meaningful.
- [ ]  Verify error message for invalid captcha is shown.
- [ ]  Verify error message is shown if captcha fails to load.
- [ ]  Verify error message for file upload errors:
    - [ ]  blank file upload attempted
    - [ ]  unsupported file type
    - [ ]  file size exceeds maximum limit
    - [ ]  file exceeds allowed quantity
- [ ]  Verify error for minimum-content or minimum-words not met is shown.
- [ ]  Verify error for maximum/upper-limit violations is shown and clear.
- [ ]  Verify partially completed inputs (e.g., partially filled captcha) show an appropriate error.

### 6. Consistency & Formatting

- [ ]  Verify the same error message format (prefixes, icons, spacing) is used across screens.
- [ ]  Verify alignment and spacing of error blocks is consistent between pages and components.

### 7. Server & System Errors

- [ ]  Verify a user-friendly 500 (server error) page is displayed when server errors occur.
- [ ]  Verify server error messages do not reveal sensitive system or stack-trace information.
- [ ]  Verify error messages log details for debugging while showing minimal, safe info to users.

### 8. Accessibility & UX

- [ ]  Verify screen readers announce error messages and link to the associated field (aria attributes).
- [ ]  Verify keyboard users can navigate to and dismiss or correct errors without a mouse.
- [ ]  Verify color is not the only means of conveying an error (include text and/or icon).
- [ ]  Verify error messages meet contrast requirements for readability.

### 9. Timing, Retry & Limits

- [ ]  Verify timeouts and expiry messages are shown when relevant (e.g., OTP or captcha expiry).
- [ ]  Verify messages for retry limits (e.g., resend email/captcha attempts) are clear and actionable.
- [ ]  Verify rate-limit / block messages are informative and include guidance (wait time, support contact).

### 10. Confirmation & Success Messages

- [ ]  Verify confirmation messages (e.g., "Check your email") are shown after successful actions and distinct from errors.
- [ ]  Verify confirmation messages follow the same style and accessibility rules as error messages.

### 11. Localization & Edge Cases

- [ ]  Verify error messages are localized correctly for all supported languages.
- [ ]  Verify special characters and RTL/LTR rendering do not break error message layout.
- [ ]  Verify messages for unusual inputs (quotes, brackets, IPs) remain readable and correct.

---

[^        back to top        ^](#manual-software-testing)

# File and Data Handling

## **Upload File / Image (formats, size limits, validation)**

- [ ]  Verify the **Upload** button/link is present on the page as per design.
- [ ]  Verify the entire upload control (button area + text + icon) is clickable.
- [ ]  Verify upload button text and icon match the design and the icon is aligned.
- [ ]  Verify clicking **Upload** opens the file picker dialog.
- [ ]  Verify the **Cancel** button in the file picker/modal closes it and aborts upload.
- [ ]  Verify users can **select and upload a single file** successfully.
- [ ]  Verify users can **select and upload multiple files at once** if supported.
- [ ]  Verify upload order is preserved (files listed in the same order as selected/uploaded).
- [ ]  Verify only **allowed file types** can be uploaded (e.g., .doc, .docx, .pdf, .jpg, .png).
- [ ]  Verify a clear error message is shown for **unsupported file types**.
- [ ]  Verify a clear error message is shown when **number of files exceeds** allowed limit.
- [ ]  Verify a clear error message is shown when **file size exceeds** allowed limit.
- [ ]  Verify an error message is shown for an **empty file** (0 bytes) upload attempt.
- [ ]  Verify uploading a file shows a **loader / progress indicator** during upload.
- [ ]  Verify there is a persistent **upload status/indicator** (progress, success, failure) after upload.
- [ ]  Verify file name is displayed after upload and **matches the original file name**.
- [ ]  Verify file **extension** is displayed alongside the file name (if applicable).
- [ ]  Verify file **size** is displayed and is accurate.
- [ ]  Verify long file names are handled (truncated with ellipsis `...`) without breaking layout.
- [ ]  Verify drag-and-drop upload works for supported file types.
- [ ]  Verify dropped files **do not open in the browser** (no inline rendering/navigation).
- [ ]  Verify dropped files **do not trigger a download** of the source file.
- [ ]  Verify behavior when uploading a **password-protected / locked file**: prompt for password if supported.
- [ ]  Verify that entering the **correct password** for a protected file allows upload/processing.
- [ ]  Verify an appropriate error message appears for an **incorrect password** on a locked file.
- [ ]  Verify server-side validation rejects invalid files (type/size/content) even if client-side validation is bypassed.
- [ ]  Verify the uploaded file is **saved correctly in the database/storage** and path/reference is persisted.
- [ ]  Verify uploaded files are scanned/validated for malicious content if required by security policy.
- [ ]  Verify file upload failures provide meaningful error text and a retry option.
- [ ]  Verify user can **remove/delete** an uploaded file from the upload list before final submission.
- [ ]  Verify appropriate accessibility features (labels, aria-live for progress, keyboard support) are implemented for upload controls.

## **Reports Downloads (PDF, CSV, Excel, etc.)**

- [ ]  Verify download links/buttons for each report type (PDF, CSV, Excel) are present and match design.
- [ ]  Verify clicking the download control initiates the correct file generation and download.
- [ ]  Verify downloaded file **format** matches the selected type (PDF, .csv, .xlsx).
- [ ]  Verify downloaded file **name** follows naming conventions (includes date, report type if required).
- [ ]  Verify file **content** matches what is displayed on the page (data completeness and correctness).
- [ ]  Verify file **size** is reasonable and does not exceed expected limits.
- [ ]  Verify partial or large downloads show a progress indicator where applicable.
- [ ]  Verify download resumes or fails gracefully on network interruptions (where applicable).
- [ ]  Verify access controls: only authorized users can download specific reports.
- [ ]  Verify the downloaded file opens correctly in the target application (PDF reader, Excel, text editor).
- [ ]  Verify CSV/Excel column headers, delimiters, encoding (UTF-8) and data formats (dates, numbers) are correct.
- [ ]  Verify sensitive data is masked/redacted in downloads if required by policy.
- [ ]  Verify downloads do not expose server stack traces or sensitive internal info.
- [ ]  Verify downloads work across supported browsers and do not get blocked by common browser settings or pop-up blockers.
- [ ]  Verify any compressions (ZIP) are correct and files inside the archive are intact.
- [ ]  Verify retention rules: downloaded report copies are not stored unintentionally on the server beyond policy.

---

[^        back to top        ^](#manual-software-testing)

# eCommerce and Transactions

## Product Selection

### **1. Product Display & Visibility**

- [ ]  Verify **all products** are visible on the listing page.
- [ ]  Verify each product displays **image, title, price, and short description**.
- [ ]  Verify **product thumbnails** are clear, properly aligned, and load correctly.
- [ ]  Verify **hover effects** (if any) display correct actions like “Add to Cart” or “View Details.”
- [ ]  Verify products are **clickable** and navigate to their **individual product detail pages**.

### **2. Product Detail Page**

- [ ]  Verify product detail page displays **full product information** (title, price, description, SKU, stock status).
- [ ]  Verify product **images can be zoomed or viewed in gallery mode** if supported.
- [ ]  Verify **price and discount details** (if any) match the listing page.
- [ ]  Verify **specifications, reviews, and additional info tabs** function properly.
- [ ]  Verify user can **select product attributes** (size, color, variant, etc.) before adding to cart.
- [ ]  Verify selecting a variant updates the **price, stock, and image** accordingly.

### **3. Add to Cart & Wishlist Actions**

- [ ]  Verify clicking **“Add to Cart”** adds the correct product to the cart.
- [ ]  Verify an **alert/toast message** confirms the product was added successfully.
- [ ]  Verify clicking **“Add to Wishlist”** adds the product to the wishlist (if available).
- [ ]  Verify **multiple products** can be added to the cart in sequence.
- [ ]  Verify **“Out of Stock”** items cannot be added to the cart.
- [ ]  Verify adding the **same product again** updates quantity instead of duplicating.

### **4. Product Filters & Search**

- [ ]  Verify filters (price, brand, category) display correct filtered results.
- [ ]  Verify multiple filters can be applied together.
- [ ]  Verify **search results** for a product return correct matches.
- [ ]  Verify **sorting options** (e.g., Low to High, Most Popular) display correct ordering.

### **5. UX & Edge Cases**

- [ ]  Verify **error message or fallback** appears when a product is unavailable.
- [ ]  Verify **empty product category pages** display appropriate messages (e.g., “No products found”).
- [ ]  Verify selecting a product **while offline or with poor network** shows a relevant warning.
- [ ]  Verify **back navigation** from product detail returns to the correct listing position.
- [ ]  Verify all product pages and images **load without broken links or missing data**.

## Cart Button & Cart Summary

### **1. Cart Button Visibility & Functionality**

- [ ]  Verify **cart button/icon** is visible and correctly positioned in the header or navigation bar.
- [ ]  Verify **cart icon updates** dynamically when products are added or removed (shows item count).
- [ ]  Verify **clicking the cart icon** opens the cart summary or redirects to the cart page.
- [ ]  Verify **hovering over the cart icon** (if supported) displays a quick summary of added items.
- [ ]  Verify **tooltip or label** (e.g., “View Cart”) appears when hovering over the cart button.

### **2. Cart Summary Display**

- [ ]  Verify the cart summary displays **product image, name, price, quantity, and subtotal** for each item.
- [ ]  Verify the **total amount** is correctly calculated (sum of all subtotals).
- [ ]  Verify **shipping, taxes, and discounts** (if any) are shown correctly.
- [ ]  Verify **“Remove” or “Delete” buttons** are present and functional for each item.
- [ ]  Verify the **“Continue Shopping”** button navigates back to the product list or homepage.
- [ ]  Verify the **“Proceed to Checkout”** button redirects correctly to the checkout page.

### **3. Real-Time Updates**

- [ ]  Verify when an item is **removed**, the cart total updates instantly.
- [ ]  Verify when a product quantity is **updated**, subtotal and total adjust dynamically.
- [ ]  Verify **currency formatting** is correct and consistent across all products.
- [ ]  Verify **discounts or promo codes** applied are reflected accurately in the total.
- [ ]  Verify the **cart retains items** after refreshing or reloading the page (session persistence).

### **4. Empty Cart Handling**

- [ ]  Verify an appropriate **message is displayed when the cart is empty** (e.g., “Your cart is empty”).
- [ ]  Verify **cart buttons (checkout, remove)** are hidden or disabled when the cart is empty.
- [ ]  Verify **empty cart illustration or suggestion** (e.g., “Browse Products”) is shown if designed.

### **5. Edge Cases & UX**

- [ ]  Verify adding a **duplicate item** merges with existing quantity instead of duplicating entries.
- [ ]  Verify **cart data syncs correctly** when user logs in/out between devices.
- [ ]  Verify **slow network or API delay** displays a proper loader or disabled button state.
- [ ]  Verify cart content is cleared **after successful order placement**.
- [ ]  Verify **back button navigation** from checkout correctly retains cart items.

## Quantity Update

### **1. Quantity Controls & UI**

- [ ]  Verify **quantity field** is visible and correctly aligned in the cart summary and/or product detail page.
- [ ]  Verify **“+” (increase) and “−” (decrease)** buttons work correctly for adjusting item quantity.
- [ ]  Verify **manual input** in the quantity field is accepted and validated properly.
- [ ]  Verify **placeholder text or default value** (e.g., `1`) is pre-filled for new items added to the cart.
- [ ]  Verify **quantity update control** is disabled for products with only one item in stock.

### **2. Quantity Update Behavior**

- [ ]  Verify increasing quantity **updates the subtotal and total amount dynamically**.
- [ ]  Verify decreasing quantity **updates totals and does not allow negative values**.
- [ ]  Verify **entering zero (0)** triggers a proper warning or removes the product (based on design).
- [ ]  Verify **maximum quantity limit** works (e.g., stock limit or per-order cap).
- [ ]  Verify the **quantity change is reflected instantly** without page reload (AJAX update, if implemented).
- [ ]  Verify **updating quantity in mini-cart** syncs correctly with main cart and checkout pages.

### **3. Validation & Error Handling**

- [ ]  Verify system restricts **non-numeric input** (letters, special characters).
- [ ]  Verify **error message** displays for invalid quantities (e.g., “Please enter a valid number”).
- [ ]  Verify **stock availability message** is displayed when quantity exceeds available stock.
- [ ]  Verify **out-of-stock products** cannot be increased beyond available limit.
- [ ]  Verify **API or server-side validation** prevents quantity mismatch on checkout.

### **4. Edge Cases**

- [ ]  Verify **updating multiple product quantities** in quick succession reflects correctly in totals.
- [ ]  Verify **refreshing the page** retains the updated quantities.
- [ ]  Verify **logged-in and guest carts** handle quantity updates consistently.
- [ ]  Verify **quantity updates under slow network** show loader or disable buttons temporarily.
- [ ]  Verify **rounding behavior** if price or discount involves fractional values (e.g., 1.5 units).

### **5. UX & Feedback**

- [ ]  Verify **real-time feedback** (spinner, toast, or update animation) after quantity change.
- [ ]  Verify **undo or revert option** (if available) restores previous quantity.
- [ ]  Verify **total summary area** recalculates immediately without page reload.
- [ ]  Verify **keyboard navigation** (tab, arrow keys) works within quantity fields.

## Payment Gateway Integration

### **1. Payment Options Display**

- [ ]  Verify all **available payment methods** (credit/debit card, PayPal, net banking, wallets, etc.) are displayed.
- [ ]  Verify **payment logos/icons** are visible and correctly linked to the method.
- [ ]  Verify **selecting a payment method** highlights it or marks it as active.
- [ ]  Verify **default payment method** is pre-selected if applicable.

### **2. Payment Process**

- [ ]  Verify entering **valid card or account details** allows successful payment.
- [ ]  Verify **invalid card details** trigger a clear error message (e.g., “Invalid card number”).
- [ ]  Verify **expired cards** or accounts are blocked with a proper error message.
- [ ]  Verify **CVV, expiry date, and name fields** are validated properly.
- [ ]  Verify **promo codes or discounts** are applied correctly during payment.
- [ ]  Verify **order total** is correctly displayed before final confirmation.

### **3. Payment Gateway Redirection & Security**

- [ ]  Verify user is redirected securely to **third-party payment gateway** (if applicable).
- [ ]  Verify **SSL/HTTPS** is active on all payment pages.
- [ ]  Verify payment gateway **opens in the same tab or new tab** as per design.
- [ ]  Verify **cross-browser and device compatibility** for payment processing.
- [ ]  Verify **session timeout** during payment is handled correctly (user redirected with proper message).

### **4. Success & Failure Handling**

- [ ]  Verify **successful payments** redirect to confirmation page with order details.
- [ ]  Verify **failed payments** show appropriate error messages without processing the order.
- [ ]  Verify **cancellation or declined payments** allow the user to retry or choose a different method.
- [ ]  Verify **duplicate transaction prevention** if user clicks multiple times.
- [ ]  Verify **transaction ID or reference number** is generated and displayed after successful payment.

### **5. Notifications & Logging**

- [ ]  Verify **email or SMS confirmation** is sent after successful payment.
- [ ]  Verify **admin/merchant dashboard** shows updated payment status.
- [ ]  Verify **logs and records** for payment attempts are maintained for audit purposes.
- [ ]  Verify **refund or reversal process** triggers correctly for canceled or failed transactions.

### **6. Edge Cases**

- [ ]  Verify **network interruption** during payment triggers a clear message and rollback.
- [ ]  Verify **multiple browser tabs** do not allow duplicate payments.
- [ ]  Verify **browser refresh or back navigation** during payment does not process duplicate orders.
- [ ]  Verify **unsupported cards or methods** display a proper warning.
- [ ]  Verify **currency and international payments** work correctly (if applicable).

## Order Confirmation

### **1. Confirmation Page Display**

- [ ]  Verify **order confirmation page** is displayed immediately after successful payment.
- [ ]  Verify **thank-you message** or confirmation header is visible (e.g., “Thank you for your order!”).
- [ ]  Verify **order number/ID** is displayed and correctly formatted.
- [ ]  Verify **order summary** shows correct items, quantity, price, and total amount.
- [ ]  Verify **billing and shipping addresses** are displayed correctly.
- [ ]  Verify **estimated delivery date** or shipping info is displayed if applicable.

### **2. Confirmation Actions**

- [ ]  Verify user can **print or save** the order confirmation.
- [ ]  Verify **email or SMS confirmation** is sent immediately with all order details.
- [ ]  Verify user can **navigate back to home or continue shopping**.
- [ ]  Verify links to **track order** or view **order history** are working.

### **3. Accuracy & Validation**

- [ ]  Verify all **product details, prices, discounts, and taxes** match the final order.
- [ ]  Verify **payment method** displayed matches what the user selected.
- [ ]  Verify **shipping charges and totals** are correct.
- [ ]  Verify **order ID is unique** for every transaction.
- [ ]  Verify **currency and formatting** are consistent.

### **4. UX & Edge Cases**

- [ ]  Verify **page layout and responsiveness** across devices and browsers.
- [ ]  Verify **refreshing or back navigation** does not duplicate the order.
- [ ]  Verify **network interruption** or slow response still completes confirmation without errors.
- [ ]  Verify **access to confirmation page** is restricted to users who completed checkout.
- [ ]  Verify **special characters or long names** in product/user info are displayed correctly.

### **5. Admin/Backend Verification**

- [ ]  Verify **order is reflected correctly in admin/merchant dashboard**.
- [ ]  Verify **inventory is updated** automatically after order confirmation.
- [ ]  Verify **order status** shows as “Confirmed” or equivalent in system records.

## Invoice Generation

### **1. Invoice Creation**

- [ ]  Verify an **invoice is generated automatically** after successful order confirmation.
- [ ]  Verify **invoice number/ID** is unique and properly formatted.
- [ ]  Verify invoice contains **all order details**: items, quantity, price, subtotal, taxes, discounts, shipping charges, and total amount.
- [ ]  Verify **billing and shipping addresses** are displayed correctly.
- [ ]  Verify **payment method** and transaction ID are shown.

### **2. Invoice Display & Download**

- [ ]  Verify user can **view the invoice** immediately on the confirmation page or account section.
- [ ]  Verify invoice can be **downloaded as PDF** or printed.
- [ ]  Verify **invoice layout and formatting** are correct (logo, header, footer, tables).
- [ ]  Verify **all currency values** are displayed correctly and consistently.

### **3. Accuracy & Validation**

- [ ]  Verify **item details, prices, and totals** match the order confirmation.
- [ ]  Verify **tax calculations** are correct and comply with regulations.
- [ ]  Verify **discounts and promo codes** applied to the order reflect correctly on the invoice.
- [ ]  Verify invoice **date and time** match the order placement.

### **4. Accessibility & UX**

- [ ]  Verify invoice is **responsive** and readable on different devices and browsers.
- [ ]  Verify **print view** preserves formatting and legibility.
- [ ]  Verify invoice **supports special characters** (product names, user names, addresses).
- [ ]  Verify **navigation from invoice to order history** works correctly.

### **5. Admin / Backend Verification**

- [ ]  Verify invoice is **recorded in the admin or merchant dashboard** for accounting purposes.
- [ ]  Verify **inventory, accounting, and payment records** sync correctly with the invoice.
- [ ]  Verify **resending invoice** via email generates the correct copy.
- [ ]  Verify **duplicate invoices** are not generated for the same order.

---

[^        back to top        ^](#manual-software-testing)

# System / Integration

## API Integration Validation

### **1. API Connection & Authentication**

- [ ]  Verify API **endpoint URLs** are correct and accessible.
- [ ]  Verify the system **connects successfully** to the configured API without timeout.
- [ ]  Verify **API keys, tokens, and credentials** are correctly configured and valid.
- [ ]  Verify **expired or invalid credentials** return proper authentication errors (e.g., `401 Unauthorized`).
- [ ]  Verify **secure HTTPS connections** are enforced for all API calls.

### **2. Request & Response Validation**

- [ ]  Verify **HTTP methods** (GET, POST, PUT, DELETE, PATCH) are correctly used for each API.
- [ ]  Verify **request headers** (Content-Type, Authorization, Accept) are correctly set.
- [ ]  Verify **request body parameters** are validated before sending.
- [ ]  Verify **API response codes** follow standard conventions (200, 400, 401, 404, 500).
- [ ]  Verify **response time** meets defined performance requirements.
- [ ]  Verify **response data format** (JSON/XML) is correct and consistent with API documentation.

### **3. Data Accuracy & Consistency**

- [ ]  Verify data returned by API matches **expected results** from backend or database.
- [ ]  Verify **data integrity** after API actions (e.g., POST creates, PUT updates, DELETE removes).
- [ ]  Verify **timestamp fields**, IDs, and references are correctly generated and linked.
- [ ]  Verify **null or missing fields** are handled gracefully.

### **4. Error Handling & Edge Cases**

- [ ]  Verify system **handles API downtime or failure** (retry logic or graceful fallback).
- [ ]  Verify **invalid inputs** return proper validation messages.
- [ ]  Verify **rate limiting or throttling** is respected if API enforces limits.
- [ ]  Verify **network or timeout errors** show user-friendly messages.
- [ ]  Verify **malformed requests** don’t break integration or expose sensitive data.

### **5. Security & Logging**

- [ ]  Verify **sensitive data** (tokens, passwords) are never exposed in logs or responses.
- [ ]  Verify **API request/response logs** are stored securely with timestamps.
- [ ]  Verify **encryption and authentication mechanisms** comply with API provider standards.
- [ ]  Verify **audit trails** record successful and failed API transactions.

## Database Validation (data saved correctly)

### **1. Data Insertion & Accuracy**

- [ ]  Verify all **form submissions and transactions** insert data into the correct database tables.
- [ ]  Verify **each field value** in the database matches exactly what was entered in the application UI.
- [ ]  Verify **auto-generated IDs**, timestamps, and default values are stored correctly.
- [ ]  Verify **special characters, emojis, and multilingual text** are saved without corruption.
- [ ]  Verify **numeric, date, and boolean fields** retain the correct data types and formats.

### **2. Data Relationships & Constraints**

- [ ]  Verify **foreign key relationships** (e.g., user → order) are correctly maintained.
- [ ]  Verify **primary keys are unique** and not duplicated.
- [ ]  Verify **cascade updates/deletes** behave correctly (child records update or delete as expected).
- [ ]  Verify **not-null and unique constraints** are enforced by the database.
- [ ]  Verify **default constraint values** are correctly applied when no input is provided.

### **3. Data Retrieval & Consistency**

- [ ]  Verify retrieved data (via UI or API) **matches stored data** in the database.
- [ ]  Verify **search and filter queries** return the correct database records.
- [ ]  Verify **pagination and sorting queries** return accurate subsets of data.
- [ ]  Verify **data consistency** between multiple related tables.
- [ ]  Verify **data integrity** after performing update or delete actions.

### **4. Error Handling & Validation**

- [ ]  Verify invalid or incomplete data is **not inserted into the database**.
- [ ]  Verify database **throws proper error messages** for constraint violations.
- [ ]  Verify **rollback** occurs when a transaction fails midway.
- [ ]  Verify **data duplication** is prevented through constraints or validations.
- [ ]  Verify **database handles null, blank, and large input values** gracefully.

### **5. Security & Performance**

- [ ]  Verify **sensitive data (passwords, tokens, payment info)** is encrypted or hashed.
- [ ]  Verify **no SQL injection vulnerabilities** exist in queries.
- [ ]  Verify **database connections** close properly after each operation.
- [ ]  Verify **indexes are optimized** for performance on frequently queried columns.
- [ ]  Verify **backup and restore** procedures maintain data integrity.

## Third-Party Service Responses (e.g., OTP, Payment APIs)

### **1. Service Connectivity & Configuration**

- [ ]  Verify **API keys and credentials** for each third-party service are configured correctly.
- [ ]  Verify system can **connect successfully** to each service endpoint (OTP, Payment, SMS, Email, etc.).
- [ ]  Verify all **endpoints use secure HTTPS** connections.
- [ ]  Verify **sandbox/test environments** behave consistently before production integration.

### **2. OTP (One-Time Password) Integration**

- [ ]  Verify OTP is **generated correctly** and delivered via configured channel (SMS/Email).
- [ ]  Verify **correct OTP validation** allows successful login or transaction.
- [ ]  Verify **incorrect OTP** returns an appropriate error message.
- [ ]  Verify **expired OTP** is not accepted.
- [ ]  Verify **resend OTP** functionality works and maintains security limits (e.g., max retries).
- [ ]  Verify **time-to-live (TTL)** for OTP expiry is enforced.
- [ ]  Verify OTP values are **not logged or stored in plain text**.

### **3. Payment Gateway Responses**

- [ ]  Verify **successful payment response** updates the order status correctly.
- [ ]  Verify **failed or declined payments** trigger the correct error messages.
- [ ]  Verify **network interruptions** during payment don’t cause duplicate transactions.
- [ ]  Verify **transaction ID and reference number** are recorded accurately.
- [ ]  Verify **refund and cancellation APIs** update order/payment status properly.
- [ ]  Verify **currency codes and amounts** match between request and response.
- [ ]  Verify **callback URLs** are triggered successfully after payment completion.

### **4. Other Third-Party Services**

- [ ]  Verify **email/SMS notifications** are triggered correctly after key events (order placed, OTP sent, etc.).
- [ ]  Verify **social login integrations** (Google, Facebook, etc.) authenticate users properly.
- [ ]  Verify **shipping/tracking APIs** return valid data and update status in the system.
- [ ]  Verify **analytics or CRM integrations** (e.g., Google Analytics, HubSpot) receive correct event data.

### **5. Error Handling & Security**

- [ ]  Verify **invalid credentials or expired tokens** return correct error responses (401/403).
- [ ]  Verify system handles **timeouts or service unavailability** gracefully.
- [ ]  Verify **no sensitive information** is exposed in API logs or error responses.
- [ ]  Verify **retries** are managed safely without duplicate actions (e.g., recharging, resending OTP).
- [ ]  Verify all **third-party data** (tokens, responses) are stored and transmitted securely.

---

[^        back to top        ^](#manual-software-testing)

# Performance and Security

## 1) Load Testing (page performance under traffic)

**Goal:** Prove the system meets performance SLAs under expected real-world traffic.

- **Preparation**
    - [ ]  Define SLAs: e.g., *P95 response time ≤ 800ms*, *P99 ≤ 2s*, error rate < 0.5%, throughput target X RPS (requests/sec)*.
    - [ ]  Build realistic user journeys (home, search, product page, add-to-cart, checkout) and weight them by expected traffic distribution.
    - [ ]  Prepare test data/environment that mirrors production (DB size, caches, network latency).
    - [ ]  Instrument monitoring: CPU, memory, disk I/O, DB metrics, app logs, network, APM traces, and error rates.
- **Test execution**
    - [ ]  Ramp-up: slowly increase load from 0 to target RPS over a realistic interval (e.g., 10–30 min).
    - [ ]  Steady-state: hold at target RPS for a soak period (e.g., 30–120 min).
    - [ ]  Measure P50/P90/P95/P99, throughput, error rates, and resource utilization.
    - [ ]  Run tests for peak-user scenarios (e.g., sale event) with higher RPS.
- **Pass criteria**
    - [ ]  Response times meet SLA percentiles.
    - [ ]  Error rate below threshold.
    - [ ]  No resource exhaustion (no OOMs, DB connection pool exhaustion).
    - [ ]  No single-component bottleneck causing cascading failures.
- **Actions on failure**
    - [ ]  Profile and identify hotspots (DB queries, external calls).
    - [ ]  Tune DB indices, cache hot results (Redis), add read replicas, scale app instances, optimize queries.
    - [ ]  Re-run tests after fixes.
- **Tools / notes**
    - Use k6/Locust/JMeter/Gatling; monitor with Prometheus/Grafana, APM (NewRelic/AWS X-Ray). Run from distributed load generators to avoid generator-bound results.

## 2) Stress Testing

**Goal:** Discover breaking points and system behavior under overload and during recovery.

- **Preparation**
    - [ ]  Define targets: increasing concurrency until failures, then observe recovery/resilience.
    - [ ]  Ensure monitoring and alerting active; have a rollback/kill-switch plan.
- **Test execution**
    - [ ]  Ramp beyond expected peak quickly to provoke failures (e.g., 2×, 5× expected peak).
    - [ ]  Identify the point where errors spike or latency explodes.
    - [ ]  Observe behavior under sustained overload (e.g., 10–30 minutes).
    - [ ]  Stop the load and observe system recovery time and data integrity.
- **Expected results**
    - [ ]  System fails gracefully (e.g., queued requests, degraded features, circuit breakers) rather than corrupting data.
    - [ ]  Recovery to healthy state without manual restarts (or with documented manual steps).
    - [ ]  No silent data loss or duplicate transactions.
- **Checks**
    - [ ]  Verify queuing/circuit breakers limit downstream failures.
    - [ ]  Ensure rate-limiting and backpressure are effective.
    - [ ]  Check for partial writes, duplicate orders, or inconsistent DB state.
- **Actions on failure**
    - [ ]  Implement or tune circuit breakers, rate limits, bulkheads.
    - [ ]  Harden scaling policies and autoscaling thresholds.

## 3) Input Validation — SQL Injection (SQLi) & Cross-Site Scripting (XSS)

**Goal:** Prevent all user-supplied input from allowing SQLi or XSS.

### SQL Injection (SQLi)

- **What to test**
    - [ ]  All user input endpoints (forms, parameters, headers, cookies, API endpoints).
    - [ ]  Dynamic query points (search, filters, advanced queries).
- **Test cases**
    - [ ]  Send classic payloads: `' OR '1'='1' --`, `'; DROP TABLE users; --`, `UNION SELECT NULL,NULL--`.
    - [ ]  Blind SQLi patterns (`AND (SELECT ASCII(SUBSTRING((SELECT TOP 1 name FROM users),1,1))) > 64`).
    - [ ]  Test parameter types (numeric vs string) and encoding.
- **Expected results**
    - [ ]  Application never executes injected SQL; input is treated as data, not code.
    - [ ]  Proper error handling — no DB errors or stack traces leaked to user.
- **Mitigations**
    - [ ]  Use parameterized queries / prepared statements / ORMs with parameter binding.
    - [ ]  Input validation and strict typing; least privilege DB user.
    - [ ]  WAF rules as defense-in-depth.
    - [ ]  Database activity monitoring and alerting.

### Cross-Site Scripting (XSS)

- **What to test**
    - [ ]  Any place where user input is rendered in the browser: comments, profile fields, product reviews, search results, error messages.
- **Test cases**
    - [ ]  Stored XSS: submit `<script>alert(1)</script>` in a field and check when rendered by other users.
    - [ ]  Reflected XSS: send URL with `?q=<script>...` and observe reflected output.
    - [ ]  DOM XSS: inject payloads into attributes, event handlers, or JSON contexts.
    - [ ]  Variants: `<img src=x onerror=alert(1)>`, `'"><svg onload=alert(1)>`.
- **Expected results**
    - [ ]  Browser never executes injected scripts.
    - [ ]  Output is HTML-escaped or sanitized per context (HTML, JS, URL, attribute).
- **Mitigations**
    - [ ]  Contextual output encoding/escaping (HTML escape, JS escape, attribute escape).
    - [ ]  Use CSP (Content Security Policy) to block inline scripts.
    - [ ]  Sanitize inputs where rich HTML is allowed, using vetted libraries (DOMPurify for HTML sanitization).
    - [ ]  HttpOnly cookies and proper SameSite flags.

## 4) Password Encryption

**Goal:** Store and handle credentials securely so passwords cannot be recovered if storage is compromised.

- **Storage & hashing**
    - [ ]  Verify passwords are never stored in plaintext.
    - [ ]  Verify a modern, slow password hashing algorithm is used: **Argon2id** (recommended), **bcrypt** or **scrypt** (acceptable), with appropriate cost parameters. (Avoid plain SHA/MD5.)
    - [ ]  Verify unique per-user salt is used (built-in for bcrypt/Argon).
    - [ ]  Verify hashing parameters are periodically reviewed and upgraded as hardware improves.
- **Transmission & handling**
    - [ ]  Verify all password transmission occurs over TLS (HTTPS) only.
    - [ ]  Verify no passwords appear in logs, error messages, or analytics.
    - [ ]  Verify password reset tokens are one-time, short-lived, cryptographically random, and single-use.
- **Password policy**
    - [ ]  Verify enforced complexity or strength policy (or use passphrase guidance) and show clear UX for strength.
    - [ ]  Verify rate-limiting on authentication attempts and account lockout or progressive delays.
    - [ ]  Verify multi-factor authentication (MFA) is available and encouraged/required for high-risk actions.
- **Recovery & rotation**
    - [ ]  Verify password reset flows validate identity securely (not revealing account existence).
    - [ ]  Verify mechanisms for rotating hashing schemes: on next successful login, re-hash with new params.

## 5) Session Management (logout, session expiration)

**Goal:** Sessions should be safe, short-lived, and impossible to hijack or reuse after logout/timeout.

- **Session tokens & cookies**
    - [ ]  Verify session tokens are cryptographically random (sufficient entropy).
    - [ ]  Verify **Secure**, **HttpOnly**, and **SameSite=strict/lax** cookie flags are set appropriately.
    - [ ]  Verify session tokens are stored server-side or use signed JWTs with short expiry and revocation strategy.
    - [ ]  Verify no sensitive state stored client-side in an unencrypted way.
- **Timeouts & logout**
    - [ ]  Verify idle session timeout matches policy and enforces logout.
    - [ ]  Verify explicit logout invalidates server-side session immediately and deletes cookies.
    - [ ]  Verify session invalidation across devices (option to log out from all devices).
- **Token lifecycle & rotation**
    - [ ]  Verify refresh tokens (if used) are stored securely, have limited lifetime, and are revocable.
    - [ ]  Verify token rotation strategy (rotate on use) to reduce replay risk.
- **Session fixation & CSRF**
    - [ ]  Verify session fixation protection (issue new session after login).
    - [ ]  Verify CSRF protection: anti-CSRF tokens for state-changing requests (or SameSite + double-submit when suitable).
    - [ ]  Verify sensitive actions require re-authentication or MFA (e.g., change password, update payment).
- **Multi-tab / concurrency**
    - [ ]  Verify session behavior is consistent across tabs and browsers.
    - [ ]  Verify session timeout triggers in all tabs or forces re-authentication on next action.
- **Logging & monitoring**
    - [ ]  Verify login attempts, successful logins, logouts, and suspicious session activity are logged and alertable.
    - [ ]  Verify unusual session behaviors (multiple IPs, geolocation changes) trigger alerts or step-up auth.

---

## Operational & Testing Best Practices

- [ ]  Always test security changes in staging before prod. For destructive tests (stress, SQLi), use isolated environments and backup data.
- [ ]  Use automated regression suites for performance and security smoke checks after each deployment.
- [ ]  Combine automated scanning (SAST/DAST) with manual penetration testing for high-risk flows.
- [ ]  Maintain an incident playbook for performance outages and a security incident response plan for compromises.
- [ ]  Prioritize fixes by risk: data-loss or compromise > financial loss > availability > UX.

---

[^        back to top        ^](#manual-software-testing)

# Compatibility & Accessibility

### **1. Browser Compatibility (Chrome, Firefox, Safari, Edge)**

- [ ]  Verify application UI and layout render correctly across all major browsers.
- [ ]  Verify all buttons, forms, and links function as expected in each browser.
- [ ]  Check CSS and JavaScript behaviors (animations, dropdowns, modals, etc.) across browsers.
- [ ]  Verify font rendering consistency and text alignment.
- [ ]  Validate cookies, sessions, and local storage behavior in each browser.
- [ ]  Ensure file uploads, downloads, and media (images/videos) load properly.
- [ ]  Check console logs for browser-specific errors or warnings.
- [ ]  Confirm responsiveness and scrolling work smoothly on all browsers.

### **2. Mobile Responsiveness**

- [ ]  Verify layout adapts to different screen sizes (mobile, tablet, desktop).
- [ ]  Check that all menus, buttons, and touch elements are accessible on mobile.
- [ ]  Validate that text, images, and tables adjust properly to smaller screens.
- [ ]  Ensure no horizontal scrolling is required on mobile devices.
- [ ]  Test orientation changes (portrait ↔ landscape) for UI consistency.
- [ ]  Confirm that modals and popups scale and remain centered.
- [ ]  Verify that clickable elements have adequate spacing for touch use.
- [ ]  Check responsive breakpoints and grid alignment across devices.

### **3. Accessibility (Keyboard navigation, ARIA labels)**

- [ ]  Verify all interactive elements (buttons, inputs, links) are reachable via **Tab** key.
- [ ]  Check **focus indicators** are visible and consistent across all elements.
- [ ]  Ensure screen readers correctly announce page titles, buttons, and form labels.
- [ ]  Validate presence and correctness of **ARIA attributes** for interactive components.
- [ ]  Confirm all images have descriptive **alt text**.
- [ ]  Check sufficient **color contrast** between text and background.
- [ ]  Verify that error messages are accessible (readable by screen readers).
- [ ]  Ensure no functionality depends solely on color or hover.
- [ ]  Test zoom levels (up to 200%) for readability and usability.
- [ ]  Validate skip navigation links (e.g., “Skip to main content”).

---

[^        back to top        ^](#manual-software-testing)

# UI/UX Design

## **Header Section**

### 1. Structure & Presence

- [ ]  Verify the header section is present on the website.
- [ ]  Verify the header section layout follows the design specification.
- [ ]  Verify the header is properly aligned across all screen sizes and resolutions.
- [ ]  Verify the header and body sections are visually distinct.

### 2. Branding & Logo

- [ ]  Verify the website logo is displayed correctly in the header.
- [ ]  Verify the logo alignment matches the design (left, center, or right).
- [ ]  Verify clicking the logo navigates to the home page from all pages.
- [ ]  Verify the logo maintains aspect ratio and clarity on different devices.

### 3. Navigation & Links

- [ ]  Verify all header navigation links are present and functional.
- [ ]  Verify clicking each link opens the correct corresponding page.
- [ ]  Verify selected header link remains active (highlighted) to indicate the current page.
- [ ]  Verify all header links are readable, with proper contrast and font size.
- [ ]  Verify navigation links open in the correct tab/window as per design (same or new tab).

### 4. Icons & Visuals

- [ ]  Verify icons (if added) are aligned properly with their respective link text.
- [ ]  Verify icon design is relevant to the corresponding link or action.
- [ ]  Verify icon color changes on mouse hover.
- [ ]  Verify hover effects for text and icons match the design (e.g., color change, underline).

### 5. Behavior & Interactivity

- [ ]  Verify the header remains fixed or sticky on scroll, as per requirements.
- [ ]  Verify dropdown menus (if any) appear correctly on hover or click as specified.
- [ ]  Verify dropdown options are aligned, readable, and clickable.
- [ ]  Verify the search bar (if present) is functional and positioned correctly.

### 6. Consistency

- [ ]  Verify the same header is used consistently across all pages.
- [ ]  Verify spacing, padding, and font style in the header are consistent throughout the site.
- [ ]  Verify responsive design behavior, header should adapt properly on mobile, tablet, and desktop.
- [ ]  Verify no overlapping or clipping occurs between header elements and page content.

## **Footer Section**

### 1. Structure & Alignment

- [ ]  Verify the footer section is aligned correctly at the bottom of the page.
- [ ]  Verify no extra white space appears below the footer on large screen resolutions.
- [ ]  Verify all footer elements are properly aligned (links, text, icons, etc.).
- [ ]  Verify consistent spacing between top and bottom elements within the footer.
- [ ]  Verify the footer remains fixed or scrolls as per the design requirements.

### 2. Consistency & Layout

- [ ]  Verify the same footer layout and design are used across all pages.
- [ ]  Verify text alignment, font style, and colors match the design specification.
- [ ]  Verify no spelling or grammatical mistakes appear in footer text.
- [ ]  Verify elements (links, buttons, social icons) are evenly spaced and aligned.

### 3. Logo & Branding

- [ ]  Verify the logo is displayed correctly in the footer section.
- [ ]  Verify logo alignment matches the design.
- [ ]  Verify clicking the footer logo redirects the user to the home page.

### 4. Links & Navigation

- [ ]  Verify all links in the footer navigate to their correct destinations.
- [ ]  Verify no broken links are present in the footer.
- [ ]  Verify mouse cursor changes from pointer to hand on hover over links.
- [ ]  Verify hover color and text decoration on footer links follow the UI design.

### 5. Social Media & External Links

- [ ]  Verify all social media icons are present and properly aligned.
- [ ]  Verify each social media icon links to the correct external page.
- [ ]  Verify social media links open in new tabs (if specified).
- [ ]  Verify social media icons are visually consistent and responsive.

### 6. Newsletter Subscription (if applicable)

- [ ]  Verify the “Subscribe to Newsletter” section is present in the footer.
- [ ]  Verify the email input field and Subscribe button are displayed properly.
- [ ]  Verify email validation is implemented (only valid emails can be submitted).
- [ ]  Verify an error message is shown for blank or invalid email inputs.
- [ ]  Verify a confirmation message appears upon successful subscription.

### 7. Copyright & Legal Information

- [ ]  Verify the copyright section is present in the footer.
- [ ]  Verify the correct copyright year is displayed.
- [ ]  Verify the copyright symbol © is shown and properly sized.
- [ ]  Verify company or site name is displayed clearly next to the copyright text.
- [ ]  Verify any legal or policy links (Terms, Privacy, etc.) are functional and correct.

## **Buttons (Primary, Secondary, Disabled states)**

### 1. Presence & Design Consistency

- [ ]  Verify the button is present on the page as per the design specification.
- [ ]  Verify the button color matches the provided design palette.
- [ ]  Verify width and height of the button match design requirements.
- [ ]  Verify border radius is applied correctly and consistent with the UI style.
- [ ]  Verify that all buttons across the site follow consistent sizing and styling.

### 2. Icons & Alignment

- [ ]  Verify icons are added on buttons where specified (e.g., Upload, Download).
- [ ]  Verify icons are aligned correctly with button text.
- [ ]  Verify icon size and spacing relative to text are uniform across buttons.

### 3. Text & Readability

- [ ]  Verify button text matches its intended functionality (e.g., “Submit”, “Cancel”).
- [ ]  Verify button text spelling is correct.
- [ ]  Verify text is readable and visible against the button background color.
- [ ]  Verify button font family, size, and weight match the design specification.

### 4. States & Interactions

- [ ]  Verify button is clickable and enabled by default (if applicable).
- [ ]  Verify button color and style change correctly on hover.
- [ ]  Verify hover color matches the design.
- [ ]  Verify disabled buttons appear visually distinct and are non-interactive.
- [ ]  Verify focus outline or effect appears when tabbing through buttons.

### 5. Functional Behavior

- [ ]  Verify clicking the button performs the intended action or navigation.
- [ ]  Verify form values are correctly submitted and saved in the database upon clicking the submit button.
- [ ]  Verify users cannot click the submit button multiple times to prevent duplicate submissions.
- [ ]  Verify reset button restores all fields to their default values.
- [ ]  Verify the entire button (not just the text) is clickable.

### 6. Navigation & Browser Behavior

- [ ]  Verify right-clicking on a button shows the “Open link in new tab” option if applicable.
- [ ]  Verify pressing **Ctrl + Click** opens the button link in a new tab (if designed to).
- [ ]  Verify external links open in a new tab as per requirements.

## **Radio Buttons**

- [ ]  Verify radio buttons are present on the page as per the design.
- [ ]  Verify the size of each radio button matches the design specifications.
- [ ]  Verify the style and color of radio buttons align with the requirements.
- [ ]  Verify label text is present alongside each radio button.
- [ ]  Verify the sequence of label text matches the design specification.
- [ ]  Verify spelling accuracy for all radio button labels.
- [ ]  Verify label text alignment with corresponding radio buttons.
- [ ]  Verify each radio button can be selected and unselected by clicking.
- [ ]  Verify clicking the label also selects the associated radio button.
- [ ]  Verify only one radio button can be selected at a time.
- [ ]  Verify radio button selection can be navigated using the **Tab** key.
- [ ]  Verify an error message appears if no radio option is selected and the user clicks **Submit**.
- [ ]  Verify the selected radio button value is correctly saved to the database.

## **Checkboxes**

- [ ]  Verify the checkbox is present on the webpage in the correct position.
- [ ]  Verify the width and height of the checkbox match the design specifications.
- [ ]  Verify the border-radius style — rounded or sharp edges — is correctly implemented.
- [ ]  Verify the tick mark color when the checkbox is selected matches the design.
- [ ]  Verify the checkbox can be selected using the **mouse click**.
- [ ]  Verify the checkbox can be selected using **keyboard navigation** (e.g., Tab + Space).
- [ ]  Verify the checkbox can be **unchecked** by clicking again.
- [ ]  Verify multiple checkboxes can be selected simultaneously if the design allows.
- [ ]  Verify the **label text** is present with each checkbox.
- [ ]  Verify label text is properly **aligned** with the checkbox.
- [ ]  Verify if the **first checkbox** is selected by default on page load, where applicable.
- [ ]  Verify clicking the **label text** also toggles the checkbox selection.
- [ ]  Verify **spelling** of all checkbox labels is correct.
- [ ]  Verify **no duplicate label text** exists among the checkboxes.
- [ ]  Verify the **order** of checkbox labels matches the design or requirements.
- [ ]  Verify that **selected checkbox values** are correctly saved in the database upon clicking **Submit**.
- [ ]  Verify that checkboxes can be **unchecked** after being selected.
- [ ]  Verify that **validation** triggers an alert or error message if no checkbox is selected and the user clicks **Submit**.

## **Dropdown Menus**

- [ ]  Verify all expected values are added to the dropdown list.
- [ ]  Verify the label text for the dropdown matches requirements and is properly aligned.
- [ ]  Verify that clicking on the dropdown displays the full list of available values.
- [ ]  Verify the dropdown expands correctly and displays all options.
- [ ]  Verify scroll-down functionality works properly when the list exceeds visible space.
- [ ]  Verify the dropdown can be navigated using **arrow keys** on the keyboard.
- [ ]  Verify a **default selected value** appears when the page loads, if required.
- [ ]  Verify the dropdown field is **not editable** unless specified.
- [ ]  Verify the **order of dropdown values** matches design or requirements.
- [ ]  Verify no **blank or placeholder values** appear unintentionally.
- [ ]  Verify case sensitivity of dropdown values as required by the system.
- [ ]  Verify users can **jump to values** by typing the first alphabet from the keyboard.
- [ ]  Verify dropdown design remains consistent and functional across all browsers.
- [ ]  Verify spelling of all dropdown values is correct.
- [ ]  Verify values are properly **aligned** within the dropdown list.
- [ ]  Verify mouse pointer changes to a **hand cursor** when hovering over dropdown values.
- [ ]  Verify there is proper **spacing and padding** between dropdown values.
- [ ]  Verify **hover effects** (color or background changes) are applied correctly.
- [ ]  Verify long text or maximum character length displays properly without truncation issues.
- [ ]  Verify users can **navigate through dropdowns using Tab** on the keyboard.

### If Search is Added in the Dropdown

- [ ]  Verify the **search field** inside the dropdown is clickable.
- [ ]  Verify users can type text into the search field from the keyboard.
- [ ]  Verify users can paste text into the search field using the mouse.
- [ ]  Verify the correct value appears when a valid keyword is entered.
- [ ]  Verify an appropriate **error message** appears if an invalid keyword is entered.

### Dropdowns Used in Web Forms (Conditional Validation)

- [ ]  Verify the dropdown opens only when required conditions are met (e.g., if a related checkbox or radio button is set to “Yes”).
- [ ]  Verify users can select a value only when the field is active based on logic or dependency rules.

## **Tooltips**

- [ ]  Verify tooltip **width and height** are properly aligned and consistent across elements.
- [ ]  Verify the **tooltip text alignment** (centered or left-aligned) matches the design specification.
- [ ]  Verify the **correct and relevant text** appears when hovering over the tooltip icon or element.
- [ ]  Verify the tooltip text **disappears immediately** when the mouse pointer moves away from the icon or link.
- [ ]  Verify the **icon color changes** on hover, if specified in the design.
- [ ]  Verify the **mouse pointer changes** (e.g., to a hand) when hovering over a tooltip-enabled element.
- [ ]  Verify the **tooltip icon is aligned** with the label or text it’s associated with.
- [ ]  Verify tooltip content is **not truncated** and all text is fully visible within the tooltip area.
- [ ]  Verify the **tooltip message is clear, relevant, and helpful** to the user.
- [ ]  Verify there are **no spelling or grammar errors** in the tooltip text.

## **Hyperlinks**

- [ ]  Verify each **link is clickable** and responsive to user interaction.
- [ ]  Verify **link text** is present and clearly visible.
- [ ]  Verify each link has the **correct URL** associated with it.
- [ ]  Verify clicking the link **redirects to the correct destination**.
- [ ]  Verify the **protocol (https:// or http://)** used in the link is correct.
- [ ]  Verify the link **opens in the same tab or a new tab** according to the design or requirement.
- [ ]  Verify the **hyperlink is applied to the intended text or image** only.
- [ ]  Verify **link text color differs from normal text** and changes on hover.
- [ ]  Verify the **link text is relevant and descriptive** of its destination.
- [ ]  Verify there are **no spelling or grammatical errors** in link text.
- [ ]  Verify the **cursor changes to a pointer (hand)** when hovering over the link.
- [ ]  Verify a **tooltip appears** on hover (if implemented).
- [ ]  Verify the **tooltip text and alignment** match the linked element.
- [ ]  Verify the **URL preview** appears in the lower-left corner of the browser on hover.
- [ ]  Verify a **loader or progress indicator** appears when clicking a link (if applicable).
- [ ]  Verify when a link is applied to an image, **the entire image is clickable**.
- [ ]  Verify **linked images are not broken** and display properly.
- [ ]  Verify **in-page anchor links** correctly scroll or navigate to the targeted section.

## **Delete Button**

- [ ]  Verify the **Delete button** is present on the page.
- [ ]  Verify a **delete/trash icon** is displayed with the button text (if part of design).
- [ ]  Verify the **entire button area is clickable**, not just the text or icon.
- [ ]  Verify a **confirmation popup or alert** appears when the user clicks the Delete button.
- [ ]  Verify that clicking **“No”** or “Cancel” on the confirmation popup **does not delete** the record.
- [ ]  Verify that clicking **“Yes”** on the confirmation popup **triggers the delete action**.
- [ ]  Verify the **record is successfully deleted** from the database after confirmation.
- [ ]  Verify the system provides an **Undo option** after deletion.
- [ ]  Verify clicking **Undo restores** the deleted record to its previous state and location.
- [ ]  Verify whether the user can **delete a record using the Delete key** on the keyboard.
- [ ]  Verify that once deleted, the **record no longer appears** in the table or list.
- [ ]  Verify the user is **redirected to the correct page or view** after successful deletion.
- [ ]  Verify the user can **delete multiple records** at once (if supported).
- [ ]  Verify multiple deletions can be performed using **checkbox selection**.
- [ ]  Verify an **error message appears** if the user clicks Delete without selecting any record.
- [ ]  Verify that **only the selected records** are deleted and other data remains unaffected.

## **GUI**

### 1. GUI Consistency

- [ ]  Verify all UI elements (inputs, buttons, checkboxes, radio buttons, selects, icons) are consistently styled across pages.
- [ ]  Verify alignment and spacing of elements is consistent (labels ↔ inputs, icons ↔ text, list items).
- [ ]  Verify font family, weights, sizes and line-height are consistent with design tokens/spec.
- [ ]  Verify colors (text, links, icons, backgrounds) follow the design palette consistently.
- [ ]  Verify iconography style and sizes are consistent (same icon set, same stroke/filled style).
- [ ]  Verify placeholder text style and visibility is consistent across fields.
- [ ]  Verify button styles (primary/secondary/disabled) are consistent in shape, size, and spacing.
- [ ]  Verify component states are consistent (hover, focus, active, disabled, loading).
- [ ]  Verify error/warning/info messages use the same format (icon, text style, placement) everywhere.
- [ ]  Verify headings, subheadings and body text sizes follow the typographic scale.
- [ ]  Verify no duplicate or inconsistent label text appears (same concept uses same wording).
- [ ]  Verify no broken links or broken images across pages.
- [ ]  Verify 404 and 500 error pages exist and match the site style.
- [ ]  Verify dynamic/third-party components adopt site styles or are visually mapped to the design.
- [ ]  Verify theme variants (if any) use consistent component styles (e.g., dark/light).

### 2. Design Responsiveness (desktop, tablet, mobile)

- [ ]  Verify page layout adapts correctly at common breakpoints (mobile, tablet, desktop).
- [ ]  Verify all interactive elements remain usable at touch sizes on mobile (minimum touch target).
- [ ]  Verify navigation transforms correctly (hamburger/menu collapse) and remains usable.
- [ ]  Verify header and footer behavior on small screens (visibility, collapsing, sticky behavior).
- [ ]  Verify grids and card lists reflow correctly (no overlap, no horizontal scroll).
- [ ]  Verify images and banners scale/resize without distortion or unwanted cropping; text on images remains readable.
- [ ]  Verify form layouts (labels, inputs, validation messages) stack and align correctly on narrow screens.
- [ ]  Verify dropdowns, modals and popovers are usable on mobile (fit viewport, not clipped).
- [ ]  Verify touch gestures and tapping targets behave as expected (no accidental clicks).
- [ ]  Verify responsive typography: text remains readable at each breakpoint; no truncation issues.
- [ ]  Verify viewport-scale/zoom behavior (page remains usable when user zooms).
- [ ]  Verify cross-browser rendering at each breakpoint (Chrome, Firefox, Safari, Edge).
- [ ]  Verify high-DPI / retina image assets render crisply (no blurring).
- [ ]  Verify CSS media queries don’t break on uncommon/resized resolutions (very large and very small).
- [ ]  Verify conditional UI elements (e.g., dropdown appears only when condition met) still work responsively.
- [ ]  Verify no extra white-space or layout shift at large screen resolutions.

### 3. Color Contrast & Accessibility

- [ ]  Verify text-to-background contrast meets WCAG AA (minimum 4.5:1 for normal text, 3:1 for large text) and note any places requiring 3:1 / AAA.
- [ ]  Verify UI controls (focus states) have visible focus indicators (keyboard focus ring) and meet contrast requirements.
- [ ]  Verify color is not the sole means of conveying information (errors must include icon/text).
- [ ]  Verify link and button contrast and hover/focus state contrast meet accessibility thresholds.
- [ ]  Verify icons have accessible names or aria-labels if they are actionable or convey meaning.
- [ ]  Verify form fields have associated labels (visible or aria-label) and correct `for`/`id` mapping.
- [ ]  Verify error messages are programmatically associated with fields (aria-describedby or aria-invalid).
- [ ]  Verify keyboard navigation order is logical and tab stops follow visual layout (test with Tab/Shift+Tab).
- [ ]  Verify all interactive elements are operable with keyboard alone (Enter/Space/Arrow keys as applicable).
- [ ]  Verify screen reader output for main components (landmarks, headings, form controls, live regions).
- [ ]  Verify pages use semantic HTML5 landmarks (header, nav, main, footer) and correct heading hierarchy.
- [ ]  Verify dynamic content changes are announced appropriately (aria-live regions for notifications).
- [ ]  Verify contrast and readability in both light and dark themes (if present).
- [ ]  Verify accessible alternatives: audio CAPTCHA option, alt text for images, transcripts for media.
- [ ]  Verify color-blindness checks (simulate common types) to ensure UI remains usable.
- [ ]  Verify text scaling: content remains usable/readable when browser text size increased to 200%.
- [ ]  Verify focusable controls are at least 4mm (recommended touch target) and meet accessibility sizing guidance.

### 4. Extras / Recommended Checks

- [ ]  Verify RTL layout and content rendering if supporting right-to-left languages.
- [ ]  Verify font fallback behavior if custom webfonts fail to load.
- [ ]  Verify visual regression snapshots for key pages to detect unintended CSS changes.
- [ ]  Maintain a short checklist of required accessibility attributes for developers (aria, role, alt, labels).