# Enterprise ERP System v2.0

A complete, self‑hosted Enterprise Resource Planning (ERP) system built entirely in a **single HTML file**.  
Modern Material You design, real‑time data, offline‑capable localStorage, and optional Google Drive sync. No server, no build step – just open in a browser.

---

LIVE: https://gitjahs.github.io/My-ERP-system/


## 📸 Demo

> *Open `index.html` in any modern browser to see the live dashboard.*

![Dashboard Screenshot](https://via.placeholder.com/800x400?text=Dashboard+Screenshot)

---

## ✨ Features

### 📊 Dashboard
- **Real‑time KPI cards** – Total Customers, Active Products, Total Revenue, Total Paid, Outstanding Due, Net Profit, Active Employees, Total Purchased.
- **Daily metrics** – Profit, Sales, Purchases, Revenue, Expenses, Orders, Products Sold, Stock Added, Stock Removed (all calculated for the current day).
- **Inventory status** – Low Stock (below reorder level), Out of Stock, Total Products, SKUs, Categories, Brands.
- **Recent Invoices** – quick overview of latest transactions.

### 👥 Customers (CRM)
- Full customer records: name, phone, email, gender, date of birth.
- Address fields (street, city, state, country, postal code).
- Business info: type (retail/wholesale/VIP), company, industry, source.
- Financial info: credit limit, total spent/paid/due, loyalty points, risk level.
- Edit, delete (moves to trash), and search functionality.

### 📦 Products (Inventory)
- Product details: SKU (auto‑generated), barcode, name, size (comma‑separated), description.
- Categorisation: category and brand (with autocomplete suggestions from existing data).
- Pricing: cost price, sale price, tax rate, discount percentage.
- Stock management: quantity, reserved, available, reorder level, warehouse location.
- Supplier assignment.
- Photo upload with preview and optional resizer link (Squoosh).
- Inventory trend bar chart (top 10 active products).
- Status: active / inactive / discontinued.
- Edit, delete (trash), and search.

### 🧾 Invoices
- Create and edit invoices with:
  - Customer selection (active customers only, auto‑fills name/phone/email/address).
  - Seller assignment (active employees, quick‑add new employee inline).
  - Payment method (cash, bank, mobile, card, COD), paid amount, transaction ID.
  - Invoice status (draft, issued, partial, paid) with smart warnings.
  - Due date picker.
- **Multi‑item support** – add/remove rows dynamically, each with:
  - Product selector (shows stock, price, reorder level).
  - Size selector (parsed from product’s size field, plus custom “Others” option).
  - Quantity, unit price, discount, tax rate, auto‑calculated subtotal.
  - Low‑stock warning indicator.
- **Promo code** integration – automatically filters applicable promos based on product presence; applies percentage or fixed discount.
- **Terms & Conditions** with checkbox.
- **Company logo** upload (displayed on invoice).
- **PDF generation** – download invoice as PDF (html2pdf library).
- **Print invoice** – opens a styled print‑ready window with QR code.
- **Mail invoice** – generates PDF and triggers download (email integration not included).
- **QR code** – quick view via modal.
- **Stock deduction** – when invoice is issued/paid, stock is reduced; when moved to draft, stock is restored.
- **Customer totals** – automatically updates total spent/paid/due based on invoice status changes.
- Edit, delete (moves to trash with linked sale/income records).

### 🛒 Sales
- Automatically created from issued/paid invoices.
- Displays sale ID, linked invoice, customer, seller, total amount, profit, date.
- Filterable and searchable.

### 💰 Finance
- **Income** – auto‑generated from invoice payments, plus manual entry.
- **Expenses** – auto‑generated from purchase completions, plus manual entry.
- Net income KPI.
- Date filters on income and expense tables.
- Edit/delete (trash) for both.

### 🧑‍💼 Employees (HRM)
- Full employee records: name, phone, email, NID, father/mother name, address.
- Job info: department, role (with custom role option), salary, join date, status.
- Attendance and payroll arrays (data structure ready, UI not implemented).
- **Sales‑by‑employee report** – automatically aggregated from sales data.
- Edit, delete (trash).

### 🚚 Suppliers
- Supplier details: name, company, phone, email, address, payment terms, rating.
- Edit, delete (trash).

### 📥 Purchases
- Create purchase orders: select supplier, add multiple items.
- Items: product, size (autocomplete from product), quantity, cost, notes.
- Payment method and transaction ID.
- Status: pending / completed.
- When completed: stock is automatically increased, expense recorded.
- Print purchase order.
- Edit, delete (trash, with stock reversal).

### 🚛 Deliveries
- Track deliveries linked to invoices.
- Status: pending, shipped, delivered.
- Cost, address.
- Edit, delete (trash).

### 🎁 Offers & Promos
- Create promotional codes with:
  - Name, code, type (percentage or fixed amount).
  - Value, optional product restriction (applies to all if none).
  - Start and expiry dates.
  - Status (active/inactive).
- Automatically available in invoice promo selection (filters by product presence).
- Edit, delete (trash).

### 🤖 AI Advisor
- Scans system for:
  - **Low stock** – products below reorder level with quick actions: call/mail supplier, create purchase order.
  - **Overdue invoices** – unpaid/partial invoices past due date with quick actions: call/mail customer, view invoice.

### 📈 Reports
- Overview pie chart: Revenue, Expenses, Net Profit.
- Generate daily report saved with timestamp.
- View history of saved reports.

### 🔐 Audit Log
- Tracks all create, update, delete, restore actions across all modules.
- Stores timestamp, user (System), action, details.
- Last 200 entries displayed.

### 🗑️ Trash Bin
- Deleted items (customers, products, invoices, etc.) are moved to trash, not permanently erased.
- Restore individual items (with proper re‑linkage of associated records, e.g., sales, income).
- Permanently delete individual items.
- Empty entire trash.
- “Move all data to trash” option in Settings.

### ⚙️ Settings
- Company name, address, phone.
- Currency (e.g., USD, BDT, ₹), country.
- Theme: light / dark mode.
- Custom accent color.
- Google Drive sync – enter your OAuth 2.0 Client ID to enable cloud backup.

### 🔗 Google Drive Sync
- Sign in with Google via OAuth 2.0.
- **Auto‑save** to a JSON file on Google Drive every 5 minutes (debounced).
- **Manual sync** button in top bar with animated status indicator:
  - Offline = red pulsing dot
  - Online = green pulsing dot
  - Syncing = orange spinning ring
  - Error = yellow fast‑blinking dot
- **Load data** from Drive on login.

### 👥 Multiple Business Profiles
- Create, switch, rename, delete profiles.
- Each profile has completely isolated data stored in separate localStorage keys.
- Quick profile switcher in top bar.

### 📦 Import / Export
- **Export** – all profiles and their data to a single JSON file.
- **Import** – overwrites current data after confirmation, supports old‑format data migration.

### 🎨 UI / UX
- **Material You design** (Material Design 3) with dynamic light/dark themes.
- Fully responsive – works on desktop, tablet, and mobile.
- Collapsible sidebar with hamburger menu.
- Animated modals, toasts, and button interactions.
- Real‑time clock in top bar.
- **Server Uptime Monitor** – displays daily uptime (resets at midnight) and lifetime uptime (persisted across sessions), updated every second.
- Alert bell with badge count and audible alert for new notifications.
- Only the close button can close modals; Escape key closes all modals safely.
- No duplicate event listeners – buttons always trigger exactly once.

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, Safari).
- Internet connection for external libraries (Material Icons, QRCode.js, html2pdf.js, Google Sign‑In). They are loaded from CDN; offline fallback toasts are shown if unavailable.

### Installation
1. **Download** the `index.html` file.
2. **Open** it directly in your browser – no server required.

> *For Google Drive sync, you need to create a Google Cloud project and obtain an OAuth 2.0 Client ID. Enter it in Settings → Google Client ID.*

---

## 🛠️ Technologies Used
- **Frontend:** HTML5, CSS3, JavaScript (vanilla ES6+)
- **Libraries (loaded via CDN):**
  - [Material Symbols Rounded](https://fonts.google.com/icons) – icons
  - [QRCode.js](https://github.com/davidshimjs/qrcodejs) – QR code generation
  - [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) – PDF generation
  - [Google Identity Services](https://developers.google.com/identity) – OAuth 2.0
- **Storage:** `localStorage` for all data (per profile), `sessionStorage` for Google token.
- **Design:** Material Design 3 (custom CSS variables, no framework).

---

## 🧩 Architecture
- Entire application is a single‑page app (SPA) with dynamic content rendering.
- Data is stored as a JSON object in `localStorage`, keyed by profile ID.
- All CRUD operations are handled by the `DB` object, with audit logging and trash bin logic.
- Google Drive sync uses the Google Drive API v3 to upload/download a JSON file.

---

## 🔒 Security Notes
- The app runs entirely client‑side; there is no backend or authentication.
- For Google Drive sync, the access token is stored in `sessionStorage` and sent to Google’s API. Use a restricted API key or OAuth client.
- All sensitive data is stored in the browser’s localStorage; clear it when needed.

---

## 📝 Changelog (v2.0 Final)
- All core ERP modules implemented.
- Google Drive sync with animated status indicator.
- Server uptime monitor (daily + lifetime).
- Enhanced dashboard with daily metrics and inventory KPIs.
- Trash bin with restore/permanent delete.
- Multiple business profiles.
- Import/export all data.
- Comprehensive bug fixes:
  - Sync status correctly shows failure.
  - Customer totals properly reversed on invoice status change.
  - Promo codes respect product restrictions.
  - Google Sign‑In button fires only once.
  - Printed invoice includes icons.
  - Advisor “Create Purchase” button works.
  - PDF generation fails gracefully.
  - Date filters retain rows without dates.
  - Event‑listener duplication eliminated.
  - Modals close correctly with Escape key.
  - All calculator code removed (final version).

---

## 📄 License
MIT – feel free to use, modify, and distribute.

---

---

##  Create the Google Drive API credentials

1. **Go to the Google Cloud Console**  
   Open [console.cloud.google.com](https://console.cloud.google.com) and sign in with the Google account you want to use for backups.

2. **Create a new project**  
   - Click the project dropdown (top left) → **New Project**.  
   - Name it `ERP System` (or anything).  
   - Click **Create**. Wait a few seconds for it to switch to the new project.

3. **Enable the Google Drive API**  
   - In the search bar, type `Google Drive API`.  
   - Click the result, then click **Enable**.  
   - After a moment you’ll see “API Enabled”.

4. **Configure the OAuth consent screen**  
   - Navigate to **APIs & Services → OAuth consent screen**.  
   - Choose **External** (unless you have a Google Workspace account). Click **Create**.  
   - Fill in the required fields:  
     - **App name**: e.g. `My Private ERP`  
     - **User support email**: your email  
     - **Developer contact email**: your email  
   - Click **Save and Continue** (skip scopes).  
   - **Test users**: click **Add Users**, enter your own email, then **Save and Continue**.  
   - Click **Back to Dashboard**.

5. **Create an OAuth 2.0 Client ID**  
   - Go to **Credentials** → **Create Credentials → OAuth client ID**.  
   - **Application type**: `Web application`.  
   - **Name**: `ERP Web Client`.  
   - **Authorised JavaScript origins**: click **Add URI** and enter your GitHub Pages origin **exactly**:  
     ```
     https://your-username.github.io
     ```  
     (replace `your-username` with your actual GitHub username – no trailing slash, no path).  
   - Click **Create**.  
   - **Copy the Client ID** that appears – you’ll need it in the next step.

---

## 🔗 Part 3 – Connect the ERP to Google Drive

1. **Open your ERP** at your GitHub Pages URL:  
   `https://your-username.github.io/my-erp/`

2. **Go to Settings**  
   Click **⚙️ Settings** in the left sidebar.

3. **Enter the Client ID**  
   Scroll down to the **🔗 Google Drive Sync** section.  
   Paste your **Client ID** into the `Google Client ID` field.

4. **Save settings**  
   Click the **Save Settings** button at the top of the page.

5. **Sign in with Google**  
   Click the **G  Sign in with Google** button in the same card.  
   - A Google pop‑up will open. Choose your Google account and grant permission.  
   - After granting, the button changes to **✅ Connected to Google Drive**.

6. **Syncing starts automatically**  
   - Every change you make in the ERP is automatically saved to your Google Drive within **2 seconds**.  
   - You can also click the **🔄 Sync** button in the top bar to force a manual sync at any time.  
   - The top‑bar indicator shows `Online` / `Offline` / `Syncing…`.

---

## ✅ Done!

Your ERP is now **online** (the page itself is public, but your business data stays **private** inside your personal Google Drive).  
A file called `erp_data.json` will appear in your Drive – it contains all your business profiles and can be used to restore your data on any other device.

---

## 🙏 Credits
- **Developed by:** AI
- **Instructed & Constructed by:** MD. JUNAYED AL HABIB
- [Subscribe on YouTube: @iamxtremeV](https://www.youtube.com/@iamxtremeV)

---

© 2025 | Material Design 3 | All rights reserved.
