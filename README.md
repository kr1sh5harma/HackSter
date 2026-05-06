<div align="center">

<img src="https://img.shields.io/badge/HackSter-v1.0.0-6C63FF?style=for-the-badge&logoColor=white" alt="HackSter" />

# ⚡ HackSter

### The All-in-One Hackathon Collaboration Platform

*From registration to real-time communication — everything teams need to build, compete, and win.*

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-hackster--mp4o.onrender.com-6C63FF?style=for-the-badge)](https://hackster-mp4o.onrender.com/)
[![React](https://img.shields.io/badge/React-Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://vitejs.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Socket.io](https://img.shields.io/badge/Socket.io-Real--Time-010101?style=for-the-badge&logo=socket.io)](https://socket.io/)

</div>

---

## 📌 Overview

**HackSter** is a full-stack MERN web application that bridges the gap between **hackathon organizers and participants**. It offers a unified platform for discovering and managing hackathons, assembling teams, sending collaboration requests, and communicating in real time — all secured with role-based access control and JWT authentication.

Whether you're an organizer running a large-scale event or a developer looking for a team to build with, HackSter has you covered from day one to demo day.

---

## 🎯 Key Highlights

| Capability | Description |
|---|---|
| 🔐 **Auth & Security** | JWT-based authentication with role-based access control |
| 🏆 **Hackathon Management** | Full CRUD for organizers; discovery & participation for builders |
| 👥 **Team Collaboration** | Create teams, send/manage join requests, remove members |
| 💬 **Real-Time Chat** | Socket.io-powered messaging scoped to authenticated team members |
| 👤 **User Profiles** | Editable personal profiles and public profile views |

---

## ✨ Features

### 🔐 Authentication & Authorization
- Secure user registration and login flows
- JWT-based stateless authentication
- Role-based access control with two distinct user roles:
  - **Organizers (Admin)** — manage hackathon events end-to-end
  - **Builders (Users)** — discover hackathons and collaborate with teams

---

### 🏆 Hackathon Management
- Browse and explore upcoming hackathons
- View detailed hackathon information
- Organizer-exclusive controls:
  - Create, update, and delete hackathon events
- Personalized view of hackathons you've created or joined

---

### 👥 Team Management
- Create dedicated teams for specific hackathons
- Discover and join teams actively recruiting members
- Send and receive join requests with an approval workflow
- Full team lifecycle management: leave, remove members, update, or disband

---

### 💬 Real-Time Team Communication
- Live team chat powered by **Socket.io**
- Messages are scoped exclusively to authenticated team members
- Secure and isolated communication per team

---

### 👤 User Profiles
- View and update your own profile
- Explore public profiles of other participants

---

## 🧑‍💻 User Roles

### 👑 Organizer (Admin)
> Designed for event organizers and hackathon hosts

- Full **CRUD** control over hackathon events
- Participate in hackathons as a team member
- Create and manage teams
- Browse all available hackathons

### 🛠️ Builder (User)
> Designed for developers, designers, and innovators

- Browse and participate in hackathons
- Create teams and invite collaborators
- Send and manage team join requests
- Communicate with teammates in real time

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| **React (Vite)** | Fast, modern UI framework |
| **Tailwind CSS** | Utility-first styling |
| **Redux Toolkit** | Global state management |
| **React Router** | Client-side routing |
| **Framer Motion** | Smooth UI animations |

### Backend
| Technology | Purpose |
|---|---|
| **Node.js + Express.js** | RESTful API server |
| **MongoDB** | NoSQL database |
| **JWT** | Stateless authentication |
| **Socket.io** | Real-time bidirectional communication |

---

## 🛣️ API Reference

### 🔑 Authentication
```
POST   /api/auth/register          Register a new user
POST   /api/auth/login             Authenticate and receive JWT
```

### 🏆 Hackathons
```
GET    /api/hackathons             Fetch all hackathons
POST   /api/hackathons             Create a hackathon          [Admin]
GET    /api/hackathons/my-events   Get user's hackathons
GET    /api/hackathons/:id         Get hackathon by ID
PUT    /api/hackathons/:id         Update a hackathon          [Admin]
DELETE /api/hackathons/:id         Delete a hackathon          [Admin]
```

### 👥 Teams
```
GET    /api/teams                      Fetch all teams
POST   /api/teams                      Create a team
GET    /api/teams/my-team              Get user's team
GET    /api/teams/:id                  Get team by ID
PUT    /api/teams/:id                  Update team details
DELETE /api/teams/:id                  Delete a team
POST   /api/teams/:id/request          Send a join request
POST   /api/teams/:id/manage-request   Accept or reject join request
POST   /api/teams/:id/leave            Leave a team
DELETE /api/teams/:id/remove/:userId   Remove a member
```

### 💬 Messages
```
GET    /api/messages/:teamId       Fetch messages for a team
```

### 👤 Users
```
GET    /api/users/profile          Get authenticated user's profile
PUT    /api/users/profile          Update authenticated user's profile
GET    /api/users/:id              Get a user's public profile
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js `v18+`
- MongoDB (local or Atlas)
- npm or yarn

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/hackster.git
cd hackster
```

**2. Set up the backend**
```bash
cd server
npm install
```

Create a `.env` file in the `/server` directory:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:5173
```

**3. Set up the frontend**
```bash
cd ../client
npm install
```

Create a `.env` file in the `/client` directory:
```env
VITE_API_URL=http://localhost:5000
```

**4. Run the application**

Start the backend:
```bash
cd server
npm run dev
```

Start the frontend:
```bash
cd client
npm run dev
```

The app will be live at **http://localhost:5173**

---

## 📁 Project Structure

```
hackster/
├── client/                   # React (Vite) frontend
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Route-level page components
│   │   ├── store/            # Redux Toolkit slices & store
│   │   ├── hooks/            # Custom React hooks
│   │   └── utils/            # Helper functions
│   └── vite.config.js
│
├── server/                   # Node.js + Express backend
│   ├── controllers/          # Route handler logic
│   ├── models/               # Mongoose schemas
│   ├── routes/               # Express API routes
│   ├── middleware/            # Auth & role guards
│   └── socket/               # Socket.io event handlers
│
└── README.md
```

---

## 🌐 Live Demo

> **Try HackSter live →** [https://hackster-mp4o.onrender.com/](https://hackster-mp4o.onrender.com/)

---

## 🤝 Contributing

Contributions are welcome! Please fork the repository, create a feature branch, and open a pull request. For major changes, open an issue first to discuss what you'd like to change.

```bash
git checkout -b feature/your-feature-name
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
```




