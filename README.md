# 🎬 MyFlix REST API

A RESTful API for movie enthusiasts, providing comprehensive information about movies, directors, and genres. Built with Node.js, Express, and MongoDB.

## 🚀 Live Demo

**API Base URL:** [https://movie-api-j617.onrender.com](https://movie-api-j617.onrender.com)

> **Note:** The API is hosted on Render's free tier and may take 30-50 seconds to wake up from inactivity on the first request.

---

## 📖 About

MyFlix API allows users to:
- Explore a curated collection of movies with detailed information
- Access data about directors and genres
- Create personalized accounts and manage favorite movies
- Authenticate securely with JWT tokens

This API serves as the backend for the MyFlix client applications (React, Angular).

---

## ✨ Key Features

### Movies
- ✅ Get all movies
- ✅ Get movie by title (with description, genre, director, image, year)
- ✅ Search movies by genre
- ✅ Search movies by director

### Genres
- ✅ Get genre information and description by name

### Directors
- ✅ Get director details (bio, birth year, death year)

### User Management
- ✅ User registration
- ✅ User authentication (login with JWT)
- ✅ Update user profile (username, password, email, date of birth)
- ✅ Add/remove movies to favorites list
- ✅ Delete account

---

## 🛠️ Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB Atlas
- **Authentication:** JWT (JSON Web Tokens)
- **Password Hashing:** bcrypt
- **Validation:** express-validator
- **CORS:** Configured for cross-origin requests
- **Deployment:** Render

---

## 📋 API Endpoints

### Public Endpoints (No Authentication Required)

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/users` | Register a new user |
| `POST` | `/login` | User login (returns JWT token) |

### Protected Endpoints (Authentication Required)

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/movies` | Get all movies |
| `GET` | `/movies/:title` | Get movie by title |
| `GET` | `/movies/genre/:genreName` | Get movies by genre |
| `GET` | `/movies/director/:directorName` | Get movies by director |
| `GET` | `/users/:username` | Get user profile |
| `PUT` | `/users/:username` | Update user info |
| `POST` | `/users/:username/movies/:MovieID` | Add movie to favorites |
| `DELETE` | `/users/:username/movies/:MovieID` | Remove movie from favorites |
| `DELETE` | `/users/:username` | Delete user account |

---

## 🔐 Authentication

This API uses **JWT (JSON Web Token)** for authentication.

### How to authenticate:

1. **Register** a new user at `/users`
2. **Login** at `/login` to receive a JWT token
3. Include the token in subsequent requests:
```
   Authorization: Bearer <your-jwt-token>
```

---

## 📦 Installation (Local Development)

### Prerequisites
- Node.js (v14 or higher)
- MongoDB Atlas account

### Steps

1. **Clone the repository**
```bash
   git clone https://github.com/acarecor/MOVIE_API.git
   cd MOVIE_API
```

2. **Install dependencies**
```bash
   npm install
```

3. **Create `.env` file**
```env
   CONNECTION_URI=your_mongodb_atlas_connection_string
   SECRET_OR_KEY=your_jwt_secret_key
   PORT=8080
```

4. **Start the server**
```bash
   npm start
```

5. **API will be running at:** `http://localhost:8080`

---

## 🌐 Environment Variables

| Variable | Description |
|----------|-------------|
| `CONNECTION_URI` | MongoDB Atlas connection string |
| `SECRET_OR_KEY` | Secret key for JWT signing |
| `PORT` | Port number (default: 8080) |

---

## 📚 Database Schema

### Movie Model
```javascript
{
  Title: String,
  Description: String,
  Genre: {
    Name: String,
    Description: String
  },
  Director: {
    Name: String,
    Bio: String,
    Birth: String,
    Death: String
  },
  ImagePath: String,
  Featured: Boolean
}
```

### User Model
```javascript
{
  Username: String,
  Password: String (hashed),
  Email: String,
  Birthday: Date,
  FavoriteMovies: [ObjectId]
}
```

---

## 🔗 Related Projects

- **[MyFlix React Client](https://github.com/acarecor/CINEFLIX-App)** - React-based client application
- **[MyFlix Angular Client](https://github.com/acarecor/MYFLIX-App)** - Angular-based client application

---

## 👩‍💻 Author

**Ana Arellano**
- GitHub: [@acarecor](https://github.com/acarecor)

---

## 💡 Key Learnings

Through building this API, I developed expertise in:
- RESTful API design and implementation
- Authentication & authorization with JWT
- Database modeling with MongoDB/Mongoose
- Security best practices (bcrypt, CORS, validation)
- Cloud deployment and environment configuration
- API documentation and endpoint design

Built as part of my transition into full-stack development (2023-2024).

---