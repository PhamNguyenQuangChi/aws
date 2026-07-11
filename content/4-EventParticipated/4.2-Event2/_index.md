---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---



# First Cloud Journey Tech Talk Series – Learning Report

## Purpose of the Event

**Sharing best practices in modern application design:** Shaping a Cloud-native mindset, transitioning from manual On-Premise infrastructure management to code-driven automation (IaC – Terraform), and building a DevOps culture.

**Introducing DDD methodology and event-driven architecture:** Approaching real-time architecture design through WebSocket protocols and stateless processing mechanisms (Stateless Lambda), combined with breaking down big-data problems using Knowledge Graphs.

**Guidance on choosing suitable compute services:** Analyzing the nature, technical pros and cons, and detailed comparison between traditional Virtualization (Virtual Machines) and lightweight application packaging technology (Containerization – Docker).

**Introducing AI tools that support the development lifecycle:** Exploring the power of Large Language Models (LLMs) integrated with Amazon Bedrock Knowledge Bases and the Amazon Neptune graph database to apply the cutting-edge GraphRAG model.

---

## Speaker List

| Speaker | Role |
| --- | --- |
| Vinh Tran | System Administrator at Central Retail Group |
| Bao Huynh | Junior Cloud Native Developer, Endava Vietnam (Founder of ITea Lab) |
| Le Hoang Gia Dai | AWS Cloud Engineer & Cyber Security Engineer, Team AWS G3 |
| Nguyen Quoc Bao | Cloud Game Core Developer / WebSocket Specialist |
| Viet Phat | AI Major, Swinburne University of Technology |
| Truong Huy Phuoc | Presenter on Soft Skills & Team Management |

---

## Key Highlights

### 1. Negative Impacts of Legacy Application Architecture

* **Slow product release time → Lost revenue/missed opportunities:** Operating on traditional On-Premise infrastructure requires complex manual configuration. Inconsistent packaging processes lead to the classic "works on my machine but breaks on the server" issue, prolonging release cycles.
* **Inefficient operations → Lost productivity, higher costs:** Traditional virtualized servers (VMs) require each VM to carry its own separate Guest OS, consuming excessive CPU, RAM, and storage. Patching each VM independently wastes resources and reduces operations team productivity.
* **Non-compliance with security regulations → Loss of security and reputation:** Relying solely on signature-based protection (such as conventional WAF rule sets) is insufficient to block sophisticated attacks (advanced SQL Injection, XSS, data-scraping bots, or anomalous behavior). Lacking real-time network behavior monitoring exposes the system to major security risks.

### 2. Transitioning to a New Application Architecture – Microservice Architecture

Moving from a heavy monolithic packaging model to a flexible modular system, where each function is decoupled and runs independently in containers, communicating efficiently over the cloud network based on 3 core pillars:

* **Queue Management & State:** Coordinating real-time connection data through API Gateway WebSocket, handling incoming requests and centralizing session management in the DynamoDB NoSQL distributed database.
* **Caching Strategy:** Applying Docker Layer Caching during the Dockerfile build process. The system automatically reuses unchanged layers from cache, minimizing build time and optimizing the CI/CD pipeline.
* **Message Handling:** Establishing full-duplex two-way communication through persistent WebSocket connections, allowing the server (AWS Lambda) to proactively push state updates directly to multiple clients simultaneously as events occur.

### 3. Domain-Driven Design (DDD) and System Boundary Segmentation

* **Data segmentation and processing method:** Approaching big-data problems through text Chunking, Entity extraction, and Embeddings generation to establish knowledge boundaries.
* **Entity-linking application case study:** Modeling complex multi-hop relationships through graph traversal, directly linking entities and relationships across multiple documents to eliminate AI hallucination.
* **Context mapping in graph storage:** The data context map is realized through Nodes (representing entities) and Edges (representing relationships), visualized in Amazon Neptune Analytics to uncover deep hidden knowledge.

### 4. Event-Driven Architecture

* **3 integration and network communication patterns:** HTTP Polling (asynchronous, intermittent protocol suited for Login/Leaderboard), UDP/ENet (lowest-latency protocol for FPS/Racing games requiring continuous sync), and WebSockets (real-time two-way communication ideal for Turn-based games, Chat, Lobby).
* **Key benefits:** High independence between Client and Server, automatic synchronized state updates displayed to all participants as soon as a new business event is successfully triggered.
* **Sync vs Async comparison:** Analyzing the major technical trade-offs when building stateless architecture with AWS Lambda. Since Lambda does not retain data in memory between requests, the system must continuously read and write state data to DynamoDB on every event.

### 5. Compute Evolution

* **Shared Responsibility Model (mindset shift journey):** Moving from manual On-Premise hardware management → Cloud Virtual Machines (VMs with separate Guest OS) → Isolated application packaging (Docker Containers sharing the Host OS Kernel) → Stateless, event-driven serverless model (AWS Lambda).
* **Serverless & Container benefits:** The ability to package source code together with all dependencies allows applications to run consistently across all environments ("Build once, run anywhere"), maximizing hardware resource efficiency by sharing the host's OS kernel.
* **Functions vs Containers:** A clear classification matrix — using Docker Containers flexibly for long-running, stable Microservices in CI/CD pipelines, while applying AWS Lambda for short-lived, event-driven tasks to optimize cost.

### 6. Amazon Q Developer and the Supporting Cloud Ecosystem

* **SDLC automation:** Using Infrastructure as Code (IaC) via Terraform to automate the entire configuration process, resource provisioning, version management, and repeatable deployment scripting with precision.
* **Code & Database transformation:** Deploying cloud-based machine learning optimization algorithms to solve the class imbalance problem, standardizing dashboards and visualization interfaces for real-time cyberattack monitoring.
* **AWS Transform agents / Managed Services:** Applying two modern knowledge-system modernization paths — the Fully Managed Route (Amazon Bedrock Knowledge Bases + Neptune Analytics) and the Custom Route (combining the LlamaIndex library with Amazon Neptune via Cypher Query language).

---

## Key Takeaways

### Design Mindset

* **Business-first approach:** Every technology solution or technical architecture must originate from clear and shared organizational goals to serve real-world problems and maximize work efficiency.
* **Ubiquitous language (common language in teamwork):** Understanding the core importance of open communication and active listening to establish a shared voice and eliminate information barriers between team members.
* **Bounded contexts:** Following the "Right Person, Right Place" principle alongside personal accountability helps clearly define task boundaries in team projects.

### Technical Architecture

* **Real-time process modeling technique:** How data flows are mapped from the Client (Godot) to the Cloud infrastructure through API Gateway's characteristic Route Keys (`$request.body.action`), enabling automatic routing of incoming JSON packets.
* **Event-driven communication:** Replacing the bandwidth-wasting continuous data-pulling mindset (HTTP Polling) with persistent WebSocket connections, optimizing network transmission and enhancing real-time user experience.
* **Integration patterns (security integration model):** A comprehensive approach combining the outer AWS WAF shield (protecting the HTTP/HTTPS web application layer) with an ML-based NIDS system (deep network behavior monitoring) trained on the standard CSE-CIC-IDS2018 dataset.
* **Compute spectrum:** Mastering the distinguishing criteria between Virtual Machines (isolated at the hardware layer with a separate OS) and Docker Containers (isolated at the application layer, sharing the host's OS kernel) to make accurate infrastructure decisions.

### Modernization Strategy

* **Phased approach (step-by-step journey):** Drawing from a real career progression from IT Helpdesk (building high-pressure troubleshooting and end-user communication skills), advancing into networking and Linux, then shifting toward a Cloud/DevOps mindset. Taking small, solid steps, focusing on building a real project portfolio rather than chasing certifications alone.
* **Application modernization framework:** Converting software source code into Docker Containers for synchronized deployment in CI/CD pipelines, thoroughly resolving software environment conflicts.
* **ROI measurement:** Flexibly using modern digital management tools (Trello, ClickUp, Google Workspace, Slack, Discord) to measure team performance, save non-technical meeting time, and increase project flexibility.

---

## Application to Current Work

* **Applying teamwork models to the current project:** Rigorously implementing the 4 golden rules of Teamwork, setting clear shared team goals, and assigning tasks according to each member's strengths, visualized on Trello/ClickUp.
* **Refactoring and packaging application source code:** Writing standardized Dockerfiles for the current software project, fully leveraging layer caching to speed up packaging during handover.
* **Implementing event-driven patterns:** Experimenting with real-time interactive features (such as an internal chat gateway or real-time notifications) using WebSocket solutions connected through API Gateway.
* **Applying stateless serverless solutions:** Separating short-lived, non-continuous processing logic of the current application into AWS Lambda, combined with storing session data in DynamoDB to optimize infrastructure costs.
* **Researching advanced security and AI applications:** Planning to integrate real-world data flows with GenAI via Amazon Bedrock to upgrade the ML-based NIDS monitoring system; in parallel, researching GraphRAG solutions to improve intelligent knowledge-search systems for enterprises.

---

## Experience During the Event

Attending the First Cloud Journey tech talk series was an extremely valuable and highly practical learning experience. The series of presentations from hands-on speakers comprehensively covered everything from personal career development paths, core infrastructure techniques, proactive security thinking, next-generation AI solutions, to the art of human connection within a project. Below are some representative highlights of the actual experience:

### Learning from Highly Skilled Speakers

Speaker Vinh Tran brought a powerfully inspiring real-life story about rising from IT Helpdesk to the position of Senior Sysadmin at Central Retail Group, breaking stereotypes about formal credentials through hands-on self-taught competence.

Young experts such as Bao Huynh (Endava Vietnam), Gia Dai, Quoc Bao, and Viet Phat shared in-depth technical knowledge on Cloud-native, AI, and Cybersecurity, distilled from real-world research and deployment experience.

### Hands-on Technical Experience

* Gained detailed exposure to the structure of writing a standard Dockerfile, clearly understanding how layers affect build speed and system resource usage.
* Visualized a real-time multiplayer game architecture through a live demo connecting a Godot client, witnessing instant data changes in DynamoDB as players made decisions.
* Recognized the importance of optimizing machine learning models when facing the Class Imbalance problem in detecting minority cyberattack classes.

### Applying Modern Tools

* Explored how the modern AWS ecosystem operates with advanced services: the AWS WAF application firewall, the stateless AWS Lambda processing service, the Amazon Neptune graph database, and the Amazon Bedrock AI platform.
* Adopted a modern project management mindset supported by leading digital tools such as Slack, Discord, and Trello for remote team interaction.

### Networking and Discussion

* The event opened up excellent opportunities to discuss hard-earned lessons (such as the Stale connections – GoneException error when players disconnect abruptly, leaving behind orphaned data, or the cost of large-scale Scan operations in DynamoDB).
* The workshop revealed a profound philosophy: no matter how advanced the technology, it still requires smooth coordination among responsible people and an open, unified team workflow.

---

## Lessons Learned

1. **"Never test in production"** — Protecting system availability is the highest form of protecting an infrastructure engineer's reputation and the entire team's time.
2. Signature-based security solutions are insufficient against modern threats; they must be combined with machine-learning-based behavioral monitoring to build a comprehensive, proactive defense shield.
3. Modernizing applications through knowledge graph models (GraphRAG) thoroughly resolves the multi-hop document-linking limitations of traditional RAG models.
![Event](/images/4-Event/event2.jpg)
---

## Conclusion

Overall, the event provided not only in-depth, practical technical knowledge — from Docker and WebSockets to Machine Learning and GraphRAG — but also delivered invaluable lessons on sustainable career development mindset and the art of highly effective team collaboration in every project.