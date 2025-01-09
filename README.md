# MERN Stack Sign-Up and Sign-In Form (Backend Only)

## Project Overview
This project implements a backend system using **Node.js**, **Express.js**, and **MongoDB** to provide **Sign-Up** and **Sign-In** functionality with password encryption and token-based authentication.

---

## Task 01: Backend Implementation

### Endpoints

#### **POST /api/signup**
- Accepts `username`, `email`, and `password`.
- Hashes the password using **bcrypt**.
- Saves the user to MongoDB.
- Ensures email uniqueness and returns a success or error response.

#### **POST /api/signin**
- Validates user credentials.
- Generates a **JWT (JSON Web Token)** on successful authentication.
- Returns an error for invalid credentials.

#### **GET /api/protected**
- Requires a valid **JWT** for access.
- Returns access to protected content or an error for invalid/missing tokens.

---

## Task 02: Database Implementation

### MongoDB Setup
- Schema includes fields: 
  - `username` (String, required)
  - `email` (String, required, unique)
  - `password` (String, required)
- Implements unique indexing on `email`.

### Password Security
- Uses **bcrypt** to hash passwords before saving them to the database.

---

## Environment Variables
Sensitive data is stored in a `.env` file:
```env
MONGO_URI=<Your_MongoDB_URI>
JWT_SECRET=<Your_Secret_Key>
