## Introduction
Scool Corner is a web application designed for managing donations and withdrawals, tracking them in real-time. The project connects sponsors and students, allowing sponsorship of various products for students. The application consists of a Node.js, Express, and Sequelize backend (for database management) and a React frontend with Socket.IO handling live updates.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Routes and Endpoints](#routes-and-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Real-Time Updates**: Socket.IO enables live notifications for donations and withdrawals.
- **Donation Management**: Tracks donations from sponsors and displays them live.
- **Withdrawal Tracking**: Monitors withdrawals with monthly reporting and balance display.
- **Admin Features**: Admin panel for managing subjects, sponsors, and products.
- **Responsive Frontend**: React UI with animations, live updates, and sponsor display.

## Technologies Used
- **Backend**: Node.js, Express, Sequelize (MySQL/MariaDB)
- **Frontend**: React, Socket.IO, Framer Motion (for animations)
- **Other**: Axios, dotenv for environment configuration, CORS for cross-origin requests.

## Installation

### Prerequisites
- **Node.js**: Ensure Node.js (version 12+ recommended) is installed.
- **MySQL/MariaDB**: Install and set up a MySQL or MariaDB database.

### Backend
1. Clone the repository and navigate to the backend folder:
   ```bash
   git clone <repository-url>
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables by creating a `.env` file in the backend root directory:
   ```bash
   PORT=3001
   DATABASE_URL=<your-database-url>
   ```

4. Configure the database connection in `config/config.json`:
   ```json
   {
     "development": {
       "username": "your_db_username",
       "password": "your_db_password",
       "database": "your_db_name",
       "host": "127.0.0.1",
       "dialect": "mysql"
     }
   }
   ```

5. Run database migrations:
   ```bash
   npx sequelize-cli db:migrate
   ```

6. Start the backend server:
   ```bash
   npm start
   ```

### Frontend
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install frontend dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the frontend directory:
   ```bash
   REACT_APP_API_URL=http://localhost:3001
   REACT_APP_WS_URL=http://localhost:3001
   ```

4. Start the frontend development server:
   ```bash
   npm start
   ```

## Configuration

- **Backend**: Configure environment variables in the `.env` file for the backend and set up database configuration in `config/config.json`.
- **Frontend**: Configure API and WebSocket endpoints in the frontend `.env` file as shown in the Installation section.

## Usage

1. Start both the backend and frontend servers as described in the installation steps.
2. Access the application at `http://localhost:3000`.
3. **Authentication**: Log in or register as an admin or sponsor to access full features.
4. **Live Updates**: View real-time updates on donations and withdrawals displayed on the frontend.

## Routes and Endpoints

### Backend API Endpoints
| Route                   | Method | Description                        |
|-------------------------|--------|------------------------------------|
| `/products`             | GET    | Retrieves a list of products      |
| `/donations`            | GET    | Retrieves a list of donations     |
| `/withdrawals`          | GET    | Retrieves a list of withdrawals   |
| `/school-subjects`      | GET    | Retrieves the current school subject |
| `/auth`                 | POST   | User authentication               |

### Frontend Routes
| Path                    | Description                              |
|-------------------------|------------------------------------------|
| `/`                     | Home page with donation data            |
| `/donate`               | Donation page                           |
| `/withdraw`             | Withdrawal page                         |
| `/sponsor`              | Add a sponsor page                      |
| `/school-subject`       | Change the subject of the month page    |
| `/admin`                | Admin dashboard                         |
| `/edit-or-delete`       | Edit or delete entries page             |
| `/edit-products`        | Edit products page                      |
| `/login`                | Login page                              |

## Contributing
1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/NewFeature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/NewFeature`).
5. Open a pull request.

## License
This project is licensed under the MIT License.
