# Client Portal Security Notice

## ⚠️ CRITICAL: Production Deployment Requirements

### Current Implementation Status
The client portal is **DEMONSTRATION/PROTOTYPE ONLY** and requires critical security updates before production use.

## Critical Security Issue

### Problem: Client-Side Data Filtering
The following API endpoints return ALL customer data without server-side scoping:

- `/api/vehicles` - Returns ALL vehicles from all customers
- `/api/appointments` - Returns ALL appointments  
- `/api/invoices` - Returns ALL invoices
- `/api/job-cards` - Returns ALL job cards

**Risk Level**: CRITICAL - Any authenticated customer can enumerate and access other customers' private data.

### Current Workaround
Client portal pages filter data on the frontend:
