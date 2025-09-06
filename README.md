# NodeJS-RBAC
# NodeJS RBAC Authorization

This project demonstrates **Role-Based Access Control (RBAC)** in a Node.js and Express.js application.  
It includes authentication and authorization for different roles: **Admin, Manager, and User**.

---

## 🚀 Features

- User Registration & Login (JWT Authentication)
- Role-Based Authorization (Admin, Manager, User)
- Protected Routes (accessible only by specific roles)
- MongoDB for user storage
- Middleware for authentication and role checking

---

## 📂 Project Structure

NodeJS-RBAC-AUTHORIZATION/
│── node_modules/ # Dependencies
│── src/
│ ├── config/
│ │ └── dbConnect.js # MongoDB connection
│ ├── controllers/
│ │ └── authController.js # Auth logic (register, login)
│ ├── middlewares/
│ │ ├── authMiddleware.js # Verify JWT
│ │ └── roleMiddleware.js # Role-based access control
│ ├── models/
│ │ └── userModel.js # User schema (with role field)
│ ├── routes/
│ │ ├── authRoutes.js # Auth routes
│ │ └── userRoutes.js # Protected user routes
│ └── index.js # Main entry point
│
│── .env # Environment variables
│── .gitignore
│── package.json
│── README.md


---

## 🔧 Installation & Setup

### 1. Clone Repository
```bash
git clone https://github.com/your-username/NodeJS-RBAC-AUTHORIZATION.git
cd NodeJS-RBAC-AUTHORIZATION

Install Dependencies
npm install

Setup Environment Variables
Create a .env file in the root folder:
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key

Run the Application
npm start
(if using nodemon)
npm run dev

🔐 Authentication & Authorization
Register User

POST /api/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "123456",
  "role": "user"   // can be "admin", "manager", or "user"
}

Login
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "123456"
}

Access Protected Route

Add JWT token in headers:
Authorization: Bearer <token>

Role Protected Example
GET /api/users/admin

Only accessible by Admin
GET /api/users/manager

Only accessible by Manager and above
GET /api/users/profile


🛠️ Tech Stack

Node.js (Express.js)
MongoDB + Mongoose
JWT Authentication
Role-Based Middleware

📌 Future Improvements
Password hashing (bcrypt)
Refresh tokens
Admin dashboard
Role hierarchy management