# PointSav Digital Systems | V6.1 Omni-Matrix Aggregation Core

## 1. Architectural Overview
The V6.1 Omni-Matrix Core is a universal Python-based synthesis engine designed to mathematically aggregate raw network telemetry into Sovereign Data Protocol (DS-ADR-06) compliant ledgers. 

Unlike legacy V6.0 systems which performed 1:1 raw data dumps, V6.1 utilizes dynamic memory structures (`collections.Counter`) to calculate volume and event density percentages across standard routing matrices.

## 2. Universal Identity Resolution (Domain Parity)
To maintain absolute strict parity across the Multi-Tier Mirror, the engine codebase is identical across all deployments. It relies exclusively on the `$FLEET_ID` environment variable to determine its institutional identity at runtime.

* **`FLEET_ID=POINTSAV`**: The engine identifies as the Vendor. It applies PointSav Digital Systems AG typographical wordmarks and designates its role as Engineering & System Logic.
* **`FLEET_ID=WOODFINE`**: The engine identifies as the Customer. It applies Woodfine Management Corp. wordmarks and designates its role as Operational Execution & Asset Ledgers.

## 3. Structural Execution Paths
The engine must execute from within its designated sub-module to prevent pathing drift.
* **Target Directory:** `/media-marketing-landing/app-mediakit-telemetry/`
* **Data Ingress:** `/assets/ledger_telemetry.csv`
* **Data Egress:** `/outbox/REPORT_<FLEET_ID>_<DATE>.md`

## 4. Typographic Protocol (DS-ADR-08)
All outputs are strictly bound by Institutional Brutalism. 
* No decorative text or unclassified summarization.
* Hard-line markdown tables with right-aligned numeric density values.
* Absolute UTC timestamps for execution tracking.
* Matrices include: Global Routing, Metro Region, Timezone Alignment, Target URI, Device Form Factor, OS, and Raw Architecture Signatures.

---
*DOCUMENTATION SIGNATURE: POINT SAV DIGITAL SYSTEMS | FOUNDRY WIKI*
