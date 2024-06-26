---
layout: content
description:The MoMRA Inspection project aims to streamline the process of inspecting workers' housing by generating visits, scheduling them, and assigning them to inspectors
author: Mawaziny
published_at: 2021-08-01
order: 2
---
The MoMRA Inspection project aims to streamline the process of inspecting workers' housing by generating visits, scheduling them, and assigning them to inspectors. This solution incorporates various APIs, including Sadad (Payment gateway), SMS provider, and two internal APIs. However, a significant challenge arises due to the existing MoMRA system, built with different technologies like ASP.net and ADF. The challenge lies in securely embedding the frontend and exchanging user information between the new microservices architecture and the monolithic architecture. To address this challenge, the project team devised an innovative solution involving iframes, OTP generation, and encrypted JWT token exchange.

## Technologies and Architecture

To overcome the challenges and achieve the project's objectives, the MoMRA Inspection project employed the following technologies and architectural principles:

### Microservices, Event-Sourcing, and CQRS Architecture

The project adopted a microservices architecture, allowing for modular development, scalability, and easier maintenance. Event-sourcing and Command Query Responsibility Segregation (CQRS) principles were implemented to ensure data consistency and separation of read and write operations.

### Spring Boot, Spring Cloud

The microservices were developed using Spring Boot and Spring Cloud, empowering developers to create scalable and resilient applications with ease. Spring Cloud facilitated service discovery, load balancing, and centralized configuration management.

### Angular 11

The frontend of the MoMRA Inspection project was built using Angular 11, a powerful JavaScript framework for developing robust and interactive user interfaces.

### Kubernetes

The project utilized Kubernetes for container orchestration, enabling efficient deployment, scaling, and management of the microservices. Kubernetes components such as Ingress, CoreDNS, ConfigMap, Secret, and auto-scaling were leveraged to ensure a secure and scalable infrastructure.

### Apache Kafka

Apache Kafka, a distributed streaming platform, served as the backbone for event-driven communication between microservices. It facilitated real-time data streaming, messaging, and event sourcing, ensuring seamless integration and data synchronization.

### Prometheus and Apache Elasticsearch

The project employed Prometheus, a monitoring and alerting toolkit, to collect and analyze metrics from the microservices. Apache Elasticsearch was used for indexing and searching log data, enabling efficient troubleshooting and analysis.

### MongoDB

MongoDB, a NoSQL database, was chosen to store and manage data related to inspections. Its flexible document-based model and scalability capabilities suited the project's requirements.

### ksqlDB, Kafka Connect, and Schema Registry

ksqlDB, a streaming SQL engine for Apache Kafka, facilitated real-time data processing and transformations. Kafka Connect was utilized for integrating external systems with Kafka, while Schema Registry ensured data compatibility and consistency.

### NodeJS, GraphQL, and RESTful

NodeJS, along with GraphQL and RESTful APIs, played a crucial role in developing the microservices, enabling efficient communication and data exchange between different components of the system.

### CI/CD - Jenkins, Git, Maven, Jkube deploying on Kubernetes

Continuous Integration and Continuous Deployment (CI/CD) practices were adopted using tools like Jenkins, Git, and Maven. The microservices were deployed on Kubernetes using Jkube, streamlining the build, test, and deployment processes.

## Secure Integration between Microservices and Legacy Systems

To securely embed the frontend and exchange user information between the new microservices architecture and the existing monolithic architecture, the project team implemented a solution involving iframes, OTP generation, and encrypted JWT token exchange.

1. Embedding the Frontend with iframes:
   - The frontend of the new microservices architecture is encapsulated within iframes.
   - These iframes are constructed from the legacy system, ensuring a seamless user experience.
   - To maintain security, the iframes are generated with a one-time password (OTP) obtained from the new system.
   - Opening the iframes outside the system invalidates the OTP, preventing unauthorized access.

2. Encrypted JWT Token Exchange:
   - User information and authentication are managed using JSON Web Tokens (JWT).
   - The new microservices architecture and the monolithic legacy system exchange encrypted JWT tokens to securely transfer user information.
   - Encryption ensures the confidentiality and integrity of the tokens, preventing unauthorized access or tampering.

By implementing the above solution, MoMRA Inspection achieves a secure integration between the new microservices architecture and the existing monolithic system. The iframes, generated with OTP authentication, ensure that the frontend remains embedded within the system and prevents unauthorized access. The encrypted JWT token exchange guarantees secure communication and exchange of user information between the two backend systems.

This innovative approach enables MoMRA to leverage the benefits of a modern microservices architecture while seamlessly integrating with their legacy systems. It ensures data integrity, security, and a smooth user experience throughout the inspection process, ultimately enhancing the efficiency and effectiveness of MoMRA's operations.