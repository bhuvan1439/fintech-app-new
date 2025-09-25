# Fintech App - Frontend (Client)

This directory contains the React frontend application built with Vite for the fintech app.

## Tech Stack

- **React 18** - Frontend framework
- **Vite** - Build tool and development server
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling framework
- **React Router** - Client-side routing
- **Firebase Auth** - Authentication
- **Zustand** - State management
- **React Query** - Server state management

## Project Structure

```
client/
├── public/              # Static assets
├── src/
│   ├── components/      # Reusable UI components
│   ├── pages/          # Page components
│   │   ├── auth/       # Authentication pages
│   │   ├── personal/   # Personal banking pages
│   │   ├── business/   # Business banking pages
│   │   └── trading/    # Stock trading simulator pages
│   ├── hooks/          # Custom React hooks
│   ├── services/       # API services
│   ├── store/          # Global state management
│   ├── utils/          # Utility functions
│   ├── types/          # TypeScript type definitions
│   └── styles/         # Global styles
├── package.json
├── vite.config.ts
├── tailwind.config.js
└── tsconfig.json
```

## Setup Instructions

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn

### Installation

1. Navigate to the client directory:
   ```bash
   cd client
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

3. Create environment file:
   ```bash
   cp ../.env.sample .env.local
   ```

4. Update the `.env.local` file with your Firebase configuration and API endpoints.

### Development

1. Start the development server:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

2. Open your browser and navigate to `http://localhost:5173`

### Building for Production

1. Build the application:
   ```bash
   npm run build
   # or
   yarn build
   ```

2. The built files will be in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
# or
yarn preview
```

## Features

### Authentication
- Firebase Authentication integration
- Email/password login
- Google OAuth
- Protected routes
- Role-based access control

### Personal Banking Dashboard
- Account overview
- Transaction history
- Money transfer
- Bill payments
- Budgeting tools

### Business Banking Dashboard
- Business account management
- Payroll processing
- Invoice management
- Business analytics
- Multi-user access

### Stock Trading Simulator
- Real-time stock data
- Portfolio management
- Trading simulation
- Performance analytics
- Market news integration

### AI Assistant
- Gemini AI powered chatbot
- Financial advice
- Transaction insights
- Smart notifications

## Code Standards

- Follow TypeScript best practices
- Use functional components with hooks
- Implement proper error boundaries
- Write unit tests for components
- Follow accessibility guidelines (WCAG 2.1)

## Environment Variables

Required environment variables for the frontend:

```
REACT_APP_API_BASE_URL=http://localhost:3000/api
REACT_APP_FIREBASE_API_KEY=your_firebase_api_key
REACT_APP_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
REACT_APP_FIREBASE_PROJECT_ID=your_project_id
```

## Contributing

1. Create a feature branch
2. Make your changes
3. Write/update tests
4. Ensure all tests pass
5. Submit a pull request

## License

This project is licensed under the MIT License.
