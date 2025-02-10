# Spring Boot JWT Authentication Backend

## 📌 Overview
This project is a Spring Boot-based backend application that implements authentication and authorization using **JSON Web Tokens (JWT)**. It provides secured APIs for user authentication, role-based access control, and token validation.

## 🛠 Technologies Used
- **Spring Boot** (REST API)
- **Spring Security** (Authentication & Authorization)
- **JWT (JSON Web Token)** (Token-based authentication)
- **Spring Data JPA** (ORM for database interaction)
- **MySQL/PostgreSQL** (Database)
- **Hibernate** (JPA implementation)
- **Maven** (Build tool)

## ⚙️ Project Structure
```
/src/main/java/com/youtube/jwt/
├── configuration/      # Security & JWT configuration classes
├── controller/         # API controllers
├── dao/                # Data access layer (Repository interfaces)
├── entity/             # Entity classes (User, Role, etc.)
├── service/            # Business logic layer
├── util/               # Utility classes (JWT token generation & validation)
└── JwtApplication.java # Main application file
```

## 🚀 Features
- **User authentication** with JWT
- **Role-based authorization** (Admin/User)
- **CORS support** (for frontend integration)
- **Secure API endpoints**
- **Custom JWT filter** for authentication

## 📂 API Endpoints
| Method | Endpoint          | Description             | Access |
|--------|------------------|-------------------------|--------|
| POST   | `/authenticate`  | User login & JWT token  | Public |
| POST   | `/register`      | Register new users      | Public |
| GET    | `/users`         | Get all users           | Admin  |
| GET    | `/user/{id}`     | Get user by ID          | Admin  |
| POST   | `/roles`         | Create new role         | Admin  |

## 🔑 JWT Authentication Flow
1. User logs in with username and password.
2. Backend validates credentials and generates a JWT.
3. JWT is returned to the client and stored (e.g., in local storage).
4. Client includes the JWT in the `Authorization` header for protected API requests.
5. Backend verifies JWT and grants/denies access.

## 🔧 Setup & Installation
### Prerequisites
- Java 17+
- Maven
- MySQL/PostgreSQL

### Steps
1. **Clone the repository**
   ```sh
   git clone https://github.com/your-repo.git
   cd your-repo
   ```
2. **Configure Database** in `application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/yourdb
   spring.datasource.username=root
   spring.datasource.password=password
   ```
3. **Build and Run**
   ```sh
   mvn clean install
   mvn spring-boot:run
   ```
4. **Access the API** at `http://localhost:9090`

## ⚠️ Common Issues & Fixes
1. **Port 9090 already in use** → Run:
   ```sh
   lsof -i :9090
   kill -9 <PID>
   ```
2. **JWT Token is invalid** → Ensure the token is included in the `Authorization` header as:
   ```sh
   Authorization: Bearer <your-token>
   ```

## 📜 License
This project is licensed under the **MIT License**.

---
### 📩 Need Help?
Feel free to create an issue or reach out to the repository owner!

