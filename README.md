# 🧪 NestJS Technical Challenge: Personal Finance Tracker API

## 🎯 Objective

Build a RESTful API using **NestJS** that allows users to track their personal finances. The system should allow users to manage **income**, **expenses**, and **monthly budgets**, and give a simple overview of their financial balance.

> **Important:** The application **must follow Domain-Driven Design (DDD)** principles.

---

## 📚 User Stories

### 1. Register a Transaction

As a user, I want to register an **income** or **expense**, so I can track my financial movements.

Each transaction must include:
- `type`: `"income"` or `"expense"`
- `category`: e.g., `"food"`, `"salary"`, `"entertainment"`
- `amount`: number
- `currency`: e.g., `"USD"`, `"EUR"`, `"BRL"`
- `date`: ISO string
- `description`: optional

### 2. Define Monthly Budgets

As a user, I want to define **monthly budgets** per category.

Example:
- `"food"` → `$1000` for June

### 3. View Monthly Summary

As a user, I want to see a **monthly summary** with:
- Total income and expenses
- Budget usage by category
- Warnings if a category exceeded the budget

---

## 🌍 External API Integration

When registering a transaction in a currency **different from the user's base currency** (assume `USD`), the system must:

✅ **Convert the transaction value to USD using a public exchange rate API**.

You may use one of the following APIs:
- https://exchangerate.host/
- https://open.er-api.com/
- https://currencyapi.com/

### Integration Requirements:
- Currency conversion logic must be isolated in the **infrastructure layer**.
- Use dependency injection — do not couple controllers or services directly to external APIs.
- Handle failure scenarios:
  - API unavailable
  - Rate not found
  - Timeouts and retries

---

## 📐 Architecture Guidelines

You must structure your application using **DDD principles**:

- Clear separation of layers:
  - `domain/`: entities, value objects, domain services
  - `application/`: use cases, DTOs
  - `infrastructure/`: persistence, external APIs, config
  - `interface/`: HTTP controllers and routes

- The `domain` layer must not depend on NestJS or any framework-specific logic.
- Use interfaces for dependency boundaries (e.g., `ExchangeRateProvider`).

---

## ✅ Bonus Points

- Unit and integration tests
- Swagger documentation for API
- Use of `@nestjs/config` for environment variables
- Proper validation and error handling
- CI-ready project (lint/test scripts)
- Clean naming, clear commit messages, good documentation

---

## 📦 Delivery Instructions

1. Push your code to a **public GitHub repo**.
2. Include a `README.md` with:
   - Project overview
   - Setup instructions
   - `.env.example` file
   - Postman or cURL examples (optional)

---

## 💡 What We'll Be Evaluating

- Code quality and architecture
- Proper use of Domain-Driven Design
- Clean and consistent abstractions
- API correctness and developer experience
- Real-world thinking (e.g., error handling, data modeling)
- Communication via README and commits
