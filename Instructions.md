# Popcorn Palace - Backend Instructions

## Technologies Used

- Java 17
- Spring Boot 3
- Maven
- JUnit 5
- Mockito
- PostgreSQL
- Docker
- Lombok
- 
---

## How to Run the Project:

### 1. Prerequisites

Make sure you have the following installed:

- Java 17 or higher
- Maven 3.8+
- Docker (for running PostgreSQL locally)
- An IDE (IntelliJ IDEA)

---

### 2. Clone the Repository

```bash
git clone https://github.com/your-username/popcorn-palace.git
cd popcorn-palace
```

---

### 3. (Optional) Start PostgreSQL Using Docker

If you want to run PostgreSQL locally with Docker:

```bash
docker-compose up -d
```
This will start a PostgreSQL container on port `5432` using the `docker-compose.yml` file.

---

### ⚙4. Build the Project

To compile the project and download all dependencies:

```bash
mvn clean install
```

---

### ▶5. Run the Application

To start the backend server:

```bash
mvn spring-boot:run
```

Once started, the API will be available at:

```
http://localhost:8080
```

---

## Running the Tests

All unit tests are written using JUnit 5 and Mockito.  
To run all tests:

```bash
mvn test
```
You can also run tests directly from your IDE.

---

### The following components are fully covered by unit tests:

- `MovieService`
- `ShowtimeService`
- `BookingService`

Edge cases, validation rules, and error scenarios are thoroughly tested.

---

## API Endpoints

### Movies
| Method | Endpoint                 | Description             |
|--------|--------------------------|-------------------------|
| GET    | `/movies/all`            | Get all movies          |
| POST   | `/movies`                | Add new movie           |
| POST   | `/movies/update/{title}` | Update movie by title   |
| DELETE | `/movies/{title}`        | Delete movie by title   |

---

### Showtimes
| Method | Endpoint                 | Description               |
|--------|--------------------------|---------------------------|
| GET    | `/showtimes/{id}`        | Get showtime by ID        |
| POST   | `/showtimes`             | Add new showtime          |
| POST   | `/showtimes/update/{id}` | Update showtime by ID     |
| DELETE | `/showtimes/{id}`        | Delete showtime by ID     |

---

### Bookings
| Method | Endpoint     | Description                          |
|--------|--------------|--------------------------------------|
| POST   | `/bookings`  | Book a seat for a specific showtime  |

---

## API Overview

The backend provides a RESTful API for managing:

- Movies — add, update, delete, list
- Showtimes — add, update, delete, get by ID
- Bookings — seat booking with validation to prevent double-booking
  All inputs are validated, and custom error messages are returned as JSON

---

### Additional Notes

- All inputs are validated through dedicated validators.
- Errors are handled globally with `@RestControllerAdvice`, returning informative JSON messages.
- You can use tools like `Postman`, `Insomnia`, or `curl` to test the API manually.
- Database configuration can be found in `application.properties` and can be overridden using environment variables.

---

## Testing Technologies Used

- `spring-boot-starter-test`
- JUnit 5 (`@Test`, `@BeforeEach`, `assertThrows`, etc.)
- Mockito (`mock()`, `verify()`, etc.)

