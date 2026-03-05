# Technical Library & Knowledge Centre | Biblioteca Técnica
**PointSav Digital Systems™ | Institutional Index**

> **OPERATIONAL POSTURE [MARCH 2026]:**
> **Phase:** Production Iteration 1
> **Focus:** 3-Track System integration and Tier-6 Contract formalization.
> **Estado:** Transición a componentes en Rust con seguridad de memoria.

This repository serves as the definitive index for all architectural decisions and system specifications governing the PointSav Sovereign Network.

## Sovereign Knowledge Matrix

### Track 1: Infrastructure & Foundation
| Document ID | Title | Tier | Description |
| :--- | :--- | :--- | :--- |
| **SYS-STRAT-01** | [The Digital First Paradigm](./SYS-STRAT-01.yaml) | Tier 6 | 3-Track architecture mapping. |
| **SYS-CONTRACTS-01**| [Mathematical Compliance](./SYS-CONTRACTS-01.yaml) | Tier 6 | The Six Orchestration Contracts enforcing SOC 3 and DARP. |
| **SYS-ARCH-01** | [Software Architecture](./SYS-ARCH-01.yaml) | Tier 6 | Defines the seL4 Foundation. |
| **SYS-CORE-01** | [Capability-Based Manager](./SYS-CORE-01.yaml) | Tier 6 | Core Rust Root-Task. |
| **PPN-01** | [Private Network](./PPN-01.yaml) | Tier 4 | Physical and virtual mesh topology. |
| **SYS-ADR-11** | [The Stateless Compiler & 4-Node Isolation](./SYS-ADR-11.yaml) | Tier 6 | Enforce a strict 4-Node Sovereign Isolation Matrix. Isolate the active document generation engine (service-content) from the permanent public presentation layers (content-wiki-*). |

### Track 2: Totebox Orchestration
| Document ID | Title | Tier | Description |
| :--- | :--- | :--- | :--- |
| **SERVICE-CONTENT-01**| [Asset & Knowledge Synthesis](./SERVICE-CONTENT-01.yaml) | Tier 5 | Legal, Memo, and Comm processing engines. |
| **SERVICE-PEOPLE-01** | [Personnel Distillation](./SERVICE-PEOPLE-01.yaml) | Tier 5 | Harvester and Surveyor logic. |
| **SYS-ADR-10** | [Sovereign AI Routing & Cryptographic Inheritance](./SYS-ADR-10.yaml) | Tier 5 | Restrict AI processing to the application layer (service-LLM) using an SLM-Default, LLM-Fallback architecture to guarantee the seL4 microkernel remains isolated from prompt injections. |

### Track 3: Sovereign Desktop
| Document ID | Title | Tier | Description |
| :--- | :--- | :--- | :--- |
| **OS-WORKPLACE-01** | [Deterministic Files](./OS-WORKPLACE-01.yaml) | Tier 4 | The "Files over Databases" strategy for native machine-readability. |
| **SYS-ADR-09** | [The Ephemeral Endpoint Doctrine](./SYS-ADR-09.yaml) | Tier 4 | Physical hardware operating the os-workplace track are classified as Ephemeral Endpoints. The architecture strictly prohibits continuous background cloud synchronization. |
| **SYS-ADR-12** | [Payload-Agnostic Flat-File Ledgers](./SYS-ADR-12.yaml) | Tier 4 | Reject opaque traditional SQL databases to maintain DARP compliance. Utilize a payload-agnostic flat-file ledger architecture accepting any file extension as an inert binary blob. |

---
*© 2026 PointSav Digital Systems™.*
