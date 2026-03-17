# TOPIC: Sovereign Personnel Ledger (service-people)

**Classification:** Totebox Service (Data Ledger)
**Domain:** pointsav-monorepo

## 1. Abstract
The `service-people` is a deterministic flat-file personnel ledger engine. It acts as the centralized master contact database for the enterprise. It stores unique identifiers, contact states, and communication ledgers.

## 2. Engineering Logic & Files Over Databases
This component enforces the Sovereign Data Archive (DS-ADR-02) standard. It rejects centralized database clusters. It utilizes a verifiable JSON flat-file state machine. This ensures that proprietary contact data remains mathematically sealed. It guarantees data portability. It allows the ledger to natively feed future local intelligence models without schema fracturing.

## 3. Operational Mechanics
The engine operates as a Command Line Interface (CLI) tool. It provides strictly defined query and update operations. It processes sub-process calls from authorized execution adapters. It executes the read and write operations against the immutable JSON file.
