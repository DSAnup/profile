# 🍽️ Restaurant Management System (RMS)

![Python](https://img.shields.io/badge/Python-Backend-blue?logo=python)
![Django](https://img.shields.io/badge/Django-Framework-darkgreen?logo=django)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue?logo=mysql)
![Bootstrap](https://img.shields.io/badge/Bootstrap-Frontend-purple?logo=bootstrap)
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-yellow?logo=javascript)
![Docker](https://img.shields.io/badge/Docker-Container-blue?logo=docker)
![Gunicorn](https://img.shields.io/badge/Gunicorn-WSGI-success)
![Nginx](https://img.shields.io/badge/Nginx-Web%20Server-green?logo=nginx)

A **complete, secure, and scalable** web based Restaurant Management System built with **Django**.  
It centralises every day restaurant operation – from **menus, orders, kitchen workflows, tables & reservations** to **billing, inventory, and staff management** – while keeping data safe with **role based access control**.

---

## 🎯 Objective  

The goal of the **Restaurant Management System** is to replace manual paperwork, spreadsheets and fragmented POS solutions with a **single digital platform** that:

* Handles **order taking**, **kitchen ticketing**, and **bill generation** in real‑time.  
* Provides **branch & multi‑kitchen support**, so a franchise can manage many outlets from one dashboard.  
* Allows **role‑based access** for owners, managers, chefs, waiters, and accountants.  
* Offers **insightful analytics** on sales, inventory, staff performance and customer activity.  

With RMS you can serve more guests, reduce errors, and get instant visibility into the health of your restaurant.

---

## 🧩 Overview  

The system is a **web‑application** that can be accessed from any modern browser (desktop, tablet, or phone).  
Key concepts in the data model (see `data.json` & `offline.json`) include:

| Model | Description |
|-------|--------------|
| `CompanySettings` | Global branding, currency and UI preferences. |
| `SiteSettings` | Current site (restaurant) configuration, subscription & activation flags. |
| `Branch` | Physical restaurant location – each branch can have its own logo, phone, paper width, etc. |
| `Kitchen` | Individual kitchen/section (e.g., “Chinese”, “Grill”, “Fast‑Food”). Supports **multiple kitchen workflow** per branch. |
| `User`, `UserRole`, `UserBranch` | Authentication with **role‑based permissions** (`admin`, `manager`, `waiter`, `chef`, `accountant`). |
| `InternationalRegion`, `Country` | Master data for address handling and tax calculations. |
| `SubscriptionPlan` | SaaS style subscription (user limits, plan description). |
| `SiteUser` | Links a Django user to a particular site/branch. |

All of the above are managed through the admin UI (`/admin/`), while the public side can be built on top of the same models (menus, order screens, etc.).

---

## 🛠️ Technology Stack  

| Layer | Technology |
|-------|------------|
| **Backend** | Python 3.11, Django 5.x, Django‑REST‑Framework |
| **Database** | MySQL (via `pymysql`) – also compatible with PostgreSQL |
| **Frontend** | HTML5, CSS3, Bootstrap 5, vanilla JavaScript (AJAX for real‑time order updates) |
| **Containerisation** | Docker (see `docker‑compose.yml`) |
| **Web Server** | Gunicorn + Nginx (recommended for production) |
| **DevOps** | Git, GitHub Actions (optional CI) |
| **Security** | Role‑Based Access Control, CSRF protection, secure file storage for receipts & documents |

---

## ✨ Key Features  

| Category | Feature |
|----------|---------|
| **Multi‑Branch & Multi‑Kitchen** | Unlimited branches, each with multiple kitchens (e.g., Grill, Juice Bar, Chap). Kitchen tickets are routed automatically. |
| **User & Role Management** | Admin, Manager, Chef, Waiter, Accountant – each with granular permissions. |
| **Subscription & Licensing** | SaaS‑style plans with user limits, expiry dates and optional feature toggles (import/export, PDF generation, etc.). |
| **Menu & Order Management** *(to be built on top of core models)* | Real‑time order entry, kitchen ticketing, order status tracking, table assignment. |
| **Billing & Payments** | Automatic invoice creation, payment recording, currency handling (`company_currency`). |
| **Inventory & Cost Control** *(future extension)* | Stock tracking per branch, low‑stock alerts, purchase orders. |
| **Analytics Dashboard** | Dashboard with case summaries, sales overview, revenue by branch/kitchen, staff KPIs, printable charts. |
| **Internationalisation** | Country/Region master data, flexible address fields, multi‑currency support. |
| **Export/Import Utilities** | CSV/Excel/PDF export for reports (controlled by `company_*` flags). |
| **Responsive UI** | Works on desktops, tablets and mobile browsers for floor‑staff. |
| **Docker Ready** | One‑command start with `docker‑compose up -d`. |
| **Secure Authentication** | Django’s built‑in auth + CSRF token handling (see `locustfile.py` for login flow). |

---

## 🖼️ Screenshots  

> _Add screenshots of your own UI (dashboard, branch list, kitchen view, order screen, etc.) in the `screenshots/` folder and reference them below._

| Description | Image |
|-------------|-------|
| **Login & Role Based Access** | `screenshots/login.png` |
| **Dashboard – Overview** | `screenshots/dashboard_overview.png` |
| **Branch Management** | `screenshots/branch_list.png` |
| **Kitchen Ticket List** | `screenshots/kitchen_tickets.png` |
| **Settings – Company & Site** | `screenshots/settings.png` |

*(If you don’t have screenshots yet, create placeholder images or remove the table.)*

---

## 👨‍💻 Roles & Responsibilities  

| Role | Typical Responsibilities |
|------|----------------------------|
| **Owner / Admin** | Create & edit branches, kitchens, subscription plans; view all reports; manage users & permissions. |
| **Manager** | Oversee daily operations of a branch, control menus, monitor kitchen workflow, approve expenses. |
| **Chef / Kitchen Staff** | Receive tickets, update order status, mark items ready, view prep queue. |
| **Waiter / Front‑of‑House** | Take orders from customers, assign to tables, send to kitchen, generate bills, record payments. |
| **Accountant** | Review invoices, process payments, generate financial statements, handle tax reports. |

---

## 📈 Business Value (Why Choose This RMS?)  

| Benefit | Impact |
|---------|--------|
| **Reduced Order Errors** | Real‑time ticket routing eliminates mis‑communication between waiters and kitchens. |
| **Faster Service** | Kitchen sees only active tickets; staff can prioritize high‑value orders. |
| **Transparent Financials** | Automatic invoicing and payment tracking provide instant revenue visibility. |
| **Scalable Architecture** | Add new branches or kitchens without code changes – just configure via the admin UI. |
| **Data‑Driven Decisions** | Dashboard analytics help you optimise menu pricing, staff scheduling and inventory. |
| **Secure & Compliant** | Role‑based permissions protect sensitive sales & client data. |
| **Lower Operating Costs** | Replace multiple POS / Excel sheets with a single, maintainable platform. |

---

## 📄 License  

The source code is provided **for portfolio and demonstration purposes only**.  
If you wish to use, modify, or commercialise this system, please reach out to the author for a proper licensing agreement.

---

## 📬 Contact  

**Author:** *Anup Mondal*  
✉️ Email: **anup12.m@gmail.com**  
💼 LinkedIn: <https://www.linkedin.com/in/dsanup/>

Feel free to open an issue or submit a pull request if you spot a bug or have a feature request.  

--- 

⭐️ **Interested in a customised restaurant management solution?** Get in touch – I can adapt this system to your exact workflow, integrate POS hardware, or deploy it on a cloud/VPS environment.  
