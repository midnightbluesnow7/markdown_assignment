## Title
ADR 001: Tech Stack Selection for Campus Event Hub

## Status
Accepted

## Context
The engineering team is building an internal web application for a campus event hub. The primary goals are to ship a functional product quickly while ensuring the stack is maintainable by student developers and compatible with modern AI coding assistants. We evaluated three potential stacks (Python/Streamlit, Spring Boot, and Node/Express) based on five key dimensions: AI Support Strength, Popularity & Community Answers, Ecosystem Maturity, Deployment Simplicity, and Path to Next Architecture.



## Decision
We will use **Stack C: Node.js + Express + Server-Rendered Views (EJS/Pug) + PostgreSQL**. This stack represents a "Swiss Army Knife" middle ground, offering high flexibility and a strong path to future architectural changes. It allows the team to transition to a modern frontend framework (like React or Next.js) later without discarding the backend logic.

## Alternatives Considered
* **Stack A (Python + Streamlit + SQLAlchemy + Postgres):** Considered for its incredible speed-to-market and high AI support. It was rejected because it offers a "Low" path to next architecture, making custom UI scaling difficult.
* **Stack B (Spring Boot + Thymeleaf + JPA + PostgreSQL):** Considered for its enterprise-grade stability and maturity. It was rejected due to high boilerplate and a steeper learning curve for junior developers compared to JavaScript.

## Consequences

### Positive
* **Unified Language:** Most campus developers are familiar with JavaScript, lowering the barrier for new contributors.
* **Future Proofing:** Using Node.js/Express makes it easy to expose APIs for a mobile app or decoupled frontend in the future.
* **AI Efficiency:** LLMs have massive training sets for Express.js, leading to high-quality code generation and faster debugging.

### Negative
* **JavaScript Fatigue:** The ecosystem moves quickly, requiring the team to be diligent about updating dependencies and managing the build pipeline.
* **Template Limitations:** Server-rendered views (EJS/Pug) can feel dated compared to modern Single Page Applications (SPAs) for highly interactive features.
