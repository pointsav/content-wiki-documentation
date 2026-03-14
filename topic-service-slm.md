# TOPIC: Sovereign SLM Routing (service-slm)

**Classification:** Totebox Service (Headless AI Bridge)
**Domain:** pointsav-monorepo

## 1. Abstract
The `service-slm` operates as a point-in-time linguistic filter. It bridges the gap between raw data ingestion (like `service-email`) and institutional synthesis (`service-content`). It utilizes locally hosted, open-weight Small Language Models (SLMs) to execute logic without exposing corporate data to external hyperscalers.

## 2. Engineering Logic: Preventing Omnipresence
To preserve the mathematical integrity of the Totebox Archive, the SLM is stripped of omnipresence. 

Legacy SaaS architectures deploy AI as listening agents that read the entire database continuously. This introduces unacceptable risk vectors (prompt injection, hallucinated state changes). 

The PointSav architecture physically neuters the engine:
* **Cold-Start Execution:** The SLM operates as a batch script. It wakes up, executes a single text-extraction command via `vendor-slm-engine`, outputs a Markdown file, and shuts down.
* **Terminal Priority:** The SLM has zero execution privileges. It cannot run code, move files, or alter the `os-totebox` ledgers. It is restricted to formatting plain text.

## 3. Operational Flow (The Email Ingestion Example)
1.  **Spool:** A raw email `.txt` file lands in the ingestion spool.
2.  **Invoke:** The `service-slm` script is triggered. It passes the `.txt` file and a strict protocol prompt (e.g., `EXTRACT`) to the local SLM binary.
3.  **Output:** The SLM returns a clean, formatted block of text.
4.  **Write:** `service-slm` saves this output to `/drafts/` and immediately terminates.
