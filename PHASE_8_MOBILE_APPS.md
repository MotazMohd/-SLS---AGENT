# Phase 8: Mobile Apps
## SALIS AUTO Mobile Applications Suite

**Status:** 📱 Documentation Complete | Implementation: React Native (Future)  
**Target Platforms:** iOS & Android via React Native  
**Completion:** 3/3 apps documented

---

## Overview

The SALIS AUTO mobile apps provide on-the-go access for three key user groups: **Technicians**, **Customers**, and **Managers**. All apps are designed as cross-platform React Native applications with real-time sync, offline support, and push notifications.

---

## 🔧 App 1: Technician Mobile App

**Purpose:** Empower technicians to manage job cards, capture media, scan parts, and track time from their mobile devices.

### Core Features

1. **Job Card Management**
   - View assigned job cards
   - Update job status (In Progress, Completed, etc.)
   - Add labor time entries
   - Record parts used

2. **Photo & Video Capture**
   - Multi-angle vehicle photos
   - Video documentation of repairs
   - Damage annotation with markup tools
   - Automatic upload to job card

3. **Barcode/QR Scanner**
   - Scan parts for inventory lookup
   - Quick part addition to job cards
   - Tool check-in/check-out
   - Vehicle VIN scanning

4. **Time Tracking**
   - Clock in/out functionality
   - Job-specific time tracking
   - Break management
   - Daily time summary

5. **Offline Mode**
   - Work without internet connection
   - Local data storage
   - Auto-sync when online

### Technical Stack
- **Framework:** React Native (Expo)
- **State:** React Query + AsyncStorage
- **Camera:** react-native-camera
- **Scanner:** react-native-vision-camera + MLKit
- **Auth:** JWT with biometric fallback

### API Integration
