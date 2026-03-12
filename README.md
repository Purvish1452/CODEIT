# 🚀 CodeIt – Competitive Programming Tracker

**CodeIt** is a full-stack web application that helps competitive programmers **track their progress across multiple platforms** such as **LeetCode, Codeforces, and CodeChef**.

It provides **analytics, problem tracking, sheets, and performance insights** in one dashboard.

---

# ✨ Features

### 🔐 Authentication

* Email & password authentication
* OTP verification system
* Google OAuth login
* Secure authentication using **JWT**

### 📊 Dashboard

* Overall CP statistics
* Recent activity tracking
* Problem-solving progress overview

### 🧩 Problem Tracker

* Track problems from multiple platforms
* Status management: **Todo, Attempted, Solved, Review**
* Difficulty and tag filtering
* Notes and solution storage

### 📚 Sheet Management

* Create custom problem sheets
* Track progress within sheets
* Public/private sheet sharing

### 🔗 Platform Integrations

* **LeetCode**
* **Codeforces**
* **GitHub**
* Automatic data synchronization

### 👤 User Profiles

* Public developer profiles
* Statistics and achievements
* Social features

---

# 🛠 Tech Stack

## Backend

* **Node.js**
* **Express.js**
* **MongoDB**
* **Mongoose**
* **JWT Authentication**
* **Passport.js (OAuth)**
* **Node-Cron**
* **Axios**

## Frontend

* **React.js**
* **React Router**
* **React Query**
* **Tailwind CSS**
* **React Hook Form**
* **Lucide Icons**

---

# 📁 Project Structure

```
CodeIt
│
├── server
│   ├── config
│   ├── models
│   ├── routes
│   ├── middleware
│   ├── jobs
│   └── index.js
│
├── client
│   ├── public
│   ├── src
│   │   ├── components
│   │   ├── pages
│   │   ├── contexts
│   │   ├── utils
│   │   └── App.js
│
└── package.json
```

---

# ⚙️ Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/CodeIt.git
cd CodeIt
```

### 2️⃣ Install Dependencies

```bash
npm install
npm run install-server
npm run install-client
```

### 3️⃣ Setup Environment Variables

Create `.env` inside **server**

```env
PORT=5000
MONGODB_URI=your_mongodb_connection
JWT_SECRET=your_secret
CLIENT_URL=http://localhost:3000
```

Create `.env` inside **client**

```env
REACT_APP_API_URL=http://localhost:5000/api
```

### 4️⃣ Run the Project

```bash
npm run dev
```

Frontend → http://localhost:3000
Backend → http://localhost:5000

---

# 📡 API Endpoints

### Authentication

```
POST /api/auth/register
POST /api/auth/login
GET  /api/auth/me
PUT  /api/auth/profile
```

### Problems

```
GET    /api/problems
POST   /api/problems
PUT    /api/problems/:id
DELETE /api/problems/:id
```

### Sheets

```
GET  /api/sheets
POST /api/sheets
GET  /api/sheets/:id
PUT  /api/sheets/:id
```

---

# 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a Pull Request

---

# ⭐ Support

If you like this project, please consider **starring the repository** ⭐

---

# 👨‍💻 Author

**Purvish Panchal**

* GitHub: https://github.com/Purvish1452
* LinkedIn: https://www.linkedin.com/in/purvish-panchal-05206a294/

**Shrey Mehta**

* GitHub: https://github.com/ShreyMehta09
* LinkedIn: https://www.linkedin.com/in/shreymehta09/
