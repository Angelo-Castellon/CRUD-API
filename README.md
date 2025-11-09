# CRUD API - Movie Management

A lightweight RESTful API built with Go and Gorilla Mux for managing a movie database with full CRUD operations.

![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white) ![REST API](https://img.shields.io/badge/REST-API-green?style=for-the-badge)

## 🎯 Overview

A simple yet functional REST API demonstrating fundamental CRUD (Create, Read, Update, Delete) operations using Go's net/http package and the Gorilla Mux router. The API manages a collection of movies with associated director information, using in-memory storage for data persistence during runtime.

**Purpose**: Learning project to understand RESTful API design, HTTP methods, JSON handling, and routing in Go.

## 🚀 Tech Stack

- **Language**: Go (Golang)
- **Router**: Gorilla Mux
- **Data Storage**: In-memory slice (no database)
- **Data Format**: JSON

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/movies` | Retrieve all movies |
| `GET` | `/movies/{id}` | Retrieve a specific movie by ID |
| `POST` | `/movies` | Create a new movie |
| `PUT` | `/movies/{id}` | Update an existing movie |
| `DELETE` | `/movies/{id}` | Delete a movie by ID |

## 📦 Data Model

**Movie Structure:**
```json
{
  "id": "1",
  "isbn": "1649456",
  "title": "Movie Title",
  "director": {
    "first_name": "John",
    "last_name": "Doe"
  }
}
```

## 🛠️ Installation & Setup

### Prerequisites

- Go 1.16 or higher installed
- Basic understanding of REST APIs

### Installation Steps

1. **Clone the repository**:
```bash
git clone https://github.com/Angelo-Castellon/CRUD-API.git
cd CRUD-API
```

2. **Install dependencies**:
```bash
go mod init CRUD-API
go get -u github.com/gorilla/mux
```

3. **Run the server**:
```bash
go run main.go
```

The server will start on `http://localhost:8080`

## 💻 Usage Examples

### Get All Movies
```bash
curl http://localhost:8080/movies
```

**Response:**
```json
[
  {
    "id": "1",
    "isbn": "1649456",
    "title": "Movie 1",
    "director": {
      "first_name": "John",
      "last_name": "Smith"
    }
  },
  ...
]
```

### Get Single Movie
```bash
curl http://localhost:8080/movies/1
```

### Create New Movie
```bash
curl -X POST http://localhost:8080/movies \
  -H "Content-Type: application/json" \
  -d '{
    "isbn": "9876543",
    "title": "New Movie",
    "director": {
      "first_name": "Jane",
      "last_name": "Doe"
    }
  }'
```

### Update Movie
```bash
curl -X PUT http://localhost:8080/movies/1 \
  -H "Content-Type: application/json" \
  -d '{
    "isbn": "1649456",
    "title": "Updated Movie Title",
    "director": {
      "first_name": "John",
      "last_name": "Smith"
    }
  }'
```

### Delete Movie
```bash
curl -X DELETE http://localhost:8080/movies/1
```

## 🧪 Testing with Postman

1. Import the API into Postman
2. Set base URL: `http://localhost:8080`
3. Test each endpoint with appropriate HTTP methods
4. View responses in JSON format

## 📂 Project Structure
```
CRUD-API/
├── main.go           # Main application file with all handlers
├── go.mod            # Go module dependencies
└── README.md         # Project documentation
```

## 🎓 What I Learned

- **RESTful API Design**: Implementing standard CRUD operations with proper HTTP methods
- **Go HTTP Handling**: Using `net/http` package for server creation and request handling
- **Gorilla Mux Router**: URL routing and parameter extraction
- **JSON Encoding/Decoding**: Marshaling and unmarshaling JSON data in Go
- **Struct Tags**: Using JSON tags for proper serialization
- **In-Memory Data Storage**: Managing application state with Go slices
- **HTTP Headers**: Setting appropriate content types for API responses

## ⚠️ Limitations

- **No Database**: Data is stored in memory and lost when server restarts
- **No Authentication**: No security or user authentication implemented
- **No Input Validation**: Limited validation on incoming data
- **Simple ID Generation**: Uses random integers, not production-ready

## 🔮 Future Enhancements

Potential improvements for learning purposes:

- [ ] Add PostgreSQL/MySQL database integration
- [ ] Implement input validation and error handling
- [ ] Add JWT authentication
- [ ] Create unit tests for all endpoints
- [ ] Add pagination for GET all movies
- [ ] Implement search and filtering functionality
- [ ] Add Docker containerization
- [ ] Create Swagger/OpenAPI documentation

## 📚 Dependencies
```go
github.com/gorilla/mux v1.8.0
```

## 🤝 Contributing

This is a learning project, but suggestions and improvements are welcome! Feel free to fork and experiment.

## 📄 License

This project is open source and available for educational purposes.

---

**Built with** ❤️ **while learning Go and REST API development**
