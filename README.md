# CityFix - Community Issue Tracking Platform

![CityFix Logo](https://img.shields.io/badge/CityFix-Community%20Issue%20Tracker-blue?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-2.0.0-green?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

A comprehensive full-stack web application for tracking and managing community issues with modern UI/UX, authentication system, and separate client and admin interfaces.

## 🌟 Overview

CityFix is a modern, responsive community issue tracking platform that enables citizens to report local issues (potholes, streetlight problems, garbage collection, etc.) and allows administrators to efficiently manage and resolve these issues. The platform features a beautiful, modern interface with real-time updates, interactive maps, and comprehensive issue management tools.

## 📁 Project Structure

```
cityfix/
├── 📁 server/          # Backend API (Node.js + Express + MongoDB)
│   ├── app.js          # Main server application
│   ├── config/         # Configuration files
│   ├── middleware/     # Authentication & custom middleware
│   ├── models/         # MongoDB data models
│   └── routes/         # API endpoints
├── 📁 client/          # User Frontend (React + Vite)
│   ├── src/
│   │   ├── components/ # React components
│   │   ├── context/    # Authentication context
│   │   └── services/   # API services
│   └── public/         # Static assets
└── 📁 admin/           # Admin Frontend (React + Vite)
    ├── src/
    │   ├── components/ # Admin-specific components
    │   └── services/   # Admin API services
    └── public/         # Admin static assets
```

## ✨ Key Features

### 🏠 **Client Application**
- **🎨 Modern UI/UX** - Beautiful, responsive design with glass morphism effects
- **🔐 User Authentication** - Secure login/signup with JWT tokens
- **📍 Interactive Maps** - Leaflet-based map integration for issue location
- **📝 Issue Reporting** - Comprehensive form with image upload support
- **📊 Personal Dashboard** - View and track your reported issues
- **📱 Responsive Design** - Mobile-first approach for all devices
- **🔔 Real-time Updates** - Live issue status updates
- **📢 Community Notices** - View important community announcements

### 🛠️ **Admin Application**
- **🎛️ Comprehensive Dashboard** - Complete issue management interface
- **📊 Analytics & Statistics** - Real-time issue metrics and charts
- **🔄 Status Management** - Update issue status workflow (New → In Progress → Resolved)
- **🔍 Advanced Filtering** - Filter issues by status, date, location, priority
- **🗺️ Map Overview** - Visual representation of all issues on interactive map
- **📢 Notice Management** - Create and manage community announcements
- **🔐 Admin Authentication** - Secure admin-only access
- **📈 Performance Monitoring** - System health and usage statistics

### 🔧 **Server API**
- **🚀 RESTful Architecture** - Clean, organized API endpoints
- **🔒 JWT Authentication** - Secure token-based authentication
- **🖼️ File Upload** - Cloudinary integration for image handling
- **📊 Data Validation** - Comprehensive input validation and sanitization
- **🛡️ Security Middleware** - CORS, authentication, and error handling
- **📱 Mobile-friendly** - Optimized for mobile app consumption

## 🚀 Getting Started

### 📋 Prerequisites
- **Node.js** (v16 or higher)
- **MongoDB Atlas** account (or local MongoDB installation)
- **Cloudinary** account (for image upload functionality)
- **Git** for version control

### ⚙️ Installation & Setup

#### 1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/cityfix.git
cd cityfix
```

#### 2. **Server Setup**

Navigate to the server directory and install dependencies:
```bash
cd server
npm install
```

Create a `.env` file in the `server` directory with the following configuration:

```env
# Database Configuration
MONGODB_CONNECTION_STRING=mongodb+srv://username:password@cluster.mongodb.net/cityfix?retryWrites=true&w=majority

# Server Configuration
PORT=5000
NODE_ENV=development

# JWT Authentication
JWT_SECRET=your-super-secret-jwt-key-change-in-production

# Cloudinary Configuration (for image uploads)
CLOUDINARY_CLOUD_NAME=your-cloudinary-cloud-name
CLOUDINARY_API_KEY=your-cloudinary-api-key
CLOUDINARY_API_SECRET=your-cloudinary-api-secret

# Admin Configuration
ADMIN_EMAIL=admin@cityfix.com
ADMIN_PASSWORD=admin123
```

**Important Environment Variables:**
- `MONGODB_CONNECTION_STRING`: Your MongoDB Atlas connection string
- `JWT_SECRET`: A secure secret key for JWT token generation (use a strong, random string)
- `CLOUDINARY_*`: Your Cloudinary credentials for image upload functionality
- `ADMIN_EMAIL` & `ADMIN_PASSWORD`: Default admin credentials

Start the server:
```bash
npm start
# For development with auto-reload:
npm run dev
```

#### 3. **Client Setup**

Open a new terminal and navigate to the client directory:
```bash
cd client
npm install
npm run dev
```

The client application will be available at `http://localhost:5173`

#### 4. **Admin Setup**

Open another terminal and navigate to the admin directory:
```bash
cd admin
npm install
npm run dev
```

The admin panel will be available at `http://localhost:5174`

## 🌐 Application URLs

- **Client Application**: http://localhost:5173
- **Admin Panel**: http://localhost:5174  
- **Server API**: http://localhost:5000

## 🔌 API Endpoints

### **Authentication**
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/api/auth/signup` | Register new user | ❌ |
| `POST` | `/api/auth/login` | User login | ❌ |

### **Issues Management**
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `GET` | `/api/issues` | Get all issues | ✅ |
| `GET` | `/api/issues/:id` | Get specific issue | ✅ |
| `POST` | `/api/issues` | Create new issue | ✅ |
| `PATCH` | `/api/issues/:id` | Update issue status | ✅ (Admin) |

### **Notices Management**
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `GET` | `/api/notices` | Get active notices | ❌ |
| `GET` | `/api/notices/all` | Get all notices | ✅ (Admin) |
| `POST` | `/api/notices` | Create notice | ✅ (Admin) |
| `PUT` | `/api/notices/:id` | Update notice | ✅ (Admin) |
| `DELETE` | `/api/notices/:id` | Delete notice | ✅ (Admin) |

## 🔄 Issue Status Workflow

1. **🆕 New** - Newly reported issues (default status)
2. **⏳ In Progress** - Issues currently being worked on
3. **✅ Resolved** - Completed/fixed issues

## 💻 Technology Stack

### **Backend**
- **Runtime**: Node.js v18+
- **Framework**: Express.js v4.18+
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JSON Web Tokens (JWT)
- **File Upload**: Multer + Cloudinary
- **Security**: bcryptjs, CORS
- **Environment**: dotenv

### **Frontend (Client)**
- **Framework**: React v19+ with Hooks
- **Build Tool**: Vite v6+
- **Routing**: React Router DOM v6+
- **HTTP Client**: Axios
- **Maps**: Leaflet + React-Leaflet
- **Styling**: Modern CSS3 with CSS Variables
- **State Management**: React Context API

### **Frontend (Admin)**
- **Framework**: React v19+ with Hooks
- **Build Tool**: Vite v6+
- **Routing**: React Router DOM v6+
- **HTTP Client**: Axios
- **Maps**: Leaflet + React-Leaflet
- **Styling**: Enhanced CSS3 with Modern Design System
- **Charts**: Custom chart components

### **Development Tools**
- **Linting**: ESLint v9+
- **Package Manager**: npm
- **Version Control**: Git
- **Development Server**: Vite Dev Server with HMR

## 🎨 Design Features

### **Modern UI/UX**
- **🎨 Glass Morphism Effects** - Modern frosted glass design elements
- **🌈 Gradient System** - Beautiful color gradients throughout
- **✨ Smooth Animations** - Micro-interactions and transitions
- **📱 Mobile-First Design** - Responsive across all devices
- **🎯 Interactive Elements** - Hover effects and visual feedback
- **♿ Accessibility** - WCAG compliant design patterns

### **Component System**
- **🎴 Modern Cards** - Elevated card designs with shadows
- **🔘 Enhanced Buttons** - Multiple variants with animations
- **📝 Smart Forms** - Advanced validation and error handling
- **🗺️ Interactive Maps** - Custom markers and popups
- **📊 Data Visualization** - Charts and statistics
- **🔔 Notification System** - Toast notifications and alerts

## 🔐 Authentication System

### **User Authentication**
- **Registration**: Email-based signup with validation
- **Login**: Secure JWT token authentication
- **Session Management**: Persistent login with localStorage
- **Password Security**: bcrypt hashing with salt rounds
- **Route Protection**: Private routes requiring authentication

### **Admin Authentication**
- **Role-based Access**: Admin-only routes and features
- **Secure Admin Panel**: Separate authentication flow
- **Permission System**: Different access levels for users vs admins

## 📊 Data Models

### **User Model**
```javascript
{
  username: String (required, unique),
  email: String (required, unique),
  password: String (required, hashed),
  role: String (enum: ['user', 'admin'], default: 'user'),
  createdAt: Date,
  updatedAt: Date
}
```

### **Issue Model**
```javascript
{
  title: String (required),
  description: String (required),
  status: String (enum: ['new', 'in-progress', 'resolved'], default: 'new'),
  priority: String (enum: ['low', 'medium', 'high'], default: 'medium'),
  location: {
    lat: Number (required),
    lng: Number (required),
    address: String
  },
  images: [String], // Cloudinary URLs
  user: ObjectId (ref: 'User', required),
  createdAt: Date,
  updatedAt: Date
}
```

### **Notice Model**
```javascript
{
  title: String (required),
  content: String (required),
  isActive: Boolean (default: true),
  createdBy: ObjectId (ref: 'User', required),
  createdAt: Date,
  updatedAt: Date
}
```

## 🛡️ Security Features

- **🔒 JWT Authentication** - Secure token-based authentication
- **🛡️ Password Hashing** - bcrypt with salt rounds
- **🔐 CORS Protection** - Cross-origin request security
- **✅ Input Validation** - Server-side data validation
- **🚫 XSS Protection** - Cross-site scripting prevention
- **🔑 Environment Variables** - Secure configuration management

## 📱 Responsive Design

- **📱 Mobile-First** - Designed for mobile devices first
- **💻 Desktop Enhanced** - Rich desktop experience
- **📊 Adaptive Layouts** - Content adapts to screen size
- **🎯 Touch-Friendly** - Optimized for touch interactions
- **⚡ Performance** - Optimized loading and rendering

## 🚀 Deployment

### **Production Environment Variables**
```env
NODE_ENV=production
MONGODB_CONNECTION_STRING=your-production-mongodb-url
JWT_SECRET=your-super-secure-production-secret
CLOUDINARY_CLOUD_NAME=your-production-cloudinary-name
CLOUDINARY_API_KEY=your-production-api-key
CLOUDINARY_API_SECRET=your-production-api-secret
```

### **Build Commands**
```bash
# Build client
cd client && npm run build

# Build admin
cd admin && npm run build

# Start production server
cd server && npm start
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For support, email support@cityfix.com or create an issue in the GitHub repository.

## 🎯 Future Enhancements

- **📱 Mobile App** - React Native mobile application
- **🔔 Push Notifications** - Real-time notifications
- **📊 Advanced Analytics** - Detailed reporting and insights
- **🗺️ GPS Integration** - Automatic location detection
- **👥 Community Features** - User interactions and discussions
- **🔍 Advanced Search** - Full-text search capabilities
- **📈 Performance Monitoring** - Application performance metrics

---

**Made with ❤️ for building better communities**
