# MicroMarket Detailed Project Structure

## Root Directory Structure
```
MicroMarket/
├── api-gateway/
├── Service-1/
├── Service-2/
├── Service-3/
├── MicroMarket-Admin/
├── MicroMarket-Client/
├── docs/
└── README.md
```

## API Gateway Structure
```
api-gateway/
├── app/
│   ├── config/
│   │   └── constant.js
│   ├── controllers/
│   │   └── proxyController.js
│   ├── middlewares/
│   │   ├── auth.middleware.js
│   │   └── rateLimit.middleware.js
│   └── routes/
│       └── index.js
├── package.json
└── server.js
```

## Service-1 (Auth & File) Structure
```
Service-1/
├── app/
│   ├── config/
│   │   ├── constant.js
│   │   ├── database.js
│   │   └── firebase.config.js
│   ├── controllers/
│   │   ├── authController.js
│   │   └── uploadFile.js
│   ├── models/
│   │   └── user.js
│   ├── routes/
│   │   ├── auth.routes.js
│   │   └── upload.routes.js
│   └── utils/
│       └── middleware.js
├── uploads/
├── package.json
└── server.js
```

## Service-2 (Orders) Structure
```
Service-2/
├── app/
│   ├── config/
│   │   ├── constant.js
│   │   └── database.js
│   ├── controllers/
│   │   └── orderController.js
│   ├── models/
│   │   └── order.js
│   ├── routes/
│   │   └── order.routes.js
│   └── services/
│       └── emailService.js
├── package.json
└── server.js
```

## Service-3 (Products) Structure
```
Service-3/
├── app/
│   ├── config/
│   │   ├── constant.js
│   │   └── database.js
│   ├── controllers/
│   │   └── productController.js
│   ├── models/
│   │   └── product.js
│   └── routes/
│       └── product.routes.js
├── package.json
└── server.js
```

## Admin Dashboard Structure
```
MicroMarket-Admin/
├── public/
├── src/
│   ├── apis/
│   │   ├── axiosClient.js
│   │   ├── orderApi.js
│   │   └── productApi.js
│   ├── components/
│   │   ├── Layout/
│   │   ├── PrivateRoute/
│   │   └── Upload/
│   ├── config/
│   │   └── FirebaseConfig.js
│   ├── pages/
│   │   ├── Dashboard/
│   │   ├── Login/
│   │   ├── OrderList/
│   │   └── ProductList/
│   ├── App.js
│   └── index.js
├── package.json
└── README.md
```

## Client Application Structure
```
MicroMarket-Client/
├── public/
├── src/
│   ├── components/
│   │   ├── common/
│   │   ├── layout/
│   │   │   ├── Footer/
│   │   │   └── Header/
│   │   ├── PrivateRoute.js
│   │   └── PublicRoute.js
│   ├── pages/
│   │   ├── Home/
│   │   ├── Product/
│   │   ├── Cart/
│   │   ├── Checkout/
│   │   └── Profile/
│   ├── routers/
│   │   └── routes.js
│   ├── App.js
│   └── index.js
├── package.json
└── README.md
```

## Key Files Description

### API Gateway
- `constant.js`: Configuration constants and environment variables
- `proxyController.js`: Service routing logic
- `auth.middleware.js`: JWT validation middleware

### Service-1
- `firebase.config.js`: Firebase storage configuration
- `authController.js`: Authentication logic
- `uploadFile.js`: File upload handling

### Service-2
- `orderController.js`: Order processing logic
- `emailService.js`: Email notification service
- `order.js`: Order database schema

### Service-3
- `productController.js`: Product management logic
- `product.js`: Product database schema

### Admin Dashboard
- `FirebaseConfig.js`: Firebase client configuration
- `axiosClient.js`: API client configuration
- `PrivateRoute.js`: Authentication route wrapper

### Client Application
- `routes.js`: Application routing configuration
- `PrivateRoute.js`: Protected route component
- `PublicRoute.js`: Public route component

## Dependencies

### Backend Services
```json
{
  "dependencies": {
    "express": "^4.17.1",
    "mongoose": "^6.0.0",
    "jsonwebtoken": "^8.5.1",
    "firebase-admin": "^10.0.0",
    "nodemailer": "^6.7.0",
    "multer": "^1.4.3"
  }
}
```

### Frontend Applications
```json
{
  "dependencies": {
    "react": "^17.0.2",
    "antd": "^4.16.13",
    "axios": "^0.24.0",
    "firebase": "^9.6.0",
    "react-router-dom": "^6.0.0"
  }
}
```