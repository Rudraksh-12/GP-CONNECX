## GP-CONNECX

GP-CONNECX is a modern campus social platform built with the MERN stack.  
Students can register with email + enrollment number, verify their account via OTP email, join communities, create posts, chat in real-time, and manage their profiles and settings.

**Live site:** [https://gpconnecx.in](https://gpconnecx.in)

This repository is a **monorepo** containing both the React frontend and the Node.js/Express backend.

---

## Features

- **Authentication & Security**
  - Email + password signup with enrollment number validation
  - Email **OTP verification** before login
  - JWT-based authentication and protected API routes

- **Social Feed & Communities**
  - Create, view, and delete posts
  - Community-based feed
  - Seeded common and single communities

- **Real-Time Functionality**
  - Real-time messaging using **Socket.IO**
  - Typing indicators
  - Live post like updates
  - Room-based communication for communities and conversations

- **User Experience**
  - Fully responsive UI (desktop & mobile)
  - Modern React SPA (login, register, OTP, home/feed, notifications, messages, profile, settings)

---

## Tech Stack

- **Frontend (`gp-connect`)**
  - React 19 + Vite
  - React Router DOM
  - Bootstrap 5 + React Bootstrap
  - Tailwind CSS
  - Axios
  - Socket.IO client

- **Backend (`gp-connect-backend`)**
  - Node.js + Express
  - MongoDB + Mongoose
  - JWT for authentication
  - Bcrypt for password hashing
  - Nodemailer + SMTP (e.g. Gmail) for email/OTP
  - Socket.IO for real-time messaging
  - Multer for uploads

---

## Monorepo Structure

Capstone/
├── gp-connect/           # React frontend (Vite)
│   ├── src/
│   │   ├── components/   # Pages & UI components (Login, Register, Home, etc.)
│   │   ├── services/     # API & WebSocket clients
│   │   ├── config/       # Frontend environment config
│   │   └── utils/        # Helpers
│   └── README.md         # Frontend-specific docs
│
├── gp-connect-backend/   # Node.js + Express + MongoDB backend
│   ├── models/           # User, Post, Community, Conversation, Message
│   ├── controllers/      # Auth, posts, profile, community, messages
│   ├── routes/           # /api/auth, /api/posts, /api/profile, /api/community, /api/messages
│   ├── middleware/       # Auth & error handling
│   ├── config/           # DB connection & config
│   ├── utils/            # Token + email utilities
│   └── README.md         # Backend-specific docs
└── README.md             # (this file)
