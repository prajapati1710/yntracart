# YntraCart Setup Guide

## Quick Start

### Prerequisites

- Node.js 18+ and npm
- PostgreSQL 14+
- Redis 6+
- Docker (optional, for containerized setup)

### Step 1: Clone and Install

```bash
# Install root dependencies
npm install

# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

### Step 2: Database Setup

```bash
# Start PostgreSQL and Redis (using Docker)
docker-compose up -d postgres redis meilisearch

# Or install locally and configure
```

### Step 3: Environment Configuration

```bash
# Backend
cd backend
cp .env.example .env
# Edit .env with your configuration

# Frontend
cd ../frontend
cp .env.example .env.local
# Edit .env.local with your configuration
```

### Step 4: Database Migration and Seeding

```bash
cd backend

# Run migrations (if using TypeORM migrations)
npm run migration:run

# Seed database with sample data
npm run seed
```

### Step 5: Start Development Servers

```bash
# From root directory
npm run dev

# Or start separately:
# Terminal 1 - Backend
cd backend
npm run start:dev

# Terminal 2 - Frontend
cd frontend
npm run dev
```

### Step 6: Access the Application

- Frontend: http://localhost:3000
- Backend API: http://localhost:4000/api
- API Documentation: http://localhost:4000/api
- ML Service: http://localhost:8000 (if running)

## Default Credentials

After seeding:

- **Admin:**
  - Email: admin@yntracart.com
  - Password: admin123

- **Sellers:**
  - Email: seller1@yntracart.com (through seller5@yntracart.com)
  - Password: seller123

## Project Structure

```
yntracart/
├── frontend/          # Next.js frontend application
│   ├── src/
│   │   ├── app/      # Next.js app router pages
│   │   ├── components/  # React components
│   │   ├── store/    # Redux store
│   │   ├── lib/      # Utilities and API client
│   │   └── types/    # TypeScript types
│   └── public/       # Static assets
│
├── backend/          # NestJS backend application
│   ├── src/
│   │   ├── auth/     # Authentication module
│   │   ├── users/    # User management
│   │   ├── products/ # Product management
│   │   ├── orders/   # Order management
│   │   ├── sellers/  # Seller management
│   │   ├── admin/    # Admin panel
│   │   ├── support/  # Customer support
│   │   ├── payments/ # Payment processing
│   │   └── database/ # Database config and seeds
│   └── test/         # Backend tests
│
├── ml-service/       # Python FastAPI ML service
│   ├── main.py       # ML service entry point
│   └── requirements.txt
│
└── docs/            # Documentation
    ├── API.md
    ├── DEPLOYMENT.md
    └── SELLER_ONBOARDING.md
```

## Development Workflow

1. **Frontend Development:**
   - Components are in `frontend/src/components/`
   - Pages are in `frontend/src/app/`
   - State management: Redux Toolkit
   - API calls: React Query

2. **Backend Development:**
   - Modules follow NestJS structure
   - Entities in `entities/` folder
   - Services contain business logic
   - Controllers handle HTTP requests

3. **Database:**
   - TypeORM entities define schema
   - Migrations for schema changes
   - Seed script for sample data

## Testing

```bash
# Backend tests
cd backend
npm test

# Frontend tests
cd frontend
npm test

# E2E tests
cd frontend
npm run test:e2e
```

## Building for Production

```bash
# Build frontend
cd frontend
npm run build

# Build backend
cd backend
npm run build

# Or use Docker
docker-compose -f docker-compose.prod.yml build
```

## Troubleshooting

### Database Connection Issues
- Check PostgreSQL is running
- Verify credentials in `.env`
- Ensure database exists

### Port Already in Use
- Change ports in `.env` files
- Kill processes using ports 3000, 4000, 5432, 6379

### Module Not Found Errors
- Run `npm install` in respective directories
- Clear `node_modules` and reinstall

## Next Steps

1. Configure payment gateways (Razorpay/Stripe)
2. Set up AWS S3 for image storage
3. Configure email service (SMTP)
4. Set up Meilisearch for search
5. Configure OAuth providers (Google, Facebook)
6. Set up monitoring and logging

## Support

For issues and questions:
- Check documentation in `/docs`
- Review API docs at `/api` endpoint
- Check GitHub issues

