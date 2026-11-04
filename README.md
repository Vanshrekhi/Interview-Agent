# InterviewAgent — AI-Powered Interview Preparation Platform

InterviewAgent is a full-stack MERN web app for practicing AI-assisted mock interviews, analysing resumes, and tracking interview performance over time. Pick a role, choose a difficulty, answer AI-generated questions (with follow-ups), and get structured feedback you can download as a PDF.

> Built as a collaborative team project (Major Project VII).
> Original repository: [Sanskritysingh24/InterviewAgent](https://github.com/Sanskritysingh24/InterviewAgent)

## 🔗 Live Demo

| Service | URL |
|---|---|
| Frontend (Netlify) | https://interviewagent-major.netlify.app/ |
| Backend API (Render) | https://interviewagent-d4jn.onrender.com/ |

## ✨ Features

- **Google sign-in** via Firebase Authentication
- **Role-based interviews** — select a role and difficulty (easy / medium / hard)
- **Resume-aware questions** — upload a resume (PDF); questions are tailored to it
- **AI follow-up questions** that thread off your previous answers
- **Voice input** for answering questions
- **Structured AI feedback** and coaching on every session
- **Interview history** with performance dashboards and charts
- **Downloadable PDF reports** of each interview
- **Gamification and leaderboard** to compare progress with other users

## 🛠 Tech Stack

**Frontend**
- React 19, Vite 7, React Router 7
- Redux Toolkit + React Redux
- Tailwind CSS 4, Motion (animations)
- Axios, Firebase Auth, Recharts
- jsPDF + jspdf-autotable (PDF reports)

**Backend**
- Node.js (ES modules), Express 5
- MongoDB + Mongoose
- JWT-based authentication
- Multer (resume uploads), PDF.js (`pdfjs-dist`) for resume text extraction
- OpenRouter API for LLM features (default model: `openai/gpt-4o-mini`)

**Hosting:** Netlify (client) · Render (server) · MongoDB (database)

## 📁 Project Structure

```
Interview-Agent/
├── client/        # React + Vite frontend
├── server/        # Express API, models, routes
├── shared/        # Shared resources
├── Criteria.md    # Evaluation criteria
├── Tech.md        # Detailed technology notes
└── netlify.toml   # Netlify build config
```

## 🚀 Getting Started (Local Setup)

**Prerequisites:** Node.js 18+, a MongoDB connection string, an OpenRouter API key, and a Firebase project with Google sign-in enabled.

### 1. Clone

```bash
git clone https://github.com/Vanshrekhi/Interview-Agent.git
cd Interview-Agent
```

### 2. Backend

```bash
cd server
npm install
```

Create `server/.env`:

```env
PORT=8000
MONGODB_URL=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
OPENROUTER_API_KEY=your_openrouter_api_key
OPENROUTER_MODEL=openai/gpt-4o-mini   # optional
```

Run:

```bash
npm run dev     # development
npm start       # production
```

### 3. Frontend

```bash
cd client
npm install
```

Create `client/.env`:

```env
VITE_SERVER_URL=http://localhost:8000
VITE_FIREBASE_APIKEY=your_firebase_api_key
```

Run:

```bash
npm run dev     # start dev server
npm run build   # production build
npm run lint    # lint
```

## 🗄 Data Models

MongoDB collections cover users, resumes, interviews, questions, responses, AI coaching results, gamification data, roles, company tracks, and leaderboard entries.

## ☁️ Deployment

- **Frontend:** Netlify — `client/public/_redirects` handles SPA route fallback; `netlify.toml` holds the build config.
- **Backend:** Render — set `PORT`, `MONGODB_URL`, `JWT_SECRET`, `OPENROUTER_API_KEY` (and optionally `OPENROUTER_MODEL`) as environment variables.
- Set `VITE_SERVER_URL` in Netlify to the Render backend URL.

## 👤 Maintainer

**Vansh Rekhi** — [GitHub](https://github.com/Vanshrekhi)
