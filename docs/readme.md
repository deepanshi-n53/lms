# LMS - Learning Management System

A full-stack learning management system for creating, selling, and taking online courses.

## Overview

This project is a comprehensive Learning Management System (LMS) designed to connect educators and students. It provides a platform for educators to create, publish, and manage their courses, while students can browse, purchase, and track their progress through the course material. The application is built with a modern tech stack, featuring a React frontend and a Node.js/Express backend, and integrates with leading third-party services for authentication, payments, and media hosting.

## What It Does

The application serves two primary user roles: students and educators.

For students, the platform offers a user-friendly interface to discover new courses. They can view detailed course information, including curriculum and pricing, before enrolling. After purchasing a course via Stripe, students gain access to the course player to watch video lectures, track their completion progress, and rate the courses they have finished.

For educators, the system provides a dedicated dashboard to manage their content and business. An authenticated user can become an educator to gain access to these features. Educators can create new courses using a rich text editor, structure them into chapters and lectures, upload course thumbnails, and set pricing. The educator dashboard provides key metrics such as total earnings, student enrollment numbers, and a list of all created courses.

The backend handles all core business logic, data persistence with MongoDB, and secure API endpoints. It integrates with Clerk for user authentication and lifecycle management, Stripe for payment processing, and Cloudinary for efficient media storage and delivery. Webhooks from Clerk and Stripe ensure that user data and course enrollments are automatically synchronized in real-time.

## Key Features

-   **Role-Based Access:** Distinct interfaces and permissions for students and educators.
-   **Educator Dashboard:** Analytics on earnings, student count, and course performance.
-   **Course Creation:** A rich interface for educators to build courses with chapters, lectures, and descriptions.
-   **Payment Integration:** Secure course purchasing powered by Stripe Checkout.
-   **User Authentication:** Managed user sessions and authentication via Clerk.
-   **Course Progress Tracking:** Students can monitor their progress and mark lectures as complete.
-   **Course Catalog:** A searchable list of all available courses for students.
-   **Video Lecture Player:** An integrated player for students to watch course content.
-   **Course Ratings:** Allows enrolled students to submit and update course ratings.

## Tech Stack

| Category             | Technology                                                              |
| -------------------- | ----------------------------------------------------------------------- |
| **Frontend**         | React, React Router, Vite, Tailwind CSS, Axios                          |
| **Backend**          | Node.js, Express.js                                                     |
| **Database**         | MongoDB with Mongoose                                                   |
| **Services & APIs**  | Clerk (Authentication), Stripe (Payments), Cloudinary (Media Storage)   |

## Getting Started

Follow these instructions to get a local copy of the project up and running for development and testing purposes.

### Installation

1.  Clone the repository:
    ```sh
    git clone https://github.com/deepanshi-n53/lms.git
    cd lms
    ```

2.  Install backend dependencies:
    ```sh
    cd server
    npm install
    ```

3.  Install frontend dependencies:
    ```sh
    cd ../client
    npm install
    ```

4.  Set up environment variables. Create a `.env` file in the `server` directory and add the necessary keys for the database, authentication, payment, and media services.

    ```env
    # server/.env
    MONGO_URI=your_mongodb_connection_string
    CLERK_SECRET_KEY=your_clerk_secret_key
    STRIPE_SECRET_KEY=your_stripe_secret_key
    STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
    CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret
    CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
    CLOUDINARY_API_KEY=your_cloudinary_api_key
    CLOUDINARY_API_SECRET=your_cloudinary_api_secret
    CLIENT_URL=http://localhost:5173
    ```

### Quick Start

1.  Start the backend server (from the `server` directory):
    ```sh
    npm start
    ```
    The API server will be running on the port configured in your environment (e.g., `http://localhost:4000`).

2.  Start the frontend development server (from the `client` directory):
    ```sh
    npm run dev
    ```
    The React application will be available at `http://localhost:5173`.

## Project Structure

The repository is organized into two main directories: `client` for the frontend application and `server` for the backend API.

```
lms/
├── client/
│   ├── src/
│   │   ├── components/   # Reusable React components (student/educator)
│   │   ├── context/      # AppContext for global state management
│   │   ├── pages/        # Page-level components for routing
│   │   ├── assets/       # Static assets like images and icons
│   │   ├── App.jsx       # Root component with routing setup
│   │   └── main.jsx      # Application entry point
│   ├── tailwind.config.js # Tailwind CSS configuration
│   └── vite.config.js     # Vite configuration
│
└── server/
    ├── controllers/    # Request handlers for API routes
    ├── models/         # Mongoose schemas (Course, User, etc.)
    ├── routes/         # Express router definitions
    ├── configs/        # Configuration for DB, Cloudinary, etc.
    ├── middlewares/    # Custom middleware (e.g., auth)
    └── server.js       # Express server entry point
```

-   `client`: Contains the Vite-powered React application.
    -   `client/src/context/AppContext.jsx`: Provides global state for user data, courses, and authentication status.
    -   `client/src/pages`: Contains top-level components for different views like the Home page, Course Details, and Educator Dashboard.
-   `server`: Contains the Node.js and Express backend.
    -   `server/models`: Defines the Mongoose schemas for `User`, `Course`, `Purchase`, and `CourseProgress`.
    -   `server/controllers`: Implements the business logic for handling API requests.
    -   `server/routes`: Defines the API endpoints for users, courses, and educators.
    -   `server/server.js`: Initializes the Express app, connects to the database, and sets up middleware and routes.

## Contributing

Contributions are welcome. To contribute, please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix (`git checkout -b feature/your-feature-name`).
3.  Make your changes and commit them with a clear message.
4.  Push your changes to your fork (`git push origin feature/your-feature-name`).
5.  Open a pull request to the `main` branch of the original repository.

## License

This project does not have a specified license. Please add a `LICENSE` file to the repository to define the terms under which it can be used.