# 🔐 Secure File-Sharing Application - Backend

A robust and secure file-sharing backend built with **Rust** and **Axum**, featuring end-to-end encryption to ensure maximum privacy and security for file transfers.

## 🌟 Features

- **End-to-End Encryption**: Files are encrypted using AES-256 before storage
- **RSA Key Exchange**: Secure key exchange mechanism using RSA encryption
- **JWT Authentication**: Secure user authentication with JSON Web Tokens
- **Password Security**: Argon2 password hashing for secure credential storage
- **File Upload**: Multipart file upload support with validation
- **RESTful API**: Clean and well-structured API endpoints
- **Database Integration**: PostgreSQL database with SQLx for async queries
- **CORS Support**: Cross-origin resource sharing for frontend integration
- **Request Tracing**: Built-in logging and tracing for debugging and monitoring
- **Scheduled Tasks**: Cron job scheduling for background tasks (e.g., cleanup)

## 🛠️ Tech Stack

- **Rust** - Systems programming language for performance and safety
- **Axum** - Web framework built on top of Tokio
- **PostgreSQL** - Relational database for data persistence
- **SQLx** - Async SQL toolkit with compile-time query verification
- **JWT** - Token-based authentication
- **Argon2** - Password hashing algorithm
- **AES & RSA** - Encryption algorithms for data security

## 📋 Prerequisites

- Rust 1.70 or higher
- PostgreSQL 14 or higher
- Cargo (comes with Rust)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd secure-backend
```

### 2. Set Up Environment Variables

Create a `.env` file in the project root:

```env
DATABASE_URL=postgres://username:password@localhost/secure_file_sharing
JWT_SECRET=your-super-secret-jwt-key
SERVER_HOST=127.0.0.1
SERVER_PORT=3000
```

### 3. Set Up the Database

```bash
# Create the database
createdb secure_file_sharing

# Run migrations (if using sqlx-cli)
sqlx migrate run
```

### 4. Build and Run

```bash
# Development mode
cargo run

# Release mode (optimized)
cargo run --release
```

The server will start at `http://127.0.0.1:3000` (or your configured host/port).

## 📁 Project Structure

```
secure-backend/
├── src/
│   └── main.rs          # Application entry point
├── Cargo.toml           # Project dependencies
├── .env                 # Environment variables (not in git)
└── README.md           # This file
```

## 🔑 API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login and receive JWT token

### Files
- `POST /api/files/upload` - Upload an encrypted file
- `GET /api/files/:id` - Download a file
- `GET /api/files` - List user's files
- `DELETE /api/files/:id` - Delete a file

### User
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile

## 🔒 Security Features

1. **Encryption at Rest**: All files are encrypted using AES-256 before storage
2. **Secure Key Exchange**: RSA encryption for sharing symmetric keys
3. **Password Hashing**: Argon2 algorithm with salt for password storage
4. **JWT Authentication**: Stateless authentication with token expiration
5. **Input Validation**: Request validation using the `validator` crate
6. **CORS Configuration**: Configurable CORS for secure frontend integration

## 🧪 Testing

```bash
# Run all tests
cargo test

# Run tests with output
cargo test -- --nocapture

# Run specific test
cargo test test_name
```

## 📦 Build

```bash
# Debug build
cargo build

# Release build (optimized)
cargo build --release
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔗 Frontend

This backend is designed to work with a Next.js frontend using ShadCN UI components. Check the frontend repository for more details.

## 📞 Support

For issues, questions, or contributions, please open an issue in the repository. 
