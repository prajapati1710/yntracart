# YntraCart — Full Dynamic Multi-Vendor Ecommerce Platform

A production-ready, full-stack multi-vendor ecommerce platform similar to Flipkart/Meesho/Glowroad with buyer panel, seller panel, customer support, and admin panel.

## 🎨 Branding

- **Primary Color**: #1DBF39 (Green)
- **Secondary Color**: #FF7A00 (Orange)
- **Accent/Text**: #000000 (Black)
- **Background**: #F4F6F5 (Light Grey)
- **Fonts**: Montserrat (Headings), Poppins (Subheadings), Inter/Roboto (Body)

## 🏗️ Architecture

```
yntracart/
├── frontend/          # Next.js + React + TypeScript + Tailwind
├── backend/           # NestJS + TypeScript + PostgreSQL
├── shared/            # Shared types and utilities
├── ml-service/        # Python FastAPI recommendation service
└── docs/              # Documentation
```

## 🚀 Quick Start

### Prerequisites

- Node.js >= 18.0.0
- PostgreSQL >= 14
- Redis >= 6
- Docker (optional, for containerized deployment)

### Installation

1. **Clone and install dependencies:**
   ```bash
   npm install
   ```

2. **Set up environment variables:**
   ```bash
   cp backend/.env.example backend/.env
   cp frontend/.env.example frontend/.env.local
   ```

3. **Set up database:**
   ```bash
   cd backend
   npm run migration:run
   npm run seed
   ```

4. **Start development servers:**
   ```bash
   npm run dev
   ```

   - Frontend: http://localhost:3000
   - Backend API: http://localhost:4000
   - API Docs: http://localhost:4000/api

## 📁 Project Structure

### Frontend (`/frontend`)
- Next.js 14 with App Router
- TypeScript
- Tailwind CSS
- Redux Toolkit for state management
- React Query for server state
- Headless UI components

### Backend (`/backend`)
- NestJS framework
- TypeScript
- PostgreSQL (via TypeORM)
- Redis (caching & sessions)
- JWT authentication
- Swagger/OpenAPI documentation

### ML Service (`/ml-service`)
- Python FastAPI
- Collaborative filtering
- Product recommendations

## 🔑 Key Features

### Buyer Panel
- ✅ Product browsing & search
- ✅ Category navigation
- ✅ Product details with variants
- ✅ Shopping cart
- ✅ Checkout (guest + authenticated)
- ✅ Order tracking
- ✅ Reviews & ratings
- ✅ Wishlist
- ✅ Wallet & coupons

### Seller Panel
- ✅ Seller registration & KYC
- ✅ Product management (CRUD, bulk upload)
- ✅ Inventory management
- ✅ Order management
- ✅ Analytics dashboard
- ✅ Payout tracking
- ✅ Store settings

### Admin Panel
- ✅ Seller approval workflow
- ✅ Dispute resolution
- ✅ Commission management
- ✅ Category management
- ✅ Site content management
- ✅ Reports & analytics
- ✅ User management

### Customer Support
- ✅ Live chat
- ✅ Ticketing system
- ✅ FAQ management
- ✅ Return/refund processing

## 🔐 Authentication

- JWT with refresh tokens
- OAuth (Google, Facebook)
- Role-based access control (Buyer, Seller, Admin, Support)

## 💳 Payments

- Razorpay integration
- Stripe integration (configurable)
- Multiple payment methods (UPI, Cards, Wallets, NetBanking)
- Auto-settlement to sellers

## 🔍 Search & Discovery

- Full-text search with typo tolerance
- Faceted filters
- Product recommendations (ML-based)
- Trending products

## 📦 Shipping

- Configurable carrier integration
- Rate calculation by weight/dimensions
- COD support
- Tracking updates

## 🧪 Testing

- Unit tests (Jest)
- E2E tests (Playwright)
- API tests (Postman/Newman)
- Load testing (k6)

## 🚢 Deployment

See [DEPLOYMENT.md](./docs/DEPLOYMENT.md) for detailed deployment instructions.

### Docker Deployment

```bash
docker-compose up -d
```

### CI/CD

GitHub Actions workflows included for automated testing and deployment.

## 📚 Documentation

- [API Documentation](./docs/API.md)
- [Database Schema](./docs/DATABASE.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)
- [Seller Onboarding](./docs/SELLER_ONBOARDING.md)

## 🤝 Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 📄 License

This project is licensed under the MIT License.

## 👥 Team

Built with ❤️ for modern ecommerce.

