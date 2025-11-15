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