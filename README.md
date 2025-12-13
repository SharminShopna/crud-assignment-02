# 🚗 Vehicle Rental Management System

🔗 **Live Demo**  
👉 https://crud-assignment-02.vercel.app


## 📌 Project Overview
The **Vehicle Rental Management System** is a full-stack web application that enables users to rent vehicles online with a secure and role-based workflow.  
The system supports **Admin** and **Customer** roles and ensures proper booking lifecycle management, vehicle availability tracking, and data integrity.


## ✨ Features

### 👤 Authentication & Authorization
- User registration and login
- JWT-based authentication
- Role-based access control (**Admin / Customer**)
- Secure password hashing using **bcrypt**


### 🚘 Vehicle Management (Admin)
- Create, update, and delete vehicles
- Vehicles **cannot be deleted** if they have active bookings
- Real-time vehicle availability tracking


### 📅 Booking System (Customer & Admin)
- Customers can book available vehicles
- Customers can cancel bookings **before the start date**
- Admin can mark bookings as **returned**
- Automatic vehicle status updates:
  - **Booked → booked**
  - **Cancelled / Returned → available**


### 🔐 Data Safety & Business Rules
- Users cannot be deleted if they have active bookings
- Vehicles are protected from deletion when bookings are active
- Referential integrity maintained using PostgreSQL constraints


## 🛠 Technology Stack

### Backend
- **Node.js**
- **Express.js**
- **TypeScript**
- **PostgreSQL**

### Tools & Libraries
- **JWT** – Authentication & authorization
- **bcrypt** – Password hashing
- **dotenv** – Environment variable management


## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository
```bash
git clone <repository-url>
cd <project-folder-name>

2️⃣ Install Dependencies
npm install

3️⃣ Configure Environment Variables

Create a .env file in the root directory:
PORT=5000
CONNECTION_STR=your_postgresql_connection_string
JWT_SECRET=your_secret_key

4️⃣ Run the Application
npm run dev

The server will start on:
http://localhost:5000

📡 API Base URL
http://localhost:5000/api/v1

👥 User Roles
 Role     | Permissions                           
 -------- | ------------------------------------- 
 Admin    | Manage vehicles, users, and bookings  
 Customer | Book vehicles and manage own bookings 
