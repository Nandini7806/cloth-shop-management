# Cloth Shop Management Backend - Quick Start

## Prerequisites

Before running the backend, make sure you have:

* Node.js 18 or higher
* npm
* MongoDB Atlas account or local MongoDB
* MongoDB Compass for viewing database data

## 1. Install dependencies

Open terminal in your project and run:

```bash
cd backend
npm install
```

## 2. Configure environment variables

Create a file named `.env` inside the `backend` folder.

Path:

```txt
backend/.env
```

Paste this structure inside it:

```env
PORT=5000
NODE_ENV=development

MONGODB_URI=mongodb+srv://USERNAME:PASSWORD@YOUR_CLUSTER.mongodb.net/inventory_billing?retryWrites=true&w=majority

JWT_SECRET=replace_with_a_long_random_secret
JWT_EXPIRE=7d

DEFAULT_BUSINESS_ID=default_business_123
FRONTEND_URL=http://localhost:3000
```

Replace:

```txt
USERNAME
PASSWORD
YOUR_CLUSTER
```

with your actual MongoDB Atlas details.

Do not commit `.env` to GitHub.

## 3. Generate JWT secret

Run this command:

```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

Copy the generated value and paste it in `.env`:

```env
JWT_SECRET=your_generated_secret_here
```

## 4. Start backend locally

From the `backend` folder, run:

```bash
npm run dev
```

Expected backend URL:

```txt
http://localhost:5000
```

## 5. Test backend health

Open this in browser:

```txt
http://localhost:5000/health
```

You can also check API docs:

```txt
http://localhost:5000/api/docs
```

## 6. Register a test user

You can register from frontend or test using curl:

```bash
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"name":"Cloth Shop Admin","email":"clothshop.test@example.com","password":"Password123","businessId":"cloth_shop_001"}'
```

Password must contain:

* at least one uppercase letter
* at least one lowercase letter
* at least one number
* minimum 6 characters

Example valid password:

```txt
Password123
```

## 7. View saved data in MongoDB Compass

Open MongoDB Compass.

Paste the same MongoDB Atlas connection string that you used in `MONGODB_URI`.

After successful registration, refresh Compass and check:

```txt
inventory_billing → users
```

Later, after adding products, contacts, and transactions, you should see collections like:

```txt
users
products
contacts
transactions
```

## 8. Common issues

### MongoDB connection failed

Check:

* Atlas username
* Atlas password
* IP access list
* database URL format
* password special characters

If password contains `@`, replace it with:

```txt
%40
```

### 400 Bad Request during register

Use a strong password like:

```txt
Password123
```

Also make sure `businessId` is not empty.

### CORS error

Make sure backend `.env` has:

```env
FRONTEND_URL=http://localhost:3000
```

For deployment, replace it with your Vercel frontend URL.

## 9. Deployment

For deployment, use:

* MongoDB Atlas for database
* Render for backend
* Vercel for frontend
* MongoDB Compass for viewing database data

See `DEPLOYMENT.md` for full deployment steps.
