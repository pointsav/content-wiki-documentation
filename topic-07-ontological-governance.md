# 📡 TOPIC-07: Ontological Governance & The Surveyor Loop
**Protocol Identifier:** DS-ADR-09
**Status:** Active Deployment (v1.6)

## I. THE TRIPARTITE PIPELINE
Data extraction is not a monolith. It operates across three mechanically isolated services:
1. **`service-email` (Ingestion):** Splinters MIME payloads and deposits raw inert text/CSV files into the Spool. Zero intelligence applied.
2. **`service-people` (Identity Resolution):** Scans the Spool for human identity clusters.
3. **`service-content` (Linguistic Compilation):** Scans the Spool for narrative knowledge, cross-referencing text against the 4 Control Valves.

## II. THE VERIFICATION SURVEYOR (`app-console-input`)
To prevent AI hallucination and enforce absolute data fidelity, `service-people` utilizes a decentralized Human-in-the-Loop workflow. 
* The system isolates unverified Identity Fragments ("Index Cards").
* A human operator uses their personal, off-network browser to verify the entity (e.g., via LinkedIn), bypassing API taxes.
* The operator inputs the verified URL and Archetype back into the Console OS.
* **Throttle:** Operators are mathematically limited to 40-60 verifications per day to ensure high-fidelity inputs and eliminate cognitive fatigue.

## III. THE ONTOLOGICAL CONTROL VALVES (HEALING SPEEDS)
`service-content` is governed by four `.csv` ledgers that self-heal at heavily throttled rates to preserve longitudinal data stability:
1. **Archetypes (>24 Months):** The psychological and functional identity of the firm (e.g., *The Fiduciary*).
2. **Chart of Accounts (18-24 Months):** The structural/financial geometry (e.g., *Compliance*, *IT Support*). Requires Executive override to alter.
3. **Domains (>12 Months):** Bilingual Glossaries defining the macro-theaters: `Corporate` (Finance), `Projects` (Real Estate), and `Documentation` (Tech). 
4. **Themes (>3-8 Months):** The active, frontline narratives (e.g., *Co-Location Expansion*).
