# API Gateway Service

This repository contains the API Gateway for the **SE4458 Final Project** – a job search platform inspired by Kariyer.net. The gateway serves as a centralized entry point for routing all HTTP requests to the corresponding microservices, including the Admin Service, Job Search Service, Notification Service, and AI Agent Service.

---

## 📹 Demo Video

[**VIDEO LINK**](https://drive.google.com/drive/folders/1JRjiEz0hcjbIAbnUIZd1u3qLuDfy4Lwg?usp=sharing)

---

## 🔗 Final Deployed URLs

- [**Frontend Application**](https://four458frontend.onrender.com)
- [**API Gateway**](https://four458aiagent.onrender.com)
- [**Admin Service**](https://four458adminservice.onrender.com)
- [**Job Search Service**](https://four458jobsearchservice.onrender.com)
- [**Notification Service**](https://four458notificationservice.onrender.com)
- [**AI Agent Service**](https://four458jobagent.onrender.com)

---

## 📌 Features

- Centralized routing for all backend services.
- Route mapping with support for service versioning.
- CORS configuration for frontend-backend communication.
- Scalable architecture for cloud deployment.

---

## 🧠 Design and Assumptions

- All services are accessed via a single entry point through this API Gateway.
- Route definitions use simple path matching (e.g., `/api/v1/job-posting/**` → Job Posting Service).
- JWT-based authentication may be supported if required for specific service routes.
- Services are assumed to be containerized and deployed independently.
- CORS origins are manually configured to avoid `*` usage when credentials are required.

---

## 🛠️ Tech Stack

- Java + Spring Cloud Gateway
- Spring Boot
- Maven
- Docker

---

## 📂 Project Structure

```
api-gateway/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/example/apigateway/
│       │       ├── ApiGatewayApplication.java
│       │       └── config/
│       │           └── GatewayConfig.java
│       └── resources/
│           ├── application.yml
│           └── ...
├── Dockerfile
└── pom.xml
```

---

## 🧪 Running Locally

1. **Clone the repository:**

```bash
git clone https://github.com/Sehrank8/4458ApiGateway.git
cd 4458ApiGateway
```

2. **Build and Run:**

```bash
./mvnw clean install
./mvnw spring-boot:run
```

3. **Docker (Optional):**

```bash
docker build -t api-gateway .
docker run -p 8080:8080 api-gateway
```

---
## 🧾 ER Diagram

![ER DIAGRAM](https://github.com/Sehrank8/4458ApiGateway/blob/master/job_search_er_diagram.png)

---

## 🧩 Problems Encountered

- CORS misconfiguration can lead to HTTP500 errors if `allowedOrigins` is set to `*` while `allowCredentials=true`. Used `allowedOriginPatterns` instead.
- Dockerfiles were redone 5 times
- I am bad at frontend
- Gateway configuration needed to be changed 15-20 times before it could work
- CORS error from frontend
- Deployed instance of my repos had a problem with the vhost of rabbitMQ, they defaulted to `/` instead of the set value
- AI agent started writing poems for some reason?

![AI POEMS](https://github.com/Sehrank8/4458ApiGateway/blob/master/AI_POEM.jpg)
  
---


