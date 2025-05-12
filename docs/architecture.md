# MicroMarket Architecture Documentation

## Overview
MicroMarket uses a microservices architecture to provide scalability, maintainability, and separation of concerns. Each service is independently deployable and handles specific business domains.

## System Architecture

### High-Level Architecture Diagram
```
                  ┌──────────────┐
                  │   Frontend   │
          ┌───────┤  Client App  ├─────┐
          │       │   (3000)     │     │
          │       └──────────────┘     │
          │                            │
          │       ┌──────────────┐     │
          │       │    Admin     │     │
          │       │ Dashboard    │     │
          └───────┤   (3006)     ├─────┘
                  └──────────────┘
                         │
                         ▼
                  ┌──────────────┐
                  │ API Gateway  │
                  │   (3100)     │
                  └──────────────┘
                         │
            ┌───────────┼───────────┐
            │           │           │
            ▼           ▼           ▼
    ┌──────────┐ ┌──────────┐ ┌──────────┐
    │Service-1 │ │Service-2 │ │Service-3 │
    │Auth/File │ │ Orders   │ │Products  │
    │ (3001)   │ │ (3002)   │ │ (3003)   │
    └────┬─────┘ └────┬─────┘ └────┬─────┘
         │            │            │
         ▼            ▼            ▼
    ┌──────────┐ ┌──────────┐ ┌──────────┐
    │Firebase  │ │ PayPal   │ │ MongoDB  │
    │Storage   │ │   API    │ │          │
    └──────────┘ └──────────┘ └──────────┘
```

## Service Descriptions

### 1. API Gateway (Port: 3100)
- **Responsibility**: Request routing, authentication, load balancing
- **Technologies**: Express.js, JWT
- **Key Features**:
  - Request routing to appropriate services
  - JWT token validation
  - API rate limiting
  - Request/Response logging

### 2. Service-1: Authentication & File Service (Port: 3001)
- **Responsibility**: User management, file handling
- **Technologies**: Node.js, MongoDB, Firebase Storage
- **Key Features**:
  - User authentication
  - File upload/download
  - Profile management
  - Token management

### 3. Service-2: Order Management (Port: 3002)
- **Responsibility**: Order processing
- **Technologies**: Node.js, MongoDB, Nodemailer
- **Key Features**:
  - Order creation/management
  - Payment processing
  - Email notifications
  - Order tracking

### 4. Service-3: Product Management (Port: 3003)
- **Responsibility**: Product catalog
- **Technologies**: Node.js, MongoDB
- **Key Features**:
  - Product CRUD operations
  - Category management
  - Inventory tracking
  - Product search

### 5. Frontend Applications
#### Admin Dashboard (Port: 3006)
- **Technology**: React.js, Ant Design
- **Features**:
  - Product management interface
  - Order management
  - User management
  - Analytics dashboard

#### Client Application (Port: 3000)
- **Technology**: React.js, Ant Design
- **Features**:
  - Product browsing
  - Shopping cart
  - User profile
  - Order tracking

## Data Flow

### Authentication Flow
1. Client sends login request to API Gateway
2. Gateway forwards to Service-1
3. Service-1 validates credentials
4. JWT token returned through Gateway
5. Client stores token for subsequent requests

### Order Processing Flow
1. Client sends order request
2. API Gateway validates token
3. Request forwarded to Service-2
4. Service-2 processes order
5. Email notification sent
6. Order confirmation returned

### File Upload Flow
1. Client initiates file upload
2. API Gateway authenticates request
3. Service-1 handles file
4. File uploaded to Firebase Storage
5. URL returned to client

## Database Schema

### Users Collection
```json
{
  "_id": "ObjectId",
  "username": "String",
  "email": "String",
  "password": "String",
  "role": "String",
  "createdAt": "Date"
}
```

### Products Collection
```json
{
  "_id": "ObjectId",
  "name": "String",
  "price": "Number",
  "description": "String",
  "imageUrl": "String",
  "category": "String",
  "stock": "Number"
}
```

### Orders Collection
```json
{
  "_id": "ObjectId",
  "userId": "ObjectId",
  "products": ["Array"],
  "total": "Number",
  "status": "String",
  "createdAt": "Date"
}
```

## Security Considerations
1. JWT token validation
2. API rate limiting
3. File upload restrictions
4. Role-based access control
5. Environment variable protection
6. MongoDB security best practices

## Scalability
- Independent service scaling
- MongoDB replication
- Load balancing
- Caching strategies
- Firebase Storage for files

## Monitoring
- Service health checks
- Error logging
- Performance metrics
- User activity tracking
- Resource utilization

## Deployment
- Docker containerization
- Environment configuration
- Service discovery
- Database backup
- Continuous integration/deployment
