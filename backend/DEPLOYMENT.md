# Cloth Shop Management System - Deployment Guide

This guide deploys the backend API on Render and connects it with MongoDB Atlas. Use this after pushing the project to your own GitHub repository.

## Required platforms

- GitHub for source code
- MongoDB Atlas for database
- Render for backend API
- Vercel for frontend
- MongoDB Compass for viewing saved data

## Backend environment variables for Render

Set these in Render Dashboard → Environment:

```env
NODE_ENV=production
PORT=5000
MONGODB_URI=mongodb+srv://USERNAME:PASSWORD@YOUR_CLUSTER.mongodb.net/inventory_billing?retryWrites=true&w=majority
JWT_SECRET=replace_with_a_long_random_secret
JWT_EXPIRE=7d
DEFAULT_BUSINESS_ID=default_business_123
FRONTEND_URL=https://your-vercel-frontend-url.vercel.app