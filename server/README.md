# Fintech App - Backend (Server)

This directory contains the Node.js backend API server for the fintech application.

## Tech Stack

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **TypeScript** - Type safety
- **PostgreSQL** - Primary database
- **Redis** - Caching and session storage
- **Firebase Admin SDK** - Authentication verification
- **Prisma** - Database ORM
- **Socket.io** - Real-time communication
- **JWT** - Token-based authentication
- **bcrypt** - Password hashing
- **Joi** - Input validation
- **Winston** - Logging
- **Helmet** - Security middleware
- **CORS** - Cross-origin resource sharing

## Project Structure

```
server/
├── src/
│   ├── controllers/     # Route handlers
│   │   ├── auth.controller.ts
│   │   ├── user.controller.ts
│   │   ├── banking.controller.ts
│   │   ├── business.controller.ts
│   │   ├── trading.controller.ts
│   │   └── ai.controller.ts
│   ├── middleware/      # Custom middleware
│   │   ├── auth.middleware.ts
│   │   ├── validation.middleware.ts
│   │   ├── error.middleware.ts
│   │   └── rateLimit.middleware.ts
│   ├── models/          # Database models
│   │   ├── user.model.ts
│   │   ├── account.model.ts
│   │   ├── transaction.model.ts
│   │   └── portfolio.model.ts
│   ├── routes/          # API routes
│   │   ├── auth.routes.ts
│   │   ├── user.routes.ts
│   │   ├── banking.routes.ts
│   │   ├── business.routes.ts
│   │   ├── trading.routes.ts
│   │   └── ai.routes.ts
│   ├── services/        # Business logic
│   │   ├── auth.service.ts
│   │   ├── banking.service.ts
│   │   ├── trading.service.ts
│   │   ├── ai.service.ts
│   │   └── notification.service.ts
│   ├── utils/           # Utility functions
│   │   ├── logger.ts
│   │   ├── encryption.ts
│   │   ├── validation.ts
│   │   └── constants.ts
│   ├── config/          # Configuration files
│   │   ├── database.ts
│   │   ├── redis.ts
│   │   ├── firebase.ts
│   │   └── gemini.ts
│   ├── types/           # TypeScript type definitions
│   │   ├── auth.types.ts
│   │   ├── banking.types.ts
│   │   └── api.types.ts
│   └── app.ts           # Express app setup
├── prisma/
│   ├── schema.prisma    # Database schema
│   └── migrations/      # Database migrations
├── tests/
│   ├── unit/
│   └── integration/
├── package.json
├── tsconfig.json
├── nodemon.json
└── server.ts        # Entry point
```

## Setup Instructions

### Prerequisites

- Node.js (v18 or higher)
- PostgreSQL (v14 or higher)
- Redis (v6 or higher)
- npm or yarn

### Installation

1. Navigate to the server directory:
   ```bash
   cd server
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

3. Set up environment variables:
   ```bash
   cp ../.env.sample .env
   ```

4. Update the `.env` file with your configuration:
   - Database credentials
   - Firebase service account key
   - Gemini AI API key
   - JWT secret
   - Redis connection details

5. Set up the database:
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

6. Seed the database (optional):
   ```bash
   npm run seed
   ```

### Development

1. Start the development server:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

2. The server will start on `http://localhost:3000`

3. API documentation will be available at `http://localhost:3000/api-docs`

### Building for Production

1. Build the application:
   ```bash
   npm run build
   # or
   yarn build
   ```

2. Start the production server:
   ```bash
   npm start
   # or
   yarn start
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh` - Refresh access token
- `POST /api/auth/verify-email` - Email verification
- `POST /api/auth/forgot-password` - Password reset

### Personal Banking
- `GET /api/banking/accounts` - Get user accounts
- `POST /api/banking/transfer` - Transfer money
- `GET /api/banking/transactions` - Get transaction history
- `POST /api/banking/pay-bill` - Pay bills
- `GET /api/banking/budget` - Get budget information

### Business Banking
- `GET /api/business/accounts` - Get business accounts
- `POST /api/business/payroll` - Process payroll
- `GET /api/business/invoices` - Get invoices
- `POST /api/business/invoice` - Create invoice
- `GET /api/business/analytics` - Business analytics

### Trading Simulator
- `GET /api/trading/portfolio` - Get user portfolio
- `POST /api/trading/buy` - Buy stocks
- `POST /api/trading/sell` - Sell stocks
- `GET /api/trading/stocks` - Get stock data
- `GET /api/trading/history` - Trading history

### AI Assistant
- `POST /api/ai/chat` - Chat with AI assistant
- `GET /api/ai/insights` - Get financial insights
- `POST /api/ai/analyze` - Analyze transactions

## Database Schema

The application uses PostgreSQL with Prisma ORM. Key entities include:

- **Users** - User accounts and profiles
- **Accounts** - Bank accounts (personal/business)
- **Transactions** - All financial transactions
- **Portfolios** - Stock trading portfolios
- **Stocks** - Stock information and prices
- **Invoices** - Business invoices
- **Sessions** - User sessions

## Security Features

- **Authentication**: Firebase Auth + JWT tokens
- **Authorization**: Role-based access control
- **Data Encryption**: Sensitive data encryption at rest
- **Rate Limiting**: API rate limiting
- **Input Validation**: Request validation with Joi
- **CORS Protection**: Cross-origin request protection
- **Helmet**: Security headers
- **SQL Injection Prevention**: Prisma ORM protection

## Real-time Features

- **Stock Price Updates**: Real-time stock price streaming
- **Transaction Notifications**: Instant transaction alerts
- **AI Chat**: Real-time chat with AI assistant
- **Account Updates**: Live account balance updates

## Testing

### Unit Tests
```bash
npm run test:unit
```

### Integration Tests
```bash
npm run test:integration
```

### Test Coverage
```bash
npm run test:coverage
```

## Monitoring and Logging

- **Winston**: Structured logging
- **Morgan**: HTTP request logging
- **Health Checks**: `/health` endpoint
- **Metrics**: Application performance metrics

## Environment Variables

Required environment variables for the backend:

```
# Database
DB_HOST=localhost
DB_PORT=5432
DB_NAME=fintech_app
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DATABASE_URL=postgresql://user:password@localhost:5432/fintech_app

# Redis
REDIS_URL=redis://localhost:6379

# Firebase
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_PRIVATE_KEY=your_private_key
FIREBASE_CLIENT_EMAIL=your_client_email

# JWT
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=24h

# Gemini AI
GEMINI_API_KEY=your_gemini_api_key

# Stock API
STOCK_API_KEY=your_stock_api_key

# Server
PORT=3000
NODE_ENV=development
```

## Deployment

### Docker

1. Build the Docker image:
   ```bash
   docker build -t fintech-server .
   ```

2. Run the container:
   ```bash
   docker run -p 3000:3000 fintech-server
   ```

### Production Deployment

1. Set up PostgreSQL and Redis instances
2. Configure environment variables
3. Run database migrations
4. Deploy using your preferred platform (AWS, Heroku, etc.)

## Contributing

1. Create a feature branch
2. Write tests for new features
3. Ensure all tests pass
4. Follow TypeScript and ESLint standards
5. Submit a pull request

## License

This project is licensed under the MIT License.
