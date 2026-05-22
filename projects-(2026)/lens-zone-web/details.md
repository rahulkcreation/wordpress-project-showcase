# Lens Zone Web - Plugin Analysis

This document provides a detailed analysis of the WordPress plugins used in the Lens Zone Web project, including their functionalities, use cases, target audience, and repository/download links.

---

## 1. AuthMe (authme-lens-zone)

* **Repository / Download URL:** [https://github.com/ART-TECH-FUZION-PROJECTS/authme-lens-zone.git](https://github.com/ART-TECH-FUZION-PROJECTS/authme-lens-zone.git)
* **Author:** Art-Tech Fuzion
* **Version:** 1.5.0

### What It Does (Functionality)
* **OTP-Based Verification:** Replaces default WordPress registration, login, and password reset flows with a secure, One-Time Password (OTP) verification system sent via email (`wp_mail()`).
* **Overlay Form Modal:** Injects a clean, modern, and highly responsive authentication popup overlay via the `wp_footer` hook for non-logged-in users.
* **Virtual Page URL:** Registers the `/authme` rewrite rule, which redirects guest users to the homepage with a query parameter (`?authme_open=1`) to automatically trigger and open the login/register overlay.
* **WooCommerce Integration:** Intercepts WooCommerce checkout and account pages. Unauthenticated users trying to access these pages are redirected to the homepage or cart page where the login popup is automatically displayed.
* **Real-time AJAX Validation:** Validates username and email availability live as the user types during registration.
* **Database Management Panel:** Provides a backend dashboard and database health checker with a one-click repair/create functionality for custom OTP storage tables.
* **OTP Cleanup Cron:** Runs a twice-daily WP-Cron job (`authme_otp_cleanup`) to purge verified and expired OTP records from the database.

### What It Is Used For (Purpose)
* **Secure Registration:** Ensures that user accounts are only created after email verification, preventing spam accounts and fake registrations.
* **Two-Factor Authentication (2FA) Login:** Enhances security by requiring both password verification and OTP validation before completing the user login.
* **Seamless Checkout Authentication:** Streamlines the user registration and login experience directly on the WooCommerce checkout page without page reloads.

### Target Users (Who is it for?)
* **Store Administrators:** Who want to protect their site/WooCommerce store from bots, spam registrations, and credential stuffing attacks.
* **E-Commerce Customers:** Who want a fast, simple, and secure authentication process without leaving the shop or checkout page.

---

## 2. Lens Zone (main-lens-zone)

* **Repository / Download URL:** [https://github.com/ART-TECH-FUZION-PROJECTS/main-lens-zone.git](https://github.com/ART-TECH-FUZION-PROJECTS/main-lens-zone.git)
* **Author:** Art-Tech Fuzion
* **Version:** 7.4 (Core logic version is 4.4)

### What It Does (Functionality)
* **Step-by-Step Selection Modal:** Displays a frontend wizard overlay for selecting eyeglass lenses:
  1. **Select Lens Type:** Primary categories (e.g., Single Vision, Bifocal, Progressive).
  2. **Select Lens Sub-Category:** Custom options (e.g., Anti-Glare, Blue Cut, Photochromic) with custom pricing and benefits.
  3. **Prescription Submission:** Offers three methods to submit eye power:
     * **Submit Later:** Allows customers to place an order and submit their prescription within 7 days.
     * **Manual Entry:** Inputs for SPH, CYL, Axis, and Add. Power for Left (OS) and Right (OD) eyes.
     * **Upload Prescription:** Customers can drag-and-drop or select PDF, JPEG, or PNG files up to 5MB.
* **WooCommerce Product Editor Integration:** Adds a custom "Lens Categories" metabox tab inside the WooCommerce product editor to configure lens options and sizing specs per product.
* **Frame Size Specifications:** Allows defining sizing options (e.g., Medium, Large) alongside precise dimensions (Lens Width, Bridge Width, Temple Length) with custom SVG icons on the product page.
* **In-Order Communication Chat:** Integrates a communication panel on the "My Account -> Order Details" (frontend) and WooCommerce Admin Order page (backend). Customers and admins can message each other and upload files/prescriptions.
* **Real-time Price Calculation:** Displays a dynamic live subtotal that combines the frame price and selected lens price during the selection flow.
* **Cart & Order Metadata Binding:** Automatically attaches selected lens options, prescription details, and uploaded prescription file URLs as line-item metadata in the WooCommerce cart, checkout, and backend order records.

### What It Is Used For (Purpose)
* **Prescription Lens Customization:** Enables optical e-commerce stores to sell prescription lenses online in combination with eyeglass frames.
* **Prescription Collection:** Streamlines the collection of complex medical prescription details (manual inputs or file uploads) from customers.
* **Post-Order Communication:** Facilitates admin-customer chat directly within WordPress for resolving prescription issues, verifying power, or submitting late files.

### Target Users (Who is it for?)
* **Optical E-Commerce Store Owners:** Who need a dedicated, professional workflow to configure, price, and sell prescription lenses with frames.
* **Eyeglass Customers:** Who want a simple, guided walkthrough to configure their lenses, input/upload their prescription details, and verify pricing in real-time.
