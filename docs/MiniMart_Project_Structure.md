# MiniMart — E-Commerce Website

## 1. Project Overview

MiniMart is a simple full-stack e-commerce website developed as a two-developer team project.

The system allows customers to:

* Register and log in
* Browse products
* View product details
* Search and filter products
* Add products to a shopping cart
* Update and remove cart items
* Complete checkout
* Place orders
* View order history
* View order details

The system also contains a basic Admin Panel for managing:

* Products
* Categories
* Orders
* Dashboard information

### Main Objective

The project is also being used to practice professional Git and GitHub collaboration, including:

* Branch creation
* Feature development
* Commits
* Pull Requests
* Code review
* Branch merging
* Pulling updated code
* Merge conflict resolution

Both developers will work on **frontend and backend**, rather than separating the team into frontend-only and backend-only roles.

---

# 2. Technology Stack

## Frontend

| Technology     | Purpose                              |
| -------------- | ------------------------------------ |
| React          | Frontend application                 |
| TypeScript     | Type-safe JavaScript development     |
| Vite           | Frontend development/build tool      |
| Tailwind CSS   | UI styling                           |
| React Router   | Frontend routing                     |
| TanStack Query | Server-state and API data management |
| Axios          | HTTP/API communication               |

## Backend

| Technology        | Purpose                        |
| ----------------- | ------------------------------ |
| Node.js           | Backend runtime                |
| NestJS            | Backend framework              |
| TypeScript        | Backend development            |
| REST API          | Frontend-backend communication |
| Prisma            | ORM/database access            |
| PostgreSQL        | Relational database            |
| JWT               | Authentication                 |
| class-validator   | Request validation             |
| Swagger / OpenAPI | API documentation              |

## Development Tools

| Tool    | Purpose                             |
| ------- | ----------------------------------- |
| Git     | Version control                     |
| GitHub  | Remote repository and collaboration |
| Postman | API testing                         |
| VS Code | Development environment             |

---

# 3. High-Level Architecture

```text
                    MiniMart
                       |
              +--------+--------+
              |                 |
           Frontend          Backend
              |                 |
       React + TypeScript   NestJS + TypeScript
              |                 |
        Tailwind CSS        REST API
              |                 |
          Axios / Query          |
              |                 |
              +--------+--------+
                       |
                    Prisma
                       |
                   PostgreSQL
```

---

# 4. Main System Modules

## Customer Side

### Authentication

* Register
* Login
* Logout
* JWT authentication
* Protected routes

### Products

* Product listing
* Product details
* Product search
* Category filtering
* Price filtering

### Shopping Cart

* Add product
* Update quantity
* Remove product
* View cart
* Calculate cart total

### Checkout

* Customer information
* Shipping information
* Order summary
* Place order

### Orders

* Order confirmation
* My Orders
* Order details
* Order status

### Profile

* View profile
* Update profile

---

# 5. Admin Side

## Admin Dashboard

The admin dashboard will provide a basic overview of the system.

Possible information:

* Total products
* Total categories
* Total orders
* Recent orders

## Product Management

Admin can:

* Create product
* View products
* Update product
* Delete product

## Category Management

Admin can:

* Create category
* View categories
* Update category
* Delete category

## Order Management

Admin can:

* View all orders
* View order details
* Update order status

---

# 6. Repository Structure

The project will use a simple monorepo structure.

```text
Task_Management_System_team/
│
├── README.md
│
├── docs/
│   └── MiniMart_Project_Structure.md
│
├── frontend/
│   ├── public/
│   │
│   ├── src/
│   │   ├── assets/
│   │   │
│   │   ├── components/
│   │   │
│   │   ├── layouts/
│   │   │
│   │   ├── pages/
│   │   │
│   │   ├── features/
│   │   │
│   │   ├── hooks/
│   │   │
│   │   ├── services/
│   │   │
│   │   ├── routes/
│   │   │
│   │   ├── types/
│   │   │
│   │   ├── utils/
│   │   │
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── index.css
│   │
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   └── .env.example
│
├── backend/
│   ├── src/
│   │   ├── auth/
│   │   ├── users/
│   │   ├── products/
│   │   ├── categories/
│   │   ├── cart/
│   │   ├── orders/
│   │   │
│   │   ├── common/
│   │   │
│   │   ├── app.module.ts
│   │   └── main.ts
│   │
│   ├── prisma/
│   │   ├── schema.prisma
│   │   └── migrations/
│   │
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
│
├── .gitignore
└── package.json
```

---

# 7. Frontend Folder Responsibilities

## `components/`

Reusable UI components.

Examples:

```text
Navbar
Footer
ProductCard
ProductGrid
Button
Input
Modal
LoadingSpinner
```

## `layouts/`

Application layouts.

Examples:

```text
MainLayout
AdminLayout
AuthLayout
```

## `pages/`

Application pages.

Examples:

```text
HomePage
ProductsPage
ProductDetailsPage
CartPage
CheckoutPage
LoginPage
RegisterPage
ProfilePage
OrdersPage
OrderDetailsPage
AdminDashboardPage
AdminProductsPage
AdminOrdersPage
```

## `features/`

Feature-specific frontend logic.

Example:

```text
features/
├── auth/
├── products/
├── cart/
├── checkout/
├── orders/
└── admin/
```

## `services/`

API communication.

Examples:

```text
authService.ts
productService.ts
cartService.ts
orderService.ts
userService.ts
```

## `routes/`

Frontend route configuration.

## `types/`

Shared TypeScript types/interfaces.

---

# 8. Backend Folder Responsibilities

Each major business area will have its own NestJS module.

Example:

```text
products/
├── dto/
├── products.controller.ts
├── products.service.ts
└── products.module.ts
```

## `auth/`

Authentication functionality.

```text
auth/
├── dto/
├── guards/
├── strategies/
├── auth.controller.ts
├── auth.service.ts
└── auth.module.ts
```

Responsibilities:

* Register
* Login
* JWT generation
* Authentication guards

## `users/`

User/profile functionality.

Responsibilities:

* Get profile
* Update profile
* User information

## `products/`

Product functionality.

Responsibilities:

* Create product
* Get products
* Get product by ID
* Update product
* Delete product

## `categories/`

Category functionality.

Responsibilities:

* Create category
* Get categories
* Update category
* Delete category

## `cart/`

Shopping cart functionality.

Responsibilities:

* Get cart
* Add item
* Update quantity
* Remove item
* Calculate totals

## `orders/`

Order functionality.

Responsibilities:

* Create order
* Get customer orders
* Get order details
* Update order status
* Admin order management

## `common/`

Shared backend functionality.

Possible contents:

```text
common/
├── decorators/
├── guards/
├── interceptors/
├── pipes/
├── filters/
└── utils/
```

---

# 9. Database Structure

The initial database will contain the following main entities:

```text
User
 │
 ├────────────── Cart
 │                 │
 │                 └── CartItem
 │                       │
 │                       ▼
 │                    Product
 │                       │
 │                       ▼
 │                    Category
 │
 └────────────── Order
                    │
                    └── OrderItem
                           │
                           ▼
                         Product
```

## Main Tables

```text
users
products
categories
carts
cart_items
orders
order_items
```

---

# 10. Developer Responsibilities

The project uses a two-developer structure.

Both developers will work on:

```text
Frontend + Backend
```

---

# 11. Developer 1 — Product & Cart

## Frontend Responsibilities

Developer 1 will work on:

* Home Page
* Product Listing
* Product Details
* Product Search
* Product Filtering
* Shopping Cart
* Admin Product Management
* Admin Category Management

## Backend Responsibilities

Developer 1 will work on:

* Product Module
* Category Module
* Cart Module

### Database Responsibilities

```text
Product
Category
Cart
CartItem
```

### Suggested Feature Branches

```text
feature/products
feature/categories
feature/cart
feature/admin-products
```

---

# 12. Developer 2 — Authentication & Orders

## Frontend Responsibilities

Developer 2 will work on:

* Register Page
* Login Page
* Authentication State
* Protected Routes
* Profile Page
* Checkout Page
* Order Confirmation
* My Orders
* Order Details
* Admin Dashboard
* Admin Order Management

## Backend Responsibilities

Developer 2 will work on:

* Authentication Module
* User Module
* Order Module

### Database Responsibilities

```text
User
Order
OrderItem
```

### Suggested Feature Branches

```text
feature/auth
feature/profile
feature/orders
feature/admin-dashboard
```

---

# 13. Developer Ownership Summary

| Area             |          Developer 1 |          Developer 2 |
| ---------------- | -------------------: | -------------------: |
| Home             |                    ✅ |                      |
| Products         | ✅ Frontend + Backend |                      |
| Categories       | ✅ Frontend + Backend |                      |
| Product Details  |                    ✅ |                      |
| Search / Filter  |                    ✅ |                      |
| Cart             | ✅ Frontend + Backend |                      |
| Register / Login |                      | ✅ Frontend + Backend |
| Profile          |                      | ✅ Frontend + Backend |
| Checkout         |                      |                    ✅ |
| Orders           |                      | ✅ Frontend + Backend |
| Admin Products   |                    ✅ |                      |
| Admin Categories |                    ✅ |                      |
| Admin Dashboard  |                      |                    ✅ |
| Admin Orders     |                      |                    ✅ |
| Product DB       |                    ✅ |                      |
| Category DB      |                    ✅ |                      |
| Cart DB          |                    ✅ |                      |
| User DB          |                      |                    ✅ |
| Order DB         |                      |                    ✅ |

---

# 14. GitHub Collaboration Workflow

The repository will use `main` as the stable branch.

```text
                       main
                         |
             +-----------+-----------+
             |                       |
       Developer 1              Developer 2
             |                       |
       feature/products        feature/auth
       feature/categories      feature/profile
       feature/cart            feature/orders
             |                       |
             ▼                       ▼
         Pull Request            Pull Request
             |                       |
          Review                  Review
             |                       |
             +-----------+-----------+
                         |
                       Merge
                         |
                        main
```

---

# 15. Git Rules

### Main Branch

The `main` branch should contain stable and reviewed code.

Developers should normally not develop directly on `main`.

### Feature Branches

Every feature should be developed in its own branch.

Example:

```bash
git checkout -b feature/auth
```

### Commits

Commits should describe the work clearly.

Examples:

```text
Add login API
Create registration page
Add product listing
Implement cart API
Create order service
```

### Pull Requests

After completing a feature:

```text
Feature Branch
      ↓
Push to GitHub
      ↓
Create Pull Request
      ↓
Code Review
      ↓
Merge into main
```

### Updating Local Main

After another developer merges changes:

```bash
git checkout main
git pull origin main
```

Then update your feature branch when necessary.

---

# 16. Merge Conflict Practice

The project will intentionally include Git merge-conflict practice.

Example:

```text
Developer 1
      |
      | modifies shared file
      |
      ▼
   feature branch
      |
      ▼
    GitHub
      |
      ▼
    Merge
      |
      ▼
     main


Developer 2
      |
      | also modified same file
      |
      ▼
   feature branch
      |
      ▼
 git pull / merge
      |
      ▼
   CONFLICT
      |
      ▼
 Resolve conflict
      |
      ▼
 Commit
      |
      ▼
 Push / Pull Request
```

The purpose is to learn how to:

* Identify a conflict
* Understand conflicting changes
* Choose the required code
* Remove conflict markers
* Test the application
* Commit the resolution
* Push the corrected branch

---

# 17. Initial Development Order

The recommended implementation order is:

```text
1. Repository Setup
        ↓
2. Frontend Setup
        ↓
3. Backend Setup
        ↓
4. Database Setup
        ↓
5. Authentication
        ↓
6. Categories
        ↓
7. Products
        ↓
8. Cart
        ↓
9. Checkout
        ↓
10. Orders
        ↓
11. Admin Dashboard
        ↓
12. Admin Management
        ↓
13. Testing
        ↓
14. Git Merge / Conflict Practice
```

---

# 18. Final Project Goal

By completing MiniMart, the team will gain practical experience in:

* React development
* TypeScript
* Tailwind CSS
* NestJS
* REST APIs
* Prisma
* PostgreSQL
* JWT authentication
* API integration
* Git branching
* GitHub Pull Requests
* Code reviews
* Branch merging
* Merge conflict resolution

The final application will be a functional mini e-commerce system developed collaboratively by two developers using a professional GitHub workflow.
