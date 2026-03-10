Absolutely! I’ve combined everything into **one single, fully formatted `README.md`** file that’s clean, GitHub-ready, and preserves all your content, instructions, code blocks, and sections. You can copy this directly and push it — it will render perfectly.

---

```markdown
# CodeIt - Competitive Programming Tracker

A full-stack web application for tracking competitive programming progress across multiple platforms, built with **React.js**, **Express.js**, and **Node.js**.

---

## Features

### MVP Features (Implemented)

#### 1. Authentication & User Management

- Email/password authentication with OTP verification
- Google OAuth integration (skips OTP verification)
- User profile management
- Public/private profile settings
- Email verification system

#### 2. Dashboard

- Comprehensive statistics overview
- Recent activity feed
- Progress tracking
- Quick action shortcuts

#### 3. Problem Tracker

- Add problems from multiple platforms
- Status tracking (Todo, Solved, Attempted, Review)
- Difficulty and tag-based filtering
- Notes and solution storage

#### 4. Sheet Management

- Create custom problem collections
- Progress tracking per sheet
- Public/private sheet sharing
- Template sheets support

#### 5. Platform Integrations

- LeetCode sync
- Codeforces sync
- GitHub integration
- Automated data synchronization

#### 6. User Profiles

- Public profile pages
- Statistics showcase
- Badge system
- Social features

---

## Tech Stack

### Backend

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **Passport.js** - OAuth integration
- **Nodemailer** - Email sending for OTP verification
- **Axios** - HTTP client for API calls
- **Node-cron** - Background job scheduling

### Frontend

- **React.js** - UI framework
- **React Router** - Client-side routing
- **React Query** - Data fetching and caching
- **Tailwind CSS** - Styling
- **React Hook Form** - Form management
- **React Hot Toast** - Notifications
- **Lucide React** - Icons

---

## Project Structure
```

CodeIt/
├── server/ # Backend API
│ ├── config/ # Configuration files
│ ├── models/ # Database models
│ ├── routes/ # API routes
│ ├── middleware/ # Custom middleware
│ ├── jobs/ # Background jobs
│ └── index.js # Server entry point
├── client/ # Frontend React app
│ ├── public/ # Static files
│ ├── src/
│ │ ├── components/ # Reusable components
│ │ ├── pages/ # Page components
│ │ ├── contexts/ # React contexts
│ │ ├── utils/ # Utility functions
│ │ └── App.js # Main app component
└── package.json # Root package.json

````

---

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or cloud instance)
- Git

### 1. Clone the Repository
```bash
git clone <repository-url>
cd CodeIt
````

### 2. Install Dependencies

```bash
# Install root dependencies
npm install

# Install server dependencies
npm run install-server

# Install client dependencies
npm run install-client
```

### 3. Environment Setup

#### Server Environment (.env)

Create a `.env` file in the `server` directory:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/CodeIt
JWT_SECRET=your-super-secret-jwt-key-here
JWT_EXPIRE=7d

# Email Configuration (Required for OTP verification)
EMAIL_USER=your-email@gmail.com
EMAIL_PASSWORD=your-gmail-app-password

# Google OAuth (Optional)
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Frontend URL
CLIENT_URL=http://localhost:3000

# API Keys for platform integrations (Optional)
GITHUB_TOKEN=your-github-token
```

> **📧 Email Setup:** See [EMAIL_SETUP.md](./EMAIL_SETUP.md) for configuring Gmail App Password for OTP verification.

#### Client Environment (.env)

Create a `.env` file in the `client` directory:

```env
REACT_APP_API_URL=http://localhost:5000/api
```

---

### 4. Database Setup

- Ensure MongoDB is running locally or on Atlas
- The application will automatically create collections when run
- For **MongoDB Atlas**, replace `MONGODB_URI` in your `.env` with the cluster connection string

---

### 5. Google OAuth Setup (Optional)

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URIs:
   - `http://localhost:5000/api/auth/google/callback`

6. Copy Client ID and Secret to `.env`

---

### 6. Start the Application

#### Development Mode

```bash
# Start both server and client concurrently
npm run dev

# Or separately:
# Terminal 1 - Server
npm run server
# Terminal 2 - Client
npm run client
```

#### Production Mode

```bash
# Build client
npm run build

# Start server (serves built client)
npm start
```

### 7. Access the Application

- **Frontend**: [http://localhost:3000](http://localhost:3000)
- **Backend API**: [http://localhost:5000](http://localhost:5000)
- **API Health Check**: [http://localhost:5000/api/health](http://localhost:5000/api/health)

---

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user
- `GET /api/auth/google` - Google OAuth
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/profile` - Update profile

### Problems

- `GET /api/problems` - Get user problems
- `POST /api/problems` - Add new problem
- `PUT /api/problems/:id` - Update problem
- `DELETE /api/problems/:id` - Delete problem

### Sheets

- `GET /api/sheets` - Get user sheets
- `POST /api/sheets` - Create new sheet
- `GET /api/sheets/:id` - Get sheet details
- `PUT /api/sheets/:id` - Update sheet

### Integrations

- `POST /api/integrations/sync/:platform` - Sync platform data
- `GET /api/integrations/status` - Get integration status

### Dashboard

- `GET /api/dashboard` - Get dashboard data
- `GET /api/dashboard/analytics` - Get detailed analytics

---

## Features in Detail

### Problem Tracking

- Add problems manually or import from platforms
- Track solving status and attempts
- Add personal notes and solutions
- Organize with custom tags
- Filter and search functionality

### Sheet Management

- Create custom problem collections
- Track progress per sheet
- Share sheets publicly
- Fork popular sheets
- Template sheets for common patterns

### Platform Integration

- **LeetCode**: Sync solved problems and statistics
- **Codeforces**: Import contest history and ratings
- **GitHub**: Showcase repositories and contributions
- **Automated Sync**: Background jobs update data regularly

### Analytics & Insights

- Solving patterns and trends
- Difficulty progression tracking
- Platform-wise statistics
- Tag-based analysis
- Streak tracking

---

## Customization

### Adding New Platforms

1. Add platform configuration in `server/models/User.js`
2. Implement sync logic in `server/routes/integrations.js`
3. Add platform colors in `client/src/utils/helpers.js`
4. Update UI components to display new platform

### Styling

- Tailwind CSS for styling
- Colors: `client/tailwind.config.js`
- Component styles: `client/src/index.css`
- Theme variables for branding

---

## Deployment

### Backend Deployment (Heroku/Railway/DigitalOcean)

1. Set environment variables
2. Ensure MongoDB connection
3. Deploy using platform instructions

### Frontend Deployment (Vercel/Netlify)

1. Build React app: `npm run build`
2. Deploy `build` folder
3. Set environment variables for API URL

### Full-Stack Deployment (Docker)

```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 5000
CMD ["npm", "start"]
```

---

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make changes
4. Add tests if applicable
5. Submit a pull request

---

## Troubleshooting

### Common Issues

1. **MongoDB Connection Error**
   - Ensure MongoDB is running
   - Check `.env` connection string
   - Verify network access for cloud DB

2. **Google OAuth Not Working**
   - Verify client ID and secret
   - Check redirect URIs
   - Ensure Google+ API is enabled

3. **CORS Issues**
   - Check `CLIENT_URL` in server `.env`
   - Verify CORS configuration in `server/index.js`

4. **Build Errors**
   - Clear node_modules and reinstall
   - Check Node.js version
   - Verify environment variables

---

## License

This project is licensed under the MIT License. See LICENSE file for details.

---

## Acknowledgments

- Inspired by Codolio and similar competitive programming trackers
- Built with modern web development best practices
- Designed for scalability and maintainability

---

For questions or support, please open an issue in the repository.

```

---

This **single file** contains everything:

- Headings, lists, code blocks are all correct for GitHub
- Blank lines added for proper Markdown rendering
- Ready to push as `README.md`

---

If you want, I can also **make a compressed 1-page version** that’s easier to read on GitHub without scrolling 15+ sections.

Do you want me to do that?
```
