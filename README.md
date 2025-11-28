# Expense Tracker

A full-stack expense tracking application built with the MERN stack (MongoDB, Express, React, Node.js) and GraphQL. Track your income, expenses, savings, and investments with an intuitive and modern user interface.

## Features

- 🔐 **User Authentication** - Secure sign up and login with session management
- 💰 **Transaction Management** - Create, update, and delete transactions
- 📊 **Category Statistics** - View statistics by category (saving, expense, investment)
- 💳 **Payment Types** - Track transactions by payment method (cash, card)
- 📅 **Date Tracking** - Record transactions with dates
- 📍 **Location Tracking** - Optional location field for transactions
- 🎨 **Modern UI** - Beautiful interface built with Tailwind CSS and Framer Motion
- 📈 **Data Visualization** - Charts and graphs using Chart.js
- 🔒 **Session Management** - Secure session handling with MongoDB session store

## Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express** - Web framework
- **GraphQL** - API query language
- **Apollo Server** - GraphQL server
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **Passport.js** - Authentication middleware
- **bcryptjs** - Password hashing
- **express-session** - Session management

### Frontend
- **React** - UI library
- **Vite** - Build tool and dev server
- **Apollo Client** - GraphQL client
- **React Router** - Routing
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Chart.js** - Data visualization
- **React Hot Toast** - Notifications

## Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd Expense_tracker
```

2. Install root dependencies:
```bash
npm install
```

3. Install frontend dependencies:
```bash
cd frontend
npm install
cd ..
```

## Environment Variables

Create a `.env` file in the `backend` directory with the following variables:

```env
MONGO_URI=your_mongodb_connection_string
SESSION_SECRET=your_session_secret_key
```

### Example `.env` file:
```env
MONGO_URI=mongodb://localhost:27017/expense_tracker
SESSION_SECRET=your_super_secret_session_key_here
```

For MongoDB Atlas, use:
```env
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/expense_tracker?retryWrites=true&w=majority
```

## Running the Application

### Development Mode

1. Start the backend server:
```bash
npm run dev
```
The backend server will run on `http://localhost:4000`

2. In a new terminal, start the frontend development server:
```bash
cd frontend
npm run dev
```
The frontend will run on `http://localhost:3000` (or the next available port)

### Production Mode

1. Build the frontend:
```bash
cd frontend
npm run build
```

2. Start the backend server:
```bash
npm start
```

## Project Structure

```
Expense_tracker/
├── backend/
│   ├── db/
│   │   └── connectDB.js          # MongoDB connection
│   ├── dummyData/
│   │   └── data.js               # Sample data
│   ├── models/
│   │   ├── transaction.model.js  # Transaction schema
│   │   └── user.model.js         # User schema
│   ├── passport/
│   │   └── passport.config.js   # Passport configuration
│   ├── resolvers/
│   │   ├── index.js              # Resolver exports
│   │   ├── transaction.resolver.js
│   │   └── user.resolver.js
│   ├── typeDefs/
│   │   ├── index.js              # Type definition exports
│   │   ├── transaction.typeDef.js
│   │   └── user.typeDef.js
│   └── index.js                  # Server entry point
├── frontend/
│   ├── src/
│   │   ├── components/           # React components
│   │   │   ├── graphql/          # GraphQL queries & mutations
│   │   │   ├── skeletons/        # Loading skeletons
│   │   │   └── ui/               # UI components
│   │   ├── pages/                # Page components
│   │   ├── utils/                # Utility functions
│   │   ├── App.jsx               # Main app component
│   │   └── main.jsx              # Entry point
│   └── package.json
└── package.json
```

## GraphQL API

The application uses GraphQL for all API operations. The GraphQL endpoint is available at `http://localhost:4000/graphql`.

### User Operations

**Queries:**
- `users` - Get all users
- `authUser` - Get authenticated user
- `user(userId: ID!)` - Get user by ID

**Mutations:**
- `signUp(input: SignUpInput!)` - Create a new user account
- `login(input: LoginInput!)` - Login user
- `logout` - Logout user

### Transaction Operations

**Queries:**
- `transactions` - Get all transactions for authenticated user
- `transaction(transactionId: ID!)` - Get transaction by ID
- `categoryStatistics` - Get statistics grouped by category

**Mutations:**
- `createTransaction(input: CreateTransactionInput!)` - Create a new transaction
- `updateTransaction(input: UpdateTransactionInput!)` - Update a transaction
- `deleteTransaction(transactionId: ID!)` - Delete a transaction

### Transaction Categories
- `saving` - Savings transactions
- `expense` - Expense transactions
- `investment` - Investment transactions

### Payment Types
- `cash` - Cash payments
- `card` - Card payments

## Usage

1. **Sign Up**: Create a new account with username, name, password, and gender
2. **Login**: Sign in with your credentials
3. **Add Transactions**: Create transactions with description, amount, category, payment type, date, and optional location
4. **View Statistics**: See your spending breakdown by category
5. **Manage Transactions**: Update or delete existing transactions

## License

This project is licensed under the ISC License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Author

[Your Name]

---

**Note**: Make sure MongoDB is running before starting the backend server. For local development, you can use MongoDB Compass or start MongoDB as a service.

