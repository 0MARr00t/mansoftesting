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
