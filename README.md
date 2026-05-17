# NavAIgate v2 — AI Powered Smart Travel Companion

A full-stack MERN app for intelligent Indian travel planning, powered by Groq Llama 3.3.

---

## What's Fixed in v2

- **Auth calls real backend** — JWT + MongoDB (was localStorage-only before)
- **Itinerary** — Day-wise expandable cards with tabs (Weather / Alternatives)
- **Budget** — Bill scanner with AI extraction via camera or image upload
- **Chatbot** — Voice input (mic), text-to-speech, Hindi & Telugu support
- **Profile** — Shows real trips and budget from MongoDB
- **API** — All frontend calls go to Express backend properly

---

## Quick Start

### Prerequisites
- Node.js 18+, MongoDB Atlas account, Groq API key (free at console.groq.com)

### 1. Install

```bash
cd backend && npm install
cd ../frontend && npm install
```

### 2. Configure

**backend/.env**
```
MONGO_URI=mongodb+srv://user:pass@cluster.mongodb.net/navaigate?retryWrites=true&w=majority
JWT_SECRET=your_long_random_secret_32chars_minimum
GROQ_API_KEY=gsk_your_groq_key_here
PORT=5000
```

**frontend/.env**
```
VITE_API_URL=http://localhost:5000/api
```

### 3. Run

```bash
# Terminal 1
cd backend && npm run dev

# Terminal 2
cd frontend && npm run dev
```

Open http://localhost:5173

---

## API Endpoints

**Auth**: POST /api/auth/signup, POST /api/auth/signin, GET /api/auth/me

**Trips**: POST /api/trips/generate, PATCH /api/trips/:id/confirm, GET /api/trips, DELETE /api/trips/:id

**Budget**: GET /api/budget, POST /api/budget/setup, POST /api/budget/expense, DELETE /api/budget/expense/:id

**Chat**: POST /api/chat/message, GET /api/chat/history, DELETE /api/chat/history

---

## Stack

Frontend: React 18 + Vite + Tailwind CSS + Lucide Icons
Backend: Node.js + Express + MongoDB + Mongoose + JWT + bcryptjs
AI: Groq (Llama 3.3 70B) + Web Speech API
