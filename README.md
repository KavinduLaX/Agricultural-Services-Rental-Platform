# GoviSaviya — Agricultural Services Rental Platform

GoviSaviya is a web-based agricultural services platform designed to connect farmers with agricultural machinery owners and service providers. It aims to make agricultural service discovery and booking more convenient through a centralized platform.

The system provides a React-based user interface, a REST API built with Node.js and Express, and MongoDB for data persistence.

## Overview

Finding suitable agricultural machinery and service providers can be challenging when information, pricing, and booking arrangements are managed manually. GoviSaviya explores a digital approach to help users discover agricultural services, review provider information, and prepare service bookings through a single platform.

## Features

### Service Discovery
- Browse agricultural service listings.
- View service descriptions, pricing, availability, photos, and service areas.
- Review provider information and ratings when available.
- Search listings using available search functionality.

### User Accounts
- User registration and login interfaces.
- Authentication state management.
- Protected frontend routes for authenticated users.
- Profile management functionality.

### Service Booking
- Select a preferred booking date and time.
- Enter field size in acres.
- Calculate an estimated service cost.
- Include optional booking notes.
- View booking and transaction details returned by the backend.

### Booking Management
- Retrieve service bookings.
- View individual booking details.
- Update booking status and booking information.
- Cancel eligible bookings subject to implemented restrictions.
- Delete eligible completed or cancelled bookings.

### Additional Modules
The application also includes frontend and backend modules for:
- Service-provider management
- Orders and cart
- Discussion forum
- Support tickets and customer service
- Administration
- Product-related functionality in the codebase

The availability and completeness of individual workflows may vary.

## Technology Stack

**Frontend**
- React
- Vite
- React Router
- Tailwind CSS
- Axios
- JavaScript

**Backend**
- Node.js
- Express.js
- MongoDB
- Mongoose
- JSON Web Tokens (JWT)
- bcryptjs
- express-validator
- Multer
- Helmet

**Development Tools**
- Git and GitHub
- npm
- Vite development server

## System Architecture

```text
User
  |
  v
React Frontend
(Vite Development Server)
  |
  | HTTP / REST API
  v
Node.js + Express Backend
  |
  | Mongoose
  v
MongoDB Database
```

The frontend communicates with backend API routes for authentication, service listings, bookings, and other application operations. The backend uses Express middleware and route modules to handle requests.

## Getting Started

### Prerequisites

Install the following before running the project:

- Node.js and npm
- MongoDB instance
- Git

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <PROJECT_FOLDER>
```

### 2. Configure the Backend

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` directory:

```env
MONGODB_URI=your_mongodb_connection_string
PORT=5001
NODE_ENV=development
JWT_SECRET=replace_with_a_strong_random_secret
CORS_ORIGIN=http://localhost:3000
```

Use your own MongoDB connection string and a strong, unique JWT secret. Never commit `.env` files or real credentials to GitHub.

Start the backend:

```bash
npm run dev
```

The backend should run on `http://localhost:5001` with the configuration above.

### 3. Configure the Frontend

Open a second terminal:

```bash
cd frontend
npm install
```

Create `frontend/.env`:

```env
VITE_API_URL=http://localhost:5001/api
```

Start the frontend development server:

```bash
npm run dev
```

Open `http://localhost:3000` in your browser.

**Configuration note:** The frontend contains both relative `/api` requests, which use the Vite proxy, and API requests configured through `VITE_API_URL`. The payment page also contains a hard-coded backend URL. Verify that all API calls use the intended backend port before considering the setup complete.

## Payment Demonstration

The current implementation includes a payment form and a simulated payment workflow. The backend generates demo transaction identifiers and simulates payment outcomes before saving successful bookings.

**This project does not currently demonstrate integration with a real payment gateway.** Do not use real card details with the demo form.

## Security and Limitations

- Configure environment variables locally and keep credentials out of version control.
- Review authorization checks for booking retrieval and payment-related endpoints before deployment.
- Use a proper payment provider for real transactions.
- Test API routes, booking conflicts, and booking lifecycle operations before production use.
- The project should be reviewed and tested before deployment to a public environment.

## Future Improvements

- Integrate a real payment gateway.
- Strengthen authorization and server-side validation.
- Improve booking availability and concurrency handling.
- Add automated backend and frontend tests.
- Improve deployment configuration and production monitoring.
- Expand agricultural service discovery and provider-management capabilities.

## Project Context

GoviSaviya was developed as a software project using the MERN stack. Refer to the repository history and project documentation for team contributions and implementation details.

## License

A license has not yet been specified. Add an appropriate license before distributing or reusing the project publicly.
