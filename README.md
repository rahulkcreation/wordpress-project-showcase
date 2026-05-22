# WordPress Project Showcase

Welcome to the **WordPress Project Showcase** repository. This repository serves as a centralized, structured portfolio and archive for various custom WordPress and WooCommerce projects, custom themes, unique feature integrations, and standalone web-based solutions.

To maintain a clean and historical record of development progress, all projects are organized chronologically by year.

---

## 📂 Repository Structure

The workspace is organized into year-based directories:

```text
wordpress-project-showcase/
└── projects-(YYYY)/          # Chronological group folders (e.g., projects-(2026))
    ├── project-name-1/       # Individual project folder
    │   ├── details.md        # Technical specifications & download references
    │   └── ...               # Additional configuration, documentation, or assets
    └── project-name-2/
```

### 1. `projects-(YYYY)/`
Each year-wise directory contains individual subdirectories for the projects worked on or delivered during that calendar year. This organization provides a clean timeline of work.

### 2. Inside Each Project Folder:
Every project folder is self-contained and typically includes:
* **Technical Analysis & Reference (`details.md`)**: Detailed documentation mapping out:
  * Key functionalities and features.
  * Purpose and business use cases.
  * Target audience/users.
  * Links to download or access the original repositories/assets.
* **Architecture Diagrams**: Visual aids (such as Entity-Relationship Diagrams or flowcharts) illustrating database tables and data flows where applicable.
* **Implementation Details**: Structural explanations and setup guidelines for deploying the features.

---

## 🛠️ Key Technical Focus Areas

The projects documented in this showcase primarily focus on:
* **WooCommerce Extensions**: Building dynamic product options, custom fields, live subtotal calculations, and tailored e-commerce workflows (e.g., step-by-step product personalization wizards).
* **Custom Authentication & Security**: Implementing OTP-based verification systems, passwordless login processes, and custom access control overlays to replace standard WordPress authentication.
* **Customer-Admin Communication**: Creating dedicated backend/frontend communication hubs (like in-order messaging/attachment handlers) within WordPress.
* **Database Optimization**: Designing custom relational database schemas alongside WordPress's core tables to support bespoke functionality efficiently.

---

## ⚡ Development & Coding Standards

All showcased projects are developed using strict WordPress development guidelines:

1. **Separation of Concerns**
   * Backend and database queries are completely separated from frontend layout logic.
   * View templates handle structure (HTML/PHP), while logic and interactivity are delegated to external controllers (JavaScript).
2. **Performance & Cache-Busting**
   * Style sheets and scripts are enqueued via standard WordPress hooks (`wp_enqueue_style`, `wp_enqueue_script`).
   * Dynamic file versioning based on file modification time (`filemtime()`) is implemented to prevent browser caching issues during updates.
3. **Tailored Styling**
   * CSS is custom-written and scoped to prevent namespace bleed.
   * Responsive layout practices ensure interfaces look premium and adjust cleanly to all screen sizes.
4. **Security & Data Integrity**
   * All dynamic queries use `$wpdb->prepare` to protect against SQL Injection.
   * Frontend actions leverage WordPress Nonces to verify request legitimacy and prevent CSRF.
   * Strict input sanitization (`sanitize_text_field()`, `sanitize_email()`) and output escaping (`esc_html()`, `esc_attr()`, `wp_kses_post()`) are used throughout.