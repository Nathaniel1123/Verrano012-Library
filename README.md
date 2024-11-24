# Library Management System with JWT

A **Library Management System** that allows users to manage books, authors, and user authentication using **JSON Web Tokens (JWT)** for secure and stateless user sessions. This system provides endpoints for adding, removing, updating, and viewing books, as well as managing users and access control via JWT-based authentication.

## Features

- **User Authentication**: Secure login and registration with JWT tokens.
- **Book Management**: Add, update, delete, and retrieve books and authors.
- **Role-Based Access**: Different levels of access for admins and regular users.
- **RESTful API**: Standardized API endpoints for interacting with the system.
- **JWT Authorization**: Protects endpoints using JWT for secure and stateless sessions.

## Prerequisites

Before getting started, ensure you have the following installed:

- Node.js (version >= 14)
- npm (Node Package Manager)
- A relational database (e.g., MySQL, PostgreSQL, SQLite) or MongoDB for data storage

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/library-management-system-jwt.git
   
2. Navigate to the project directory:
   ```bash
   cd library-management-system-jwt

3. Install the required dependencies:
   ```bash
   npm install
   
4. Set up the environment variables: Create a .env file in the root of your project and add the following variables:
   ```bash
   JWT_SECRET=your-secret-key
   DB_HOST=your-database-host
   DB_USER=your-database-username
   DB_PASSWORD=your-database-password
   DB_NAME=your-database-name
   PORT=3000

5. Run the application:
   ```bash
   npm start
  This will start the server on the specified port (default is 3000).

## API Endpoints

### Authentication

- **POST /api/auth/register** - Register a new user (Admin or User)
- **POST /api/auth/login** - Login and obtain JWT token
  
### Books Management (Admin Only)

- **GET /api/books** - Get a list of all books
- **POST /api/books** - Add a new book (Admin only)
- **PUT /api/books/:id** - Update a book (Admin only)
- **DELETE /api/books/:id** - Delete a book (Admin only)

### Users Management (Admin Only)

- **GET /api/users** - List all users (Admin only)
- **GET /api/users/:id** - Get user details (Admin only)
- **DELETE /api/users/:id** - Delete a user (Admin only)

### Protected Routes (JWT Authentication)
All routes except authentication require a valid JWT token in the Authorization header:
  ```bash
     Authorization: Bearer <your-jwt-token>
  ```
## Usage Example
### Register a new user:
```bash
POST /api/auth/register
{
  "username": "nathaniel_verrano",
  "password": "dmmmsumluc"",
  "role": "user"
}
```
### Login to get a JWT token:
```
POST /api/auth/login
{
  "username": "nathaniel_verrano",
  "password": "dmmmsumluc"
}
```
### Accessing Protected Routes:
After logging in, use the returned JWT token to access protected routes. For example, to get the list of books:
```
GET /api/books
Authorization: Bearer <your-jwt-token>
```
### Add a new book (Admin Only):
```
POST /api/books
Authorization: Bearer <admin-jwt-token>
{
  "title": "The CIT Krakens",
  "author": "W. Nathaniel Verrano",
  "isbn": "10101011111010101",
  "published_date": "2024-11-24"
}
```
## Technologies Used
- **Node.js**: Backend JavaScript runtime.
- **Express**: Web framework for Node.js to handle HTTP requests.
- **JWT (JSON Web Token)**: Stateless authentication system.
- **MySQL/PostgreSQL/MongoDB**: Database system (depends on configuration).
- **Sequelize (for SQL) / Mongoose (for MongoDB)**: ORM/ODM for interacting with the database.






