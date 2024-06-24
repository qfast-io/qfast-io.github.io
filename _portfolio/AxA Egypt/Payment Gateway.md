---
layout: content
description: The Payment Gateway project is a system developed for AXA Egypt. It consists of four microservices, Payment Aggregator, Paymob Integration Adaptor, Fawry Integration Adaptor...
author: Mawaziny
published_at: 2022-11-01
order: 2
---
The Payment Gateway project is a system developed for AXA Egypt. It consists of four microservices: Payment Aggregator, Paymob Integration Adaptor, Fawry Integration Adaptor, and File Processor. The system facilitates payment processing by integrating with external payment providers and handling recurring payments based on policy payment installments.

## Description

The Payment Gateway project comprises the following components:

### Payment Aggregator

The Payment Aggregator microservice is responsible for receiving payment requests through a REST endpoint or Kafka events. It acts as the central hub for payment processing. When a payment request is received, the Payment Aggregator sends the request to the appropriate integration service based on the payment method specified (Paymob or Fawry). It also handles recurring payments by coordinating with the policy payment installments.

### Paymob Integration Adaptor

The Paymob Integration Adaptor microservice holds all the integration details related to the Paymob payment provider. It acts as an intermediary between the Payment Aggregator and Paymob, facilitating communication and transaction processing. The integration adaptor handles the necessary authentication, data mapping, and API calls required for payment processing with Paymob.

### Fawry Integration Adaptor

Similar to the Paymob Integration Adaptor, the Fawry Integration Adaptor microservice holds all the integration details specific to the Fawry payment provider. It enables communication between the Payment Aggregator and Fawry for payment processing. The integration adaptor handles the necessary authentication, data mapping, and API calls required for payment processing with Fawry.

### File Processor

The File Processor microservice is responsible for reading files from an FTP server and uploading files to the FTP server for bank integrations. This service facilitates the exchange of payment-related files, such as transaction reports or reconciliation files, between the Payment Gateway system and banks.

### Kafka and Schema Registry

The architecture of the Payment Gateway project includes the usage of Kafka, a distributed streaming platform. Kafka acts as the messaging system for communication between microservices, allowing the exchange of payment-related events and data. Additionally, the project incorporates a Schema Registry to enforce data schema compatibility and evolution across different microservices, ensuring data consistency and interoperability.

## Summary

The Payment Gateway project developed for AXA Egypt consists of four microservices: Payment Aggregator, Paymob Integration Adaptor, Fawry Integration Adaptor, and File Processor. These microservices work together to facilitate payment processing, integrating with external payment providers (Paymob and Fawry) and handling recurring payments based on policy payment installments. The project utilizes Kafka as the messaging system and incorporates a Schema Registry for data consistency and compatibility.