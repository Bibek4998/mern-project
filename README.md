# 🛍️ Full-Stack E-Commerce Platform

A modern, feature-rich e-commerce application with secure authentication, payment processing, and admin dashboard.

![Project Screenshot](/frontend/public/screenshot-for-readme.png)

## 🚀 Live Demo
- **Live URL:** [Your Live URL Here]
- **Admin Demo:** [Admin Demo URL]
- **Video Tutorial:** [Watch on YouTube](https://youtu.be/sX57TLIPNx8)

## ✨ Features

### 👤 User Features
- User registration & login with JWT authentication
- Product browsing & search functionality
- Shopping cart management
- Secure checkout with Stripe payments
- Order history & tracking
- Coupon code application

### 🛒 Product Management
- Product catalog with categories
- Product details with images
- Product reviews & ratings
- Stock management
- Featured products

### 👑 Admin Dashboard
- Sales analytics & reports
- Product CRUD operations
- Order management
- User management
- Coupon code generation
- Revenue tracking

### 🔒 Security Features
- JWT with refresh/access tokens
- Password encryption
- Secure payment processing
- Input validation & sanitization
- Rate limiting

## 🛠️ Tech Stack

**Frontend:**
- React.js
- Tailwind CSS
- Axios
- React Router
- Context API / Redux

**Backend:**
- Node.js
- Express.js
- MongoDB
- Redis (Upstash)
- JWT
- Stripe API

**Services:**
- Cloudinary (Image storage)
- Stripe (Payments)
- Upstash Redis (Caching)

# 1. Clone and enter project
git clone https://github.com/yourusername/ecommerce-store.git
cd ecommerce-store

# 2. Install backend dependencies
cd backend
npm install

# 3. Create backend .env file
cat > .env << EOF
PORT=5000
MONGO_URI=your_mongodb_connection_string
UPSTASH_REDIS_URL=your_upstash_redis_url
ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
STRIPE_SECRET_KEY=your_stripe_secret_key
CLIENT_URL=http://localhost:3000
NODE_ENV=development
EOF

# 4. Install frontend dependencies
cd ../frontend
npm install

# 5. Create frontend .env file
cat > .env << EOF
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_STRIPE_PUBLIC_KEY=your_stripe_public_key
EOF

# 6. Run development mode (open in two terminals)

# Terminal 1 - Backend:
cd backend && npm run dev

# Terminal 2 - Frontend:
cd frontend && npm start

# 7. OR run production build:
cd frontend && npm run build && cd ../backend && npm start

# 8. Access URLs:
echo "Frontend: http://localhost:3000"
echo "Backend API: http://localhost:5000"

# 9. Common troubleshooting:
# Clear ports if occupied:
sudo lsof -i :5000 && sudo kill -9 PID
sudo lsof -i :3000 && sudo kill -9 PID

# 10. Reset everything:
cd backend && rm -rf node_modules package-lock.json
cd ../frontend && rm -rf node_modules package-lock.json
npm cache clean --force
cd ../backend && npm install
cd ../frontend && npm install

# 11. Test everything is working:
curl http://localhost:5000/api/health
curl http://localhost:3000

# 12. Build and run production:
cd frontend && npm run build
cp -r build ../backend/public
cd ../backend && npm start
