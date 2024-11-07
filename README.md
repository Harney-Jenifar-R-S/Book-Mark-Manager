# Bookmark Manager

A web application that allows users to save, categorize, and manage bookmarks. The app includes features for tagging and searching bookmarks, and it also has a user authentication system.

## Features
- User registration and login.
- Ability to add, categorize, and tag bookmarks.
- Search bookmarks by title, tags, or category.
- JWT-based user authentication.

## Technologies Used
- **Frontend**: React.js (for building the user interface)
- **Backend**: Node.js, Express.js (for handling API requests)
- **Database**: MongoDB (for storing user data and bookmarks)
- **Authentication**: JWT (JSON Web Tokens)
- **Password Hashing**: bcrypt.js (for securely storing passwords)

## Installation

### Prerequisites
- Node.js (v14.x or higher)
- MongoDB (local or MongoDB Atlas)
- A `.env` file for sensitive information like JWT secret and MongoDB URI

### Steps to Install
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/bookmark-manager.git
    cd bookmark-manager
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Create a `.env` file in the root of the project with the following:
    ```bash
    MONGO_URI=mongodb://localhost:27017/bookmark_manager
    JWT_SECRET=your_jwt_secret
    ```

4. Start the server:
    ```bash
    npm start
    ```

5. The server will now run on `http://localhost:5000`.

## API Endpoints

### Authentication Routes
- **POST** `/api/auth/register`: Register a new user. Requires `username`, `email`, and `password`.
- **POST** `/api/auth/login`: Login a user. Requires `email` and `password`.

### Bookmark Routes
- **POST** `/api/bookmarks/add`: Add a new bookmark. Requires `url`, `title`, `description`, `tags`, and `category`.
- **GET** `/api/bookmarks`: Get all bookmarks for the logged-in user.
- **GET** `/api/bookmarks/search`: Search bookmarks by title, tags, or category. Query parameters can be passed in the URL.

## Example Usage

### Registering a New User
```bash
POST /api/auth/register
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securepassword"
}
