# 🚀 Career Guidance MERN Stack

A **full-stack MERN application** with modern authentication (Email/Password + Google OAuth 2.0) for career guidance and counseling. Features user authentication, career path recommendations, eligibility tracking, and AI-powered insights powered by Google's Gemini API.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-career--guidance--mern.vercel.app-blue)](https://career-guidance-mern.vercel.app)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-18+-blue)](https://react.dev)
[![MongoDB](https://img.shields.io/badge/MongoDB-8.5+-green)](https://www.mongodb.com)

---

## ✨ Features

### 🔐 **Authentication**
- Email/Password authentication with JWT
- Google OAuth 2.0 integration (Passport.js)
- Secure session management
- Role-based access control (User/Admin)

### 💼 **Career Guidance**
- Career path recommendations
- Eligibility assessment
- Alternative career paths
- Job market insights
- AI-powered career advice (Google Gemini API integration)

### 📊 **Dashboard & Analytics**
- User profile management
- Career progress tracking
- Interactive charts and visualizations
- Document uploads (Resume, CV)
- Email notifications

### �� **Frontend**
- React 18 with Vite (fast build times)
- Tailwind CSS for responsive design
- Framer Motion for smooth animations
- Chart.js for data visualization
- React Router for navigation

### ⚙️ **Backend**
- Express.js REST API
- MongoDB with Mongoose ODM
- Advanced data seeding
- CORS & security middleware
- Email notifications with Nodemailer

---

## 📋 Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React 18, Vite, Tailwind CSS, Framer Motion |
| **Backend** | Node.js, Express.js, MongoDB, Mongoose |
| **Auth** | JWT, Passport.js, bcrypt |
| **AI** | Google Generative AI (Gemini API) |
| **Deployment** | Vercel (Frontend), Node.js server (Backend) |
| **Package Manager** | npm |

---

## 🛠️ Prerequisites

Before you begin, ensure you have installed:
- **Node.js** 18+ ([Download](https://nodejs.org))
- **MongoDB** (Local or [Atlas Cloud](https://www.mongodb.com/products/platform/atlas))
- **npm** or **yarn**
- **Git**

### Required API Keys
- **Google OAuth Client ID & Secret** ([Setup Guide](https://developers.google.com/identity/protocols/oauth2))
- **Google Gemini API Key** ([Get Key](https://ai.google.dev))

---

## 📦 Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/vipooshans/career-guidance-mern.git
cd career-guidance-mern
```

### 2️⃣ Backend Setup

```bash
cd server

# Copy environment template
cp .env.example .env

# Install dependencies
npm install

# Start development server
npm run dev
```

**Backend URL**: `http://localhost:5000`

### 3️⃣ Frontend Setup

```bash
cd ../client

# Copy environment template
cp .env.example .env

# Install dependencies
npm install

# Start development server
npm run dev
```

**Frontend URL**: `http://localhost:5173`

---

## 🔑 Environment Variables

### `server/.env`

```env
# Database
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/career-guidance

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_min_32_chars

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:5000/auth/google/callback

# Frontend URL
CLIENT_URL=http://localhost:5173

# Google Gemini API
GEMINI_API_KEY=your_google_gemini_api_key

# Email Configuration (Optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASSWORD=your_app_password

# Server Port
PORT=5000
NODE_ENV=development
```

### `client/.env`

```env
# Backend API URL
VITE_API_URL=http://localhost:5000

# Google Client ID (for frontend OAuth button)
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

---

## 🚀 Running the Application

### Development Mode

**Terminal 1 - Backend:**
```bash
cd server
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd client
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Seed Database (Optional)

Populate sample data:
```bash
cd server
npm run seed:careers
npm run seed:eligibility
npm run seed:alternatives
```

---

## 🌐 Google OAuth Setup

### Step 1: Create Google Cloud Project
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project
3. Enable "Google+ API"

### Step 2: Create OAuth 2.0 Credentials
1. Go to **Credentials** → **Create Credentials** → **OAuth 2.0 Client ID**
2. Choose **Web Application**
3. Add authorized redirect URIs:
   - `http://localhost:5000/auth/google/callback` (dev)
   - `https://yourdomain.com/auth/google/callback` (production)
4. Copy **Client ID** and **Client Secret** to `.env`

### Step 3: Test OAuth Flow
- Click "Continue with Google" on login/register page
- Grant permissions
- Backend creates user & issues JWT
- Redirected to dashboard with token stored

---

## 📚 API Documentation

### Authentication Endpoints

#### Register
```http
POST /api/auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "SecurePassword123"
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "SecurePassword123"
}
```

#### Google OAuth
```
GET /auth/google
```

#### Logout
```http
POST /api/auth/logout
Authorization: Bearer <token>
```

### Career Endpoints

#### Get All Careers
```http
GET /api/careers
```

#### Get Career by ID
```http
GET /api/careers/:id
```

#### Get Recommendations
```http
POST /api/careers/recommend
Authorization: Bearer <token>
Content-Type: application/json

{
  "skills": ["JavaScript", "React"],
  "interests": ["Web Development"]
}
```

---

## 🧪 Testing

To add tests to the project:

```bash
cd server
npm install --save-dev jest supertest

cd ../client
npm install --save-dev vitest @testing-library/react
```

Run tests:
```bash
npm run test
```

---

## 🚀 Deployment

### Deploy Backend (Vercel / Railway)

**Using Vercel:**
```bash
npm i -g vercel
vercel
```

**Using Railway:**
1. Connect GitHub repo to Railway
2. Add environment variables
3. Deploy with one click

### Deploy Frontend

**Using Vercel:**
```bash
cd client
npm run build
vercel
```

**Using Netlify:**
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

### Production Checklist

- [ ] Use MongoDB Atlas (not local)
- [ ] Enable HTTPS
- [ ] Set up httpOnly cookies for JWT
- [ ] Configure CORS properly
- [ ] Enable rate limiting
- [ ] Add CSRF protection
- [ ] Set up email verification
- [ ] Configure password reset flow
- [ ] Enable refresh token rotation
- [ ] Add error tracking (Sentry)
- [ ] Set up CI/CD pipeline

---

## 🔒 Security Considerations

### Current Implementation
✅ Password hashing with bcrypt  
✅ JWT-based authentication  
✅ CORS protection  
✅ Environment variables for secrets  

### Recommended Improvements
- Implement **httpOnly cookies** instead of localStorage
- Add **refresh token rotation**
- Enable **rate limiting** on auth endpoints
- Implement **CSRF protection**
- Add **email verification** for new accounts
- Implement **password reset** functionality
- Use **helmet.js** for HTTP headers
- Add **input validation** with joi or zod
- Implement **request logging** and monitoring

---

## 📂 Project Structure

```
career-guidance-mern/
├── server/                    # Express.js backend
│   ├── src/
│   │   ├── models/           # MongoDB schemas
│   │   ├── routes/           # API endpoints
│   │   ├── controllers/       # Business logic
│   │   ├── middleware/        # Auth & logging
│   │   ├── seeds/            # Database seeds
│   │   └── server.js         # Entry point
│   ├── .env.example
│   └── package.json
│
├── client/                    # React frontend
│   ├── src/
│   │   ├── components/       # React components
│   │   ├── pages/           # Page components
│   │   ├── context/         # Context API state
│   │   ├── services/        # API calls
│   │   └── App.jsx          # Root component
│   ├── .env.example
│   └── package.json
│
├── README.md
├── LICENSE.md
└── CONTRIBUTING.md
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit changes**: `git commit -m 'Add amazing feature'`
4. **Push to branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

## 📝 License

This project is licensed under the **MIT License** - see [LICENSE.md](LICENSE.md) for details.

---

## 🆘 Troubleshooting

### MongoDB Connection Error
```
Error: connect ECONNREFUSED 127.0.0.1:27017
```
**Solution**: Ensure MongoDB is running or update `MONGO_URI` to use MongoDB Atlas

### Google OAuth Redirect Error
```
Error: Redirect URI mismatch
```
**Solution**: Add your redirect URI to Google Cloud Console → OAuth 2.0 Authorized redirect URIs

### CORS Error in Browser
```
Access to XMLHttpRequest blocked by CORS policy
```
**Solution**: Verify `CLIENT_URL` in `server/.env` matches your frontend URL

---

## 🙋 Support & Questions

- **Issues**: [GitHub Issues](https://github.com/vipooshans/career-guidance-mern/issues)
- **Discussions**: [GitHub Discussions](https://github.com/vipooshans/career-guidance-mern/discussions)
- **Email**: vipoos.hans@gmail.com

---

## 📈 Roadmap

- [ ] Mobile app (React Native)
- [ ] Advanced analytics dashboard
- [ ] Video interview preparation module
- [ ] Resume builder with AI suggestions
- [ ] Job matching algorithm
- [ ] Mentor connection feature
- [ ] Dark mode support
- [ ] Multi-language support

---

## ⭐ Show Your Support

If you found this project helpful, please give it a star! ⭐

---

**Made with ❤️ by [vipooshans](https://github.com/vipooshans)**
