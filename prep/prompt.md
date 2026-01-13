## Java building app

Act as a senior staff engineer and system design interviewer.

I want to build an interview-grade, production-style payment processing platform that I can publish on GitHub and walk through in senior/staff-level interviews.

### Requirements

**Backend**

Java 17, Maven, Spring Boot 3

REST + GraphQL (BFF) + gRPC

JWT authentication & authorization

Idempotent payment APIs

Saga-based transaction retries with compensation

Redis for idempotency, caching, and token-bucket rate limiting

SQL sharding (PostgreSQL, merchant-based shard key)

MongoDB for gateway/webhook payloads and retry diagnostics

Cassandra for immutable payment event timeline

Bloom filters for negative lookups / dedup protection

Observability (metrics, tracing, correlation IDs)

Docker Compose for all dependencies

**Frontend**

React 18 + TypeScript

GraphQL client (Apollo or equivalent)

Modern interview topics: concurrency, server-state management, idempotency handling, 429 handling, performance, error boundaries

**Expectations**

Use BFF + internal gRPC services (payments, retries)

Provide repo structure, Maven multi-module layout, proto schemas, GraphQL schema, data ownership model, and request flow diagrams

Explain trade-offs (why REST vs GraphQL vs gRPC, SQL vs NoSQL, sharding strategy, retry design)

Keep scope realistic and interview-credible (not toy, not overbuilt)

Design this step-by-step and focus on what interviewers actually care about, not academic completeness.

### System Design Whiteboard Prompt

Act as a senior system design interviewer.

I want to whiteboard and explain the design of a production-grade payment processing platform.

**Problem statement**

Design a system that supports idempotent payment creation, high-volume transaction retries, and real-time payment status visibility for multiple merchants at scale. The system must be resilient to retries, partial failures, and traffic spikes.

Constraints & goals

Handle duplicate requests safely (idempotency)

Support retryable and non-retryable failures (saga-based orchestration)

Scale horizontally for high write throughput

Enforce rate limits and prevent retry storms

Provide auditability and observability

Support UI-driven aggregation and internal service-to-service communication

Required design dimensions

Walk through the design step by step on a whiteboard, covering:

High-level architecture (clients, BFF, internal services, datastores)

API design (REST vs GraphQL vs gRPC and why)

Request flow for Create Payment and Retry Payment

Idempotency strategy (keys, storage, correctness guarantees)

Retry and saga orchestration (state machine, compensation)

Data modeling and ownership

SQL vs NoSQL vs event timeline

Sharding strategy and shard key

Caching, Bloom filters, and Redis usage

Rate limiting and backpressure (token bucket, 429 handling)

Failure modes and recovery (partial failures, retries, consistency)

Observability (metrics, logs, tracing, correlation IDs)

Security (JWT, HTTPS, service identity)

Scalability and trade-offs (what breaks first, how to evolve)

**Expectations**

Use clear box-and-arrow explanations suitable for a whiteboard

Explicitly state assumptions and trade-offs

Justify technology choices (Postgres sharding, Redis, Cassandra, Mongo, gRPC, GraphQL)

Keep the solution realistic and interview-credible

Optimize for clarity over completeness

After the walkthrough, ask follow-up questions as an interviewer would (e.g., shard rebalancing, retry storms, schema evolution).

## Ruby
# System Design Whiteboard Prompt  
*(Senior Backend Ruby Engineer – Interview Optimized)*

## Role & Context
Act as a **senior system design interviewer** evaluating a **principal-level backend engineer with a Ruby/Rails background**.

The goal is to **whiteboard and explain** a **production-grade payment processing platform**, focusing on **correctness, resiliency, scalability, and trade-offs**, not framework mechanics.

---

## Problem Statement
Design a system that supports:

- **Idempotent payment creation**
- **High-volume transaction retries**
- **Real-time payment status visibility**
- **Multi-tenant (merchant-based) isolation**

The system must handle:
- Duplicate client requests  
- Partial failures across external payment providers  
- Retry storms and traffic spikes  
- Strong auditability and observability requirements  

---

## Explicit Assumptions (state these early)
- Payments are **financially sensitive**; correctness > latency
- External providers are unreliable and inconsistent
- The system is **eventually consistent**, not distributed-transactional
- Retries are expected and must be bounded
- Multi-tenant isolation is a first-class concern

---

## Whiteboard Walkthrough Structure

### 1. High-Level Architecture
Draw and explain:
- React Client
- Backend-for-Frontend (GraphQL + limited REST)
- Internal services (payment execution, retry orchestration)
- Datastores and their responsibilities

Focus on **clear boundaries** and **ownership**.

---

### 2. API Boundary Decisions
Explain **why each interface exists**:
- **GraphQL** for UI-driven aggregation and controlled data fetching
- **REST** for webhooks, admin, and debugging flows
- **RPC (gRPC-style)** for internal, strongly-typed service communication

State trade-offs explicitly.

---

### 3. Core Request Flow: Create Payment
Whiteboard the full flow:

1. Request enters system
2. Idempotency key is validated
3. Payment intent is persisted
4. External provider is invoked
5. Result is classified:
   - Success
   - Retryable failure
   - Terminal failure

Relate this to:
- Rails controllers
- Background jobs (Sidekiq-style execution)

---

### 4. Idempotency Strategy
Explain:
- Where idempotency keys are generated
- How they are stored (Redis + durable store)
- How duplicate requests return the **same response**
- Why idempotency is enforced at the **boundary**, not deep inside the system

---

### 5. Retry Orchestration (Saga Mindset)
Describe:
- Explicit retry state machine
- Bounded retries with backoff and jitter
- Compensation steps (cancel auth, release holds)
- Why orchestration is preferred over implicit callbacks

Tie this to real payment failures.

---

### 6. Data Modeling & Ownership
Explain **why multiple datastores exist**:

- **Relational DB** – authoritative payment state machine
- **NoSQL (Mongo)** – raw provider and webhook payloads
- **Event / Timeline store (Cassandra)** – immutable history
- **Redis** – coordination primitives (idempotency, rate limiting)

Emphasize **clear ownership and access patterns**.

---

### 7. Scaling Strategy
Explain:
- SQL **sharding by merchant**
- Why cross-shard transactions are avoided
- How shard routing works
- How read models and analytics are separated from OL

