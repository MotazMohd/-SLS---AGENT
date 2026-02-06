# SALIS AUTO - Administrator Guide

## 📋 Table of Contents
- [Overview](#overview)
- [System Administration](#system-administration)
- [User Management](#user-management)
- [Security Administration](#security-administration)
- [Database Management](#database-management)
- [System Configuration](#system-configuration)
- [Monitoring & Maintenance](#monitoring--maintenance)
- [Backup & Recovery](#backup--recovery)
- [Performance Optimization](#performance-optimization)

---

## Overview

This guide is for **System Administrators** who manage and maintain the SALIS AUTO platform. It covers installation, configuration, user management, security, and ongoing maintenance tasks.

### Administrator Responsibilities

- ✅ System installation and configuration
- ✅ User account management
- ✅ Security and access control
- ✅ Database administration
- ✅ System monitoring and performance
- ✅ Backup and disaster recovery
- ✅ Integration management
- ✅ Compliance and auditing

---

## System Administration

### Accessing Admin Panel

1. Login as System Administrator
   ```
   Email: admin@salisauto.com
   Password: password123 (change immediately!)
   ```

2. Navigate to **Settings** → **System Administration**

3. Admin panel includes:
   - User Management
   - Role & Permission Management
   - System Configuration
   - Integration Settings
   - Security & Audit Logs
   - Database Management
   - System Health Monitoring

### System Information

View system status at **Settings** → **System Info**:

- **Version**: Current platform version
- **Database**: Connection status, size, table count
- **Server**: CPU, memory, disk usage
- **Active Users**: Currently logged in users
- **Workflows**: Background jobs status
- **Integrations**: Connected services status

---

## User Management

### Creating User Accounts

1. Navigate to **Settings** → **User Management**
2. Click **"+ Add User"**
3. Enter user details:
   - Full Name *
   - Email Address * (will be username)
   - Phone Number
   - User Type: staff / customer
   - Garage Assignment
   - Branch Assignment (for branch-level roles)
4. Assign Role (see RBAC section)
5. Click **"Create User"**
6. System sends welcome email with temp password

### Assigning Roles

SALIS AUTO includes **24 pre-configured professional roles**:

**System Level:**
- System Administrator (full access)

**Garage Level:**
- Business Owner
- General Manager
- Garage Manager
- Finance Manager
- Accountant
- HR Manager
- Marketing Manager
- Warehouse Manager

**Branch Level:**
- Service Manager
- Service Advisor
- Parts Manager
- Lead Technician
- Technician
- Call Center Agent
- Customer Service Representative
- Receptionist
- Quality Control Inspector

**To Assign Role:**
1. Select user
2. Go to **Roles** tab
3. Click **"+ Assign Role"**
4. Select Role
5. Select Branch (for branch-level roles)
6. Set as Primary Role (checkbox)
7. Click **"Assign"**

### Managing Permissions

**View User Permissions:**
1. Select user
2. Go to **Permissions** tab
3. View all granted permissions by category

**Permission Override:**
1. Select user
2. Click **"Add Override"**
3. Select resource and action
4. Grant or Deny
5. Add reason (for audit trail)
6. Set expiration date (optional)
7. Click **"Save Override"**

### Deactivating Users

1. Navigate to user profile
2. Click **"Deactivate Account"**
3. Enter reason
4. Confirm deactivation
5. User cannot login (data preserved)
6. Can reactivate anytime

### Resetting Passwords

**Force Password Reset:**
1. Select user
2. Click **"Reset Password"**
3. Choose method:
   - Send reset link via email
   - Generate temporary password
4. User must change on next login

---

## Security Administration

### Two-Factor Authentication (2FA)

**Enable 2FA for Administrators:**
1. Navigate to **Security Settings**
2. Toggle **"Require 2FA for Administrators"**
3. All admin users must setup 2FA on next login

**Setup 2FA (User)**:
1. Profile → Security
2. Click **"Enable 2FA"**
3. Scan QR code with authenticator app
4. Enter verification code
5. Save backup codes

### Session Management

**Configure Session Settings:**
- **Session Timeout**: 30 minutes (configurable)
- **Max Sessions Per User**: 3 (configurable)
- **Remember Me**: 30 days
- **Force Logout**: After password change

**View Active Sessions:**
1. Navigate to **Security** → **Active Sessions**
2. View all logged-in users
3. Force logout individual sessions
4. Bulk logout all sessions

### Access Control

**IP Whitelisting:**
1. Navigate to **Security** → **IP Whitelist**
2. Add allowed IP ranges
3. Block all others
4. Useful for restricting admin access

**Rate Limiting:**
- Login attempts: 5 per 15 minutes
- API requests: 100 per minute per user
- Password resets: 3 per hour

### Audit Logs

**View Audit Trail:**
1. Navigate to **Security** → **Audit Logs**
2. Filter by:
   - User
   - Action type
   - Resource
   - Date range
   - IP address
3. Export logs for compliance

**Logged Actions:**
- User login/logout
- Password changes
- Permission changes
- Data modifications (create/update/delete)
- Configuration changes
- Payment transactions
- Failed login attempts

---

## Database Management

### Database Health

**Monitor Database:**
1. Navigate to **Settings** → **Database**
2. View metrics:
   - Total size
   - Table count (290+ tables)
   - Row counts
   - Index health
   - Query performance
   - Connection pool status

### Database Backup

**Automated Backups:**
- Frequency: Every 6 hours
- Retention: 30 days
- Storage: Encrypted cloud storage
- Includes: Full database dump

**Manual Backup:**
