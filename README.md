Library Management System with JWT
Introduction
The Library Management System (LMS) is a web application designed to facilitate the management of library resources, including books, patrons, and borrowing records. This system utilizes JSON Web Tokens (JWT) for secure authentication and authorization of librarians accessing the API.

Features
User Authentication: Librarians can register and log in to obtain a JWT for accessing protected routes.
Book Management: Add, update, delete, and retrieve book information.
Patron Management: Manage patron details, including registration and updates.
Borrowing Records: Track which patrons have borrowed which books and manage return dates.
Caching Mechanism: Utilizes Redis for caching frequently accessed data to improve performance.
Technologies Used
Spring Boot: Framework used for building the RESTful API.
Spring Security: Provides security features including authentication and authorization.
JWT (JSON Web Tokens): Used for secure transmission of information between parties as a JSON object.
Hibernate: ORM framework for database interactions.
Redis: In-memory data structure store used as a cache.
Installation
Clone the repository:
git clone https://github.com/yourusername/library-management-system.git
cd library-management-system
Update the .properties file with your database connection settings and Redis configuration.
Install dependencies using Maven or Gradle:
mvn install
Run the application:
mvn spring-boot:run
API Endpoints
Authentication
POST /librarian/auth/sign-in: Authenticate librarian and receive a JWT token.
Book Management
GET /api/books: Retrieve all books.
POST /api/books: Add a new book.
PUT /api/books/{id}: Update an existing book by ID.
DELETE /api/books/{id}: Remove a book by ID.
Patron Management
GET /api/patrons: Retrieve all patrons.
POST /api/patrons: Register a new patron.
Borrowing Records
GET /api/borrows: Retrieve all borrowing records.
POST /api/borrows: Record a new borrowing transaction.
Usage
First, register a librarian account using the sign-up endpoint if you do not have one already.
Log in using your credentials to receive your JWT token.
Use this token in the Authorization header as follows:
Authorization: Bearer 
Access other endpoints using this token to perform various operations on books, patrons, and borrowing records.
Testing
Unit tests are implemented for API endpoints using mocking frameworks to ensure functionality without needing actual database access during tests.

Conclusion
This Library Management System provides an efficient way to manage library resources while ensuring secure access through JWT authentication. It is designed to be scalable and maintainable, making it suitable for libraries of any size.
