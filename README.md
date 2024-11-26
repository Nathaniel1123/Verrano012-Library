## Library API Documentation
 Welcome to the Library API! This API allows users to register, authenticate, manage authors, and books in a library system. The API uses secure authentication via JWT (JSON Web Tokens), ensuring that every request to modify or retrieve data is properly authenticated. After every action, a new JWT token is provided, which should be used for subsequent requests. This provides enhanced security and ensures that each operation is properly validated.

## Features:
-  User Registration & Authentication: Users can register a new account and authenticate to obtain a token for further actions.
-  Author Management: Create, read, update, and delete authors from the system.
-  Book Management: Create, read, update, and delete books, while associating them with authors.
-  Token-based Authentication: Each request requires a valid JWT token for authentication. After each action (such as creating or updating an author or book), a new token is issued.

## Register a New User 
### ENDPOINT: (/user/register)
Method: POST

Request Payload:
```bash
  {
  "username": "your_username"  
  "password": "your_password"   
}
```
Response:
```bash
{
  "status": "success",
  "data": null
}
```

## USER AUTHENTICATION
### ENDPOINT: (/user/auth)
Method: POST

Request Payload:
```bash
  {
  "username": "your_username"  
  "password": "your_password"   
}
```
Response:
```bash
{
  "status": "success",
  "token": "jwt_token_here",
  "data": null
}
```
## Create a New Author 
### ENDPOINT: (/user/author/create)
Method: POST

Request Payload:
```bash
 {
  "name": "Nathaniel",
  "token": "jwt_token_here"
}

```
Response:
```bash
{
  "status": "success",
  "token": "new_jwt_token_here",
  "data": null
}
```
## Read All Authors
### ENDPOINT: (/user/author/read)
Method: GET

Request Payload:
```bash
{
  "token": "new_jwt_token_here",
}
```
Response:
```bash
{
  "status": "success",
  "data": [
    {
      "id": 1,
      "name": "George Orwell"
    },
    {
      "id": 2,
      "name": "J.K. Rowling"
    }
  ]
}

```

### Update an Author 
## Endpoint: (/user/author/update)
## Method: PUT

Request Payload:
```bash
{
  "authorid": "1",  
  "name": "Invictus",       
  "token": "jwt_token_here"       
}
```

Response:
```bash
{
  "status": "success",
  "token": "new_jwt_token_here",
  "data": null
}
```

### Delete Author
## Endpoint: /user/author/delete

## Method: DELETE

Request Payload:

```bash
{
  "authorid": "integer",
  "token": "your_jwt_token"
}

```
Response:
```bash
{
  "status": "success",
  "token": "new_jwt_token_here",
  "data": null
}
```
### Create Book
## Endpoint: /user/book/create

## Method: POST

## Request Payload:
```bash
{
  "title": "THEBOOKOFWISDOM",
  "authorid": "1",
  "token": "your_jwt_token"
}

```
## Response:
```bash
{
  "status": "success",
  "token": "new_jwt_token_here",
  "data": null
}
```
### Read All Books

## Endpoint: /user/book/read

## Method: GET

Request Payload
```bash
{
  "token": "new_jwt_token_here",

}
```
Response:
```bash
{
  "status": "success",
  "data": [
    {
      "id": 1,
      "title": "Book Title",
      "authorid": 1
    },
    {
      "id": 2,
      "title": "Another Book Title",
      "authorid": 2
    }
  ]
}

```
### Update book
## Endpoint: (/user/book/update)
## Method: PUT

Request Payload:
```bash
{
  "id": "1",  
  "title": "Invictus",       
  "token": "jwt_token_here"       
}
```

Response:
```bash
{
  "status": "success",
  "token": "new_jwt_token_here",  
  "data": null
}

```
## Get Book
## Endpoint: (/user/book/read/{id})
## Method: GET

Request Payload:
```bash
{
  "token": "jwt_token_here",  
}

```
Response:
```bash
{
  "status": "success",
  "data": {
    "id": 1,
    "title": "Invictus",
    "authorid": 1
  },
  "token": "new_jwt_token_here" 
}
```








