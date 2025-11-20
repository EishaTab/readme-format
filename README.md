# Prestigeride Accounts Portal

The Prestigeride Accounts Portal is a modern web application that provides customers with secure access to their account details, ride history, invoices, payment methods, reservations, and personalized service settings. The application is built using the Next.js App Router framework with a hybrid UI approach combining Tailwind CSS, Material UI (MUI), and Ant Design (AntD). The entire project is developed in JavaScript.

---

## Table of Contents

1. [Features](#features)
2. [Ride Types](#ride-types)
3. [Technologies Used](#technologies-used)
4. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
   - [Running Locally](#running-locally)
5. [Environment Variables](#environment-variables)
6. [Folder Structure](#folder-structure)
7. [Deployment](#deployment)
8. [Contributing](#contributing)
9. [Dependencies](#dependencies)
10. [Known Issues and Workarounds](#known-issues-and-workarounds)
11. [License](#license)

---

## Features

- User Account Dashboard for centralized access to personal and booking information.
- Ride History Management with options to view, edit, or duplicate reservations.
- Payment Method Management for storing and updating card details.
- Hybrid UI Styling using Tailwind CSS, Material UI, and Ant Design.
- Responsive layout optimized for desktops, tablets, and mobile devices.
- Real-time UI experience using the Next.js App Router.
- Entire application built using JavaScript.

---

## Ride Types

### 1. Copy Ride
Duplicates an existing reservation with the same pickup/drop-off, vehicle, date/time, and passenger details. Useful for frequent or recurring bookings.

### 2. Return Ride
Creates a return trip by automatically swapping pickup and drop-off locations. Users may adjust the date and time.

### 3. Hourly Ride
Designed for customers who require vehicle and chauffeur service for a specific number of hours. Includes wait-time flexibility and additional hourly billing.

### 4. Point-to-Point (P2P) Ride
A standard one-way ride including pickup to drop-off routing, estimated travel time, distance calculation, and real-time fare details.

---

## Technologies Used

| Category | Tools / Libraries |
|----------|--------------------|
| Framework | Next.js (App Router) |
| Language | JavaScript |
| UI & Styling | Tailwind CSS, Material UI (MUI), Ant Design (AntD) |
| Cache / State | Redis |

---

## Getting Started

Follow the steps below to set up and run the application.

---

## Prerequisites

Ensure the following are installed on your machine:

- Node.js (v18 or later)
- pnpm (recommended) or npm/yarn
- Git
- Redis server (local or remote)

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/optlinkhub-IT/Accounts-Portal.git
cd Accounts-Portal
````

### 2. Install dependencies

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

[http://localhost:3000](http://localhost:3000)

---

## Environment Variables

Create a `.env.local` file in the project root. Example variables:

```env
NEXT_PUBLIC_API_BASE_URL=
REDIS_URL=redis://localhost:6379
JWT_SECRET=
NEXTAUTH_SECRET=
STRIPE_PUBLIC_KEY=
STRIPE_SECRET_KEY=
```

---

## Folder Structure

```
Accounts-Portal/
│── app/                    # Next.js App Router pages
│── components/             # Shared UI components
│── lib/                    # Redis, API clients, utilities
│── hooks/                  # Custom React hooks
│── context/                # Context providers and global states
│── public/                 # Static assets
│── styles/                 # Global styling
│── package.json
│── README.md
```

---

## Deployment

### Deploy on Vercel (recommended)

1. Push your code to GitHub.
2. Import the repository into Vercel.
3. Add environment variables in Vercel dashboard.
4. Deploy.

### Deploy using Node server

```bash
npm run build
npm start
```
---

## Contributing

Contributions are welcome. Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Commit your changes.
4. Submit a pull request.

---

## Dependencies

Main dependencies include:

* Next.js
* React
* Tailwind CSS
* Material UI
* Ant Design
* Redis
* Axios

List all installed dependencies:

```bash
npm list --depth=0
```

---

## Known Issues and Workarounds

| Issue                                             | Cause                            | Workaround                                                       |
| ------------------------------------------------- | -------------------------------- | ---------------------------------------------------------------- |
| Redis connection failure                          | Redis not running or invalid URL | Ensure Redis is running and `REDIS_URL` is correct               |
| Styling conflicts between MUI, AntD, and Tailwind | CSS priority collisions          | Use Tailwind for layout and override component styles carefully  |
| Build errors during deployment                    | Missing env variables            | Add required environment variables in the deployment environment |
| Slow initial load time                            | Large UI libraries               | Use dynamic imports for heavy components                         |

---

## License

This project is licensed under the MIT License.
