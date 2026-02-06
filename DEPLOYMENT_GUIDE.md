# SALIS AUTO - Production Deployment Guide

**Version:** 1.0  
**Last Updated:** November 3, 2025  
**Platform:** Replit

---

## Pre-Deployment Checklist

### ✅ Environment Configuration

1. **Environment Variables**
   ```bash
   # Database
   DATABASE_URL=postgresql://user:password@host:port/database
   
   # Session
   SESSION_SECRET=your-secure-random-string-min-32-chars
   
   # Stripe (if using payments)
   STRIPE_SECRET_KEY=sk_live_...
   STRIPE_PUBLISHABLE_KEY=pk_live_...
   
   # PayPal (if using payments)
   PAYPAL_CLIENT_ID=...
   PAYPAL_CLIENT_SECRET=...
   
   # Twilio (SMS notifications)
   TWILIO_ACCOUNT_SID=...
   TWILIO_AUTH_TOKEN=...
   TWILIO_PHONE_NUMBER=+1234567890
   
   # OpenAI (AI features)
   OPENAI_API_KEY=sk-...
   
   # Google APIs (Calendar/Gmail)
   GOOGLE_CLIENT_ID=...
   GOOGLE_CLIENT_SECRET=...
   
   # Application
   NODE_ENV=production
   PORT=5000
   ```

2. **Database Setup**
   - Provision Neon PostgreSQL database
   - Run migrations: `npm run db:push`
   - Verify connection: Test DATABASE_URL
   - Create database backup

3. **Security Configuration**
   - Generate strong SESSION_SECRET (32+ characters)
   - Enable HTTPS (automatic on Replit)
   - Configure CORS if needed
   - Set secure cookie flags

### ✅ Code Quality

1. **Testing**
   - Run all tests: `npm test` (when implemented)
   - Check for LSP errors
   - Verify build: `npm run build`
   - Test critical user flows

2. **Performance**
   - Optimize images
   - Enable caching
   - Minimize bundle size
   - Test load times

3. **Security**
   - No hardcoded secrets
   - Input validation on all endpoints
   - SQL injection prevention (via ORM)
   - XSS protection (React escaping)

---

## Deployment Steps on Replit

### Step 1: Database Migration
