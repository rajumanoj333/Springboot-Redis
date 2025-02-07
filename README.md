# Spring Boot Redis API

Welcome to the **Spring Boot Redis API** project! This project demonstrates how to integrate **Redis** with **Spring Boot** to build a RESTful API that performs CRUD operations on user data. Redis is used as the data store, allowing fast data retrieval and storage. This application showcases best practices for interacting with Redis through Spring Boot.

## 🚀 Features
- **CRUD Operations** for Users in Redis
- Fast and Efficient **Redis Caching**
- Clean separation of concerns with **DAO** and **Controller** patterns
- Built-in **REST API** for handling user data
- Easy-to-configure and extend using Spring Boot

## 🛠️ Technologies Used
- **Spring Boot** - Framework to build and deploy Java applications
- **Redis** - In-memory data structure store used for fast data retrieval
- **Spring Boot Starter Web** - To create a web application and expose APIs
- **Spring Boot DevTools** - To speed up development with auto-reload capabilities
- **Spring Boot Starter Data Redis** - To integrate Redis into Spring Data
- **Lombok** - A Java library that reduces boilerplate code

## 📂 Project Structure
The project is structured into the following packages:

1. **`ApiRedisApplication.java`**  
   Main entry point with `@SpringBootApplication` annotation enabling component scanning and auto-configuration.

2. **`dao/UserDao.java`**  
   Implements the DAO pattern to interact with Redis for User entity operations.

3. **`config/RedisConfig.java`**  
   Configures Redis connection factory and templates.

4. **`controllers/UserController.java`**  
   REST controller handling HTTP requests for user operations.

5. **`models/User.java`**  
   Defines the User entity with fields and Redis mapping annotations.

## Prerequisites
- Redis server installed and running
- Java 11+
- Maven

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/spring-boot-redis-api.git
cd spring-boot-redis-api
```

2. Start Redis server:
```bash
redis-server
```

3. Run the Spring Boot application:
```bash
mvn spring-boot:run
```

## API Endpoints

Base URL: `http://localhost:8080`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/users` | Create a new user |
| GET | `/users` | Fetch all users |
| GET | `/users/{id}` | Fetch user by ID |
| PUT | `/users/{id}` | Update user by ID |
| DELETE | `/users/{id}` | Delete user by ID |

### Request Body Format

```json
{
  "id": "1",
  "name": "John Doe",
  "email": "john@example.com"
}
```

## Example Usage

### Create User
```bash
curl -X POST http://localhost:8080/users \
  -H "Content-Type: application/json" \
  -d '{
    "id": "1",
    "name": "John Doe",
    "email": "john@example.com"
  }'
```

### Get All Users
```bash
curl http://localhost:8080/users
```

### Get User by ID
```bash
curl http://localhost:8080/users/1
```

### Update User
```bash
curl -X PUT http://localhost:8080/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "id": "1",
    "name": "John Smith",
    "email": "johnsmith@example.com"
  }'
```

### Delete User
```bash
curl -X DELETE http://localhost:8080/users/1
```
