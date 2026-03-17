# TOPIC: Message Courier Service (service-message-courier)

**Classification:** Totebox Service (Headless UI Automation)
**Domain:** pointsav-monorepo

## 1. Abstract
The `service-message-courier` is a headless web automation and messaging protocol designed to bridge internal databases (`service-people`) with external web portals. It operates strictly as a generic execution engine.

## 2. Engineering Logic & The Adapter Pattern
To maintain the mathematical neutrality of the PointSav monorepo, the core engine contains no hard-coded selectors, URLs, or target-specific logic. Instead, it utilizes an **Adapter Pattern**. 

Operational logic is injected at runtime via scripts placed in the `private-adapters/` directory. This directory is strictly ignored by version control to ensure that proprietary client operational data (credentials, specific target sites) is never exposed to the public Git ledger.

## 3. Operational Flow
1.  **Query:** The courier polls a local ledger for pending dispatches.
2.  **Execution:** The engine mounts the specified private adapter and executes the headless browser routine.
3.  **Write-Back:** Upon success, the engine logs the timestamp and unloads the adapter.
