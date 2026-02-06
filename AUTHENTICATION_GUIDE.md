# SALIS AUTO - Authentication System Guide

## Overview

The SALIS AUTO Garage Management System now uses **email/password authentication** instead of Replit Auth. This provides direct control over user management and role-based access.

## Authentication Features

✅ **Email/Password Login** - Secure bcrypt password hashing  
✅ **User Registration** - Self-service account creation  
✅ **Role-Based Access Control** - 7 different user roles  
✅ **Session Management** - PostgreSQL-backed sessions  
✅ **Secure Logout** - Proper session cleanup  

---

## Test User Accounts

All test users have been pre-created with the following credentials:

### Administrator Access
- **Email:** admin@salisauto.com  
  **Password:** motaz@6646  
  **Role:** Super Admin  
  **Description:** Full system access for administration

### General Testing
- **Email:** testuser@salisauto.com  
  **Password:** 1234abcd  
  **Role:** Garage Manager  
  **Description:** Standard testing account

### Role-Specific Users

#### Garage Manager
- **Email:** manager@salisauto.com  
  **Password:** Manager123!  
  **Role:** Garage Manager  

#### Branch Manager
- **Email:** branchmanager@salisauto.com  
  **Password:** Branch123!  
  **Role:** Branch Manager  

#### Lead Technician
- **Email:** leadtech@salisauto.com  
  **Password:** Lead123!  
  **Role:** Lead Technician  

#### Technician
- **Email:** technician@salisauto.com  
  **Password:** Tech123!  
  **Role:** Technician  

#### Assistant
- **Email:** assistant@salisauto.com  
  **Password:** Assist123!  
  **Role:** Assistant  

---

## User Roles & Permissions

### 1. Super Admin
- Full system access
- User management
- System configuration
- All garage operations

### 2. Garage Manager
- Manage garage operations
- View reports and analytics
- Manage inventory and orders
- Oversee technicians

### 3. Branch Manager
- Manage branch-specific operations
- Assign tasks to technicians
- View branch reports
- Handle customer relations

### 4. Lead Technician
- Oversee technical staff
- Assign and review work
- Technical decision making
- Quality control

### 5. Technician
- Perform repairs and maintenance
- Update job cards
- Log parts usage
- Complete assigned tasks

### 6. Assistant
- Administrative support
- Customer communication
- Appointment scheduling
- Basic data entry

---

## Authentication Endpoints

### Login
- **URL:** `POST /api/login`
- **Body:** `{ "email": "user@example.com", "password": "password123" }`
- **Response:** User object (without password)

### Register
- **URL:** `POST /api/register`
- **Body:** `{ "email": "user@example.com", "password": "password123", "fullName": "John Doe", "phone": "+1234567890" }`
- **Response:** User object (without password)

### Logout
- **URL:** `POST /api/logout`
- **Response:** `{ "message": "Logged out successfully" }`

### Get Current User
- **URL:** `GET /api/auth/user`
- **Headers:** Requires authenticated session
- **Response:** User object (without password)

---

## Frontend Routes

### Public Routes (No Authentication Required)
- `/` - Landing page with login/register buttons
- `/login` - Login form
- `/register` - Registration form

### Protected Routes (Authentication Required)
- `/dashboard` - Main dashboard
- `/job-cards` - Job card management
- `/customers` - Customer management
- `/vehicles` - Vehicle management
- All other application routes...

---

## Security Features

1. **Password Hashing** - Bcrypt with 10 salt rounds
2. **Session Storage** - PostgreSQL-backed sessions
3. **HTTP-Only Cookies** - Prevents XSS attacks
4. **Secure Cookies** - HTTPS-only in production
5. **Password Field Protection** - Never returned in API responses
6. **Audit Logging** - All user actions are logged

---

## Database Schema

### Users Table
