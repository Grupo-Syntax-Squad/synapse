# 📡 **Synapse API Endpoints Documentation**

## 📋 **Overview**

This document provides comprehensive documentation for all Synapse API endpoints, including request/response formats, authentication requirements, and usage examples. The API follows RESTful principles with JWT-based authentication and role-based access control.

---

## 🔗 **Base Configuration**

- **API Version**: v1
- **Authentication**: JWT tokens via HTTPOnly cookies
- **Content Type**: `application/json`
- **Rate Limiting**: To be implemented (see security considerations)

---

## 🗺️ **Endpoints Mapping**

### 🔑 **Authentication Module (`/auth`)**

#### **POST `/auth/login`**

User authentication with email and password.

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Response (200 OK):**

```json
{
  "message": "OK"
}
```

**Cookies Set:**

- `access_token`: JWT access token (30min expiry)
- `refresh_token`: JWT refresh token (7 days expiry)

**Error Responses:**

- `401 Unauthorized`: Invalid credentials
- `403 Forbidden`: User account deactivated

---

#### **POST `/auth/logout`**

Terminate user session and clear authentication cookies.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Response (200 OK):**

```json
{
  "message": "Logout realizado com sucesso"
}
```

**Cookies Cleared:**

- `access_token`
- `refresh_token`

---

#### **POST `/auth/refresh`**

Renew access token using refresh token.

**Headers Required:**

```
Cookie: refresh_token=<refresh_jwt_token>
```

**Response (200 OK):**

```json
{
  "message": "OK"
}
```

**New Cookies Set:**

- `access_token`: New JWT access token
- `refresh_token`: New JWT refresh token

**Error Responses:**

- `401 Unauthorized`: Invalid or expired refresh token

---

### 👤 **Users Module (`/users`)**

#### **POST `/users/register`**

Register a new user in the system.

**Request Body:**

```json
{
  "username": "newuser",
  "email": "newuser@example.com",
  "password": "securepassword123"
}
```

**Response (200 OK):**

```json
{
  "message": "OK"
}
```

**Error Responses:**

- `400 Bad Request`: Validation errors (empty fields, password too short)
- `409 Conflict`: Username or email already exists

---

#### **GET `/users/me`**

Retrieve current authenticated user data.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Response (200 OK):**

```json
{
  "data": {
    "id": 1,
    "username": "currentuser",
    "email": "currentuser@example.com",
    "is_admin": false,
    "is_active": true,
    "receive_email": true,
    "last_update": "2025-09-29T10:30:00Z",
    "last_access": "2025-09-29T15:45:00Z"
  },
  "message": "OK"
}
```

---

### 📊 **Reports Module (`/reports`)**

#### **GET `/reports/`**

List report history with optional date filtering.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Query Parameters:**

- `start_date` (optional): Start date filter (YYYY-MM-DD format)
- `end_date` (optional): End date filter (YYYY-MM-DD format)

**Example Request:**

```
GET /reports/?start_date=2025-09-01&end_date=2025-09-30
```

**Response (200 OK):**

```json
{
  "data": [
    {
      "id": 1,
      "name": "Monthly Sales Report",
      "created_at": "2025-09-29T08:00:00Z",
      "content": "Report content here...",
      "delivered_to": [
        {
          "user_id": 1,
          "username": "user1"
        }
      ]
    }
  ],
  "message": "OK"
}
```

---

#### **GET `/reports/{report_id}`**

View specific report details by ID.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Path Parameters:**

- `report_id`: Integer - Report identifier

**Response (200 OK):**

```json
{
  "data": {
    "id": 1,
    "name": "Monthly Sales Report",
    "created_at": "2025-09-29T08:00:00Z",
    "content": "Detailed report content...",
    "delivered_to": [
      {
        "user_id": 1,
        "username": "user1"
      }
    ]
  },
  "message": "OK"
}
```

**Error Responses:**

- `404 Not Found`: Report not found

---

#### **POST `/reports/send`** (Admin Only)

Send report to subscribers via email.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Request Body:**

```json
{
  "subject": "Monthly Report",
  "report_id": 1
}
```

**Response (200 OK):**

```json
{
  "message": "O envio do relatório está sendo processado em background."
}
```

**Error Responses:**

- `403 Forbidden`: User is not admin

---

#### **POST `/reports/generate`** (Admin Only)

Generate new report on demand.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Response (200 OK):**

```json
{
  "message": "Report generated sucessfully"
}
```

---

### 💬 **Chat/NLP Module (`/chat`) [Planned]**

#### **WebSocket `/chat/connect`**

Establish WebSocket connection for real-time chat.

**Connection URL:**

```
ws://localhost:8000/chat/connect
```

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Connection Events:**

- `connect`: Connection established
- `message`: Receive AI response
- `disconnect`: Connection closed

---

#### **POST `/chat/send`** [Planned]

Send message to NLP agent.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Request Body:**

```json
{
  "message": "What are the sales trends for this month?",
  "conversation_id": "conv_123" // optional
}
```

**Response (200 OK):**

```json
{
  "data": {
    "response": "Based on the data, sales have increased by 15% this month...",
    "conversation_id": "conv_123",
    "message_id": "msg_456"
  },
  "message": "OK"
}
```

---

#### **GET `/chat/history`** [Planned]

Retrieve user conversation history.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Query Parameters:**

- `conversation_id` (optional): Filter by specific conversation
- `limit` (optional): Number of messages to retrieve (default: 50)
- `offset` (optional): Pagination offset (default: 0)

**Response (200 OK):**

```json
{
  "data": [
    {
      "message_id": "msg_456",
      "conversation_id": "conv_123",
      "user_message": "What are the sales trends?",
      "ai_response": "Sales have increased by 15%...",
      "timestamp": "2025-09-29T14:30:00Z"
    }
  ],
  "message": "OK"
}
```

---

### 🛠️ **Administrative Module (`/admin`) [Planned]**

#### **GET `/admin/users`** (Admin Only)

List all users in the system.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Query Parameters:**

- `status` (optional): Filter by user status (`active`, `inactive`)
- `limit` (optional): Number of users per page (default: 50)
- `offset` (optional): Pagination offset (default: 0)

**Response (200 OK):**

```json
{
  "data": [
    {
      "id": 1,
      "username": "user1",
      "email": "user1@example.com",
      "is_admin": false,
      "is_active": true,
      "receive_email": true,
      "last_access": "2025-09-29T15:45:00Z"
    }
  ],
  "message": "OK"
}
```

---

#### **PATCH `/admin/users/{user_id}/toggle-status`** (Admin Only)

Activate or deactivate a user account.

**Headers Required:**

```
Cookie: access_token=<jwt_token>
```

**Path Parameters:**

- `user_id`: Integer - User identifier

**Response (200 OK):**

```json
{
  "data": {
    "user_id": 1,
    "is_active": false
  },
  "message": "User status updated successfully"
}
```

---

### 🔧 **System Endpoints (`/`)**

#### **GET `/`**

Health check endpoint.

**Response (200 OK):**

```json
{
  "message": "Synapse API is running"
}
```

---

#### **POST `/test`** (Development Only)

Test endpoint for development purposes.

**Request Body:**

```json
{
  "name": "test_data"
}
```

**Response (200 OK):**

```json
{
  "message": "Test completed successfully"
}
```

---

## 🔒 **Authentication & Authorization**

### **JWT Token Structure**

**Access Token Payload:**

```json
{
  "sub": "1", // User ID
  "type": "access", // Token type
  "exp": 1727634000 // Expiration timestamp
}
```

**Refresh Token Payload:**

```json
{
  "sub": "1", // User ID
  "type": "refresh", // Token type
  "exp": 1728238800 // Expiration timestamp
}
```

### **Permission Requirements**

| Endpoint Category | Admin Required | User Required | Public Access |
| ----------------- | :------------: | :-----------: | :-----------: |
| Authentication    |       ❌       |      ❌       |      ✅       |
| User Registration |       ❌       |      ❌       |      ✅       |
| User Profile      |       ❌       |      ✅       |      ❌       |
| Reports View      |       ❌       |      ✅       |      ❌       |
| Reports Send      |       ✅       |      ❌       |      ❌       |
| Admin Panel       |       ✅       |      ❌       |      ❌       |
| Chat/NLP          |       ❌       |      ✅       |      ❌       |

---

## 📝 **Error Handling**

### **Standard Error Response Format**

```json
{
  "detail": "Error description",
  "status_code": 400
}
```

### **Common HTTP Status Codes**

| Code | Description           | When It Occurs           |
| ---- | --------------------- | ------------------------ |
| 200  | OK                    | Successful request       |
| 400  | Bad Request           | Invalid request data     |
| 401  | Unauthorized          | Missing or invalid token |
| 403  | Forbidden             | Insufficient permissions |
| 404  | Not Found             | Resource not found       |
| 409  | Conflict              | Resource already exists  |
| 422  | Unprocessable Entity  | Validation errors        |
| 500  | Internal Server Error | Unexpected server error  |

---

## 🔍 **Testing & Development**

### **Interactive API Documentation**

Access the Swagger UI for interactive testing:

```
http://localhost:8000/docs
```

### **Example cURL Commands**

**Login:**

```bash
curl -X POST "http://localhost:8000/auth/login" \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "password": "password123"}'
```

**Get Current User:**

```bash
curl -X GET "http://localhost:8000/users/me" \
  -H "Cookie: access_token=<jwt_token>"
```

**List Reports:**

```bash
curl -X GET "http://localhost:8000/reports/" \
  -H "Cookie: access_token=<jwt_token>"
```

---

## 🚀 **API Versioning & Future Enhancements**

### **Current Version: v1**

- Basic authentication and user management
- Report generation and delivery
- Foundation for chat/NLP features

### **Planned Enhancements (v1.1)**

- WebSocket chat implementation
- Advanced filtering and search
- Bulk operations for admin
- API rate limiting
- Enhanced error responses with field-level validation

### **Future Considerations (v2)**

- GraphQL support
- Webhook notifications
- Advanced analytics endpoints
- Third-party integrations API

---

## 📖 **Additional Resources**

- **[RBAC Documentation](./rbac.md)** - Security model and permissions
- **[Database Schema](./db_model.md)** - Data models and relationships

---

**📝 Last Updated:** 29/09/2025  
**👤 Responsible:** Synapse Development Team  
**🔄 Next Review:** Sprint 3 Start  
**📊 API Version:** v1.0
