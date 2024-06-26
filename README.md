## Environment Variables
```plaintext
NODE_ENV=development
PORT=4000
MONGO_URL=<your-mongodb-connection-string>
CLOUD_NAME=<your-cloudinary-cloud-name>
CLOUD_API_KEY=<your-cloudinary-api-key>
CLOUD_API_SECRET=<your-cloudinary-api-secret>
JWT_SECRET=<your-jwt-secret>
JWT_EXPIRES_IN=1d


Project Structure
  src/
  
  controllers/: Contains the logic for handling requests and responses for different routes.
  
  middleware/: Custom middleware functions for authentication, error handling, validation, and file uploads.
  
  models/: Mongoose schemas and models for User and Job.
  
  routes/: Defines the express routes for job, user, and authentication functionalities.
  
  utils/: Utility functions for token management, password hashing, and application constants.

  errors/: Custom error classes for handling specific error scenarios.


--------------------------------------------------------------------------------------------------------------------------------------


Main Components
  server.js
  This file sets up the Express server, connects to MongoDB, and configures middleware. It also sets up routes and error handling.

Routes
  /api/v1/auth: Authentication routes for registering, logging in, and logging out users.
  /api/v1/user: User routes for getting the current user, updating user profiles, and accessing admin-specific statistics.
  /api/v1/jobs: Job routes for creating, reading, updating, and deleting job listings, as well as displaying job statistics.
Middleware
  authMiddleware.js: Contains functions for authenticating users, authorizing roles, and checking for test users.
  errorHandlerMiddleware.js: Handles errors and sends appropriate responses.
  validationMiddleware.js: Validates request data for various routes.
  multerMiddleware.js: Configures Multer for handling file uploads.
Models
  User.js: Mongoose schema and model for user data.
  Job.js: Mongoose schema and model for job data.
Utils
  tokenUtils.js: Functions for creating and verifying JWTs.
  passwordUtils.js: Functions for hashing and comparing passwords.
  constants.js: Contains application constants such as job status, type, and sorting options.
Errors
  customErrors.js: Custom error classes for handling NotFoundError, BadRequestError, UnauthenticatedError, and UnauthorizedError.
Controllers
  authController.js: Handles user registration, login, and logout.
  userController.js: Handles fetching the current user, updating user profiles, and getting application statistics.
  jobController.js: Handles CRUD operations for job listings and fetching job statistics.
