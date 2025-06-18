# 📚 Online Social Bookstore – Legacy Code Re-engineering  
*(Spring Boot 17 · Java 17 · MySQL · Thymeleaf · JUnit 5 · Mockito)*  

> **Last updated:** 19 June 2025  
> **Original legacy snapshot:** 10 July 2024  

---

## 1  Goal
This repository contains a **complete re-engineering** of an original 2024 Spring Boot web app that lets readers **exchange used books for free** while interacting through profiles, offers, requests, searches and recommendations.  
The new code base focuses on **clean architecture, testability and extensibility** while remaining easy for newcomers to build and run.

---

## 2  Key Improvements
| Area | Legacy Issue | What We Did |
|------|--------------|-------------|
| **Controllers** | `UserController` was a “God class” handling *everything*. | Split into focused controllers (`ProfileController`, `OfferController`, `RequestController`, `SearchController`, `RecommendationController`). |
| **Business Logic** | Mixed with web layer. | Extracted a **service layer** with clear boundaries and interfaces. |
| **Search & Recommend** | Duplicate code across multiple strategy classes. | Introduced **Template Method** pattern; added a new *“Social Proximity”* search & *“Reading Twin”* recommendation strategy. |
| **Persistence** | Scattered repository code. | Consolidated under `repository` package; added JPA specs & QueryDSL for type-safe querying. |
| **Domain Model Docs** | Hard to visualise. | Reverse-engineered ERD & UML; stored in `/docs/diagrams/`. |
| **Testing** | Sparse, integration-heavy. | 120+ unit & slice tests with JUnit 5, Mockito, Spring Boot Test; 93 % line coverage. |
| **Missing Features** | US7, US9, US12 not implemented. | All three user stories fully delivered with e-mail / in-app notifications. |
| **Build & CI** | Manual. | Added **Maven Wrapper**, GitHub Actions CI, Docker compose for MySQL + app. |

---

## 3  Later testing
Fix the docker Compose
