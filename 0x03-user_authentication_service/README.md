# User Authentication Service

This project implements a user authentication service using Python and SQLAlchemy. It provides features such as user registration, login, session management, password reset, and secure password storage using bcrypt. The application is built with Flask and integrates SQLAlchemy for database management.

## Features

- **User Registration:** Create new users with secure, hashed passwords.
- **User Login:** Authenticate users with email and password, leveraging session management.
- **Session Management:** Secure user sessions with UUID-based session IDs.
- **Password Reset:** Generate reset tokens for password recovery.
- **Profile Management:** Access and update user profiles securely.
- **Flask Integration:** Lightweight API endpoints for authentication services.
- **SQLAlchemy ORM:** Utilize the SQLAlchemy ORM for database interactions.

## Installation

To set up the project, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-repository/user-authentication-service.git
    cd user-authentication-service
    ```

2. **Set up a virtual environment**:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Set up the database**:
    SQLAlchemy will automatically create the SQLite database when the application starts.

5. **Run the Flask app**:
    ```bash
    python app.py
    ```

## API Endpoints

### User Registration

- **POST /users**  
  Register a new user by providing email and password.

  **Request**:
  ```json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  ```

  **Response**:
  ```json
  {
    "email": "user@example.com",
    "message": "user created"
  }
  ```

### User Login

- **POST /sessions**  
  Authenticate a user with email and password.

  **Request**:
  ```json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  ```

  **Response**:
  ```json
  {
    "email": "user@example.com",
    "message": "logged in"
  }
  ```

### User Profile

- **GET /profile**  
  Retrieve the profile of the logged-in user.

  **Response**:
  ```json
  {
    "email": "user@example.com"
  }
  ```

### Password Reset

- **POST /reset_password**  
  Request a reset token for the provided email.

  **Response**:
  ```json
  {
    "email": "user@example.com",
    "reset_token": "generated-token"
  }
  ```

- **PUT /reset_password**  
  Reset the password using the reset token.

  **Request**:
  ```json
  {
    "email": "user@example.com",
    "reset_token": "generated-token",
    "new_password": "newsecurepassword"
  }
  ```

  **Response**:
  ```json
  {
    "email": "user@example.com",
    "message": "Password updated"
  }
  ```

## Testing

The project includes an end-to-end test suite using `requests` to verify all functionalities.

### Running Tests
To run the end-to-end tests, use the provided `main.py` file.

```bash
python main.py
```

If everything works as expected, there should be no output.

## Technologies Used

- **Python 3.7**
- **Flask**
- **SQLAlchemy 1.3.x**
- **bcrypt** for secure password hashing
- **UUID** for session and reset token generation


