# APIs (Application Programming Interfaces) - Notes

## 1. What is an API?
- **Definition:** An API (Application Programming Interface) is a **set of rules and protocols** that allow software applications to communicate with each other.
- **Analogy:** Think of an API as a waiter in a restaurant—taking your order (request), bringing it to the kitchen (server), and returning with your food (response).
- **Purpose:**
  - Allows software components to interact
  - Enables automation and integration
  - Standardizes communication between services

---

## 2. API Components
### 1. Request
- Sent by the client to the server
- Includes **method, headers, parameters, and body**

### 2. Endpoint
- A specific URL where an API can be accessed
- Example: `https://api.example.com/users`

### 3. HTTP Methods (CRUD Operations)
| Method  | Purpose  | Example  |
|---------|---------|----------|
| **GET** | Read data | `GET /users` |
| **POST** | Create new data | `POST /users` |
| **PUT** | Update existing data | `PUT /users/1` |
| **DELETE** | Remove data | `DELETE /users/1` |

### 4. Response
- Sent by the server back to the client
- Contains **status codes, headers, and body**

---

## 3. API Response Status Codes
| Code | Meaning |
|------|---------|
| **200 OK** | Successful request |
| **201 Created** | New resource created |
| **400 Bad Request** | Client-side error |
| **401 Unauthorized** | Authentication required |
| **403 Forbidden** | Access denied |
| **404 Not Found** | Resource does not exist |
| **500 Internal Server Error** | Server-side issue |

---

## 4. API Types
### 1. REST (Representational State Transfer)
- **Stateless, uses HTTP methods**
- **JSON or XML format**
- Example: `GET https://api.example.com/products`

### 2. GraphQL
- Allows **flexible querying** of only needed data
- Single endpoint (`POST /graphql`)
- Example Query:
  ```graphql
  query {
    user(id: 1) {
      name
      email
    }
  }

## 5. API Best Practices

✅ Use versioning (/api/v1/users)
✅ Return meaningful error messages
✅ Implement pagination for large datasets
✅ Use consistent naming conventions
✅ Secure sensitive data (never expose API keys)
✅ Log API requests & responses for debugging
