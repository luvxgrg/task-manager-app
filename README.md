# Task Manager App 📝

> A modern, full-stack task management application built with React, Node.js, Express, and MongoDB. Features user authentication, real-time task updates, and a clean, intuitive UI.

## ✨ Features

- **User Authentication**: Secure JWT-based login/signup with password hashing
- **Create, Read, Update, Delete (CRUD)**: Full task management capabilities
- **Real-time Updates**: Instant task synchronization across the UI
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Task Categories**: Organize tasks by category or priority
- **Due Date Tracking**: Set reminders and track deadlines
- **User Dashboard**: Clean, modern dashboard with task statistics
- **Protected Routes**: Secure API endpoints with authentication

## 🛠️ Tech Stack

**Frontend:**
- React 18.x
- React Router for navigation
- Axios for API calls
- Tailwind CSS for styling
- React Query for state management

**Backend:**
- Node.js
- Express.js
- MongoDB for database
- JWT for authentication
- bcrypt for password hashing
- Cors for cross-origin requests

**DevOps:**
- Docker (optional)
- Git for version control

## 📦 Installation

### Prerequisites

- Node.js v14+ and npm
- MongoDB (local or Atlas cloud)
- Git

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/luvxgrg/task-manager-app.git
   cd task-manager-app
   ```

2. **Install backend dependencies**
   ```bash
   cd server
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../client
   npm install
   ```

4. **Set up environment variables**

Create `.env` in the `server` directory with your configuration:
   ```env
   PORT=5000
   DB_URL=<your-mongodb-connection-string>
   JWT_SECRET=<your-secret-key>
   NODE_ENV=development
   ```
   See `.env.example` file for all available options..env]://YOUR_USERNAME:YOUR_PASSWORD@YOUR_CLUSTER.mongodb.net/taskdb
   JWT_SECRET=your_jwt_secret_key
   NODE_ENV=development
   ```

   Create `.env.local` in the `client` directory:
   ```env
   REACT_APP_API_URL=http://localhost:5000
   ```

5. **Start MongoDB** (if using locally)
   ```bash
   mongod
   ```

6. **Start the backend**
   ```bash
   cd server
   npm run dev
   ```

7. **Start the frontend** (in another terminal)
   ```bash
   cd client
   npm start
   ```

   The app will open at `http://localhost:3000`

## 🚀 Usage

### Register & Login
1. Click "Sign Up" to create a new account
2. Enter email and password
3. Login with your credentials

### Manage Tasks
1. **Create**: Click "+ New Task" and fill in details
2. **View**: All your tasks appear in the main dashboard
3. **Update**: Click on a task to edit title, description, or due date
4. **Delete**: Click trash icon to remove a task
5. **Mark Done**: Click checkbox to mark tasks as complete

## 📁 Project Structure

```
task-manager-app/
├── client/                    # React frontend
│   ├── src/
│   │   ├── components/        # Reusable components
│   │   ├── pages/             # Page components
│   │   ├── hooks/             # Custom React hooks
│   │   ├── services/          # API service calls
│   │   ├── App.js
│   │   └── index.js
│   ├── public/
│   └── package.json
│
├── server/                    # Node.js backend
│   ├── models/                # MongoDB schemas
│   ├── routes/                # API routes
│   ├── controllers/           # Route handlers
│   ├── middleware/            # Auth & validation
│   ├── config/                # Configuration files
│   ├── server.js              # Entry point
│   └── package.json
│
└── README.md                  # This file
```

## 🔌 API Endpoints

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/auth/signup` | Register new user | ❌ |
| POST | `/auth/login` | User login | ❌ |
| GET | `/api/tasks` | Get all user tasks | ✅ |
| POST | `/api/tasks` | Create new task | ✅ |
| PUT | `/api/tasks/:id` | Update task | ✅ |
| DELETE | `/api/tasks/:id` | Delete task | ✅ |
| GET | `/api/user` | Get user profile | ✅ |

## 🔐 Authentication

The app uses **JWT (JSON Web Tokens)** for authentication:
1. User provides email/password
2. Server validates and returns a JWT token
3. Token is stored in localStorage on the client
4. Token is sent in every authenticated request header
5. Server validates token before processing requests

## 🧪 Testing

```bash
# Backend tests
cd server
npm test

# Frontend tests
cd client
npm test
```

## 🐛 Troubleshooting

### MongoDB Connection Error
- Check your MongoDB URI in `.env`
- Ensure MongoDB is running
- Verify IP whitelist in MongoDB Atlas

### CORS Error
- Frontend and backend URLs don't match
- Check `REACT_APP_API_URL` in frontend `.env`
- Ensure server has `cors` middleware enabled

### Port Already in Use
```bash
# Kill process on port 5000 (Linux/Mac)
lsof -ti:5000 | xargs kill -9

# Windows
netstat -ano | findstr :5000
taskkill /PID <PID> /F
```

## 📈 Future Features

- [ ] Task filtering and sorting
- [ ] Recurring tasks
- [ ] Team collaboration
- [ ] Email notifications
- [ ] Dark mode
- [ ] Mobile app (React Native)
- [ ] Task templates
- [ ] Bulk task operations

## 📝 License

MIT License - See LICENSE file for details

## 👨‍💻 Author

**Lovish** ([@luvxgrg](https://github.com/luvxgrg))

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## ⭐ Support

If you found this project helpful, please star it on GitHub! It means a lot.

---

**Last Updated**: March 2026
