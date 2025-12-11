# HEKAX Architecture

## System Design and Orchestration Documentation

This repository documents the system architecture, orchestration layers, and design patterns used across all HEKAX products.

---

## Architecture Domains

### 1. Multi-World Operating Model

Defines the Calls, Messages, and Live Control worlds and their interactions.

### 2. Codex Decision Engine

Outlines how events are evaluated through sequential policies, producing structured decisions.

### 3. AI Layer

Model routing strategy across SLMs and external LLMs, including cost and latency considerations.

### 4. Event Mesh

Redis Streams-based event flow for real-time processing.

### 5. Telephony Architecture

Covers signaling, sandbox mode, Twilio modes, and HEKAX-managed telephony.

### 6. State Machine Service

Workflow orchestration for leads, conversations, and system actors.

### 7. Trial and Upgrade System

Enterprise SaaS onboarding, usage limits, and plan enforcement.

### 8. Executive Cockpit

Profile-aware business intelligence dashboard.

---

## Design Philosophy

- Clear separation of concerns
- Multi-tenant safety
- Modular intelligence layers
- Predictable event flow
- Auditability
- Enterprise scalability

---

## Documentation

- [Architecture Overview](ARCHITECTURE_OVERVIEW.md)

---

## License

Proprietary. All rights reserved.
