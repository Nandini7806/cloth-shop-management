# Cloth Shop Management Backend

Backend API for a cloth shop management system. It supports product inventory, customers, vendors, sales, purchases, stock updates, reports, and JWT-based authentication.

## Features

- **Authentication**: Register, login, profile management, password change, and JWT protection
- **Product Management**: Add, update, delete, search, categorize, and track stock
- **Customer & Vendor Management**: Store customer/vendor details and balances
- **Transactions**: Record sales and purchases with automatic stock updates
- **Reports**: Inventory, transaction, customer/vendor, and dashboard reports
- **Security**: Helmet, CORS, rate limiting, password hashing, request validation, and business-level data isolation

## Tech Stack

- Node.js
- Express.js
- MongoDB + Mongoose
- JWT + bcryptjs
- Helmet, CORS, express-rate-limit
- express-validator
- Morgan

## Prerequisites

- Node.js 18 or higher
- MongoDB Atlas account or local MongoDB
- npm

## Quick Start

Install dependencies from the backend folder:

```bash
cd backend
npm install