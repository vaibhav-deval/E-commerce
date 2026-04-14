# 🛍️ E-Commerce Platform

A full-stack, production-ready e-commerce platform built with the **MERN** stack (MongoDB, Express, React, Node.js). This project demonstrates modern web development practices with a responsive UI, secure payment integration, and comprehensive admin management system.

[![React](https://img.shields.io/badge/React-19.0-blue?logo=react)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-Express-green?logo=node.js)](https://nodejs.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-8.13-green?logo=mongodb)](https://www.mongodb.com)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0-38B2AC?logo=tailwind-css)](https://tailwindcss.com)
[![License](https://img.shields.io/badge/License-ISC-blue)](LICENSE)

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Usage Guide](#usage-guide)
- [Key Functionalities](#key-functionalities)
- [Screenshots](#screenshots)
- [Performance & Security](#performance--security)
- [Contributing](#contributing)
- [License](#license)

---

## ✨ Features

### 👥 **Customer Features**
- ✅ User authentication with JWT-based security
- ✅ Product browsing with search and filtering capabilities
- ✅ Dynamic product catalog with categories and subcategories
- ✅ Shopping cart with real-time updates
- ✅ Secure checkout process
- ✅ Multiple payment methods (Razorpay, Stripe integration)
- ✅ Order tracking and history
- ✅ Responsive design (Mobile, Tablet, Desktop)
- ✅ User account management

### 🛡️ **Admin Features**
- ✅ Secure admin login and authentication
- ✅ Product management (Create, Read, Update, Delete)
- ✅ Product image upload via Cloudinary
- ✅ Order management and status tracking
- ✅ Inventory management
- ✅ Real-time order notifications
- ✅ Admin dashboard with sidebar navigation

### 🔧 **Technical Features**
- ✅ RESTful API architecture
- ✅ JWT token-based authentication
- ✅ Password encryption with Bcrypt
- ✅ CORS enabled for cross-origin requests
- ✅ Error handling and validation
- ✅ Environment variable configuration
- ✅ Modular and scalable code structure

---

## 🛠 Tech Stack

### **Frontend (Customer)**
| Technology | Purpose |
|-----------|---------|
| **React 19** | UI framework |
| **Vite 6** | Build tool & dev server |
| **Tailwind CSS 4** | Styling & responsive design |
| **React Router 7** | Client-side routing |
| **Axios** | HTTP client for API calls |
| **React Toastify** | Notifications & alerts |

### **Admin Panel**
| Technology | Purpose |
|-----------|---------|
| **React 19** | UI framework |
| **Vite 6** | Build tool |
| **Tailwind CSS 4** | UI styling |
| **React Router 7** | Navigation |
| **Axios** | API communication |

### **Backend**
| Technology | Purpose |
|-----------|---------|
| **Node.js & Express 5** | Server framework |
| **MongoDB 8** | NoSQL database |
| **Mongoose** | MongoDB ODM |
| **JWT** | Authentication |
| **Bcrypt** | Password hashing |
| **Multer** | File upload handling |
| **Cloudinary** | Cloud image storage |
| **Razorpay** | Payment gateway |
| **Stripe** | Payment processing |
| **Dotenv** | Environment management |

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    E-COMMERCE PLATFORM                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────┐ │
│  │   Frontend       │  │   Admin Panel    │  │   Backend    │ │
│  │   (Customer)     │  │   (Manager)      │  │   (API)      │ │
│  │                  │  │                  │  │              │ │
│  │  - Home          │  │  - Login         │  │  - Routes    │ │
│  │  - Collection    │  │  - Add Products  │  │  - Models    │ │
│  │  - Product       │  │  - List Products │  │  - Controllers
│  │  - Cart          │  │  - Order Mgmt    │  │  - Middleware│
│  │  - Checkout      │  │  - Dashboard     │  │  - Config    │
│  │  - Orders        │  │                  │  │              │ │
│  └──────────────────┘  └──────────────────┘  └──────────────┘ │
│          │                    │                      │          │
│          └────────────────────┴──────────────────────┘          │
│                        │                                        │
│                   Axios (HTTP)                                 │
│                        │                                        │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │             REST API Endpoints                          │  │
│  │  /api/user   /api/product   /api/cart   /api/order      │  │
│  └──────────────────────────────────────────────────────────┘  │
│                        │                                        │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │              MongoDB Database                           │  │
│  │  Users | Products | Orders | Cart Data                 │  │
│  └──────────────────────────────────────────────────────────┘  │
│                                                                 │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │        External Services                                │  │
│  │  Cloudinary (Images) | Razorpay/Stripe (Payments)     │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v16+ recommended) - [Download](https://nodejs.org)
- **npm** or **yarn** package manager
- **MongoDB** (local or Atlas cloud database) - [Setup Guide](https://www.mongodb.com/docs/manual/installation/)
- **Git** for version control

### Required Accounts & API Keys:
- [Cloudinary](https://cloudinary.com) - Image hosting
- [Razorpay](https://razorpay.com) - Payment gateway (Optional)
- [Stripe](https://stripe.com) - Payment processing (Optional)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) - Cloud database

---

## 📦 Installation & Setup

### **1. Clone the Repository**

```bash
git clone https://github.com/yourusername/e-commerce.git
cd e-commerce
```

### **2. Backend Setup**

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
PORT=4000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET_KEY=your_cloudinary_secret
JWT_SECRET=your_jwt_secret_key
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_SECRET=your_razorpay_secret
STRIPE_SECRET_KEY=your_stripe_secret
EOF

# Start the server
npm run server  # For development with nodemon
# OR
npm start      # For production
```

**Server runs on:** `http://localhost:4000`

---

### **3. Frontend Setup (Customer)**

```bash
# Navigate to frontend directory (from root)
cd frontend

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
VITE_BACKEND_URL=http://localhost:4000
EOF

# Start development server
npm run dev
```

**Frontend runs on:** `http://localhost:5173`

---

### **4. Admin Panel Setup**

```bash
# Navigate to admin directory (from root)
cd admin

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
VITE_BACKEND_URL=http://localhost:4000
EOF

# Start development server
npm run dev
```

**Admin panel runs on:** `http://localhost:5174` (or next available port)

---

## 🔐 Environment Variables

### **Backend (.env)**

```env
# Server Configuration
PORT=4000
NODE_ENV=development

# Database
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net

# Authentication
JWT_SECRET=your_super_secure_jwt_secret_key_min_32_chars

# Image Storage (Cloudinary)
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET_KEY=your_cloudinary_secret_key

# Payment Gateway (Razorpay)
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_SECRET=your_razorpay_secret_key

# Payment Processing (Stripe)
STRIPE_SECRET_KEY=your_stripe_secret_key
```

### **Frontend & Admin (.env)**

```env
VITE_BACKEND_URL=http://localhost:4000
```

---

## 📁 Project Structure

```
e-commerce/
│
├── backend/                          # Node.js & Express API
│   ├── config/
│   │   ├── mongodb.js               # MongoDB connection
│   │   └── cloudinary.js            # Cloudinary setup
│   ├── controllers/                 # Business logic
│   │   ├── userController.js        # User operations
│   │   ├── productController.js     # Product management
│   │   ├── cartController.js        # Cart operations
│   │   └── orderController.js       # Order processing
│   ├── middleware/
│   │   ├── auth.js                  # JWT authentication
│   │   ├── adminAuth.js             # Admin verification
│   │   └── multer.js                # File upload handling
│   ├── models/                      # Database schemas
│   │   ├── userModel.js
│   │   ├── productModel.js
│   │   └── orderModel.js
│   ├── routes/                      # API endpoints
│   │   ├── userRoute.js
│   │   ├── productRoute.js
│   │   ├── cartRoute.js
│   │   └── orderRoute.js
│   ├── server.js                    # Main server file
│   └── package.json
│
├── frontend/                        # React customer application
│   ├── src/
│   │   ├── components/             # Reusable components
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── CartTotal.jsx
│   │   │   ├── ProductItem.jsx
│   │   │   └── ...
│   │   ├── pages/                  # Page components
│   │   │   ├── Home.jsx
│   │   │   ├── Product.jsx
│   │   │   ├── Collection.jsx
│   │   │   ├── Cart.jsx
│   │   │   ├── PlaceOrder.jsx
│   │   │   └── ...
│   │   ├── context/                # React Context
│   │   │   └── ShopContext.jsx     # Global state management
│   │   ├── assets/                 # Static resources
│   │   ├── App.jsx                 # Root component
│   │   └── index.css
│   ├── vite.config.js
│   ├── package.json
│   └── index.html
│
├── admin/                          # React admin dashboard
│   ├── src/
│   │   ├── components/
│   │   │   ├── Login.jsx           # Admin login
│   │   │   ├── Navbar.jsx
│   │   │   └── Sidebar.jsx
│   │   ├── pages/
│   │   │   ├── Add.jsx             # Add products
│   │   │   ├── List.jsx            # Product listing
│   │   │   └── Order.jsx           # Order management
│   │   ├── App.jsx
│   │   └── index.css
│   ├── vite.config.js
│   ├── package.json
│   └── index.html
│
└── README.md                        # This file
```

---

## 📡 API Endpoints

### **User Routes** (`/api/user`)

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/register` | Register new user | ❌ |
| POST | `/login` | User login | ❌ |

### **Product Routes** (`/api/product`)

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/list` | Get all products | ❌ |
| GET | `/single/:id` | Get product details | ❌ |
| POST | `/add` | Add new product | ✅ Admin |
| POST | `/remove` | Delete product | ✅ Admin |

### **Cart Routes** (`/api/cart`)

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/add` | Add to cart | ✅ User |
| POST | `/remove` | Remove from cart | ✅ User |
| POST | `/get` | Get user cart | ✅ User |

### **Order Routes** (`/api/order`)

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/place` | Place new order | ✅ User |
| POST | `/userorders` | Get user orders | ✅ User |
| POST | `/list` | Get all orders | ✅ Admin |
| POST | `/status` | Update order status | ✅ Admin |

---

## 🚀 Usage Guide

### **For Customers:**

1. **Register/Login**
   - Navigate to `/login`
   - Create an account or sign in with existing credentials

2. **Browse Products**
   - Visit `/collection` to view all products
   - Use search functionality to find specific items
   - Filter by category and subcategory

3. **Add to Cart**
   - Click on a product to view details
   - Select size and quantity
   - Click "Add to Cart"

4. **Checkout**
   - Go to cart (`/cart`)
   - Review items and proceed to checkout
   - Fill in delivery address
   - Choose payment method (Razorpay/Stripe or COD)
   - Complete payment

5. **Track Orders**
   - Visit `/order` to see order history
   - Monitor order status in real-time

### **For Admins:**

1. **Login to Admin Panel**
   - Access `/login` on admin portal
   - Use admin credentials

2. **Add Products**
   - Navigate to `/add`
   - Fill product details
   - Upload images
   - Set prices and categories

3. **Manage Inventory**
   - View product list at `/list`
   - Edit or delete products as needed
   - Monitor bestsellers

4. **Process Orders**
   - Check `/orders` for new orders
   - Update order status (pending, processing, shipped, delivered)
   - View order details and customer info

---

## 🎯 Key Functionalities

### **Authentication & Security**
- JWT-based stateless authentication
- Password encryption using Bcrypt
- Admin authentication middleware
- Token refresh mechanism

### **Product Management**
- Dynamic product catalog with multiple categories
- Product images stored on Cloudinary
- Size and variant support
- Bestseller tracking

### **Shopping Experience**
- Real-time cart updates
- Persistent cart storage
- Search and filter functionality
- Responsive design for all devices

### **Order Processing**
- Secure checkout process
- Multiple payment gateways integrated
- Order tracking and history
- Admin order management system

### **Performance Optimizations**
- Lazy loading of components
- Optimized images via Cloudinary
- Efficient API calls with Axios
- MongoDB indexing for faster queries

---

## 🔒 Performance & Security

### **Security Measures**
- ✅ JWT token validation on protected routes
- ✅ Password hashing with Bcrypt (salt rounds: 10)
- ✅ CORS configuration for API safety
- ✅ Input validation using validator library
- ✅ Environment variables for sensitive data
- ✅ Secure payment gateway integration

### **Performance Features**
- ✅ Vite for fast build times
- ✅ React Router for efficient client-side routing
- ✅ Cloudinary image optimization
- ✅ MongoDB query optimization
- ✅ Gzip compression enabled
- ✅ Asset minification in production builds

---

## 📊 Future Enhancements

- [ ] Email notifications for orders
- [ ] Advanced analytics dashboard
- [ ] Wishlist functionality
- [ ] Product reviews and ratings
- [ ] Coupon and discount codes
- [ ] Multi-currency support
- [ ] Inventory alerts
- [ ] Order refund management
- [ ] Dark mode UI
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### **Contribution Guidelines**
- Follow the existing code style
- Add comments for complex logic
- Test your changes before submitting
- Update README if adding new features

---

## 📝 License

This project is licensed under the **ISC License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author & Contact

**Created by:** [Your Name](https://github.com/yourusername)

**Connect with me:**
- 📧 Email: your.email@example.com
- 🔗 LinkedIn: [Your LinkedIn Profile](https://linkedin.com/in/yourprofile)
- 🐙 GitHub: [@yourusername](https://github.com/yourusername)
- 🌐 Portfolio: [Your Portfolio](https://yourportfolio.com)

---

## 🙏 Acknowledgments

- React Team for the amazing library
- Tailwind CSS for utility-first styling
- MongoDB documentation
- Express.js community
- All open-source contributors

---

## 📞 Support

If you have any questions or need help, please:

1. Check the [FAQs](#frequently-asked-questions) section
2. Review existing GitHub Issues
3. Create a new Issue with detailed description
4. Contact via email

---

## 🎓 Learning Resources

This project is built with best practices in mind. Here are some resources that helped:

- [React Official Documentation](https://react.dev)
- [Node.js Best Practices](https://nodejs.org/docs)
- [MongoDB University](https://university.mongodb.com)
- [RESTful API Design](https://restfulapi.net)
- [Web Security Academy](https://portswigger.net/web-security)

---

**⭐ If you found this project helpful, please consider giving it a star! It helps others discover it.**

---

<div align="center">

Made with ❤️ by [Your Name]

**Last Updated:** April 2026

</div>
