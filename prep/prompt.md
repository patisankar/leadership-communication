### building app

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

## System Design Whiteboard Prompt

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
