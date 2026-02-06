# SALIS AUTO ERP - Technical Guidelines Documentation

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technology Stack](#technology-stack)
3. [Project Structure](#project-structure)
4. [Module Reference](#module-reference)
5. [Database Architecture](#database-architecture)
6. [Authentication & Authorization](#authentication--authorization)
7. [RBAC System](#rbac-system)
8. [API Reference](#api-reference)
9. [Frontend Development](#frontend-development)
10. [Component Library](#component-library)
11. [Styling & Theming](#styling--theming)
12. [Internationalization (i18n)](#internationalization-i18n)
13. [Real-Time Features](#real-time-features)
14. [Saudi Arabia Compliance](#saudi-arabia-compliance)
15. [AI & Automation](#ai--automation)
16. [Mobile Applications](#mobile-applications)
17. [Data Seeding](#data-seeding)
18. [Testing Guidelines](#testing-guidelines)
19. [Error Handling](#error-handling)
20. [Performance Best Practices](#performance-best-practices)
21. [Security Guidelines](#security-guidelines)
22. [Deployment](#deployment)
23. [Troubleshooting](#troubleshooting)
24. [Related Documentation](#related-documentation)

---

## Project Overview

SALIS AUTO is a world-class automotive ERP platform designed for efficient garage operations at scale. The platform features:

- **141+ Comprehensive Modules** across 13 phases
- **290+ Database Tables** for complete data management
- **24 Professional Roles** with granular RBAC permissions
- **70 Staff Users** across all departments
- **174 UI Pages** with consistent design system
- **7 Language Support** including RTL for Arabic

### Key Features
- Franchise management & multi-tenant architecture
- OBD diagnostics integration
- OEM software licensing
- Global multi-currency/multi-language support
- B2B spare parts supply network
- AI-powered predictive diagnostics
- Blockchain service history
- Smart contracts & digital signatures

---

## Technology Stack

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| React | 18.3.1 | UI Framework |
| TypeScript | 5.6.3 | Type Safety |
| Vite | 5.4.15 | Build Tool & Dev Server |
| Wouter | 3.3.5 | Client-side Routing |
| TanStack Query | 5.60.5 | Server State Management |
| Tailwind CSS | 3.4.17 | Utility-first Styling |
| shadcn/ui (Radix UI) | Various | Component Library |
| Framer Motion | 11.13.1 | Animations |
| i18next | 25.6.0 | Internationalization |
| @dnd-kit | 6.3.1 | Drag and Drop |
| Recharts | 2.15.2 | Data Visualization |
| react-big-calendar | 1.19.4 | Calendar Views |

### Backend
| Technology | Version | Purpose |
|------------|---------|---------|
| Express.js | 4.21.2 | HTTP Server |
| TypeScript | Latest | Type Safety |
| Drizzle ORM | 0.39.1 | Database ORM |
| Zod | 3.24.2 | Schema Validation |
| Passport.js | 0.7.0 | Authentication |
| WebSocket (ws) | 8.18.0 | Real-time Communication |
| express-session | 1.18.1 | Session Management |
| connect-pg-simple | 10.0.0 | PostgreSQL Session Store |

### Database
| Technology | Purpose |
|------------|---------|
| PostgreSQL | Primary Database |
| Neon (@neondatabase/serverless) | Serverless PostgreSQL Provider |
| Drizzle Kit | Schema Push & Migrations |

### External Services
| Service | Package | Purpose |
|---------|---------|---------|
| OpenAI | openai 6.3.0 | AI Chatbot & Diagnostics |
| Twilio | twilio 5.10.3 | SMS Notifications |
| Stripe | stripe 19.1.0 | Payment Processing |
| PayPal | @paypal/paypal-server-sdk 1.1.0 | Alternative Payments |
| Google APIs | googleapis 163.0.0 | Calendar & Gmail |

---

## Project Structure
