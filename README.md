# Web3 Platform

A production-ready full-stack decentralized application showcasing modern blockchain integration, real-time features, and enterprise-grade architecture patterns.

## Overview

This project demonstrates a comprehensive Web3 platform combining prediction markets, staking mechanisms, and exchange functionality. The platform features seamless external integrations, real-time updates, and a robust RESTful API architecture designed for scalability and maintainability.

## ⚠️ Implementation Status

**Current State**: Design prototype with production-grade UI

**What Works**:
- ✅ Complete visual design and components
- ✅ Dashboard, portfolio, charts, transactions (UI only)

**What Doesn't Work**:
- ❌ Authentication (endpoint mismatch: Frontend `/auth` ≠ Backend `/api/v1/auth`)
- ❌ Backend integrations (Market data, portfolio calculations, transactions)
- ❌ Web3 wallets (MetaMask, Phantom, Coinbase, WalletConnect)
- ❌ Google OAuth (not implemented)

**Data**: All displayed data is static/mock - not connected to backend services.

**Testing**: No automated tests. No CI/CD pipeline.

This README describes the planned architecture, not the current implementation.
See [DEVELOPMENT-STATUS.md](./DEVELOPMENT-STATUS.md) for a detailed rundown of current capabilities and priorities.

### Claim vs Reality

| Claim (Planned Architecture) | Reality (Jan 2026) |
| --- | --- |
| “Production-ready full-stack decentralised application.” | Production-grade **UI prototype** with mock/in-memory backend and no live integrations. |
| Fully functional prediction markets, staking automation, referrals, notifications, support, and admin controls. | Corresponding routes/controllers exist, but all business logic relies on mocked data and is not wired to real services. |
| Integrated Web3 wallets (MetaMask, Phantom, Coinbase, WalletConnect) and Google OAuth. | Wallet and OAuth flows are UI-only (no provider detection), signing, or OAuth callbacks are implemented. |
| Tested & deployable system. | **No** automated tests, CI/CD, or deployment scripts—manual validation only. |

## Key Features

- **Prediction Markets**: Bull/Bear prediction system with live price feeds and automated round management
- **Staking Platform**: Multiple staking plans with automated earnings calculation and distribution
- **External Integrations**: Multi-chain support with secure third-party connections and transaction handling
- **Exchange Dashboard**: Real-time market tracking, portfolio management, and analytics
- **Referral System**: Complete referral tracking, rewards calculation, and user hierarchy management
- **Transaction History**: Comprehensive transaction logging with filtering and export capabilities
- **Admin Dashboard**: Full administrative controls for user management, withdrawals, and system monitoring
- **Support System**: Ticket-based customer support with message threading
- **Real-time Notifications**: Live updates and event broadcasting
- **Authentication & Security**: Secure user authentication with session management

## Architecture Highlights

- **Modular Design**: Clean separation of concerns with layered architecture (controllers, services, models)
- **Middleware Pattern**: Authentication, validation, and error handling middleware
- **RESTful API**: Well-structured API routes with versioning and comprehensive error responses
- **Real-time Communication**: Bidirectional communication for live updates
- **Blockchain Integration**: Secure external connections and transaction processing
- **State Management**: Global state management patterns for complex application flows
- **Type Safety**: Strong typing throughout the codebase
- **Error Handling**: Comprehensive error handling and logging strategies

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v16 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js) or **yarn**
- **Git** - [Download](https://git-scm.com/)

### Installation

#### 1. Install Frontend Dependencies

```bash
npm install
```

#### 2. Install Backend Dependencies

```bash
cd backend
npm install
cd ..
```

**Or use the convenience script:**

```bash
npm run start-all
```

This will install dependencies for both frontend and backend, then start both servers.

## Running the Project

### Option 1: Run Both Servers Together (Recommended)

From the root directory:

```bash
npm start
```

This will:
- Start the backend server on `http://localhost:1357` (with mock data)
- Start the frontend development server on `http://localhost:2468`

**Note**: The backend uses in-memory mock data. All data will reset when you restart the server.

### Option 2: Run Servers Separately

**Terminal 1 - Backend:**
```bash
cd backend
npm start
```

**Terminal 2 - Frontend:**
```bash
npm run client
```

### Access the Application

Once both servers are running:
- **Frontend**: Open [http://localhost:2468](http://localhost:2468) in your browser
- **Backend API**: Available at [http://localhost:1357/api](http://localhost:1357/api)
- **Health Check**: [http://localhost:1357](http://localhost:1357)

## Testing

**Status**: No testing infrastructure.

To validate changes: `npm start` → Manual testing at [http://localhost:2468](http://localhost:2468)

### Recommended Early-Cycle Testing Strategy

1. **Sprint Planning**  
   - Define acceptance criteria + user journeys before implementation.  
   - Pair designers/devs to produce testable UI states (Figma references, fixtures).
2. **Component & Hook Tests**  
   - Use React Testing Library for visual components and hooks, focused on wallet/auth flows, staking widgets, and dashboard cards.  
   - Snapshot critical layout states to detect regression in mock-driven UI.
3. **Contract Tests for Mock APIs**  
   - Write Jest contract tests against the in-memory services to lock request/response schemas before wiring real data.  
   - Generate shared TypeScript types from these contracts to keep frontend/back-end aligned.
4. **Integration Smoke Tests**  
   - Spin up both servers via `npm start` and run Playwright smoke flows (login, dashboard load, staking plan view).  
   - Fail the pipeline if any page relies on missing backend endpoints.
5. **Static + Lint Gates (Daily)**  
   - Enforce TypeScript strict mode, ESLint, and Prettier in pre-commit hooks.  
   - Add `npm run lint && npm test` to CI.
6. **Exploratory Regression (Weekly)**  
   - QA/dev buddy system runs scripted scenarios focusing on admin dashboards, referrals, and wallet prompts.  
   - Capture findings in DEVELOPMENT-STATUS to keep documentation truthful.

**Known Issues**: Auth broken, Web3 integrations incomplete, no backend connections.

## What Makes This Special

This codebase showcases production-ready patterns including:
- Secure authentication flows with token-based sessions
- Real-time bidirectional communication
- Blockchain transaction handling and external integrations
- Responsive design with modern UI/UX principles
- Comprehensive error handling and validation
- Scalable architecture patterns suitable for enterprise deployment
- Clean code organization and maintainable structure

Perfect for evaluating technical depth, code quality, architectural decision-making, and understanding of modern software development practices.

---

*Built with modern best practices and designed for scalability.*
