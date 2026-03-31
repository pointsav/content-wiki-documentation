# TOPIC: The Template Ledger (service-email-template)

**System Origin:** PointSav Digital Systems
**Execution Target:** Woodfine Management Corp.

## Executive Summary
The Template Ledger is an autonomous distribution engine designed to eliminate formatting degradation and version control errors in corporate communications. It pairs standardized email bodies with dynamic legal/marketing assets and injects them directly into the Microsoft 365 environment.

## The Operational Workflow
Operators do not draft these emails; they deploy them. 

1. **The Root Catalog:** Operators navigate to their `Template Ledger` folder in Microsoft 365.
2. **The `[TMPL-000]` Dashboard:** The root folder contains a single email (`[TMPL-000]`). Attached to this email is a self-contained, offline `.html` interactive catalog.
3. **Search & Isolate:** The operator opens the catalog, filters by taxonomy (e.g., *Compliance*, *Finance*), and clicks **Copy Key** on the desired template.
4. **Execution:** The operator pastes the globally unique key (e.g., `[TMPL-042]`) into the M365 Search bar, which instantly pulls up the exact, current version of the template.
5. **Deployment:** The operator clicks **Forward**, updates the recipient, deletes the routing telemetry block at the top of the email body, and clicks Send.

## Engineering Protocol (Silent Sync)
To prevent operator fatigue, the system uses a **Silent Sync** via the Microsoft Graph API. When a PointSav engineer updates a template asset (e.g., a new Direct-Hold Solutions rider), the Rust compiler connects to M365, silently deletes the old templates from the operator's sub-folders, and injects the new versions. No push notifications are triggered.
