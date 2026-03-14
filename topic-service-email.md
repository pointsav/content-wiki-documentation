# TOPIC: Sovereign Email Bridge (service-email)
**Classification:** Totebox Service (Transport Interceptor)
**Domain:** pointsav-monorepo

## 1. Abstract
The `service-email` engine is an autonomous transport interceptor. It functions as a Cloud Bridge, mathematically extracting inbound communications from legacy third-party infrastructure (Microsoft 365 Exchange) and writing them directly to a local, physically isolated disk.

## 2. Engineering Logic & The Cloud Boundary
To bypass the vulnerabilities of IMAP and SMTP, the engine utilizes a strict OAuth2 cryptographic handshake against the Microsoft Graph API.
* **The Extraction Loop:** It actively polls for unread, transmitted assets (excluding local UI drafts).
* **The State Mutation:** Upon successful extraction, it executes an authorized `PATCH` command to alter the physical state of the third-party server, marking the asset as read to prevent infinite extraction loops.

## 3. Operational Flow
The engine operates strictly as a transport mechanism. It maintains zero visibility into the semantic meaning of the payload.
1. Penetrate the cloud boundary.
2. Extract the raw OData JSON payload.
3. Write the toxic JSON strictly to a temporary `/assets/tmp-maildir/` queue.
4. Surrender execution to the downstream parser.
