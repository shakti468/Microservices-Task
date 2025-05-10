# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!


# 🐳 Microservices Containerization Assessment

## 📌 Objective

Containerize and orchestrate a Node.js microservices-based application using Docker and Docker Compose. The application includes four services:
- User Service
- Product Service
- Order Service
- Gateway Service

---

## 📁 Project Structure
```
submission/
├── user-service/
│ └── Dockerfile
├── product-service/
│ └── Dockerfile
├── order-service/
│ └── Dockerfile
├── gateway-service/
│ └── Dockerfile
├── docker-compose.yml
└── README.md
```


---

## ⚙️ Setup Instructions

### 1. Prerequisites

Ensure the following are installed:
- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Docker Compose

---

### 2. Build and Run All Services

Navigate to the root of your project directory, then run:

```bash
docker-compose build
docker-compose up

