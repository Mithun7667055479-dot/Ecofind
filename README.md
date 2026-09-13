# EcoFinds | Sustainable E-Commerce & Discovery Platform

EcoFinds is an AI-powered sustainability discovery and shopping platform that enables users to evaluate eco-friendly products, discover greener alternatives, track carbon footprints, and support verified sustainable sellers.

---

## 🚀 Quick Start Guide (Single Command)

You can launch the entire application (both Frontend and Backend API) with a single command:

```bash
# 1. Install dependencies
npm install

# 2. Start both Frontend & Backend API concurrently
npm run dev
```

- **Frontend Application**: [http://localhost:3000](http://localhost:3000)
- **Backend Express API**: [http://localhost:4000/api](http://localhost:4000/api)

---

## 🛠️ Step-by-Step Localhost Setup & Installation

### 1. Install Dependencies
Run the root installation command to set up all monorepo workspaces (`apps/web`, `apps/api`, `packages/ui`):
```bash
npm install
```

### 2. Configure Environment Variables
Environment configuration templates are provided in each workspace:

#### Frontend (`apps/web/.env.local`):
```env
NEXT_PUBLIC_API_URL=http://localhost:4000/api
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_placeholder
CLERK_SECRET_KEY=sk_test_placeholder
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/
NEXT_PUBLIC_RAZORPAY_KEY_ID=rzp_test_placeholder
NEXT_PUBLIC_GA_ID=G-placeholder
```

#### Backend API (`apps/api/.env`):
```env
PORT=4000
DATABASE_URL="file:./dev.db"
OPENAI_API_KEY=mock-key
FIREBASE_PROJECT_ID=mock-id
FIREBASE_CLIENT_EMAIL=mock-email
FIREBASE_PRIVATE_KEY="mock-key"
CLAUDE_SECRET_KEY=sk_test_placeholder
RAZORPAY_KEY_ID=rzp_test_placeholder
RAZORPAY_KEY_SECRET=rzp_test_secret_placeholder
```

---

### 3. Initialize & Seed Database
The project utilizes SQLite via Prisma for seamless zero-configuration localhost development:

```bash
cd apps/api

# Sync Prisma Schema with Local SQLite Database (dev.db)
npx prisma db push

# Seed Sample Products, Categories, and Admin Accounts
npx tsx src/seed.ts
```

---

### 4. Run Servers Individually (Optional)

If you prefer running services in separate terminal windows:

#### Start Backend API (`http://localhost:4000`):
```bash
# From workspace root:
npm run dev:api
```

#### Start Frontend (`http://localhost:3000`):
```bash
# From workspace root:
npm run dev:web
```

---

## 📁 Repository Structure

```
EcoFinds/
├── apps/
│   ├── web/           # Next.js 15 + React 19 Frontend App
│   ├── api/           # Express.js + Prisma API Server
│   └── mobile/        # Mobile Application Scaffold
├── packages/
│   └── ui/            # Shared React UI Component Library
├── README.md          # Localhost Hosting & Setup Documentation
└── package.json       # Monorepo Workspace Configuration
```

---

## 🧪 Production Build & Type Checking

To verify production readiness:

```bash
# Build both frontend and backend
npm run build
```
