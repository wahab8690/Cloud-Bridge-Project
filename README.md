# CloudBridge: Serverless Agent Communication System on AWS

## Overview
CloudBridge is a serverless communication system built on AWS using the Model Context Protocol (MCP).  
It enables lightweight, real-time messaging between agents via a fully serverless architecture.

## Architecture
- **API Gateway**: Provides RESTful endpoints for sending and receiving messages.
- **AWS Lambda**: Handles message processing (send and receive functions).
- **DynamoDB**: Stores agent messages for retrieval.
- **IAM Roles**: Secure function permissions.

## Endpoints
**Base Invoke URL:**  
```
https://me7vmk6fcl.execute-api.us-east-2.amazonaws.com/prod
```

### 1. Send a Message (POST)
**Endpoint:**  
```
/send
```
**Method:** `POST`  
**Headers:**  
- `Content-Type: application/json`

**Body Example:**
```json
{
  "sender": "agent1",
  "receiver": "agent2",
  "message": "Hello from Agent1!"
}
```

---

### 2. Receive Messages (GET)
**Endpoint:**  
```
/ReceiveMessageFunction/messages?receiver=agent2&limit=10
```
**Method:** `GET`

**Response Example:**
```json
[
  {
    "sender": "agent1",
    "receiver": "agent2",
    "message": "Hello from Agent1!",
    "timestamp": "2025-08-15T22:35:00Z"
  }
]
```

---

## How It Works
1. An agent sends a message via the **POST /send** endpoint.  
2. The message is stored in **DynamoDB**.  
3. Another agent retrieves messages via the **GET /ReceiveMessageFunction/messages** endpoint.  

---

## Screenshots

<img width="1850" height="950" alt="01" src="https://github.com/user-attachments/assets/9724437a-ce6d-4f2d-9427-80f1aaf5ca1c" />

---
<img width="1870" height="956" alt="02" src="https://github.com/user-attachments/assets/623d138b-57cc-4500-8905-fab8129700fa" />

## Author
- Abdulwahab Hussein  
Associate Degree in Cloud Networking Technology  


