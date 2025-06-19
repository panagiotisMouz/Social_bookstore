  Online Social Bookstore – Legacy Code Re-engineering

A full re-engineering of a 2024 Spring Boot application that enables users to **exchange used books**, interact socially via **offers**, **requests**, **profiles**, and **recommendations**.  
The project focuses on improving **architecture**, **modularity**, and **testability**, while remaining easy to build and extend.

 Original codebase: July 2024  
 Last updated: June 2025

---

##  Project Goals

- Refactor a monolithic legacy codebase into a clean, modular system
- Improve test coverage and reliability
- Simplify contribution and extension for new developers

---

##  Tech Stack

- **Java 17**, **Spring Boot 3**, **MySQL**
- **Thymeleaf** (frontend)
- **JUnit 5**, **Mockito**, **Spring Boot Test**
- **Maven**, **GitHub Actions**, **Docker Compose**

---

##  Key Improvements

| Area             | Legacy Issues                                 | Improvements Made                                      |
|------------------|-----------------------------------------------|--------------------------------------------------------|
| Controllers       | One large UserController ("God class")         | Split into focused controllers by concern              |
| Business Logic    | Mixed with web layer                          | Separated service layer with clear interfaces          |
| Search & Recommend| Code duplication                              | Used Template Method pattern; added new strategies     |
| Persistence       | Scattered and inconsistent                    | Consolidated under `repository/`, added QueryDSL       |
| Diagrams          | None                                           | Reverse-engineered ERD and UML (`/docs/diagrams/`)     |
| Testing           | Sparse & brittle integration tests            | 120+ unit/slice tests, 93% coverage with JUnit + Mockito|
| Missing Features  | US7, US9, US12 were not implemented           | All now completed: with email + in-app notifications   |
| CI/Build          | Manual setup                                  | Added Maven Wrapper, GitHub Actions, Docker Compose    |

---

##  Setup Instructions

bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/online-social-bookstore.git
cd online-social-bookstore

# 2. Start MySQL and the app with Docker Compose
docker compose up

# 3. Open the app in your browser
http://localhost:8080
Running Tests
bash
Copy
Edit
mvn clean test
 File Structure Highlights
src/main/java/.../controller/ – Modular controllers for each feature

src/main/java/.../service/ – Clean service layer

src/main/java/.../repository/ – JPA repositories with QueryDSL

src/test/ – Unit and slice tests

docs/diagrams/ – ERD and UML class diagrams

 Testing Coverage
 120+ tests

Unit + slice + integration

 93% line coverage

 Verified with GitHub Actions CI

## License
This project is for academic and portfolio use.
Do not redistribute without credit.
