# HEKAX — Architecture Overview

This document describes the overall structure of the HEKAX platform across products, focusing on the relationships between communication worlds, decision layers, intelligence layers, and the event mesh.

---

## Platform Layers

### 1. Interface Layer

- Web application and APIs
- Calls, messaging, and operational interfaces

### 2. Worlds Layer

- Calls World
- Messages World
- Live Control World

### 3. Decision Layer

- Codex decision engine
- Policy chains per vertical
- Structured decisions and actions

### 4. Intelligence Layer

- Voice models
- Small language models
- External models where required

### 5. Event Mesh

- Stream-based event transport
- Consumer groups and processing workers
- Dead-letter queues and retries

### 6. State and Storage

- Relational database for primary entities
- Object storage where appropriate
- Caches and transient state where needed

### 7. Observability

- Metrics
- Logs
- Traces
- Dashboards

---

## Multi-World Model

The multi-world model separates concerns while maintaining a unified platform:

- **Calls World** focuses on telephony-specific concerns.
- **Messages World** focuses on multi-channel text-based communication.
- **Live Control World** presents an operational, real-time view for managers and operators.

Each world publishes and consumes events on the event mesh and relies on Codex for consistent decision logic.

---

## Codex Decision Engine

Codex is the central decision component responsible for:

- Normalizing inputs into structured events
- Running them through policy chains
- Producing decisions that include priority, labels, and actions
- Recording outcomes for later analysis and auditing

These decisions drive Smart Inbox behavior, Cockpit metrics, automation triggers, and SLA handling.

---

## Intelligence Integration

The intelligence layer connects voice and language models to the rest of the system through a single orchestration surface. Application code interacts with this layer using clear contracts rather than direct model calls.

---

## Event Mesh

The event mesh decouples producers and consumers, allowing the platform to evolve and scale without tightly coupling components. It is central to:

- Real-time behavior
- Reliability under load
- Horizontal scaling of workers
- Operational transparency

---

## Design Focus

The HEKAX architecture aims to:

- Keep boundaries explicit
- Maintain tenant safety
- Support incremental feature delivery
- Enable clear reasoning about data flow and decisions
- Be understandable to both engineers and non-technical stakeholders

Further diagrams, sequence flows, and service-level breakdowns can be added as the platform evolves.
