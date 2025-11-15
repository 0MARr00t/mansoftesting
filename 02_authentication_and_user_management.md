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