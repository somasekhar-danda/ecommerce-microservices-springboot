# E-Commerce Microservices Backend (Java + Spring Boot)

This repository contains a **microservices-based E-Commerce backend** built using:

- **Java 17+**
- **Spring Boot**
- **Spring Cloud (Eureka, API Gateway)**
- **REST APIs**
- **MySQL**

Designed as a **portfolio + learning project** to showcase experience with **microservices architecture, service discovery, API gateway routing, and database-backed services**.

---

## 🧩 Architecture Overview (Phase 1)

**Services in this repo (Phase 1):**

1. **discovery-server**
   - Spring Cloud **Eureka Server**
   - All other services register themselves here

2. **api-gateway**
   - Routes external client requests to the correct microservice
   - Example:
     - `/api/products/**` → `product-service`
     - `/api/orders/**` → `order-service`

3. **product-service**
   - Manages products
   - REST APIs for:
     - Create product
     - Update product
     - Get product by ID
     - List all products
   - Persists data in **MySQL**

4. **order-service**
   - Manages customer orders
   - Places new orders and fetches order details
   - Communicates with `product-service` to validate product and (later) stock availability
   - Persists data in **MySQL**

---

## 📁 Repository Structure

```text
ecommerce-microservices-springboot/
├── discovery-server/        # Eureka server for service discovery
├── api-gateway/             # API Gateway for routing requests
├── product-service/         # Product management microservice
├── order-service/           # Order management microservice
├── docs/
│   ├── architecture-diagram.md   # High-level architecture notes/diagrams
│   └── api-specs.md              # API documentation (endpoints, payloads)
└── README.md                # This file
