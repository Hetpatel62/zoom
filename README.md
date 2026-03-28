# ZoomClone 🎥

A full-stack video conferencing web app built from scratch — inspired by Zoom. Supports real-time video/audio calls, in-call chat, screen sharing, and meeting history, all powered by WebRTC and Socket.IO.

---

## 🛠 Tech Stack

**Frontend**
- React 18 + React Router v6
- Material UI (MUI) — icons, buttons, UI components
- Socket.IO Client — real-time communication
- Axios — API requests
- WebRTC — peer-to-peer video/audio streaming

**Backend**
- Node.js + Express 4
- Socket.IO — signaling server for WebRTC
- MongoDB + Mongoose — user accounts & meeting history
- bcrypt — password hashing
- crypto — token-based authentication

---

## 📁 Project Structure

```
ZoomClone/
├── backend/
│   └── src/
│       ├── controllers/
│       │   ├── socketManager.js      # WebRTC signaling & chat via Socket.IO
│       │   └── user.controller.js    # Auth & meeting history logic
│       ├── models/
│       │   ├── user.model.js         # User schema
│       │   └── meeting.model.js      # Meeting history schema
│       ├── routes/
│       │   └── users.routes.js       # Auth & history API routes
│       └── app.js                    # Express + Socket.IO server entry
│
└── frontend/
    └── src/
        ├── pages/
        │   ├── landing.jsx           # Landing / home page
        │   ├── authentication.jsx    # Login & register
        │   ├── home.jsx              # Dashboard after login
        │   ├── history.jsx           # Past meetings list
        │   └── VideoMeet.jsx         # Core video call room
        ├── contexts/
        │   └── AuthContext.jsx       # Global auth state
        ├── utils/
        │   └── withAuth.jsx          # Protected route HOC
        └── environment.js            # Backend URL config
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v18+)
- MongoDB (local or [MongoDB Atlas](https://www.mongodb.com/atlas))

---

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ZoomClone.git
cd ZoomClone
```

---

### 2. Backend Setup

```bash
cd backend
npm install
```

In `src/app.js`, replace the MongoDB connection string with your own:

```js
await mongoose.connect("your_mongodb_connection_string_here");
```

Start the backend:

```bash
npm run dev
```

The server runs on **http://localhost:8000**

---

### 3. Frontend Setup

```bash
cd ../frontend
npm install
```

In `src/environment.js`, make sure the backend URL points to:

```js
http://localhost:8000
```

Start the frontend:

```bash
npm start
```

The frontend runs on **http://localhost:3000**

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/users/login` | Login and receive auth token |
| `POST` | `/api/v1/users/register` | Register a new user |
| `GET` | `/api/v1/users/get_user_history` | Get past meetings for a user |
| `POST` | `/api/v1/users/add_to_history` | Save a meeting to history |

---

## ✨ Features

- 📹 Real-time video & audio calls using **WebRTC**
- 💬 In-call **chat** with message history preserved for late joiners
- 🖥️ **Screen sharing** support
- 🔇 Toggle **mic and camera** on/off during a call
- 👥 **Multi-participant** rooms — multiple users can join the same meeting link
- 🔐 **User authentication** — register, login, token-based sessions
- 📋 **Meeting history** — view all past meetings per user
- ⚡ Real-time signaling via **Socket.IO**

---

## 📸 Screenshots

> Add screenshots of your app here

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
