# 🚀 HR Leave Management System API

This project is built using **.NET 8** and is based on a comprehensive course taught by Microsoft MVP **Trevoir Williams**.

## 🎯 Key Project Focus

The core focus of this repository is the implementation of a robust **ASP.NET Core Web API** designed for Human Resources (HR) leave management. It serves as a practical example for implementing modern, scalable back-end architecture and practices:

* **Architectural Pattern:** Implementation of the **CQRS (Command Query Responsibility Segregation)** pattern.
* **Design Principles:** Strict adherence to **SOLID principles** and **Clean Architecture**.
* **Messaging:** Utilization of the **Mediator pattern** (specifically using MediatR) for efficient command and query handling.
* **Testing:** Comprehensive coverage with both **Unit Tests** and **Integration Tests**.

The application provides essential API functionality for managing employee leave, including handling leave requests, defining leave types, and tracking leave periods.

## 🏗️ Architecture and Project Structure

The solution strictly follows the principles of **Clean Architecture** to ensure optimal separation of concerns, testability, and long-term maintainability. This structure naturally organizes the codebase into distinct, decoupled layers.

> **Dependency Inversion:** This structure ensures that higher-level layers, such as **Application** and **Domain**, are decoupled from lower-level concerns (**Persistence**, **Infrastructure**). This is achieved by depending on **abstractions (interfaces)** rather than concrete implementations.

### Project Breakdown

| Project Name | Layer | Key Responsibilities |
| :--- | :--- | :--- |
| **API** | Presentation | The application's entry point, containing **Controllers** and API **Endpoints**. |
| **Domain** | Core Layer | Holds **Entities**, **Enums**, **Exceptions**, and **Domain Events**. It defines the core business logic and rules. |
| **Application** | Use Case Layer | Coordinates business logic flow. Implements **CQRS Features (Commands & Queries)**, **Handlers**, and application-level **Interfaces** (e.g., repository interfaces). |
| **Infrastructure** | Infrastructure | Provides concrete implementations for external concerns (e.g., Email Services, File Storage) defined by interfaces in the Application layer. |
| **Persistence** | Infrastructure | Manages data access implementation, typically utilizing **Entity Framework Core** for database interactions. |
| **Identity** | Security | Dedicated project for managing user identity, roles, and security/authentication concerns. |
| **BlazorUI** | Presentation (Briefly Covered) | A basic UI implementation using **Blazor** to consume the API endpoints. (Note: The API is the primary focus of this project). |
| **Unit and Integration Tests** | Testing | Contains comprehensive test suites for validating application logic and integration points. |

## 🧪 Testing Strategy

The project includes dedicated testing projects to ensure a high level of code quality and functional reliability:

* **Unit Tests:** Focused on testing individual components and pure business logic (within the Domain and Application layers) in isolation.
* **Integration Tests:** Designed to verify that different application layers and external dependencies (like the database, via the Persistence layer) work correctly together.
