# MicroMarket E-commerce Platform

## 📋 Project Overview
MicroMarket is a microservices-based e-commerce platform built with modern technologies. The system consists of multiple services handling different business domains, including authentication, order management, product management, and separate frontend applications for customers and administrators.

## 🏗️ Architecture
```
MicroMarket/
├── api-gateway/               # API Gateway Service
├── Service-1/                # Authentication & File Service
├── Service-2/                # Order Management Service
├── Service-3/                # Product Management Service
├── MicroMarket-Admin/        # Admin Dashboard
└── MicroMarket-Client/       # Client Application
```

## 🚀 Tech Stack

### Backend
- **Node.js & Express.js**: Server runtime and framework
- **MongoDB**: NoSQL database
- **JWT**: Authentication
- **Firebase Storage**: File storage
- **Nodemailer**: Email service

### Frontend
- **React.js**: UI library
- **Ant Design**: UI components
- **Axios**: HTTP client
- **React Router**: Navigation
- **Firebase SDK**: Cloud services

## 📥 Installation

### Prerequisites
- Node.js (v14+)
- MongoDB (v4+)
- npm/yarn
- Git

### Setup Steps

1. **Clone Repository**
```bash
git clone https://github.com/your-username/MicroMarket.git
cd MicroMarket
```

2. **Install Dependencies**
```bash
# API Gateway
cd api-gateway && npm install

# Service-1
cd ../Service-1 && npm install

# Service-2
cd ../Service-2 && npm install

# Service-3
cd ../Service-3 && npm install

# Admin Dashboard
cd ../MicroMarket-Admin && npm install

# Client Application
cd ../MicroMarket-Client && npm install
```

3. **Environment Configuration**
Create `.env` files in each service directory:

```env
# API Gateway
PORT=3100
JWT_ACCESS_KEY=your_secret_key

# Service-1
PORT=3001
MONGODB_URI=mongodb://localhost:27017/micromarket
JWT_SECRET=your_jwt_secret

# Service-2
PORT=3002
MONGODB_URI=mongodb://localhost:27017/micromarket
```

4. **Start Services**
```bash
# Start each service in separate terminals
npm start
```

## 🎯 Features

### Admin Dashboard
- Product Management
- Order Management
- User Management
- Analytics Dashboard
- File Upload System

### Client Application
- Product Browsing
- Shopping Cart
- Checkout Process
- Order Tracking
- User Profiles

## 🔒 Security
- JWT Authentication
- Role-based Access Control
- Secure File Upload
- API Rate Limiting

## 📚 Documentation
Detailed documentation available in `/docs` directory:
- API Documentation
- Architecture Overview
- Development Guide
- Deployment Guide

## 🤝 Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team
- John Doe - Backend Developer
- Jane Smith - Frontend Developer
- Bob Johnson - DevOps Engineer

## 📧 Contact
QiTune1603 - tungonlytop1@gmail.com
Project Link: https://github.com/QTune1603/E-Commerce-Microservice.git