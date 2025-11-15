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