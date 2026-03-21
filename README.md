# Payment Transaction System

This project is a Node.js-based backend for a payment transaction system. It provides APIs for user authentication, account management, and transaction processing, with a modular structure for scalability and maintainability.

## Project Structure

```
project-root/
│
├── package.json           # Project metadata and dependencies
├── server.js              # Entry point for the server
└── src/
    ├── app.js             # Main Express app setup
    ├── config/
    │   └── db.js          # Database connection configuration
    ├── controllers/       # Route handler logic
    │   ├── account.controller.js
    │   ├── auth.controller.js
    │   └── transaction.controller.js
    ├── middleware/        # Express middleware
    │   └── auth.middleware.js
    ├── models/            # Mongoose models (MongoDB schemas)
    │   ├── account.model.js
    │   ├── blackList.model.js
    │   ├── ledger.model.js
    │   ├── transaction.model.js
    │   └── user.model.js
    ├── routes/            # API route definitions
    │   ├── account.routes.js
    │   ├── auth.routes.js
    │   └── transaction.routes.js
    └── services/          # Business logic/services
        └── email.service.js
```

## File/Folder Explanations

- **package.json**: Lists project dependencies, scripts, and metadata.
- **server.js**: Starts the Express server and connects to the database.
- **src/app.js**: Sets up the Express app, middleware, and routes.
- **src/config/db.js**: Handles MongoDB connection using Mongoose.
- **src/controllers/**: Contains logic for handling API requests:
  - `account.controller.js`: Account-related operations (create, update, etc.)
  - `auth.controller.js`: User authentication (login, register, etc.)
  - `transaction.controller.js`: Handles payment transactions.
- **src/middleware/auth.middleware.js**: Middleware for authentication (e.g., JWT verification).
- **src/models/**: Mongoose schemas for MongoDB collections:
  - `account.model.js`: Account data structure.
  - `blackList.model.js`: Stores blacklisted tokens (for logout, etc.).
  - `ledger.model.js`: Ledger entries for transactions.
  - `transaction.model.js`: Transaction data structure.
  - `user.model.js`: User data structure.
- **src/routes/**: Express route definitions, mapping endpoints to controllers.
- **src/services/email.service.js**: Handles email sending (e.g., notifications).

## How It Works

1. **Server Startup**: `server.js` initializes the Express app and connects to MongoDB.
2. **Routing**: Requests are routed via files in `src/routes/` to the appropriate controller.
3. **Controllers**: Controllers process requests, interact with models, and return responses.
4. **Models**: Mongoose models define the structure of data in MongoDB.
5. **Middleware**: Authentication middleware protects routes as needed.
6. **Services**: Business logic (like sending emails) is handled in the `services` folder.

## Main Features
- User registration and authentication (JWT-based)
- Account management (CRUD)
- Payment transaction processing
- Email notifications
- Token blacklisting for secure logout

## Getting Started

1. **Install dependencies:**
   ```bash
   npm install
   ```
2. **Configure environment:**
   - Set up your MongoDB URI and other environment variables as needed.
3. **Run the server:**
   ```bash
   npm start
   ```

## Notes
- The project uses Express.js for the server and Mongoose for MongoDB interaction.
- All business logic is separated into controllers and services for maintainability.
- Authentication is handled via JWT tokens, with blacklisting for logout security.

---

For more details, review the code in each folder as described above.