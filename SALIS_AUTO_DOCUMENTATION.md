# SALIS AUTO - Garage Management System
## Comprehensive System Documentation

### Executive Summary
SALIS AUTO is a complete, enterprise-grade SaaS platform for garage management, built with modern web technologies. The system serves 7 user types with role-based access control and implements 48 comprehensive modules covering all aspects of garage operations, from job cards and appointments to fleet management, warranty tracking, and vendor management.

**Current Status**: 45/48 modules complete (93.75%)  
**Technology Stack**: React 18, TypeScript, Express, PostgreSQL, Drizzle ORM  
**Design System**: SALIS AUTO Monochrome (Black/White/Gray palette)  
**Database Tables**: 70+ tables with full relational integrity  
**API Endpoints**: 250+ authenticated REST endpoints

**🇸🇦 NEW: Saudi Arabia Market Ready** (October 2025)  
Complete compliance and localization package including:
- ✅ 15% VAT calculations and breakdown
- ✅ ZATCA e-invoicing with QR codes (Fatoora standard)
- ✅ Hijri calendar support with dual date display
- ✅ Zakat calculations (2.5% Islamic tax)
- ✅ Arabic language with RTL support
- ✅ PDF/Excel exports with VAT compliance reports
- ✅ SMS reminders with Saudi phone formatting
- ✅ Dark/Light theme toggle

📖 **See [SAUDI_ARABIA_FEATURES.md](./SAUDI_ARABIA_FEATURES.md) for complete documentation**

---

## Table of Contents
1. [System Architecture](#system-architecture)
2. [Design System](#design-system)
3. [User Roles & Permissions](#user-roles--permissions)
4. [Core Modules (1-36)](#core-modules-1-36)
5. [Advanced Modules (37-48)](#advanced-modules-37-48)
6. [Technology Stack](#technology-stack)
7. [Database Architecture](#database-architecture)
8. [API Documentation](#api-documentation)
9. [Security & Compliance](#security--compliance)
10. [🇸🇦 Saudi Arabia Market Features](#saudi-arabia-market-features)
11. [Future Roadmap](#future-roadmap)

---

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with Vite build system
- **Routing**: wouter (lightweight routing library)
- **State Management**: TanStack Query v5 for server state
- **UI Components**: shadcn/ui (Radix UI primitives)
- **Styling**: Tailwind CSS with custom SALIS AUTO theme
- **Forms**: react-hook-form with Zod validation
- **Real-time**: WebSocket client for live updates

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Custom email/password auth with sessions
- **Session Store**: PostgreSQL-backed session storage
- **API Design**: RESTful endpoints with JSON responses
- **Real-time**: WebSocket server for chat and notifications

### Key Architectural Patterns
- **Component-Based**: Reusable UI components with consistent design
- **Type-Safe**: End-to-end TypeScript with shared schemas
- **Validation**: Zod schemas shared between client and server
- **Data Fetching**: React Query for caching, optimistic updates
- **Authentication**: Session-based auth with middleware protection
- **Database**: Drizzle ORM with type-safe queries

---

## Design System

### SALIS AUTO Monochrome Palette
The entire application uses a strict grayscale color palette with no colored accents.

**Core Colors**:
- **Black** (#010101): Primary text, active states, primary buttons, dark backgrounds
- **White** (#FFFFFF): Backgrounds (light mode), text on dark backgrounds
- **Gray** (#6B7280): Secondary text, muted elements, borders
- **Gray Light** (#D1D5DB): Subtle borders, disabled states, light backgrounds
- **Gray Dark** (#374151): Hover states, dark mode borders
- **50% Black** (#808080): Secondary buttons, muted accents

**Gradient**: Linear gradient from Black (#000000) → Gray (#505050) → 50% Black (#808080)

### Typography
**Primary Font (Headers/Logo)**: Montserrat
- Logo: Montserrat Bold with gradient text effect
- H1: Montserrat SemiBold, 2.5rem
- H2: Montserrat SemiBold, 2rem
- H3: Montserrat Medium, 1.5rem

**Secondary Font (Body/UI)**: Poppins and Inter
- Body text: Poppins Regular, 14-16px
- Subheadings: Poppins Medium, 18-24px
- Captions/Labels: Inter Light/Regular, 12-14px
- UI elements: Poppins Medium/SemiBold

### Tailwind Custom Classes
- `salis-black`, `salis-white`, `salis-gray`, `salis-gray-light`, `salis-gray-dark`, `salis-50-black`
- `font-montserrat`, `font-poppins`, `font-inter`
- `text-gradient-salis` (for logo)

### Light/Dark Theme
**Light Mode**:
- Backgrounds: White (#FFFFFF) for main, light gray for cards
- Text: Black (#010101) primary, grays for secondary
- Borders: Light gray (#D1D5DB)

**Dark Mode**:
- Backgrounds: Near-black (#010101) for main, dark gray for cards
- Text: White (#FFFFFF) primary, light grays for secondary
- Borders: Dark gray (#374151)

---

## User Roles & Permissions

### 7 User Types
1. **Super Admin**: Full system access, multi-tenant management
2. **Garage Owner**: Garage-level administration, reporting, settings
3. **Manager**: Operations management, staff oversight, approvals
4. **Service Advisor**: Customer interaction, job creation, estimates
5. **Technician**: Job execution, parts usage, time tracking
6. **Parts Manager**: Inventory management, purchase orders, suppliers
7. **Accountant**: Financial operations, invoicing, payments, reporting

### Permission System
- Granular role-based access control (RBAC)
- Module-level permissions (view, create, edit, delete)
- Action history tracking for audit compliance
- Session management with secure token handling

---

## Core Modules (1-36)

### 1. SaaS & Multi-Tenant Management
**Status**: ✓ Fully Implemented  
**Features**:
- Multi-garage support with branch management
- Subscription plan management (Free, Basic, Pro, Enterprise)
- Tenant isolation and data segregation
- Custom branding per garage
- Usage tracking and billing

**Database Tables**: `garages`, `branches`, `subscription_plans`

---

### 2. User & Role Management
**Status**: ✓ Fully Implemented  
**Features**:
- 7 user types with granular permissions
- Custom email/password authentication
- Role-based access control (RBAC)
- User profiles with preferences
- Session management
- Two-factor authentication (2FA) support

**Database Tables**: `users`, `roles`, `permissions`, `user_sessions`

---

### 3. Customer Profiles
**Status**: ✓ Fully Implemented  
**Features**:
- Comprehensive customer data management
- Contact information and communication preferences
- Service history tracking
- Customer notes and tags
- Preferred communication methods
- Birthday and anniversary tracking for marketing

**Database Tables**: `customers`, `customer_vehicles`, `customer_communications`

---

### 4. Technician Management
**Status**: ✓ Fully Implemented  
**Features**:
- Technician profiles with skills and certifications
- Performance tracking and KPIs
- Workload management
- Commission calculation
- Training and certification tracking
- Efficiency ratings

**Database Tables**: `technicians`, `technician_skills`, `technician_certifications`, `technician_performance`

---

### 5. Vehicle Management
**Status**: ✓ Fully Implemented  
**Features**:
- Complete vehicle records with VIN decoding
- NHTSA API integration for vehicle data
- Service history and maintenance schedules
- Vehicle photos and documentation
- Odometer tracking
- Automated maintenance reminders
- Support for all vehicle types (cars, trucks, motorcycles, etc.)

**Database Tables**: `vehicles`, `vehicle_service_history`, `vehicle_maintenance_schedules`

---

### 6. Job Cards (Work Orders)
**Status**: ✓ Fully Implemented  
**Features**:
- Digital work order creation and management
- Status tracking (Draft, Scheduled, In Progress, Completed, Invoiced)
- Technician assignment and time tracking
- Parts and labor management
- Customer approval workflows
- Before/after photos
- Digital signatures

**Database Tables**: `job_cards`, `job_card_items`, `job_card_technicians`, `job_card_parts`

---

### 7. Appointments
**Status**: ✓ Fully Implemented  
**Features**:
- Visual calendar scheduling with react-big-calendar
- Appointment types (Service, Inspection, Pickup, Dropoff)
- Customer and vehicle association
- SMS/Email reminders via Twilio
- Status tracking (Scheduled, Confirmed, In Progress, Completed, Cancelled)
- Recurring appointment support
- Technician availability management

**Database Tables**: `appointments`, `appointment_reminders`

---

### 8. Tool Management
**Status**: ✓ Fully Implemented  
**Features**:
- Equipment inventory tracking
- Calibration schedules and history
- Tool assignment to technicians
- Maintenance tracking
- Barcode scanning support
- Tool condition monitoring

**Database Tables**: `tools`, `tool_calibrations`, `tool_assignments`

---

### 9. Spare Parts Inventory
**Status**: ✓ Fully Implemented  
**Features**:
- Multi-location stock management
- Barcode scanning with @zxing/library
- Low stock alerts and notifications
- Automatic reorder point calculations
- Batch tracking and expiration dates
- Parts usage history
- Stock transfer between locations

**Database Tables**: `spare_parts`, `stock_locations`, `stock_movements`, `parts_usage`

---

### 10. TecDoc Integration
**Status**: ✓ Fully Implemented  
**Features**:
- Parts catalog lookup by VIN or vehicle details
- Cross-reference part numbers
- OEM and aftermarket parts
- Technical specifications
- Pricing information
- Part images and diagrams

**Integration**: TecDoc API with cached responses

---

### 11. Purchase Orders
**Status**: ✓ Fully Implemented  
**Features**:
- Supplier management with contact details
- Multi-item purchase orders
- Status tracking (Draft, Sent, Confirmed, Received, Cancelled)
- Expected delivery dates
- Partial receiving support
- Cost tracking and variance analysis
- Automated email notifications to suppliers

**Database Tables**: `purchase_orders`, `purchase_order_items`, `suppliers`

---

### 12. Invoicing & Billing
**Status**: ✓ Fully Implemented  
**Features**:
- Multi-currency invoice generation
- Automated tax calculations
- Line-item details (parts and labor)
- Discount and promotion application
- Payment status tracking
- PDF invoice generation
- Recurring invoices support
- Credit memo processing

**Database Tables**: `invoices`, `invoice_items`, `invoice_payments`

---

### 13. Payments
**Status**: ✓ Fully Implemented  
**Features**:
- Stripe integration for card payments
- PayPal integration for online payments
- Payment plan support (installments)
- Receipt generation
- Refund processing
- Payment history tracking
- Multiple payment methods per invoice

**Integrations**: Stripe SDK, PayPal Server SDK

**Database Tables**: `payments`, `payment_plans`, `refunds`

---

### 14. Estimates & Quotes
**Status**: ✓ Fully Implemented  
**Features**:
- Digital estimate creation with line items
- Parts and labor pricing
- Multiple versions and revisions
- Customer approval workflow
- Conversion to job cards
- Email delivery to customers
- Expiration date tracking

**Database Tables**: `estimates`, `estimate_items`, `estimate_approvals`

---

### 15. Reports & Analytics
**Status**: ✓ Fully Implemented  
**Features**:
- Business intelligence dashboard with recharts
- Revenue and profitability reports
- Technician performance metrics
- Customer retention analysis
- Parts usage and inventory reports
- Service type breakdown
- Time period comparisons
- Export to PDF/Excel

**Components**: Interactive charts, KPI cards, trend analysis

---

### 16. SMS Notifications
**Status**: ✓ Fully Implemented  
**Features**:
- Twilio integration for SMS delivery
- Appointment reminders (24hr, 1hr before)
- Job status updates
- Invoice payment reminders
- Service reminder notifications
- Custom message templates
- Delivery status tracking

**Integration**: Twilio API with message queuing

---

### 17. Service Reminders
**Status**: ✓ Fully Implemented  
**Features**:
- Automated maintenance schedule tracking
- Mileage-based reminders (oil change, tire rotation)
- Time-based reminders (annual inspection)
- Multi-channel notifications (SMS, Email, In-app)
- Customer opt-in/opt-out management
- Service history integration

**Database Tables**: `service_reminders`, `reminder_schedules`

---

### 18. Vehicle Service History
**Status**: ✓ Fully Implemented  
**Features**:
- Complete repair and maintenance logs
- Parts replaced tracking
- Labor performed details
- Warranty information
- Service recommendations
- Technician notes
- Before/after photos
- Timeline view of all services

**Database Tables**: `service_history`, `service_items`

---

### 19. Tax Configuration
**Status**: ✓ Fully Implemented  
**Features**:
- Multiple tax rates support
- Tax jurisdiction management
- Automated tax calculations on invoices
- Tax exemption handling
- Tax reporting for compliance
- Regional tax rules (state, county, city)

**Database Tables**: `tax_rates`, `tax_jurisdictions`

---

### 20. Discounts & Promotions
**Status**: ✓ Fully Implemented  
**Features**:
- Percentage and fixed amount discounts
- Promotion campaigns with start/end dates
- Customer segment targeting
- Automatic application rules
- Usage tracking and analytics
- Coupon code management
- Volume discounts

**Database Tables**: `discounts`, `promotions`, `promotion_usage`

---

### 21. Data Import/Export
**Status**: ✓ Fully Implemented  
**Features**:
- Bulk data import from CSV/Excel
- Customer data migration
- Vehicle import with VIN validation
- Parts inventory import
- Export to CSV/Excel/PDF
- Data validation and error reporting
- Template downloads

**Supported Entities**: Customers, Vehicles, Parts, Suppliers, Invoices

---

### 22. Global Search
**Status**: ✓ Fully Implemented  
**Features**:
- Advanced filtering across all entities
- Full-text search capabilities
- Multi-field search (name, email, phone, VIN, etc.)
- Real-time search results
- Search history
- Quick filters by status, date, type
- Keyboard shortcuts (Cmd+K)

**Searchable Entities**: Customers, Vehicles, Job Cards, Invoices, Parts, Appointments

---

### 23. Saved Filter Presets
**Status**: ✓ Fully Implemented  
**Features**:
- Custom search configuration saving
- Named filter presets
- Share presets with team members
- Quick access to common searches
- Default preset settings per user
- Filter templates for reports

**Database Tables**: `saved_filters`, `filter_presets`

---

### 24. Notifications
**Status**: ✓ Fully Implemented  
**Features**:
- In-app notification center
- Email notifications
- SMS notifications via Twilio
- Push notifications (PWA support)
- Notification preferences per user
- Read/unread tracking
- Notification history
- Custom notification rules

**Database Tables**: `notifications`, `notification_preferences`

---

### 25. Commission Management
**Status**: ✓ Fully Implemented  
**Features**:
- Technician commission tracking
- Configurable commission rules (%, fixed, tiered)
- Service type-based commissions
- Performance bonuses
- Commission period management (weekly, monthly)
- Payout tracking
- Commission reports

**Database Tables**: `commissions`, `commission_rules`, `commission_payouts`

---

### 26. Employee Attendance
**Status**: ✓ Fully Implemented  
**Features**:
- Time tracking with clock in/out
- Shift management
- Break time tracking
- Overtime calculation
- Attendance reports
- Late arrival tracking
- Absence management
- Mobile-friendly time clock

**Database Tables**: `attendance`, `time_entries`, `shifts`

---

### 27. Shift Templates
**Status**: ✓ Fully Implemented  
**Features**:
- Flexible scheduling system
- Recurring shift patterns
- Shift swapping with approvals
- Coverage management
- Shift preferences per employee
- Holiday scheduling
- On-call rotation management

**Database Tables**: `shift_templates`, `shift_assignments`, `shift_swaps`

---

### 28. Performance Reviews
**Status**: ✓ Fully Implemented  
**Features**:
- Employee evaluation system
- Customizable review criteria
- Review cycle management (quarterly, annual)
- Self-assessment options
- Manager feedback
- Goal setting and tracking
- Performance improvement plans
- Review history

**Database Tables**: `performance_reviews`, `review_criteria`, `review_goals`

---

### 29. Training Programs
**Status**: ✓ Fully Implemented  
**Features**:
- Employee skill development tracking
- Training course catalog
- Enrollment management
- Completion tracking with certificates
- Skill gap analysis
- Mandatory training assignments
- Training cost tracking
- External training provider integration

**Database Tables**: `training_programs`, `training_enrollments`, `training_completions`

---

### 30. Stock Alerts
**Status**: ✓ Fully Implemented  
**Features**:
- Low inventory notifications
- Out-of-stock alerts
- Reorder point triggers
- Excess stock warnings
- Expiration date alerts
- Multi-channel notifications (Email, SMS, In-app)
- Alert customization per part

**Database Tables**: `stock_alerts`, `alert_settings`

---

### 31. Security & Compliance
**Status**: ✓ Fully Implemented  
**Features**:
- Two-factor authentication (2FA) with speakeasy
- QR code-based TOTP setup
- Audit logs for all actions
- GDPR compliance tools
- Data retention policies
- User consent management
- Session security with timeout
- IP address logging
- Failed login tracking

**Database Tables**: `audit_logs`, `user_consents`, `security_settings`

---

### 32. User Settings
**Status**: ✓ Fully Implemented  
**Features**:
- Personalized preferences
- Theme selection (Light/Dark mode)
- Language preferences (i18next integration)
- Notification settings
- Email preferences
- Display settings (date format, currency)
- Keyboard shortcuts customization
- Dashboard widget configuration

**Database Tables**: `user_settings`, `user_preferences`

---

### 33. Action History
**Status**: ✓ Fully Implemented  
**Features**:
- Complete audit trail
- Entity-level change tracking
- User action logging
- Timestamp tracking
- Before/after value capture
- Searchable history
- Export for compliance
- Undo/Redo system integration

**Database Tables**: `action_history`, `change_logs`

---

### 34. Permission System
**Status**: ✓ Fully Implemented  
**Features**:
- Granular access control
- Module-level permissions
- Action-based permissions (view, create, edit, delete)
- Role-permission mapping
- Custom permission sets
- Permission inheritance
- Real-time permission checks
- Permission audit trails

**Database Tables**: `permissions`, `role_permissions`, `user_permissions`

---

### 35. Consent Management
**Status**: ✓ Fully Implemented  
**Features**:
- GDPR compliance
- Consent tracking for data processing
- Marketing consent management
- Cookie consent
- Terms of service acceptance
- Privacy policy acknowledgment
- Consent withdrawal
- Audit trail for legal compliance

**Database Tables**: `consents`, `consent_types`, `consent_history`

---

### 36. In-App Chat Support
**Status**: ✓ Fully Implemented  
**Features**:
- Real-time WebSocket-based chat
- Team collaboration messaging
- Direct messages between users
- Group chat rooms
- File sharing support
- Message history
- Typing indicators
- Online status tracking
- Unread message badges

**Technology**: WebSocket server with ws library

**Database Tables**: `chat_messages`, `chat_rooms`, `chat_participants`

---

## Advanced Modules (37-48)

### 37. Customer Self-Service Portal ✓
**Status**: ✓ COMPLETED  
**Implementation**: Comprehensive customer portal with secure access

**Features**:
- Online appointment booking with real-time availability
- Service history viewing with detailed records
- Estimate approval with digital signatures
- Online payment processing (Stripe/PayPal)
- Digital receipt downloads (PDF)
- Session management with token revocation
- Mobile-responsive interface
- Secure customer authentication

**Database Tables**: `customer_portal_sessions`, `portal_access_logs`

**Security**:
- Token-based authentication
- Session expiration (24 hours)
- IP address logging
- Secure password reset flow

**User Experience**:
- Clean, intuitive interface
- Real-time updates
- Mobile-first design
- Accessibility compliant (WCAG 2.1 AA)

---

### 38. Digital Signatures & Media Documentation ✓
**Status**: ✓ COMPLETED  
**Implementation**: Complete signature and media management system

**Features**:
- Canvas-based signature capture
- Consent tracking with legal compliance
- Photo/video upload with validation
- Before/after comparison gallery
- Media categorization (damage, walkaround, invoice, estimate)
- Server-side security (10MB limit, MIME type whitelist)
- Base64 validation for secure upload
- Audit trail (IP address, device info, timestamps)
- Reusable components across job cards/estimates/inspections

**Database Tables**: `digital_signatures`, `media_files`, `signature_consents`

**Security Measures**:
- MIME type validation (image/jpeg, image/png, video/mp4, etc.)
- File size limits (10MB max)
- Virus scanning integration ready
- Secure storage with access logs

**Integration Points**:
- Job Cards: Customer authorization signatures
- Estimates: Approval signatures
- Inspections: Damage documentation
- Invoices: Payment authorization

---

### 39. QR Code Check-In System ✓
**Status**: ✓ COMPLETED  
**Implementation**: Full QR code generation and scanning system

**Features**:
- Server-side QR generation with PNG images (qrcode library)
- Unique QR codes per appointment/customer/vehicle
- Scan validation (expiration, already used, invalid)
- Automated check-in workflow
  - Appointment status update (Scheduled → In Progress)
  - SMS notification to customer
  - In-app notification to service advisor
- Scan logging (device info, IP address, scan results)
- Appointment status history tracking
- Frontend components (QRCodeGenerator, QRScanner)
- Download/print QR codes
- Auto check-in support

**Database Tables**: `qr_codes`, `qr_scans`, `appointment_status_history`

**Use Cases**:
- Customer appointment check-in
- Vehicle identification
- Equipment tracking
- Document authentication

**Technical Implementation**:
- QR code format: JSON with encrypted appointment ID
- Expiration: 24 hours from appointment time
- One-time use validation
- @zxing/library for scanning

---

### 40. Fleet Management ✓
**Status**: ✓ COMPLETED  
**Implementation**: Enterprise fleet management with 5-tab interface

**Features**:
- **Groups Tab**: Fleet group organization, corporate client management
- **Vehicles Tab**: Fleet vehicle assignments, bulk operations
- **Contracts Tab**: Service contracts with terms & conditions
- **Pricing Tab**: Volume-based pricing tiers, garage-specific rules
- **Schedules Tab**: Automated maintenance scheduling

**Core Capabilities**:
- Corporate fleet client management with billing details
- Fleet vehicle assignments with group hierarchy
- Service contract management (annual, per-service, unlimited)
- Volume-based pricing tiers (Bronze, Silver, Gold, Platinum)
- Automated maintenance scheduling based on mileage/time
- Comprehensive filtering and search
- Full CRUD operations across all entities

**Database Tables**: `fleet_groups`, `fleet_vehicles`, `fleet_contracts`, `fleet_pricing`, `fleet_schedules`

**QA Coverage**: 150+ data-testid attributes for automation

**Business Benefits**:
- Streamlined fleet operations
- Automated billing for corporate clients
- Predictive maintenance scheduling
- Volume discount management
- Contract compliance tracking

---

### 41. Warranty Tracking ✓
**Status**: ✓ COMPLETED  
**Implementation**: Complete warranty management with claims processing

**Features**:
- **Active Warranties Tab**: Current warranty tracking
- **Expired Tab**: Historical warranty records
- **Claims Tab**: Warranty claim processing

**Warranty Types**:
- Parts warranties (manufacturer, extended)
- Labor warranties (garage-provided)
- Transferable warranties (vehicle sale support)

**Claims Processing**:
- Status tracking (Submitted, Approved, Rejected, Paid)
- Supporting documentation upload
- Claim amount tracking
- Approval workflow
- Settlement recording

**Alerts & Notifications**:
- 30-day expiration banner
- Automatic expiration notifications
- Claim status updates

**Database Tables**: `warranties`, `warranty_claims`

**Storage Methods**: 16 total (10 warranties, 6 claims)

**API Routes**: 16 authenticated endpoints with Zod validation

**QA Coverage**: 80+ data-testid attributes

**Integration Points**:
- Job Cards: Warranty-covered repairs
- Parts: Warranty part replacement
- Invoicing: Warranty claim billing

---

### 42. Marketing Automation
**Status**: ⏳ PENDING IMPLEMENTATION  
**Planned Features**:
- Email/SMS campaign management
- Customer segmentation and targeting
- Birthday and anniversary promotions
- Automated review requests
- Campaign analytics and ROI tracking
- A/B testing support
- Drip campaign automation
- Integration with Google Analytics

**Planned Database Tables**: `campaigns`, `campaign_segments`, `campaign_sends`, `campaign_analytics`

---

### 43. Vendor/Supplier Portal ✓
**Status**: ✓ COMPLETED  
**Implementation**: Complete vendor management with 4-tab interface

**Features**:
- **Suppliers Tab**: Supplier directory with contact management
- **Price Lists Tab**: Multi-supplier price comparison
- **Performance Tab**: Supplier performance tracking
- **Reorder Rules Tab**: Automated reordering configuration

**Price Comparison**:
- Side-by-side price comparison cards
- Multiple suppliers per part
- Lead time comparison
- Availability status
- Minimum order quantities

**Automated Reordering**:
- Min/max stock level rules
- Automatic PO generation
- Lead time consideration
- Preferred supplier selection

**Performance Tracking**:
- Quality scores (0-100%)
- On-time delivery rate
- Defect rate tracking
- Price competitiveness metrics
- Overall supplier rating
- Performance period tracking

**Database Tables**: `supplierPriceList`, `supplierPerformance`, `reorderSettings`

**Storage Methods**: 11 total (price lists, performance, comparison)

**API Routes**: 11 authenticated endpoints with Zod validation

**QA Coverage**: 71 data-testid attributes

**Business Benefits**:
- Cost optimization through price comparison
- Reduced stockouts with automated reordering
- Supplier accountability through performance metrics
- Data-driven supplier selection

---

### 44. Customer Loyalty Program
**Status**: ⏳ PENDING IMPLEMENTATION  
**Planned Features**:
- Points system for service spending
- Membership tiers (Bronze, Silver, Gold, Platinum)
- Referral tracking and rewards
- Rewards catalog with redemption
- Points expiration management
- Tier upgrade notifications
- Birthday and anniversary bonuses
- Gamification elements

**Planned Database Tables**: `loyalty_members`, `loyalty_points`, `loyalty_tiers`, `loyalty_rewards`, `loyalty_redemptions`

---

### 45. Vehicle Inspection Checklists ✓
**Status**: ✓ COMPLETED  
**Implementation**: Digital multi-point inspection system

**Features**:
- **Templates Tab**: Customizable inspection templates
- **Inspections Tab**: Performed inspections with results

**Template Management**:
- Customizable inspection templates
- JSON-based checklist items
- Multi-category support (Engine, Brakes, Tires, etc.)
- Default templates for common services

**Digital Inspections**:
- Multi-point inspection performance
- Pass/Fail/Attention Required status per item
- Findings and recommendations
- Photo documentation per checkpoint
- Auto-estimate generation from findings
- Technician notes

**Database Tables**: `inspection_templates`, `vehicle_inspections`

**Storage Methods**: 10 total (templates & inspections CRUD)

**API Routes**: 10 authenticated endpoints with Zod validation

**QA Coverage**: 60+ data-testid attributes

**Integration Points**:
- Job Cards: Inspection results attachment
- Estimates: Auto-generate from inspection findings
- Customer Portal: Share inspection results

**Benefits**:
- Standardized inspection process
- Transparent customer communication
- Upsell opportunities from findings
- Digital record keeping

---

### 46. Towing & Roadside Assistance ✓
**Status**: ✓ COMPLETED  
**Implementation**: Complete towing and roadside assistance management

**Features**:
- **Towing Requests Tab**: Service request management
- **Tow Trucks Tab**: Fleet management

**Service Types**:
- Towing (standard, flatbed, heavy-duty)
- Jump start
- Tire change
- Fuel delivery
- Lockout service

**Request Management**:
- GPS coordinates for pickup/dropoff locations
- Status badges (Requested, Assigned, En Route, Arrived, In Progress, Completed, Cancelled)
- Urgency levels (Normal, Urgent, Emergency)
- Customer contact information
- Vehicle details
- Cost tracking

**Truck Fleet Management**:
- Truck inventory with specifications
- Capacity levels (Light, Medium, Heavy)
- Availability status
- Driver assignment
- GPS location tracking
- Service history

**Database Tables**: `towing_requests`, `tow_trucks`

**Storage Methods**: 11 total (requests, trucks, GPS tracking)

**API Routes**: 11 authenticated endpoints with Zod validation

**QA Coverage**: 65+ data-testid attributes

**Integration Points**:
- Customer Portal: Request roadside assistance
- SMS Notifications: Status updates
- Job Cards: Convert to service job if needed

---

### 47. Document Management
**Status**: ⏳ PENDING IMPLEMENTATION  
**Planned Features**:
- Centralized document storage
- Document categorization (Insurance, Registration, Contracts, etc.)
- Expiration tracking with alerts
- Access logging for compliance
- Version control
- Document sharing with customers
- OCR for searchable documents
- Secure storage with encryption

**Planned Database Tables**: `documents`, `document_categories`, `document_access_logs`, `document_versions`

---

### 48. Loaner Vehicle Management ✓
**Status**: ✓ COMPLETED  
**Implementation**: Complete loaner vehicle tracking system

**Features**:
- **Loaner Fleet Tab**: Vehicle inventory management
- **Reservations Tab**: Reservation scheduling and tracking

**Fleet Management**:
- Vehicle condition tracking (Excellent, Good, Fair, Poor)
- Status tracking (Available, Reserved, On Loan, Maintenance, Retired)
- Maintenance scheduling
- Insurance tracking
- Registration management

**Reservation System**:
- Start/end date scheduling
- Customer assignment
- Fuel level tracking (Empty, Quarter, Half, Three Quarters, Full)
- Mileage tracking (start/end odometer)
- Damage documentation with charges
- Deposit management (Paid, Refunded)
- Status tracking (Reserved, Active, Returned, Late, Cancelled)

**Database Tables**: `loaner_vehicles`, `loaner_reservations`

**Storage Methods**: 10 total (vehicles & reservations CRUD)

**API Routes**: 10 authenticated endpoints with Zod validation

**QA Coverage**: 70+ data-testid attributes

**Business Features**:
- Automated late return detection
- Damage charge calculation
- Fuel charge calculation
- Utilization tracking
- Revenue reporting

**Integration Points**:
- Job Cards: Automatic loaner assignment for long repairs
- Customer Portal: View loaner vehicle details
- Invoicing: Add loaner fees to job card invoice

---

## Technology Stack

### Frontend Technologies
- **React**: 18.x (UI library)
- **TypeScript**: 5.x (Type safety)
- **Vite**: 5.x (Build tool)
- **wouter**: 3.x (Routing)
- **TanStack Query**: 5.x (Server state management)
- **shadcn/ui**: Latest (UI components)
- **Radix UI**: Latest (Accessible primitives)
- **Tailwind CSS**: 3.x (Styling)
- **react-hook-form**: 7.x (Form management)
- **Zod**: 3.x (Schema validation)
- **recharts**: 2.x (Data visualization)
- **lucide-react**: Latest (Icons)
- **date-fns**: 3.x (Date utilities)
- **react-big-calendar**: 1.x (Calendar component)
- **framer-motion**: 11.x (Animations)
- **i18next**: 23.x (Internationalization)

### Backend Technologies
- **Node.js**: 20.x
- **Express**: 4.x (Web framework)
- **TypeScript**: 5.x
- **PostgreSQL**: Latest (Database)
- **Drizzle ORM**: 0.36.x (Database ORM)
- **drizzle-zod**: Latest (Zod integration)
- **express-session**: 1.x (Session management)
- **connect-pg-simple**: 9.x (Session store)
- **bcrypt**: 5.x (Password hashing)
- **ws**: 8.x (WebSocket server)

### External Services & APIs
- **Stripe**: Payment processing
- **PayPal**: Payment processing
- **Twilio**: SMS notifications
- **OpenAI**: AI features (GPT-5 model)
- **Google Calendar**: Integration via Replit connector
- **Gmail**: Integration via Replit connector
- **NHTSA API**: VIN decoding
- **TecDoc API**: Parts catalog

### Development Tools
- **ESBuild**: Bundling
- **tsx**: TypeScript execution
- **drizzle-kit**: Database migrations
- **Vite plugins**: Cartographer, Error modal

### Security Libraries
- **speakeasy**: Two-factor authentication
- **qrcode**: QR code generation
- **@zxing/library**: Barcode/QR scanning

---

## Database Architecture

### Database Overview
- **Database**: PostgreSQL (Neon-backed on Replit)
- **ORM**: Drizzle ORM with type-safe queries
- **Tables**: 70+ tables with full relational integrity
- **Migrations**: Managed with drizzle-kit (npm run db:push)
- **Schema File**: `shared/schema.ts` (shared between client/server)

### Key Database Patterns
- **UUIDs**: Primary keys for all tables
- **Timestamps**: createdAt, updatedAt on most tables
- **Soft Deletes**: deletedAt for archival
- **Foreign Keys**: Strict referential integrity
- **Indexes**: Strategic indexing on frequently queried columns
- **JSON Columns**: Flexible data where appropriate (preferences, metadata)

### Core Table Categories

**User Management**: `users`, `roles`, `permissions`, `user_sessions`, `user_settings`

**Customer Management**: `customers`, `customer_vehicles`, `customer_communications`, `customer_portal_sessions`

**Vehicle Management**: `vehicles`, `vehicle_service_history`, `vehicle_maintenance_schedules`

**Operations**: `job_cards`, `job_card_items`, `appointments`, `technicians`

**Inventory**: `spare_parts`, `stock_locations`, `stock_movements`, `tools`

**Financial**: `invoices`, `invoice_items`, `payments`, `estimates`, `purchase_orders`

**Advanced Features**: `fleet_groups`, `warranties`, `inspection_templates`, `towing_requests`, `loaner_vehicles`, `digital_signatures`, `qr_codes`

**System**: `audit_logs`, `notifications`, `action_history`, `chat_messages`

### Sample Schema (Job Cards)
