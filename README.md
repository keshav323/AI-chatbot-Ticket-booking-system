# AI Chatbot Ticket Booking System 🏛️🤖

[![Live Frontend](https://img.shields.io/badge/Frontend-Vercel-black?logo=vercel)](https://client-silk-psi-23.vercel.app)
[![Live Backend](https://img.shields.io/badge/Backend-Render-46E3B7?logo=render&logoColor=white)](https://museum-booking-api.onrender.com)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

A state-of-the-art, AI-powered museum ticket booking system featuring a conversational intelligent assistant, interactive 3D visualizations, and integrated Razorpay payment processing. The application enables users to book tickets seamlessly using natural language, dynamically query slot availability, complete secure payments, and manage reservations via a comprehensive admin dashboard.

---

## 🌐 Live URLs & Demo

| Service | Platform | Live URL | Status |
| :--- | :--- | :--- | :--- |
| **Frontend Application** | **Vercel** | [https://client-silk-psi-23.vercel.app](https://client-silk-psi-23.vercel.app) | 🟢 Active |
| **Backend API** | **Render** | [https://museum-booking-api.onrender.com](https://museum-booking-api.onrender.com) | 🟢 Active |
| **API Base URL** | **Render** | [https://museum-booking-api.onrender.com/api](https://museum-booking-api.onrender.com/api) | 🟢 Active |

---

## 🏗️ Tech Stack

- **Frontend**: React (Vite), Framer Motion, Three.js, TailwindCSS, Lucide Icons
- **Backend**: Node.js, Express.js, SQLite3
- **AI Engine**: Google Gemini (`gemini-3-flash-preview` / `gemini-1.5-flash`)
- **Payments**: Razorpay Gateway (Test & Live modes)
- **Deployment**: Render (Backend Web Service) + Vercel (Frontend Static SPA)

---

## 📁 Project Structure

```
.
├── client/                 # React frontend (Vite SPA)
│   ├── src/
│   │   ├── components/     # UI Components, 3D Hero, Admin Dashboard
│   │   ├── context/        # Booking & Chat Context Providers
│   │   └── services/       # API and payment integration client
│   ├── package.json
│   └── vite.config.js
├── server/                 # Express.js backend API
│   ├── database.js         # SQLite database schema and initial seed data
│   ├── ai.js               # Gemini AI assistant integration & prompt engine
│   ├── routes.js           # REST API endpoints (chat, booking, slots, payments)
│   ├── server.js           # Server entry point and CORS configuration
│   └── package.json
├── render.yaml             # Render Infrastructure-as-Code Blueprint
└── README.md
```

---

## 🚀 Local Getting Started

### Prerequisites
- Node.js 18+ & npm
- Google Gemini API Key ([Google AI Studio](https://aistudio.google.com/))
- Razorpay Account Key ID & Secret ([Razorpay Dashboard](https://dashboard.razorpay.com/))

### 1. Backend Setup

```bash
cd server
npm install
```

Create a `.env` file in `server/`:
```env
PORT=3001
GEMINI_API_KEY=your_gemini_api_key_here
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_secret
FRONTEND_URL=http://localhost:5173
```

Start the backend server:
```bash
npm run dev
# or: node server.js
```
The backend will run on `http://localhost:3001`.

### 2. Frontend Setup

```bash
cd ../client
npm install
npm run dev
```

The frontend app will be available at `http://localhost:5173`.

---

## 🌐 Deployment Guide

### 🚀 Backend Deployment (Render - Free Tier)

Since this repository is a monorepo, follow these steps to deploy the backend (`/server`) service on Render:

#### Option A: One-Click Blueprint (Recommended)
1. Push your repository to GitHub.
2. Log into [Render Dashboard](https://dashboard.render.com/).
3. Click **New +** -> **Blueprint**.
4. Select this repository: `AI-chatbot-Ticket-booking-system`. Render will automatically read [`render.yaml`](file:///c:/Users/Admin/.gemini/antigravity/scratch/render.yaml) and configure the web service.
5. Fill in the secret environment variables (`GEMINI_API_KEY`, `RAZORPAY_KEY_ID`, `RAZORPAY_KEY_SECRET`, `FRONTEND_URL`).
6. Click **Apply**.

#### Option B: Manual Web Service Setup
1. Go to [dashboard.render.com](https://dashboard.render.com/) and click **New +** -> **Web Service**.
2. Select repository: `keshav323/AI-chatbot-Ticket-booking-system`.
3. Configure the following settings:
   - **Name**: `museum-booking-api`
   - **Root Directory**: `server`
   - **Environment**: `Node`
   - **Build Command**: `npm install`
   - **Start Command**: `node server.js`
   - **Instance Type**: `Free`
4. Add the **Environment Variables** in Render:
   | Key | Value / Description |
   | :--- | :--- |
   | `GEMINI_API_KEY` | Your Google Gemini API Key |
   | `RAZORPAY_KEY_ID` | Your Razorpay Key ID |
   | `RAZORPAY_KEY_SECRET` | Your Razorpay Key Secret |
   | `FRONTEND_URL` | `https://client-silk-psi-23.vercel.app` (enables CORS) |
   | `NODE_ENV` | `production` |
5. Click **Create Web Service**.

---

### 🎨 Frontend Deployment (Vercel)

1. Go to [Vercel Dashboard](https://vercel.com/) and import `keshav323/AI-chatbot-Ticket-booking-system`.
2. In the Project Settings:
   - **Framework Preset**: `Vite`
   - **Root Directory**: `client`
3. Add Environment Variable:
   - `VITE_API_URL`: `https://museum-booking-api.onrender.com/api`
4. Click **Deploy**.

---

## ✨ Features

- 🤖 **AI Booking Assistant**: Conversational ticket booking powered by Google Gemini AI with intelligent fallbacks.
- 🔄 **Real-time Dynamic Context**: AI dynamically fetches live ticket pricing, limits, and time slot availability directly from the database.
- 💳 **Razorpay Integration**: Secure checkout process with HMAC SHA256 signature verification.
- 📊 **Admin Dashboard**: Real-time management interface to monitor bookings, adjust ticket prices, and configure capacity limits.
- 🎨 **Modern Aesthetics & 3D Visualizer**: Glassmorphism UI, Framer Motion transitions, and interactive Three.js 3D prism.

---

## 👨‍💻 Author & Repository

- **Author**: [keshav323](https://github.com/keshav323)
- **Repository**: [https://github.com/keshav323/AI-chatbot-Ticket-booking-system](https://github.com/keshav323/AI-chatbot-Ticket-booking-system)

