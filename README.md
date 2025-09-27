# FastAPI Users Demo

A simple demonstration of FastAPI Users with JWT authentication for signup and signin functionality.

## Features

- ✅ User registration (signup)
- ✅ User authentication (signin) with JWT tokens
- ✅ Protected routes that require authentication
- ✅ User profile information
- ✅ PostgreSQL database for user storage

## Quick Start

1. **Install dependencies:**
   ```bash
   uv sync
   ```

2. **Run the application:**
   ```bash
   python main.py
   ```

3. **Access the API documentation:**
   - Open your browser to `http://127.0.0.1:8000/docs`
   - Interactive API documentation with Swagger UI

## API Endpoints

### Authentication
- `POST /auth/register` - Register a new user
- `POST /auth/jwt/login` - Login and get JWT token
- `POST /auth/jwt/logout` - Logout (invalidate token)

### Protected Routes
- `GET /authenticated-route` - Access protected content (requires authentication)
- `GET /users/me` - Get current user information (requires authentication)


## Example Usage

1. **Register a new user:**
   ```bash
   curl -X POST "http://127.0.0.1:8000/auth/register" \
        -H "Content-Type: application/json" \
        -d '{"email": "user@example.com", "password": "password123", "username": "testuser"}'
   ```

2. **Login and get token:**
   ```bash
   curl -X POST "http://127.0.0.1:8000/auth/jwt/login" \
        -H "Content-Type: application/x-www-form-urlencoded" \
        -d "username=user@example.com&password=password123"
   ```

3. **Access protected route:**
   ```bash
   curl -X GET "http://127.0.0.1:8000/authenticated-route" \
        -H "Authorization: Bearer YOUR_JWT_TOKEN"
   ```

## Project Structure

```
├── src/app.py       # FastAPI application with routes
├── src/db.py        # Database setup and initialization
├── src/schemas.py   # Schemas for the application
├── src/users.py     # User Manament and Strategy
├── main.py          # Main file to run the application
└── pyproject.toml   # Project dependencies
```