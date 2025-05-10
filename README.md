# Microservices Containerization Assignment

## 📦 Overview

This project involves containerizing four Node.js microservices—**User**, **Product**, **Order**, and **Gateway**—and orchestrating them using Docker Compose.

Each service is independently built and exposed on different ports. The Gateway service aggregates the other three.

---

## 📁 Project Structure
```
Microservices/
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

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone <https://github.com/shakti468/Microservices-Task>
```

## Docker file for all these services
### Code 
```bash
FROM node:16
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### Screenshot 
![image](https://github.com/user-attachments/assets/78e3fde9-5aa6-45cb-82e0-f3b0158a1f6e)


---

## docker-compose.yml

### Code 
```
version: '3'
services:
  user-service:
    build:
      context: ./user-service
    ports:
      - "3000:3000"
    networks:
      - app-network

  product-service:
    build:
      context: ./product-service
    ports:
      - "3001:3001"
    networks:
      - app-network

  order-service:
    build:
      context: ./order-service
    ports:
      - "3002:3002"
    networks:
      - app-network

  gateway-service:
    build:
      context: ./gateway-service
    ports:
      - "3003:3003"
    networks:
      - app-network

networks:
  app-network:
    driver: bridge
```

### Screenshot

![image](https://github.com/user-attachments/assets/bef25eba-410e-444f-9cfd-a73338ca058d)

---


## Build the Docker Containers
```
docker-compose build
```

### Screenshot
![image](https://github.com/user-attachments/assets/a4f88b29-ab46-4518-a616-5cb122f8891f)

--- 

## Start All Services

```
docker-compose up

```

### Screenshots
![image](https://github.com/user-attachments/assets/5ce7098e-f836-4826-a421-572aadb78eb1)

---
## 🌐 Service Endpoints
- Once the containers are running, you can access the services at the following URLs:

## User Service
- URL: http://localhost:3000/users
### Screenshot
![image](https://github.com/user-attachments/assets/ad9f505b-7a0a-4ea5-8f13-919951548e54)

---

## Product Service
- URL: http://localhost:3001/products

### Screenshots

![image](https://github.com/user-attachments/assets/6e45166f-bd9f-43e9-8d01-c6a195493e93)

---

## Order Service
- URL: http://localhost:3002/orders

### Screenshot
![image](https://github.com/user-attachments/assets/f89e1c89-6fa8-458c-8bb9-60e31b096a05)

---

#  Gateway Service (API Aggregator)

- Users: http://localhost:3003/api/users

### Screenshot

![image](https://github.com/user-attachments/assets/317d99a7-a8b1-4c87-946a-db5abe85a7f4)

---

- Products: http://localhost:3003/api/products

### Screenshot
![image](https://github.com/user-attachments/assets/e88f81ff-57b0-44af-923e-c5c09bdf2da5)

---

- Orders: http://localhost:3003/api/orders

### Screenshots 

![image](https://github.com/user-attachments/assets/87d9c98c-f7d4-4fb9-8b49-e97cb8167966)

---

### Stop all services:
```
docker-compose down

```
