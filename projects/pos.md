# Point‑of‑Sale System (POS)

![Python](https://img.shields.io/badge/Python-Backend-blue?logo=python)
![Django](https://img.shields.io/badge/Django-Framework-darkgreen?logo=django)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue?logo=mysql)
![Bootstrap](https://img.shields.io/badge/Bootstrap-Frontend-purple?logo=bootstrap)
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-yellow?logo=javascript)
![Docker](https://img.shields.io/badge/Docker-Container-blue?logo=docker)
![Gunicorn](https://img.shields.io/badge/Gunicorn‑WSGI-success)
![VPS](https://img.shields.io/badge/VPS‑Production%20Server-orange)

A **full‑featured, secure, and scalable** Point‑of‑Sale (POS) web application designed to **streamline retail operations**, **manage inventory**, and **track sales & payments** for small‑to‑medium businesses.

---

## 🎯 Objective

Create a **single, web‑based platform** that eliminates manual cash registers and spreadsheets by enabling:

* Real‑time product & stock management  
* Fast, reliable sales entry and receipt generation  
* Integrated billing, invoicing, and payment tracking  
* Role‑based access control for cashiers, managers, and admins  

All of this while keeping **data integrity**, **auditability**, and **ease of deployment** at the core.

---

## 🧩 Overview

The POS system is built around a **modular Django architecture**:

| App | Core purpose |
|-----|--------------|
| `administrator` | Company settings, user roles, site configuration |
| `inventory`     | Products, categories, brands, stock, warehouses, serial numbers |
| `sales`         | Customers, sale orders, sale items, payments |
| `purchases`     | Suppliers, purchase orders, purchase items |
| `finance`       | Expenses, expense approval workflow |
| `crm`           | Loyalty transactions, customer rewards |
| `userprofile`  | Profile extensions for all users |
| Default Django apps (`auth`, `admin`, `contenttypes`, `sessions`, `sites`) | Authentication, admin UI, content‑type registry |

The **data model** mirrors a classic retail workflow:

1. **Products** belong to **categories** & **brands** → stocked in **warehouses**.  
2. **Stock** records track quantity per **product variant** (size, colour, etc.).  
3. **SaleOrder** creates a **receipt**, links **SaleItem** (product + quantity) and **Payment** info.  
4. **PurchaseOrder** updates **Stock** when goods are received.  
5. **Expense** entries can be submitted and approved by managers, feeding the **financial dashboard**.  

All CRUD permissions are generated automatically (see `data.json`), and custom roles (`staff`, `admin`) are seeded for quick testing.

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| **Backend** | Python 3.11+, Django 4.x, Django REST Framework (optional APIs) |
| **Database** | MySQL (default) – can be swapped for PostgreSQL |
| **Frontend** | HTML5, CSS3, Bootstrap 5, vanilla JavaScript (AJAX) |
| **Containerisation** | Docker & Docker‑Compose (single service for dev, ready to extend for prod) |
| **WSGI Server** | Gunicorn (recommended for production) |
| **Static Files** | Collected via `collectstatic`, served by Nginx in prod |
| **Security** | Role‑Based Access Control (RBAC), Django’s built‑in auth, CSRF protection, HTTPS enforcement |

---

## ✨ Key Features

### 🏪 Retail Management
* **Product catalog** with images, pricing, tax rates, and multi‑variant support.
* **Category & brand hierarchy** to organise merchandise.
* **Warehouse & stock location** management (multiple warehouses supported).

### 📦 Inventory Control
* **Real‑time stock updates** on sales and purchases.
* **Serial number tracking** for high‑value items (e.g., electronics, jewellery).
* **Stock movement logs** (inbound/outbound) for audit trails.

### 💰 Sales & Payments
* **Fast sales entry** – barcode scanning / product search.
* **Multiple payment methods** (cash, card, digital wallets) with auto‑generated receipts.
* **Partial / over‑payment handling**, refunds, and return processing.

### 📄 Purchasing & Supplier Management
* **Supplier directory** with contact information.
* **Purchase order creation**, receipt of goods, automatic stock replenishment.
* **Purchase history** linked to each product for cost analysis.

### 📊 Dashboard & Reporting
* **Overview cards** – today’s sales, low‑stock alerts, revenue, expenses.
* **Charts** (sales per day, top‑selling products, cash vs. card split).
* **Export** options – CSV / PDF for end‑of‑day reporting.

### 👥 Role‑Based Access
| Role | Permissions |
|------|-------------|
| **Superuser** (`anup`) | Full admin, site settings, data import/export |
| **Staff** (`admin`, `staff`) | Sale entry, product lookup, limited admin UI |
| **Manager** (custom role) | View reports, approve expenses, manage users |

### 📦 Extensibility
* **REST API** (DRF) ready for mobile POS terminals or third‑party integrations.
* **Pluggable payment gateway** stub – replace with Stripe/PayPal in minutes.
* **Docker‑Compose** makes scaling to a production stack (Gunicorn + Nginx + DB) straightforward.

---

## 🖼️ Screenshots (placeholder)

> Add screenshots of the actual UI under the `screenshots/pos/` folder and reference them here.

| Login | Dashboard |
|-------|-----------|
| `![Login](screenshots/pos/login.png)` | `![Dashboard](screenshots/pos/dashboard.png)` |

| Product List | Sale Entry |
|------------|------------|
| `![Products](screenshots/pos/products.png)` | `![Sale](screenshots/pos/sale.png)` |

| Stock Movement | Purchase Order |
|----------------|----------------|
| `![Stock](screenshots/pos/stock.png)` | `![Purchase](screenshots/pos/purchase.png)` |

---

## 👨‍💻 Role & Responsibilities (author’s view)

* **System architecture & DB schema design** – mapped retail workflows to Django models.  
* **Implemented core business logic** – stock deduction on sale, purchase receipt handling, expense approval workflow.  
* **Built a clean, responsive UI** using Bootstrap 5 and vanilla JavaScript for quick data entry.  
* **Secured the application** with RBAC, CSRF protection, and hashed passwords.  
* **Dockerised the project** for one‑click local development and easy production rollout.  
* **Wrote initial fixtures** (`data.json`) to seed permissions, countries, and demo users.

---

## 📈 Business Value (client‑focused)

| Benefit | Impact |
|---------|--------|
| **Reduced checkout time** | Faster sales → higher customer satisfaction and throughput. |
| **Accurate inventory** | Prevents stock‑outs, minimizes shrinkage, enables reorder alerts. |
| **Transparent financials** | Real‑time sales & expense reports simplify bookkeeping. |
| **Scalable** | Add new stores/warehouses without code changes – just new DB rows. |
| **Audit‑ready** | All stock movements & payments are logged; helps with compliance. |

---

## 📄 License

This repository is shared **for portfolio and demonstration purposes** only.  
For commercial use, customisation, or support, please get in touch with the author.

---

## 📬 Contact  

**Author:** *Anup Mondal*  
📧 Email: [anup12.m@gmail.com](mailto:anup12.m@gmail.com)  
💼 LinkedIn: <https://www.linkedin.com/in/dsanup/>  

---

**⭐ Interested in a tailored POS solution?** Feel free to open an issue or send a direct message.! 

---  
