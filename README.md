<div align="center">

# PointSav Digital Systems
### *Documentation Wiki: Architectural Law & Security Proofs | Wiki de Documentación: Ley Arquitectónica y Pruebas de Seguridad*
**Vancouver | New York | Berlin**

[ **System Monorepo** ](https://github.com/pointsav/pointsav-monorepo) | [ **Design System** ](https://github.com/pointsav/pointsav-design-system) | [ **Reference Deployment (Woodfine Fleet)** ](https://github.com/woodfine/woodfine-fleet-deployment)

</div>

---

## 1. EXECUTIVE OVERVIEW | VISIÓN GENERAL EJECUTIVA

**[ EN ]** This repository serves as the definitive, audited index for all architectural decisions and system specifications governing PointSav Digital Systems. It operates as the technical data room, proving the structural integrity of the enterprise. Compliance is treated as a structural primitive, guaranteed by the architecture rather than human policy. The fundamental baseline is enforced at the hardware level via the seL4 microkernel, ensuring absolute physical isolation across all active domains.

---

## 2. TRACK 1: INFRASTRUCTURE & FOUNDATION
The engineering logic establishing the physical mesh and absolute network boundaries.

| Document ID | Title | Description |
| :--- | :--- | :--- |
| **SYS-STRAT-01** | [The Digital First Paradigm](./sys-strat-01.yaml) | The 3-Track architecture mapping. |
| **SYS-CONTRACTS-01**| [Structural Compliance](./sys-contracts-01.yaml) | The Six Orchestration Contracts enforcing statutory auditability. |
| **SYS-ARCH-01** | [Software Architecture](./sys-arch-01.yaml) | Defines the isolated protection domains. |
| **SYS-CORE-01** | [Capability-Based Manager](./sys-core-01.yaml) | Core Rust Root-Task hardware execution. |
| **PPN-01** | [Private Network Topology](./ppn-01.yaml) | Physical and virtual mesh routing rules. |
| **SYS-ADR-13** | [Type-II Command Authority](./sys-adr-13.yaml) | Enforces localized physical control of algorithmic keys. |
| **TOPIC-UDP-01** | [The Independent Mesh](./topic-system-udp.yaml) | Defines the Zero-Broker UDP broadcast architecture. |

---

## 3. TRACK 2: DATA LEDGERS & GATEWAYS
The operational logic governing data isolation and institutional reporting.

| Document ID | Title | Description |
| :--- | :--- | :--- |
| **SERVICE-EMAIL-01** | [The Communications Ledger](./service-email-01.yaml) | The ingress protocol and permanent event log. |
| **SERVICE-PEOPLE-01** | [The Identity Ledger](./service-people-01.yaml) | Identity resolution and algorithmic mapping. |
| **SERVICE-CONTENT-01**| [The Taxonomy Ledger](./service-content-01.yaml) | Immutable corporate architecture and reporting logic. |
| **TOPIC-SLM-01** | [The API Gateway](./topic-system-slm.yaml) | The secure port bridging external computing models to the archive. |
| **TOPIC-STORAGE-01** | [Bare-Metal WORM Custody](./TOPIC-STORAGE-01.md) | Physical write-limitations and state-tethered spillover. |
| **TOPIC-EDGE-01** | [Edge-Terminated Protocol Isolation](./TOPIC-EDGE-01.md) | Decoupling public internet routing from the internal ledger. |

---

## 4. TRACK 3: OPERATOR TERMINALS
The human interface standards for the enterprise.

| Document ID | Title | Description |
| :--- | :--- | :--- |
| **OS-WORKPLACE-01** | [State Projection](./os-workplace-01.yaml) | The "Machine-Readable Primitives" strategy, abandoning analog files. |
| **SYS-ADR-10** | [The Fiduciary Interface](./sys-adr-10.yaml) | Zero-Form architecture and Human-in-the-Loop verification. |

---
*© 2026 PointSav Digital Systems. Public Architectural Blueprint. "PointSav Digital Systems" and "Totebox" are trademarks.*
