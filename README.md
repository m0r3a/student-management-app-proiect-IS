# Student Management Dashboard

A full-stack web application for managing students and courses, built with React (Frontend) and Node.js/Express with MongoDB (Backend).

## 🚀 Project Structure

```
Student Management app/
├── Backend/          # Node.js/Express API server
├── Frontend/         # React application
└── README.md         # This file
```

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14 or higher) - [Download Node.js](https://nodejs.org/)
- **npm** (comes with Node.js)
- **MongoDB** - Either:
  - MongoDB installed locally, OR
  - MongoDB Atlas account (free tier available)

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/m0r3a/student-management-app-proiect-IS.git
cd student-management-app-proiect-IS
```

### 2. Backend Setup

#### Install Dependencies

```bash
cd Backend
npm install
```

#### Configure MongoDB

Create a `.env` file in the `Backend` directory:

```bash
# For local MongoDB
MONGODB_URI=mongodb://localhost:27017/student-management-app

# OR for MongoDB Atlas (recommended)
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/student-management-app
```

**To get MongoDB Atlas connection string:**

1. Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas/database)
2. Create a free cluster
3. Create a database user
4. Whitelist your IP address (or use 0.0.0.0/0 for development)
5. Get your connection string from "Connect" → "Connect your application"

#### Start the Backend Server

```bash
# From the Backend directory
node server.js
```

The backend server will start on **http://localhost:3000**

You should see:

```
Server is running on port 3000
Connected to MongoDB
```

### 3. Frontend Setup

#### Install Dependencies

```bash
cd Frontend
npm install
```

#### Start the React Development Server

```bash
# From the Frontend directory
npm run dev
```

The frontend will start on **http://localhost:5173** (or another port if 5173 is busy)

## 🎯 Running the Application

### Option 1: Run Backend and Frontend Separately

**Terminal 1 - Backend:**

```bash
cd Backend
node server.js
```

**Terminal 2 - Frontend:**

```bash
cd Frontend
npm run dev
```

### Option 2: Use npm scripts (if configured)

You can add scripts to the root `package.json` to run both simultaneously.

## 📡 API Endpoints

The backend API runs on `http://localhost:3000` and provides the following endpoints:

### Students

- `GET /api/students` - Get all students
- `POST /api/students` - Create a new student
- `GET /api/students/:id` - Get a specific student
- `PUT /api/students/:id` - Update a student
- `DELETE /api/students/:id` - Delete a student
- `GET /api/students/search?q=term` - Search students

### Courses

- `GET /api/courses` - Get all courses
- `POST /api/courses` - Create a new course
- `GET /api/courses/:id` - Get a specific course
- `PUT /api/courses/:id` - Update a course
- `DELETE /api/courses/:id` - Delete a course

### Dashboard

- `GET /api/dashboard/stats` - Get dashboard statistics

### Health Check

- `GET /health` - Basic health check
- `GET /health/detailed` - Detailed health check with MongoDB status

## 🧪 Testing the Setup

1. **Check Backend Health:**

   ```bash
   curl http://localhost:3000/health
   ```

2. **Check MongoDB Connection:**

   ```bash
   curl http://localhost:3000/health/detailed
   ```

3. **Open Frontend:**
   - Navigate to `http://localhost:5173` in your browser
   - You should see the React application

## 🐛 Troubleshooting

### Backend Issues

**MongoDB Connection Error:**

- Ensure MongoDB is running (if using local MongoDB)
- Check your `.env` file has the correct `MONGODB_URI`
- Verify MongoDB Atlas network access allows your IP

**Port Already in Use:**

- Change the port in `Backend/server.js`:
  ```javascript
  const PORT = process.env.PORT || 3001; // Use different port
  ```

### Frontend Issues

**Cannot Connect to Backend:**

- Ensure backend is running on port 3000
- Check `Frontend/src` files for API base URL configuration
- Verify CORS is enabled in backend (it should be by default)

**Port Already in Use:**

- Vite will automatically use the next available port
- Check the terminal output for the actual port number

## 📦 Technologies Used

### Backend

- **Node.js** - Runtime environment
- **Express** - Web framework
- **MongoDB** - Database
- **Mongoose** - MongoDB object modeling
- **Winston** - Logging
- **Morgan** - HTTP request logger
- **CORS** - Cross-origin resource sharing

### Frontend

- **React** - UI library
- **Vite** - Build tool and dev server
- **JavaScript** - Programming language

## 📝 Environment Variables

### Backend (.env)

```
MONGODB_URI=mongodb://localhost:27017/student-management-app
PORT=3000
NODE_ENV=development
```

## 🔧 Development

### Backend Development

- Server auto-restarts on file changes (if using nodemon)
- Logs are saved to `Backend/combined.log` and `Backend/error.log`

### Frontend Development

- Hot module replacement (HMR) enabled
- Fast refresh for React components
- Source maps for debugging

## 📄 License

ISC

## 👤 Author

m0r3a

## 🔗 Repository

https://github.com/m0r3a/student-management-app-proiect-IS
