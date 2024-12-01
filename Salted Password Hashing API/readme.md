# Salted Password Hashing API

## Overview
This project is a secure **User Authentication API** that uses salted password hashing to ensure secure handling of user credentials. It provides routes for user registration, login, password change, and password validation. 

---

## Features
- **User Registration**: Create accounts with salted and hashed passwords.
- **User Login**: Authenticate users by validating salted hashes.
- **Change Password**: Update user passwords securely.
- **Password Validation**: Validate passwords using stored salted hashes.
- **Security**: Implements bcrypt or Argon2 for secure password hashing.

---

## API Requirements

### 1. **User Registration (`/register`)**
- Allows users to create an account by providing a username and password.
- Passwords are hashed with a unique salt before storing in the database.
- Both the salt and the hashed password are stored securely.
- Sends a response indicating whether the registration was successful.

### 2. **User Login (`/login`)**
- Allows users to log in by providing a username and password.
- Retrieves the salt and hashed password from the database.
- Rehashes the provided password with the stored salt and compares it with the hashed password.
- Sends a success message if the passwords match; otherwise, returns an error message.

### 3. **Change Password (`/change-password`)**
- Allows users to update their password by providing:
  - Username
  - Old password
  - New password
- Verifies the old password by rehashing and comparing with the stored hash.
- Salts and hashes the new password before updating the database.

### 4. **Password Validation (`/validate-password`)**
- Accepts a password and validates it against the stored salted hash (internal use).
- Ensures that only valid passwords are recognized.

---

## User Database
- Stores user data including:
  - `username`
  - `hashed password`
  - `salt`
- Can use in-memory storage for simplicity.

---

## Security Considerations
- **No Plaintext Passwords**: Passwords are never stored in plaintext.
- **Secure Hashing**: Uses industry-standard algorithms like **bcrypt** or **Argon2**.
- **Salting**: Ensures that password hashing uses unique salts for each user.

---

## API Documentation
- Use **Swagger** or **Postman** to document the API.
- Include:
  - Endpoint descriptions
  - Request/response samples
  - Authentication and authorization procedures

---

## Docker Deployment
- **Dockerfile**: Create a Dockerfile to containerize the application.
- **Docker Compose**: Add a `docker-compose.yml` file to manage the container.

---

## Testing
- Write unit tests for:
  - Password hashing and validation.
  - API routes (`/register`, `/login`, `/change-password`, `/validate-password`).
- Ensure full test coverage for core functionalities.

---

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/SaltedPasswordAPI.git
   ```
2. Follow the instructions to set up and run the API (see installation instructions in the next section).

---
