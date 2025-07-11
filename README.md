# Task Manager App

A full-stack Task Manager application built with an Express.js backend and a React frontend. This application allows users to manage their tasks efficiently.

## Table of Contents

* [Features](#features)
* [Technologies Used](#technologies-used)
* [Prerequisites](#prerequisites)
* [Getting Started](#getting-started)
    * [Backend Setup](#backend-setup)
    * [Frontend Setup](#frontend-setup)
* [Usage](#usage)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

## Features

* **Task Management:** Create, read, update, and delete tasks.
* **User Authentication:** Secure user login and registration.
* **MongoDB Integration:** Persistent storage for tasks and user data.
* **RESTful API:** A well-structured API for seamless communication between frontend and backend.

## Technologies Used

### Backend
* **Node.js**: JavaScript runtime environment.
* **Express.js**: Web application framework for Node.js.
* **MongoDB**: NoSQL database.
* **Mongoose**: MongoDB object data modeling (ODM) for Node.js.
* **JWT (JSON Web Tokens)**: For secure authentication.

### Frontend
* **React**: JavaScript library for building user interfaces.
* **npm**: Package manager for JavaScript.

## Prerequisites

Before you begin, ensure you have the following installed:

* Node.js (version `v23.10.0` or higher recommended)
* npm (version `v11.2.0` or higher recommended)
* A MongoDB Atlas account (free tier is sufficient)

## Getting Started

Follow these steps to get your Task Manager App up and running locally.

### Backend Setup

1.  **Navigate to the backend directory:**
    ```bash
    cd backend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Connect to MongoDB Atlas:**
    * Go to [https://www.mongodb.com/](https://www.mongodb.com/) and log in or create an account.
    * Create a new project.
    * Build a new cluster (select the free tier). Choose a cloud provider and a region near you.
    * Once the cluster is deployed, navigate to "Database Access" under "Security" and add a new database user (remember the username and password).
    * Go to "Network Access" under "Security" and add your current IP address or allow access from anywhere (for development purposes).
    * Go to "Clusters", click "Connect" on your cluster, and select "Connect your application".
    * Choose "Drivers" and select Node.js. Copy the provided connection string.

4.  **Create and configure the `.env` file:**
    * In the `backend` directory, create a file named `.env`.
    * Paste the MongoDB connection string you copied into this file, replacing `<password>` with the password of the database user you created.
        ```
        MONGO_URI=mongodb+srv://<username>:<password>@<cluster-url>/taskmanager.mongodb.net/Pretraertruelimajority?retryWrites=true&w=majority
        JWT_SECRET=YOUR_OWN_SECRET_HERE
        ADMIN_INVITE_TOKEN=4588944
        PORT=8800
        ```
        **Example:**
        ```
        MONGO_URI=mongodb+srv://testuser:yourpassword@cluster0.abcde.mongodb.net/taskmanager?retryWrites=true&w=majority
        JWT_SECRET=YOUR_OWN_SECRET_HERE
        ADMIN_INVITE_TOKEN=4588944
        PORT=8800
        ```

5.  **Generate JWT Secret:**
    * Open your terminal in the `backend` folder and run the following command to generate a strong JWT secret:
        ```bash
        node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
        ```
    * Copy the output (a long hexadecimal string) and paste it as the value for `JWT_SECRET` in your `.env` file.

6.  **Start the backend server:**
    ```bash
    npm run dev
    ```
    The backend server should now be running, typically on port `8800`.

### Frontend Setup

1.  **Navigate to the frontend directory:**
    ```bash
    cd frontend/Task-Manager
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Start the React development server:**
    ```bash
    npm run dev
    ```
    This will start the frontend server and open the app in your default web browser (usually `http://localhost:5173` or similar).

## Usage

Once both the backend and frontend servers are running:

1.  Open your web browser and navigate to the frontend URL (e.g., `http://localhost:5173`).
2.  Register a new user or log in with existing credentials.
3.  Start creating and managing your tasks!

## Contributing

Contributions are welcome! If you'd like to contribute, please follow these steps:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add new feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

## License

This project is licensed under the [MIT License](LICENSE.md) - see the `LICENSE.md` file for details.

## Contact

If you have any questions or suggestions, feel free to reach out.
