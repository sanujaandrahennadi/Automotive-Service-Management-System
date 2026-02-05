# 🚗 Auto Elite - Automotive Service Management System

A comprehensive **full-stack MERN application** for connecting customers with certified mechanics, featuring advanced ML-powered inventory management, real-time booking, and service coordination.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Machine Learning Integration](#machine-learning-integration)
- [Contributing](#contributing)
- [License](#license)
- [Contact & Support](#contact--support)

## ✨ Features

### Customer Features
- **Service Booking**: Browse and book automotive services with transparent pricing
- **Mechanic Finder**: Locate certified mechanics near you with real-time availability
- **Booking Management**: Track and manage your service bookings
- **Service Tracking**: Real-time updates on service status and mechanics' location
- **Waiting Room**: Real-time updates while waiting for mechanic assignments

### Mechanic Features
- **Profile Management**: Create and manage mechanic profiles with specialties
- **Service Requests**: Receive and respond to service requests in real-time
- **Availability Management**: Control your service schedule and location
- **Job Dashboard**: Track assigned jobs and service history
- **Earnings Tracking**: Monitor completed jobs and ratings

### Admin Features
- **User Management**: Manage customers and mechanics
- **Bookings Management**: Monitor all bookings and generate reports
- **Analytics Dashboard**: View system-wide statistics and insights

### ML Features
- **Inventory Forecasting**: Predictive analytics for parts inventory management
- **Reorder Recommendations**: AI-powered suggestions for parts ordering
- **Dashboard Analytics**: Comprehensive ML-powered insights

## 🛠️ Tech Stack

### Frontend
- **React 18** with Vite
- **Tailwind CSS** for styling
- **React Router** for navigation
- **Material-UI** for components
- **Recharts** for data visualization
- **Socket.io** for real-time updates

### Backend
- **Node.js & Express.js**
- **MongoDB** with Mongoose
- **JWT** for authentication
- **Socket.io** for real-time communication
- **Multer** for file uploads

### ML/AI
- **Python 3.8+**
- **FastAPI** for ML service API
- **Pandas & Scikit-learn** for data processing
- **Prophet** for time series forecasting
- **Joblib** for model serialization

## 📁 Project Structure

```
Automotive-Service-Management-System/
├── client/                          # React frontend
│   ├── src/
│   │   ├── pages/                  # Page components
│   │   ├── components/             # Reusable components
│   │   ├── services/               # API services
│   │   ├── store/                  # State management
│   │   └── api/                    # API client configuration
│   └── package.json
├── server/                          # Express backend
│   ├── src/
│   │   ├── controllers/            # Request handlers
│   │   ├── models/                 # MongoDB models
│   │   ├── routes/                 # API routes
│   │   ├── middleware/             # Custom middleware
│   │   └── services/               # Business logic
│   └── package.json
├── ml/                              # Machine Learning module
│   ├── ml-inventory-system/
│   │   ├── working_ml_service.py   # Main ML service
│   │   ├── requirements.txt        # Python dependencies
│   │   └── integration/            # React component integration
│   └── README.md
└── package.json                     # Root configuration

```

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **Python** (v3.8 or higher)
- **MongoDB** (local or Atlas)
- **Git**

### Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Automotive-Service-Management-System.git
cd Automotive-Service-Management-System
```

#### 2. Install Backend Dependencies

```bash
cd server
npm install
```

#### 3. Install Frontend Dependencies

```bash
cd ../client
npm install
```

#### 4. Install ML Dependencies

```bash
cd ../ml/ml-inventory-system
pip install -r requirements.txt
```

## ⚙️ Configuration

### Backend Setup

Create a `.env` file in the `server` directory:

```env
# Database
MONGODB_URI=mongodb://localhost:27017/autoelite
MONGODB_ATLAS_URI=your_atlas_connection_string

# Server
PORT=5000
NODE_ENV=development

# JWT
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d

# Email (Optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_email_password

# File Upload
MAX_FILE_SIZE=5242880
UPLOAD_PATH=uploads/

# ML Service
ML_SERVICE_URL=http://localhost:8001
```

### Frontend Setup

Create a `.env` file in the `client` directory:

```env
VITE_API_URL=http://localhost:5000
VITE_API_TIMEOUT=10000
```

### ML Service Setup

Create a `.env` file in the `ml/ml-inventory-system` directory:

```env
ML_SERVICE_HOST=localhost
ML_SERVICE_PORT=8001
MONGODB_URI=mongodb://localhost:27017/autoelite
MODEL_RETRAIN_INTERVAL=7
SERVICE_LEVEL=0.95
```

## 🏃 Running the Application

### Start MongoDB

```bash
# Local MongoDB
mongod

# Or use MongoDB Atlas connection string in .env
```

### Start Backend Server

```bash
cd server
npm run dev
# Server runs on http://localhost:5000
```

### Start Frontend Application

```bash
cd client
npm run dev
# Frontend runs on http://localhost:5173
```

### Start ML Service

```bash
cd ml/ml-inventory-system
python working_ml_service.py
# ML service runs on http://localhost:8001
```

### Run All Services (Using Batch Scripts)

**Windows:**
```bash
start-servers.bat
```

**Stop Services:**
```bash
stop-servers.bat
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `POST /api/auth/logout` - Logout

### Bookings
- `GET /api/bookings` - Get all bookings
- `GET /api/bookings/:id` - Get booking details
- `POST /api/bookings` - Create booking
- `PUT /api/bookings/:id` - Update booking
- `DELETE /api/bookings/:id` - Cancel booking

### Mechanics
- `POST /api/mechanics/register` - Register as mechanic
- `GET /api/mechanics/nearby` - Find nearby mechanics
- `GET /api/mechanics/:id` - Get mechanic profile
- `PUT /api/mechanics/:id` - Update mechanic profile

### Services
- `GET /api/services` - Get all services
- `POST /api/services` - Create service
- `GET /api/services/:id` - Get service details

### ML Endpoints
- `GET /api/ml/health` - Check ML service health
- `GET /api/ml/predict` - Get predictions
- `GET /api/ml/reorder-recommendations` - Get reorder suggestions
- `GET /api/ml/dashboard-data` - Get ML dashboard data

## 🤖 Machine Learning Integration

The ML module provides:

### Features
- **Demand Forecasting**: Predict future parts demand
- **Inventory Optimization**: Optimize stock levels
- **Reorder Recommendations**: Automated reorder suggestions
- **Cost Analysis**: Inventory holding cost insights

### Accessing ML Dashboard

Navigate to: `/inventory/ml-dashboard`

The dashboard includes:
- Summary statistics
- Reorder recommendations
- Model performance metrics
- Inventory optimization insights

## 📊 Dashboard Features

### Customer Dashboard
- Booking history
- Service requests status
- Payment tracking
- Mechanic ratings

### Mechanic Dashboard
- Pending requests
- Active jobs
- Service area map
- Earnings summary
- Rating and reviews

### Admin Dashboard
- User management
- Booking analytics
- Financial reports
- System performance

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/Automotive-Service-Management-System.git
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the existing code style
   - Write meaningful commit messages
   - Add comments for complex logic

4. **Test your changes**
   ```bash
   npm test
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Submit a Pull Request**
   - Provide a clear description of changes
   - Reference any related issues

## 📄 License

This project is licensed under the **ISC License** - see the [LICENSE](LICENSE) file for details.

## 📞 Contact & Support

### GitHub
- **Repository**: [GitHub - Automotive Service Management System]( https://github.com/TheekshanaMayadunna/Automotive-Service-Management-System)
- **Issues**: Report bugs and request features via [GitHub Issues](https://github.com/TheekshanaMayadunna/Automotive-Service-Management-System/issues)



## 🔗 Related Documentation

- [ML Inventory System README](ml/ml-inventory-system/README.md)
- [ML Dashboard Integration Guide](ml/ml-inventory-system/integration/ReactComponents/README.md)
- [Server Documentation](server/README.md)
- [Client Documentation](client/README.md)

## 🎯 Roadmap

### Current Features ✅
- User authentication & profiles
- Service booking system
- Real-time mechanic finder
- ML inventory forecasting
- Admin dashboard

### Upcoming Features 🔄
- Mobile app (React Native)
- Payment gateway integration
- Advanced analytics
- Automated notifications
- Video call support

## 💻 System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| RAM | 4GB | 8GB+ |
| Storage | 2GB | 10GB+ |
| CPU | Dual Core | Quad Core+ |
| Node.js | v14 | v18+ |
| Python | 3.8 | 3.10+ |

## 🚨 Troubleshooting

### Common Issues

**MongoDB Connection Error**
```bash
# Check if MongoDB is running
mongod --version

# Start MongoDB service
# Windows: net start MongoDB
# Mac: brew services start mongodb-community
# Linux: sudo systemctl start mongod
```

**Port Already in Use**
```bash
# Change port in .env or
# Kill process using the port
# Windows: netstat -ano | findstr :PORT
# Mac/Linux: lsof -i :PORT
```

**ML Service Not Responding**
```bash
# Check if service is running on port 8001
curl http://localhost:8001/health

# Restart ML service
cd ml/ml-inventory-system
python working_ml_service.py
```

---


