---
layout: content
description: The AxA Life Modernization project aimed to address performance issues and limitations in a legacy desktop system written in VB.net with database access to Oracle...
author: Mawaziny
published_at: 2022-11-01
order: 2
---
The AxA Life Modernization project aimed to address performance issues and limitations in a legacy desktop system written in VB.net with database access to Oracle. The system frequently experienced performance problems, particularly during end-of-day and end-of-month processes, leading to system blockages. To overcome these challenges, the project adopted a modernization approach that leveraged various technologies and architectural patterns.

## Description

The modernization approach involved the following key technologies and strategies:

## Microservices Architecture and Database Per Service

The project adopted a microservices architecture to decompose the monolithic system into smaller, independent services. Each microservice was responsible for a specific business capability. To ensure data isolation and scalability, a database-per-service approach was implemented. Each microservice had its dedicated `MongoDB` instance, allowing efficient data management and retrieval.

## Event-Driven Architecture with Kafka

To enable communication and loose coupling between microservices, the project implemented an event-driven architecture using `Kafka` as the messaging system. When users performed search operations, an anti-corruption service called `DBaaS` (Database as a Service) with `GraphQL` was utilized. The service retrieved relevant data from `Oracle` and produced events containing the search results. Other microservices consumed these events to update their respective data stores.

## Strangler Pattern for Vertical Module Modernization

To modernize a vertical module without disrupting other modules, the `strangler` pattern was employed. This involved gradually replacing the functionality of the old system while keeping it running. A `feature flag` was used to determine whether the system should read from `Oracle` and write to `MongoDB` or read from `MongoDB` and fallback to `Oracle` if the data was not available. This approach ensured the uninterrupted functionality of other modules during the modernization process.

## KSQL for Kafka Stream Processing

To filter and join topics within Kafka and create data streams, the project utilized `KSQL`. `KSQL` enabled real-time data processing, combining and transforming events in `Kafka` to generate valuable insights. These streams of data could be consumed by upcoming modules or downstream systems for further processing.

## Audit Service for Change Tracking

To track changes made to the system, an audit service was implemented. The service monitored changes in `MongoDB` using the `CDC` (Change Data Capture) `Kafka connector`. It produced events containing the state before and after the change, along with information about who made the change. These events were consumed by the audit service, which built a collection with the name of the file, the value before and after the change, and the user responsible for the change. This allowed for easy viewing and tracking of values such as name, age, gender, and the corresponding changes made by users.

## Supporting Customer 360 View with Trino

The modernization journey involved moving health policies to a separate system called TOSHFA. However, the challenge arose in providing a comprehensive customer 360 view by retrieving policies from different systems. To address this, the team utilized `Trino` (PrestoSQL) for querying databases with pagination and filters. `Trino` facilitated easy access to multiple databases, allowing the modernized system to retrieve and consolidate policy data from various sources without significant architectural changes.

## Summary

The AxA Life Modernization project successfully transformed a legacy `VB.net` system into a modernized, scalable, and performant architecture. By adopting a microservices architecture, leveraging event-driven patterns with `Kafka`, applying the strangler pattern for vertical module modernization with a feature flag, utilizing `KSQL` for stream processing, and leveraging Trino for data querying, the project achieved its objectives of improving performance and scalability while ensuring uninterrupted functionality during the modernization process.