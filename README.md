# Food Delivery Application

End-to-end enterprise-style food delivery platform based on the project recommendation: Java 8, Spring Boot microservices, DTO + MapStruct, Eureka service discovery, AngularJS micro frontend, JUnit/Mockito/Postman-friendly REST APIs, Docker, MySQL/MongoDB, AWS/EKS-ready Kubernetes manifests, Jenkins/SonarQube/ArgoCD deployment assets.

## Services
- discovery-server: Eureka registry
- gateway-service: Spring Cloud Gateway entry point
- user-service: users and addresses (MySQL)
- restaurant-service: restaurants/menu (MongoDB)
- order-service: cart/order lifecycle (MySQL; calls restaurant/payment)
- payment-service: payment simulation (MySQL)
- frontend: AngularJS single-page client

## Run locally
1. Start MySQL and MongoDB with `docker compose up -d mysql mongodb`.
2. Start discovery-server, then gateway-service, then domain services.
3. Open `frontend/index.html` or serve the frontend from any static server.

Default ports: Eureka 8761, Gateway 8080, User 8081, Restaurant 8082, Order 8083, Payment 8084.

The payment implementation is deliberately a local simulation; replace it with a real provider adapter for production.
