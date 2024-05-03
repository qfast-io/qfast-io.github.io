---
layout: content
description: The Etisalat Marketplace admin tool is a powerful solution designed to streamline the management of products,...
author: Mawaziny
published_at: 2022-11-01
order: 1
---
The Etisalat Marketplace admin tool is a powerful solution designed to streamline the management of products, quantities, and availability within the Etisalat Marketplace and SuperApp ecosystem. This system empowers both Etisalat administrators and merchant administrators to efficiently collaborate and ensure smooth operations.

## Description

The purpose of this project is to create an admin tool for Etisalat Marketplace / SuperApp using a Microservices and event-driven architecture. This ensures a scalable, flexible, and maintainable system for managing product data and facilitating seamless communication between administrators.

The admin tool is built using Microservices architecture, where the application is divided into smaller, loosely coupled services. Each Microservices focuses on a specific functionality, such as product management, inventory control, or integration with merchant systems. This approach allows for independent development, deployment, and scaling of services.

To enable real-time communication and responsiveness, the system utilizes an event-driven architecture. Events play a crucial role in triggering actions and propagating changes across the system. For example, when a merchant updates the quantity of a product, an event is generated and propagated to relevant services to reflect the changes in real-time.

Through a user-friendly interface, both Etisalat administrators and merchant administrators can efficiently manage product quantities and availability. The admin tool allows for tasks such as adding new products, updating stock levels, and monitoring inventory. Additionally, the system supports direct integration with the merchant systems, ensuring seamless synchronization of product data, quantities, and availability.

## Summary

The Etisalat Marketplace admin tool, implemented using a Microservices and event-driven architecture, offers a robust and scalable solution for managing products, quantities, and availability. It empowers administrators to effectively collaborate and streamline operations within the marketplace ecosystem. The user-friendly interface and direct integration with merchant systems enhance efficiency and accuracy in managing inventory.

## Technologies
The Technolgies used in this project:
* Microservices built with Spring boot
* Event streaming plaform - Apache Kafka for interservice communication
* Tibco as ESB between Microservices and internal systems and also for integration with external systems
* Oracle database