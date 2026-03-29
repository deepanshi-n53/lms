# LMS - Learning Management System

A full-stack learning management system for educators and students.

## Overview

This project is a web-based Learning Management System (LMS) designed to connect educators and students. It provides a platform for educators to create, publish, and manage their video courses. Students can browse a catalog of courses, enroll in them, track their progress, and consume the educational content. The application features distinct interfaces and functionalities tailored to the needs of both user roles.

## What It Does

The application operates with two primary user roles: Educators and Students.

For educators, the platform provides a comprehensive dashboard to manage their content and audience. An educator can create new courses, structuring them with chapters and individual lectures. The course creation process includes adding titles, rich-text descriptions, pricing, and video content. Once published, educators can monitor key metrics such as total student enrollments, course-specific earnings, and view lists of enrolled students.

For students, the platform offers a user-friendly interface to discover and learn. The homepage features available courses, which can be searched and filtered. Students can view detailed course pages with descriptions, chapter breakdowns, and free preview lectures before deciding to enroll. After enrolling, they gain access to a dedicated course player to watch lectures, mark them as complete, and track their overall progress through a visual progress bar. Students can also rate the courses they have completed.

## Key Features

-   **Dual User Roles:** Separate, feature-rich interfaces for Students and Educators.
-   **Course Management:** Educators can create, update, and manage courses with chapters and lectures.
-   **Rich Content Creation:** Utilizes a rich text editor for detailed course descriptions.
-   **Student Enrollment:** Students can browse, purchase, and enroll in courses.
-   **Video Playback:** Integrated course player for streaming video lectures from YouTube.
-   **Progress Tracking:** Students can track their completion progress for each enrolled course.
-   **Educator Dashboard:** Provides educators with analytics on enrollments, earnings, and student data.
-   **Course Ratings:** Allows students to rate courses they have completed.
-   **User Authentication:** Secure user management and authentication handled by Clerk.

## Tech Stack

| Area                | Technologies                                                              |
| ------------------- | ------------------------------------------------------------------------- |
| **Frontend**        | React, Vite, React Router, Tailwind CSS, Axios, Quill.js                  |
| **Backend**         | Node.js, Express.js                                                       |
| **Database**        | MongoDB                                                                   |
| **Services**        | Clerk (Authentication), Stripe (Payments), Cloudinary (Media Storage)     |
| **Development**     | ESLint, Vite                                                              |

## Getting Started

Follow these instructions to get a local copy of the project up and running.

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

3.  Create a `.env` file in the `server` directory and add the necessary environment variables for your database connection (MongoDB), authentication (Clerk), payment gateway (Stripe), and media storage (Cloudinary).

4.  Install frontend dependencies:
    ```sh
    cd ../client
    npm install
    ```

5.  Create a `.env` file in the `client` directory and add your frontend-specific environment variables, such as the Clerk Publishable Key.

### Quick Start

1.  Start the backend server from the `server` directory:
    ```sh
    npm start
    ```
    The API will be running on the configured port.

2.  Start the frontend development server from the `client` directory in a separate terminal:
    ```sh
    npm run dev
    ```
    The application will be available at `http://localhost:5173` or the next available port.

## Project Structure

The repository is structured as a monorepo with separate directories for the client and server applications.

```
.
├── client/         # React frontend application
│   ├── public/
│   ├── src/
│   │   ├── assets/         # Static assets (images, icons)
│   │   ├── components/     # Reusable React components (student/educator)
│   │   ├── context/        # Global state management (AppContext)
│   │   ├── pages/          # Top-level page components (student/educator)
│   │   ├── App.jsx         # Main component with client-side routing
│   │   └── main.jsx        # Client application entry point
│   ├── tailwind.config.js  # Tailwind CSS configuration
│   └── vite.config.js      # Vite configuration
│
└── server/         # Node.js/Express backend API
    ├── configs/        # Configuration for DB, Cloudinary, etc.
    ├── controllers/    # Business logic and request handlers
    ├── middlewares/    # Express middleware (e.g., auth)
    ├── models/         # Mongoose database schemas
    ├── routes/         # API route definitions
    └── server.js       # Backend server entry point
```

## Contributing

Contributions are welcome. To contribute, please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature (`git checkout -b feature/YourFeature`).
3.  Commit your changes (`git commit -m 'Add some feature'`).
4.  Push to the branch (`git push origin feature/YourFeature`).
5.  Open a Pull Request.

## License

This project does not have a specified license. Please add a `LICENSE` file to the repository to define the terms under which it can be used.