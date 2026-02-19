# Product Service - Spring Boot Microservice

A RESTful microservice for managing products, built with Spring Boot, JPA, H2 in-memory database, and Swagger UI.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| Java 17 | Programming Language |
| Spring Boot 4.0.3 | Application Framework |
| Spring Data JPA | Database Operations |
| H2 Database | In-Memory Database |
| Swagger/OpenAPI | API Documentation |
| Maven | Build Tool |

## Project Structure

```
product-service/
├── src/main/java/com/sliit/product_service/
│   ├── ProductServiceApplication.java    # Entry point
│   ├── controller/
│   │   └── ProductController.java        # REST API endpoints
│   ├── model/
│   │   └── Product.java                  # Entity class
│   └── repository/
│       └── ProductRepository.java        # Data access layer
├── src/main/resources/
│   └── application.properties            # Configuration
├── pom.xml                               # Dependencies
└── README.md                             # This file
```

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6+ (or use included Maven Wrapper)

### Run the Application

```bash
# Using Maven Wrapper (recommended)
./mvnw spring-boot:run

# Or using Maven directly
mvn spring-boot:run
```

The application will start on **http://localhost:8080**

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/products` | Create a new product |
| `GET` | `/products` | Get all products |
| `GET` | `/products/{id}` | Get product by ID |
| `PUT` | `/products/{id}` | Update a product |
| `DELETE` | `/products/{id}` | Delete a product |

## API Usage Examples

### Create a Product
```bash
curl -X POST http://localhost:8080/products \
  -H "Content-Type: application/json" \
  -d '{"name": "Laptop", "price": 999.99}'
```

### Get All Products
```bash
curl http://localhost:8080/products
```

### Get Product by ID
```bash
curl http://localhost:8080/products/1
```

### Update a Product
```bash
curl -X PUT http://localhost:8080/products/1 \
  -H "Content-Type: application/json" \
  -d '{"name": "Gaming Laptop", "price": 1299.99}'
```

### Delete a Product
```bash
curl -X DELETE http://localhost:8080/products/1
```

## Useful URLs

| URL | Description |
|-----|-------------|
| http://localhost:8080/swagger-ui.html | Swagger UI - Interactive API Documentation |
| http://localhost:8080/h2-console | H2 Database Console |
| http://localhost:8080/products | Products API |

### H2 Console Connection

| Field | Value |
|-------|-------|
| JDBC URL | `jdbc:h2:mem:productdb` |
| Username | `sa` |
| Password | *(leave empty)* |

## Configuration

Key settings in `application.properties`:

```properties
spring.application.name=product-service
spring.datasource.url=jdbc:h2:mem:productdb
spring.h2.console.enabled=true
spring.jpa.hibernate.ddl-auto=update
```

## Product Entity

```json
{
  "id": 1,
  "name": "Product Name",
  "price": 99.99
}
```

## HTTP Response Codes

| Code | Description |
|------|-------------|
| 200 | OK - Successful GET/PUT |
| 201 | Created - Successful POST |
| 204 | No Content - Successful DELETE |
| 404 | Not Found - Resource doesn't exist |

## Documentation

For a detailed explanation of the project architecture, Spring Boot concepts, and best practices, see [SPRING_BOOT_MICROSERVICE_GUIDE.md](./SPRING_BOOT_MICROSERVICE_GUIDE.md).

## Author

SLIIT - CTSE Lab 3
