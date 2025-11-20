
# Prestigeride Accounts Portal

The **Prestigeride Accounts Portal** is a modern, secure, and user-friendly web application that allows customers to manage their reservations, ride history, invoices, payments, and personal settings. Built using **Next.js App Router**, the portal leverages a hybrid UI system combining **Tailwind CSS**, **Material UI (MUI)**, **Ant Design (AntD)**, and **TanStack Query** for frontend caching — all written entirely in **JavaScript**.

---

## Table of Contents

1. [Features](#features)  
2. [Ride Types](#ride-types)  
3. [Technologies Used](#technologies-used)  
4. [Getting Access & Working With the Repository](#getting-access--working-with-the-repository)  
   - [Requesting Access](#requesting-access)  
   - [Cloning the Repository](#cloning-the-repository)  
   - [Branch Workflow](#branch-workflow)  
5. [Getting Started](#getting-started)  
   - [Prerequisites](#prerequisites)  
   - [Installation](#installation)  
   - [Running Locally](#running-locally)  
6. [Environment Variables](#environment-variables)  
7. [Folder Structure](#folder-structure)  
8. [Deployment](#deployment)  
9. [Dependencies](#dependencies)  
10. [Known Issues and Workarounds](#known-issues-and-workarounds)  
11. [License](#license)

---

## Features

- User Account Dashboard with personal information and activity overview
- Ride history with options to view, edit, duplicate, rebook, or create return rides
- Payment method management including storing, updating, and reusing saved cards
- Passenger management with the ability to save, edit, and reuse passenger profiles
- Airport ride support with inside pickup, curbside pickup, and flight tracking
- Hybrid UI using Tailwind CSS, Material UI (MUI), and Ant Design
- Client-side data fetching, caching, and auto-refetching with TanStack Query (React Query)
- Responsive design optimized for all screen sizes
- Powered by Next.js App Router for an efficient, modern UI/UX
- Fully JavaScript-based architecture

---

## Ride Types

### 1. Copy Ride
Duplicates an existing ride with all original details for quick rebooking.

### 2. Return Ride
Creates a reverse trip by swapping pickup and drop-off locations automatically.

### 3. Hourly Ride
Provides a chauffeur-driven vehicle for a set number of hours with flexible routing.

### 4. Point-to-Point (P2P) Ride
Standard one-way ride from pickup to drop-off with full route and fare calculation.

### 5. Ride Rebook
Allows customers to instantly rebook a past ride with updated date and time.
---

## Technologies Used

| Category      | Tools / Libraries                               |
|---------------|--------------------------------------------------|
| Framework     | Next.js (App Router)                            |
| Language      | JavaScript                                      |
| UI & Styling  | Tailwind CSS, Material UI (MUI), Ant Design     |
| Cache / State | Redis, TanStack Query (React Query)             |
| Networking    | Axios                                           |

---

# Getting Access & Working With the Repository

This project is private. Follow the workflow below to gain access and contribute to development.

---

## Requesting Access

To access the repository:

1. Contact the **Prestigeride Engineering/Admin team**.  
2. Provide your GitHub username and verified email.  
3. Once approved, you will receive repository access.

---

## Cloning the Repository

After access is granted:

```bash
git clone https://github.com/optlinkhub-IT/Accounts-Portal.git
cd Accounts-Portal


---

## Branch Workflow

The project follows a structured branching model:

| Branch Type | Purpose                        |
| ----------- | ------------------------------ |
| `main`      | Production-ready code          |
| `dev`       | Active development integration |
| `feature/*` | Feature-specific development   |
| `bugfix/*`  | Hotfixes and minor issues      |
| `release/*` | Pre-release staging            |

### Creating a Feature Branch

```bash
git checkout dev
git pull
git checkout -b feature/<feature-name>
```

### Submitting Changes

1. Commit changes with clear messages.
2. Push the branch.
3. Create a Pull Request (PR) into `dev`.
4. Request a review from the engineering team.

---

# Getting Started

## Prerequisites

Install the following before running the app:

* Node.js (v18 or later)
* pnpm (recommended) or npm/yarn
* Git
* Redis (local or remote instance)

---

## Installation

Install dependencies using your preferred package manager:

```bash
npm install
# or
yarn install
# or
pnpm install
```

---

## Running Locally

Start the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

The application will be available at:

> [http://localhost:3000](http://localhost:3000)

---

## Environment Variables

Environment configuration must be stored in:

```txt
.env.local
```

A complete example file is included in the repository:

```txt
.env.example
```

Create your local configuration file from the example:

```bash
cp .env.example .env.local
```

> **Note:**
>
> * Do **not** store real secrets in `.env.example`.
> * Use `.env.development` / `.env.production` as needed for environment-specific overrides, following your deployment setup.

---

## Folder Structure

```txt
Accounts-Portal/
│── node_modules/
│── public/
│── src/
│   ├── api/                     # Backend/API helpers & route logic
│   ├── app/                     # Next.js App Router entry & routes
│   │   ├── account/             # Account-related pages
│   │   ├── affiliate-summary/   # Affiliate summary views
│   │   ├── components/          # Route-level components
│   │   ├── passenger-reservation/   # Reservation flow pages
│   │   ├── ride-summary/        # Ride summary views
│   │   ├── standard-confirmation/   # Confirmation screens
│   │   ├── style/               # App-level style modules
│   │   ├── testing/             # Route-level testing utilities/pages
│   │   ├── _document.js         # Custom Document (if used with app router)
│   │   ├── globals.css          # Global styles
│   │   ├── layout.js            # Root layout
│   │   ├── not-found.js         # 404 handler
│   │   └── page.js              # Root page
│   ├── data/                    # Static data, mocks, or config
│   ├── store/                   # Global state management
│   ├── utils/                   # Shared utilities/helpers
│   └── middleware.js            # Middleware (auth, routing, etc.)
│── .env.example                 # Example env configuration
│── .env.development             # Dev environment configuration
│── .env.production              # Production environment configuration
│── package.json
│── README.md
│── .eslintrc.json
│── .prettierrc
│── .gitignore
```

---

## Deployment

### Deploy on Vercel (Recommended)

1. Push your code to GitHub.
2. Import the repository into Vercel.
3. Add environment variables in the Vercel dashboard.
4. Trigger deployment.

### Deploy Using Node Server

```bash
npm run build
npm start
```

---

## Dependencies

Primary dependencies include:

* Next.js
* React
* Tailwind CSS
* Material UI
* Ant Design
* TanStack Query (React Query)
* Redis
* Axios

To list all installed dependencies:

```bash
npm list --depth=0
```

---

## Known Issues and Workarounds

| Issue                                             | Cause                            | Workaround                                                       |
| ------------------------------------------------- | -------------------------------- | ---------------------------------------------------------------- |
| Redis connection failure                          | Redis server offline or bad URL  | Verify Redis is running and `REDIS_URL` is correct               |
| Styling conflicts between Tailwind, MUI, and AntD | CSS specificity/priority clashes | Use Tailwind for layout; override library styles in a scoped way |
| Deployment build failures                         | Missing environment variables    | Ensure `.env.local` and deployment env vars are complete         |
| Slow initial load                                 | Large UI and data libraries      | Use dynamic imports & TanStack caching to reduce re-fetching     |

---

## License

This project is licensed under the **MIT License**.

