# GP-CONNECX

GP-CONNECX is a modern campus social platform built with the MERN stack.  
Students can register with email + enrollment number, verify their account via OTP email, join communities, create posts, chat in real-time, and manage their profile and settings.

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
  - Common and single communities with seeding scripts

- **Real-Time Functionality**
  - Real-time messaging using **Socket.IO**
  - Typing indicators
  - Live post like updates
  - Room-based communication for communities and conversations

- **User Experience**
  - Fully responsive UI (desktop & mobile)
  - Modern React SPA
  - Separate pages for Login, Register, OTP Verification, Home/Feed, Notifications, Messages, Profile, and Settings

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
  - Multer for file uploads
  - Deployed-oriented with `Procfile` and environment-based config

---

## Monorepo Structure

Capstone/
├── gp-connect/           # React frontend (Vite)
│   ├── src/
│   │   ├── components/   # Pages & UI components (Login, Register, Home, etc.)
│   │   ├── services/     # API & WebSocket clients
│   │   ├── config/       # Frontend environment config
│   │   └── utils/        # Helpers (e.g., image utils)
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
└── README.md             # (this file)---

## Getting Started

### Prerequisites

- Node.js (LTS)
- npm
- MongoDB Atlas account (or local MongoDB instance)
- An email account (e.g. Gmail) for SMTP / OTP emails

---

## Backend Setup (`gp-connect-backend`)

1. **Install dependencies**

  
   cd gp-connect-backend
   npm install
   2. **Create `.env`**

   Create a `.env` file in `gp-connect-backend` (you can use `config.example.js` and the backend `README` as reference). Example:

  
   # Database
   MONGO_URI=mongodb+srv://<user>:<password>@cluster0.xxxxxx.mongodb.net/gpconnex

   # JWT Secret
   JWT_SECRET=a-very-strong-secret-key-for-jwt

   # Email (SMTP)
   EMAIL_HOST=smtp.gmail.com
   EMAIL_PORT=587
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-app-password

   # Server
   PORT=5000

   # CORS
   CORS_ORIGIN=http://localhost:5173
   3. **Run the backend**

  
   npm run dev
      The API will be available at: `http://localhost:5000/api`

---

## Frontend Setup (`gp-connect`)

1. **Install dependencies**

  
   cd gp-connect
   npm install
   2. **Create `.env`**

   Create `.env` in `gp-connect`:

  
   VITE_API_BASE_URL=http://localhost:5000/api
   VITE_WS_BASE_URL=ws://localhost:5000/ws
   3. **Run the frontend**

  
   npm run dev
      By default Vite runs on `http://localhost:5173`.

---

## Running the Full App Locally

In summary:

- **Terminal 1** (backend):

 
  cd gp-connect-backend
  npm run dev
  - **Terminal 2** (frontend):

 
  cd gp-connect
  npm run dev
  Then open `http://localhost:5173` in your browser and walk through:

1. Register with your details (name, email, enrollment number, password)
2. Check your email for the OTP and verify
3. Login and start using the feed, communities, chat, and profile pages

---

## Deployment

- **Frontend**
  - Build: `npm run build` inside `gp-connect`
  - Deploy the `dist` folder (e.g. Netlify, Vercel)
  - Configure production environment variables for API URLs

- **Backend**
  - Deploy `gp-connect-backend` to a Node-compatible host (e.g. Render)
  - Set environment variables (`MONGO_URI`, `JWT_SECRET`, email SMTP settings, etc.)
  - Make sure CORS / API base URL match your deployed frontend

See the `README.md` files inside `gp-connect` and `gp-connect-backend` for more detailed deployment notes.

---

## License

This project is currently licensed under the MIT/ISC-style terms defined in the subprojects’ `package.json`/READMEs. You can adjust this section based on your preferred license.
