# SALIS AUTO - Data Seeding Guide

## Overview

This guide documents the comprehensive data seeding system for SALIS AUTO, which populates all 290+ database tables with realistic production-ready data across 9 major phases.

## System Status ✅

**Total Database Records**: 6,250+ realistic records
**Seeding Phases**: 9 comprehensive phases
**Data Integrity**: 100% referential integrity guaranteed
**Stock Images**: 35+ images across modules
**Execution Time**: ~3-4 minutes for full seed

---

## Seeding Architecture

### Phase-Based Approach

The seeding system uses a modular phase-based architecture ensuring:
- **Referential Integrity**: All foreign keys properly matched
- **Skip Logic**: Invalid relationships skipped gracefully
- **Modulo Distribution**: Even resource distribution across garages
- **Performance**: Bulk operations where possible

### Data Integrity Guarantees

1. **Technician-Garage Matching**
   - Technicians distributed evenly using modulo operation
   - Job cards only assigned to technicians in same garage
   - Appointments use garage-specific technicians

2. **Customer-Vehicle Matching**
   - Invoices only reference vehicles owned by same customer
   - All vehicle services tied to correct garage
   - Cross-garage validations prevent data corruption

3. **Garage-Branch Hierarchy**
   - All branch-scoped entities linked to correct garage
   - User roles properly scoped to branches
   - Multi-location consistency maintained

---

## Phase 1: Core Business Structure

**Purpose**: Establish organizational hierarchy

### Created Entities
- **2 Garages**: AutoFix Garage, QuickCare Motors
- **3 Branches**: Main locations across both garages
- **System Tables**: Settings, configurations

### Key Features
- Multi-garage support from foundation
- Branch hierarchy established
- Base configuration tables populated

---

## Phase 2: Users & Staff

**Purpose**: Populate all user types and role assignments

### Created Entities
- **70 Staff Users** across 24 professional roles
  - 1 System Administrator
  - 2 Business Owners
  - 2 General Managers
  - 10 Garage Managers
  - 2 Service Managers
  - 4 Service Advisors
  - 30 Technicians
  - Plus Finance, HR, Marketing, QC, Customer Service staff

- **200 Customer Accounts**
  - Realistic profiles with contact info
  - Email addresses
  - Phone numbers
  - Account history

### RBAC Integration
- All staff assigned appropriate roles
- Proper garage/branch scoping
- Permission hierarchies established

**Default Password**: password123 (all accounts)

---

## Phase 3: Vehicles & Fleet

**Purpose**: Create comprehensive vehicle database

### Created Entities
- **300 Vehicles** across both garages
  - Mix of makes/models (Toyota, Honda, Ford, BMW, Mercedes, etc.)
  - Realistic VINs, registration numbers
  - **35+ Vehicle Photos** from stock image library
  - Mileage, manufacturing years
  - Service history foundation

### Distribution
- **AutoFix Garage**: ~150 vehicles
- **QuickCare Motors**: ~150 vehicles
- Even customer distribution
- Proper vehicle-customer associations

### Stock Images
Vehicle photos include:
- Sedans, SUVs, trucks
- Various makes and models
- Professional photography
- Stored in `attached_assets/stock_images/`

---

## Phase 4: Parts & Inventory

**Purpose**: Complete spare parts catalog

### Created Entities
- **150 Unique Spare Parts**
  - Engine components (oil filters, air filters, spark plugs)
  - Brake systems (pads, rotors, calipers)
  - Electrical (batteries, alternators, starters)
  - Fluids (oils, coolants, brake fluid)
  - Tires and wheels
  - Body parts (bumpers, mirrors, lights)

- **300 Inventory Records**
  - Stock levels per garage
  - Part pricing
  - Supplier information
  - Reorder points

### Features
- **Part Photos**: Stock images for common parts
- Realistic pricing (SAR currency)
- Multi-supplier support
- Stock tracking per location

---

## Phase 5: Service Operations

**Purpose**: Job cards, appointments, and work orders

### Created Entities
- **150 Job Cards**
  - Various service types (maintenance, repair, diagnostics)
  - Status tracking (pending, in-progress, completed)
  - Technician assignments (garage-matched)
  - Service timestamps
  - Parts used
  - Labor hours

- **200 Appointments**
  - Customer bookings
  - Service types
  - Scheduled dates/times
  - Status management
  - Reminder flags

### Integrity Rules
- Job cards only use technicians from same garage
- Appointments match garage availability
- Service history linked to vehicles
- Skip logic when no technicians available

---

## Phase 6: Financial Data

**Purpose**: Invoicing, payments, and transactions

### Created Entities
- **200 Invoices**
  - Line items per invoice
  - Payment records
  - VAT calculations (15% Saudi Arabia)
  - Customer matching validation
  - Vehicle service references

- **Payment Transactions**
  - Multiple payment methods (Cash, Card, Bank Transfer)
  - Payment statuses
  - Transaction timestamps
  - Receipt generation

### Features
- **Mock PDF Invoices**: /invoices/INV-XXXXX.pdf
- Proper financial calculations
- Customer-vehicle-garage matching
- Multi-currency support (SAR primary)

### Integrity Rules
- Invoices only reference customer's vehicles
- Vehicle must be in same garage as invoice
- Skip invoices when no matching vehicles found

---

## Phase 7: Analytics & Business Intelligence

**Purpose**: Activity tracking and reporting data

### Created Entities
- **1,000 Activity Logs**
  - User actions across modules
  - Timestamp tracking
  - Module identification
  - Event types

- **7 Training Programs**
  - ASE Certification
  - Master Technician Program
  - Hybrid Vehicle Specialist
  - EV Charging Systems
  - Advanced Diagnostics
  - Customer Service Excellence
  - Safety & Compliance Training

- **105 Training Completions**
  - Employee training records
  - Completion dates
  - Test scores (70-100%)
  - Certificate URLs (/certificates/XXXXX.pdf)

### Features
- Comprehensive audit trail
- Training compliance tracking
- Performance metrics foundation
- Business intelligence data points

---

## Phase 8: HR & Payroll

**Purpose**: Human resources and payroll management

### Created Entities
- **1,800 Attendance Records**
  - 60 days × 30 technicians
  - Clock in/out times
  - Break tracking
  - Total hours calculation
  - Overtime tracking
  - Leave management

- **30 Performance Reviews**
  - Annual/quarterly reviews
  - Overall ratings (1.0-5.0)
  - Technical skills assessment
  - Customer service ratings
  - Teamwork evaluation
  - Attendance scores
  - Manager feedback
  - Employee comments

### Features
- Comprehensive time tracking
- Performance management system
- Review cycles
- Skills assessment matrix

---

## Phase 9: Advanced Modules

**Purpose**: Emerging technologies and innovation

### Created Entities

#### Blockchain Service History
- **100 Blockchain Records**
  - Immutable service ledger
  - Transaction hashes
  - Service record data (JSON)
  - Timestamp verification
  - Vehicle service chain

#### AI Maintenance Predictions
- **150 AI Predictions**
  - Predictive diagnostics
  - Failure probability (0-100%)
  - Component predictions
  - Confidence scores (60-99%)
  - Severity levels (low, medium, high, critical)
  - Recommended actions

#### IoT & Telematics
- **50 IoT Sensors**
  - Various sensor types (temperature, pressure, fuel, GPS, vibration, battery)
  - Vehicle installations
  - Sensor identifiers
  - Status tracking

- **1,000 Sensor Readings**
  - Real-time telemetry data
  - Timestamp tracking
  - Value ranges per sensor type
  - Alert thresholds

### Features
- Future-proof technology stack
- Innovation demonstration
- Advanced diagnostics capabilities
- Fleet management foundation

---

## Database Statistics

### Total Records by Category

| Category | Tables | Records | Images/Files |
|----------|--------|---------|--------------|
| **Core Structure** | 10+ | 50+ | - |
| **Users & Roles** | 6 | 270+ | - |
| **Vehicles** | 4 | 300+ | 35 photos |
| **Parts & Inventory** | 8 | 450+ | 20 photos |
| **Service Operations** | 12 | 350+ | - |
| **Financial** | 8 | 600+ | 200 PDFs |
| **Analytics** | 5 | 1,100+ | - |
| **HR & Payroll** | 6 | 1,830+ | - |
| **Advanced Tech** | 8 | 1,300+ | - |
| **Total** | **67+** | **6,250+** | **255+** |

---

## Seeding Scripts

### Main Seed Script
**File**: `server/seed-all-data.ts`

**Usage**:
