# NumTrade FinTech & Research Labs LLP

**Website:** https://numtrade.in

NumTrade FinTech & Research Labs LLP is a research-driven financial technology studio.  
We design and operate low-latency trading services, skill-based prediction engines, and
non-custodial payment infrastructure with escrow segregation, deterministic accounting,
and verifiable audit trails.

NumTrade is funded by **Bayesrock Corporation**. **Bayespark DAO** operates as a NumTrade
subsidiary focused on non-custodial wallets and programmable settlement.

> **Legal scope**  
> We develop and serve financial technology solutions **exclusively** for  
> **[Bayesrock Corporation](https://bayesrock.com)** and its subsidiaries, including  
> **[bayespark.com](https://bayespark.com)**, **[shivpe.org](https://shivpe.org)**, and **[projecthalley.org](https://projecthalley.org)**.

---

## Governance & structure

- **Strategic backer:** [Bayesrock Corporation](https://bayesrock.com)  
- **Operating entity:** NumTrade FinTech & Research Labs LLP (Mumbai, India)  
- **Subsidiary program:** [Bayespark DAO](https://bayespark.com) — non-custodial payments, multi-chain rails

---

## What we build

- **Skill-based prediction / contest engines**  
  Deterministic scoring, provably-fair allocation, Merkle proofs, RBI-aligned escrow segregation, live odds and liability control.

- **Low-latency trading & market services**  
  Streaming order ingestion, idempotent state transitions, durable queues, position & P&L accounting, explicit recovery semantics.

- **Non-custodial payments (Bayespark DAO)**  
  Wallet orchestration, signed transactions, webhook/queue settlement, chain adapters with strict boundary contracts.

- **Data & research pipelines**  
  Tick/event ingestion, columnar storage, reconciliation rollups, reproducible research notebooks and model evaluation.

---

## Architectural stance

We do **not** ship monoliths. Systems are constructed as small, testable services with stable contracts.

1. **Determinism first** — every state transition is reproducible from logs and inputs.  
2. **Strong boundaries** — ingest, score/match, settle, and audit are isolated services.  
3. **Idempotency & replay safety** — all mutations carry dedupe keys and versioned schemas.  
4. **Typed interfaces** — Protobuf/gRPC and JSON APIs are versioned and migration-driven.  
5. **Observability as a requirement** — metrics, traces, SLOs, cardinality budgets, red/black-box probes.  
6. **Defense in depth** — escrow segregation, immutable/WORM logs, policy KMS, least-privilege runtime.

---

## Languages & technologies

We use multiple languages intentionally, chosen for their strengths on each layer.

- **Go** — realtime services, WebSocket hubs, engines, workers, gRPC APIs.  
- **Rust** — proof/verification kernels, high-safety adapters, cryptographic primitives.  
- **C++** — latency-critical computation and simulation where metal-level control is required.  
- **Python** — research pipelines, data tooling, ETL, statistical testing, notebooks.  
- **Haskell / OCaml** — specification, property-based testing, and correctness-oriented components.  
- **TypeScript / React** — client applications, admin consoles, and internal ops UIs.  
- **Node.js** — API gateways, edge adapters, signing services.  
- **PostgreSQL, Redis, S3/Parquet** — ledgers, queues/caches, archival lakes.  
- **Nginx, CloudFront, WAF** — ingress, shielding, and distribution.  
- **Prometheus, OpenTelemetry, Loki** — metrics, tracing, logging.  
- **GitHub Actions, Terraform, rsync** — CI/CD and infrastructure automation.

---

## System components (typical deployment)
[Find Tech Stack PDF](https://numtrade.in/public/trading.pdf)

| Layer               | Responsibilities                                                            | Illustrative technologies                                                                 |
|---------------------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Edge / Ingress**  | TLS termination, WAF, rate limits, circuit breakers, request shaping        | Nginx, CloudFront, WAF                                                                    |
| **API Gateways**    | AuthN/Z, quotas, request signing, schema routing                            | Go / Node.js gateways, JWT, HMAC                                                          |
| **Realtime Svcs**   | WebSocket hubs, pub/sub, fan-out, presence, live odds                       | **Go**, Redis Streams, NATS                                                               |
| **Core Engines**    | Matching/scoring, deterministic state machines, liability/escrow orchestration | **Go**, **Rust**, **C++** (where latency demands), property-based tests in **Haskell/OCaml** |
| **Settlement**      | Escrow disbursal, bank rails adapters, chain writers                         | **Go** workers, gRPC, chain SDKs, signed jobs                                             |
| **Data Plane**      | OLTP ledgers, append-only audit, analytics lake                             | PostgreSQL, Redis, S3/Parquet                                                             |
| **Batch / Jobs**    | Rollups, reconciliation, backfills, simulations, model runs                 | Cron, Airflow or Temporal, **Python** pipelines                                           |
| **Observability**   | Metrics, traces, logs, anomaly detection                                    | Prometheus, OpenTelemetry, Loki                                                           |
| **CI/CD & Ops**     | Build, sign, deploy, config promotion, secrets                              | GitHub Actions, Terraform, rsync, KMS                                                     |
| **Frontends**       | Client UIs, consoles, dashboards                                            | **React/TypeScript**, Tailwind, CSR/SSR where appropriate                                 |
| **Web Apps / Portals** |  Informational pages, ToS, admin tools, light dynamic content            |PHP, Django, simple SSR sites                                                              |


*Technologies are indicative; exact stacks vary per product and regulatory context.*

---

## Security & compliance

- **Escrow segregation** with policy-bound disbursals and explicit human-in-the-loop where mandated.  
- **Merkle-audited rounds** and append-only internal logs; reproducible state from event streams.  
- **PII minimisation** and encryption for customer and financial data.  
- **Key management** via policy KMS and multi-stage signing for infrastructure and on-chain operations.  
- **Immutable snapshotting** and versioned deployments for full traceability.

---

## Repository policy

Core repositories are **private** to protect proprietary engines, market logic, and compliance artefacts.  
We selectively publish public interfaces, SDKs, and documentation as needed.

For diligence access under NDA, contact **legal@numtrade.in**.

---

## Contact

- Business: **contact@numtrade.in**  
- Legal: **legal@numtrade.in**  
- Research & Careers: **careers@numtrade.in**

---

Sincerely,

[Darshan P.](https://drshn.me)

Research Lead

With thanks to Bayesrock, Inc.
