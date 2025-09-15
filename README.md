# POSSPOLO - Premium Feedback Management System

A sophisticated educational feedback management platform featuring premium platinum design, comprehensive analytics, and advanced administrative controls.

![POSSPOLO Banner](src/assets/logo-icon.jpg)

## 🌟 Features

### Student Features
- **Secure Authentication**: JWT-based login system
- **Course Feedback**: Submit detailed feedback with ratings
- **Modern Interface**: Platinum-themed responsive design
- **Real-time Updates**: Dynamic feedback submission

### Admin Features
- **Student Management**: View, block, unblock, and delete user accounts
- **Analytics Dashboard**: Comprehensive feedback trends and course performance metrics
- **Feedback Management**: Advanced filtering and response capabilities
- **Security Controls**: Protected admin routes with middleware authentication

### Premium Design
- **Platinum Theme**: Luxury color scheme with sophisticated gradients
- **Responsive Layout**: Mobile-first design with elegant animations
- **Modern UI**: Shadcn/ui components with custom platinum styling

## 🛠️ Tech Stack

- **Frontend**: React 18, TypeScript, Tailwind CSS
- **Build Tool**: Vite
- **UI Components**: Shadcn/ui with custom platinum theme
- **Authentication**: localStorage-based JWT system
- **Styling**: Tailwind CSS with HSL color variables
- **State Management**: React hooks with TypeScript

## 🚀 Getting Started

### Prerequisites

- **Node.js**: Version 18+ required
- **Package Manager**: npm, yarn, or bun
- **MongoDB**: Version 5.0+ (for backend data storage)

### Frontend Setup

1. **Clone the repository**
```bash
git clone <repository-url>
cd feedback-fluent-11-main
```

2. **Install dependencies**
```bash
# Using npm
npm install

# Using yarn
yarn install

# Using bun
bun install
```

3. **Start the development server**
```bash
# Using npm
npm run dev

# Using yarn
yarn dev

# Using bun
bun dev
```

4. **Access the application**
   - Open your browser and navigate to `http://localhost:5173`
   - The application will hot-reload as you make changes

### Backend Setup

> **Note**: This is currently a frontend-only application using localStorage for data persistence. For production use, you'll need to implement a backend API.

1. **Install backend dependencies** (when implementing)
```bash
npm install express mongoose cors dotenv bcryptjs jsonwebtoken
```

2. **Backend structure** (recommended)
```
backend/
├── src/
│   ├── models/         # MongoDB schemas
│   ├── routes/         # API endpoints
│   ├── middleware/     # Auth and validation
│   ├── controllers/    # Business logic
│   └── config/         # Database configuration
├── .env               # Environment variables
└── server.js          # Entry point
```

## 🗄️ MongoDB Setup

### Local Installation

1. **Install MongoDB Community Edition**
   - Download from [MongoDB Official Site](https://www.mongodb.com/try/download/community)
   - Follow the installation guide for your OS

2. **Start MongoDB Service**
```bash
# Windows
net start MongoDB

# macOS
brew services start mongodb-community

# Linux
sudo systemctl start mongod
```

3. **Create Database**
```bash
# Connect to MongoDB
mongosh

# Create database
use posspolo_db

# Create collections
db.createCollection("users")
db.createCollection("courses")
db.createCollection("feedback")
```

### Cloud Setup (MongoDB Atlas)

1. **Create Atlas Account**
   - Visit [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
   - Create a free cluster

2. **Configure Database Access**
   - Create database user with read/write permissions
   - Whitelist your IP address

3. **Get Connection String**
   - Copy the connection string from Atlas dashboard

## ⚙️ Environment Configuration

Create a `.env` file in the root directory:

```env
# Application Configuration
NODE_ENV=development
PORT=5000

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/posspolo_db
# For MongoDB Atlas:
# MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/posspolo_db

# JWT Configuration
JWT_SECRET=your_super_secure_jwt_secret_key_here
JWT_EXPIRE=24h

# Frontend Configuration
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=POSSPOLO

# Email Configuration (optional)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password

# File Upload (optional)
MAX_FILE_SIZE=5MB
UPLOAD_PATH=./uploads
```

## 🔐 Test Login Information

### Current Implementation (localStorage-based)

The application currently uses localStorage for authentication. To test:

1. **Register a new account**:
   - Navigate to the login page
   - Click "Create Account"
   - Fill in your details
   - Your account will be stored locally

2. **Default Admin Access**:
   - Any user can be made an admin by modifying localStorage
   - Or register with email containing "admin" (e.g., admin@posspolo.com)

### Sample Test Accounts (for backend implementation)

```javascript
// Sample users to seed your database
const testUsers = [
  {
    email: "admin@posspolo.com",
    password: "Admin123!",
    role: "admin",
    name: "POSSPOLO Administrator"
  },
  {
    email: "student@posspolo.com", 
    password: "Student123!",
    role: "student",
    name: "Test Student"
  },
  {
    email: "instructor@posspolo.com",
    password: "Instructor123!", 
    role: "instructor",
    name: "Test Instructor"
  }
];
```

## 📜 Available Scripts

```bash
# Development
npm run dev          # Start development server (Vite)
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint

# Backend (when implemented)
npm run server       # Start backend server
npm run seed         # Seed database with sample data
npm run test         # Run test suite
```

## 📁 Project Structure

```
POSSPOLO/
├── public/
│   ├── favicon.ico
│   └── placeholder.svg
├── src/
│   ├── components/
│   │   ├── auth/           # Authentication components
│   │   ├── admin/          # Admin-only components
│   │   ├── dashboard/      # Dashboard components
│   │   ├── feedback/       # Feedback system
│   │   ├── layout/         # Layout components
│   │   └── ui/             # Shadcn/ui components
│   ├── lib/
│   │   ├── auth.ts         # Authentication logic
│   │   ├── courses.ts      # Course management
│   │   ├── feedback.ts     # Feedback utilities
│   │   └── utils.ts        # General utilities
│   ├── pages/              # Page components
│   ├── hooks/              # Custom React hooks
│   ├── assets/             # Images and static files
│   └── styles/             # Global styles
├── .env                    # Environment variables
├── package.json
└── README.md
```

## 🔧 Configuration Files

- **`vite.config.ts`**: Vite build configuration
- **`tailwind.config.ts`**: Tailwind CSS with platinum theme
- **`tsconfig.json`**: TypeScript configuration
- **`eslint.config.js`**: ESLint rules and plugins

## 🎨 Customization

### Platinum Theme Colors

The platinum color scheme is defined in `src/index.css`:

```css
:root {
  --primary: 220 12% 85%;        /* Platinum silver */
  --primary-light: 220 15% 92%;  /* Light platinum */
  --primary-dark: 220 10% 70%;   /* Dark platinum */
  --academic: 210 20% 80%;       /* Academic blue-platinum */
  --surface: 220 20% 98%;        /* Premium surface */
}
```

### Adding New Components

1. Create component in appropriate directory
2. Export from `index.ts` if creating a new module
3. Apply platinum theme classes for consistency

## 🚦 Deployment

### Frontend Deployment

1. **Build the application**
```bash
npm run build
```

2. **Deploy to hosting service**
   - Vercel: `npx vercel`
   - Netlify: Drag `dist` folder
   - Firebase: `firebase deploy`

### Backend Deployment

1. **Prepare for production**
```bash
npm run build
```

2. **Deploy to cloud service**
   - Heroku
   - Railway
   - DigitalOcean
   - AWS EC2

## 🔍 Troubleshooting

### Common Issues

1. **Port already in use**
```bash
# Kill process using port 5173
npx kill-port 5173
```

2. **Dependencies issues**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

3. **Build errors**
```bash
# Check TypeScript errors
npx tsc --noEmit
```

## 📞 Support

For technical support or feature requests:
- Create an issue in the repository
- Contact the development team
- Check the documentation wiki

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

**POSSPOLO** - Premium Educational Feedback Management Platform  
*Crafted with platinum-level attention to detail* ✨
