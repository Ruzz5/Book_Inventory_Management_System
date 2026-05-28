# PeakBook — Book Inventory Management System
### By Rizza Paga | University of Mindanao | CS20/L | S.Y. 2025–2026

---

## Tech Stack
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Backend**: PHP 8+
- **Database**: MySQL / MariaDB
- **Charts**: Chart.js (CDN)
- **Fonts**: Google Fonts (Cormorant Garamond + DM Sans)

---

## Project Structure

```
peakbook/
├── index.php               ← Login page
├── database.sql            ← Run this first to create the DB
├── css/
│   └── style.css           ← All styles
├── js/
│   └── main.js             ← API calls, table manager, modals, toasts
├── php/
│   ├── config.php          ← DB credentials
│   ├── auth.php            ← Session helper
│   ├── login.php           ← Login handler
│   ├── register.php        ← Register handler
│   ├── logout.php          ← Logout + redirect
│   └── api.php             ← CRUD API for all entities
├── pages/
│   ├── layout.php          ← Shared sidebar include
│   ├── register.php        ← Sign-up page
│   ├── dashboard.php       ← Dashboard with stats + weekly chart
│   ├── inventory.php       ← Main CRUD (Orders, Customers, Books,
│   │                          Suppliers, Couriers, Payments)
│   ├── analysis.php        ← Charts & analysis
│   └── reports.php         ← Printable income reports
└── images/
    ├── mountain.png        ← The mountain background image
    ├── wallet_icon.png     ← Wallet icon for stat card
    ├── shield_icon.png     ← Shield icon for stat card
    └── chart_icon.png      ← Chart icon for stat card
```

---

## Setup Instructions

### 1. Place the project in your web server root
Copy the `peakbook/` folder to:
- **XAMPP**: `C:/xampp/htdocs/peakbook/`
- **WAMP**: `C:/wamp64/www/peakbook/`
- **LAMP**: `/var/www/html/peakbook/`

### 2. Create the database
Open **phpMyAdmin** (or MySQL CLI) and run:
```sql
SOURCE /path/to/peakbook/database.sql;
```
Or paste the contents of `database.sql` into phpMyAdmin's SQL tab.

### 3. Configure database credentials
Edit `php/config.php`:
```php
define('DB_HOST', 'localhost');
define('DB_USER', 'root');        // Your MySQL username
define('DB_PASS', '');            // Your MySQL password
define('DB_NAME', 'peakbook_db');
```

### 4. Add your images
Copy your design images into the `images/` folder:
- `mountain.png`   — the black & white mountain photo
- `wallet_icon.png` — the gold wallet icon
- `shield_icon.png` — the shield icon
- `chart_icon.png`  — the bar chart icon

### 5. Open in browser
Navigate to: `http://localhost/peakbook/`

**Default login** (from seed data):
- Email: `rizz@peakbook.com`
- Password: `password`

---

## Features
- ✅ User Login & Registration (bcrypt password hashing)
- ✅ Dashboard with live stats (total books, customers, income)
- ✅ Weekly income bar chart
- ✅ Full CRUD for: **Books, Customers, Orders, Suppliers, Couriers, Payments**
- ✅ Search / pagination on all tables
- ✅ Add / Edit modal dialogs with smart dropdowns
- ✅ Delete confirmation dialog
- ✅ Toast notifications (success / error)
- ✅ Analysis page with 4 charts
- ✅ Reports page with date range filter and print support
- ✅ Responsive sidebar layout
- ✅ Dark mountain aesthetic matching your Figma design

---

## Database Tables
| Table | Primary Key | Description |
|---|---|---|
| users | user_id | Admin accounts |
| books | book_id | Book inventory |
| customers | customer_id | Customer records |
| orders | order_id | Purchase orders |
| suppliers | supplier_id | Book suppliers |
| couriers | courier_id | Delivery couriers |
| payments | payment_id | Payment records |
