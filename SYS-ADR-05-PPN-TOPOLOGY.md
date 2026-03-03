# SYS-ADR-05: PointSav Private Network (PPN) Showcase Topology

## 1. Context
The PPN employs a **Symmetric Authority Model**. Every distinct service cluster executing on the Mesh is managed by a dedicated, siloed console on the Command Node.

## 2. Infrastructure Authority (Tier-4)
* **`route-network-admin`**: Allocates resources on the PPN (90% weight to Node 1).

## 3. System Administration Authority (Tier-5)
The Command Authority (Node 3) maintains four (4) specialized operator consoles:

### Primary Aggregator
* **`node-console-keys`**: Administrates the `gateway-interface-command`.

### Service-Specific Consoles
* **`node-console-email`**: Direct admin for `cluster-totebox-personnel-2`.
* **`node-console-content`**: Direct admin for `cluster-totebox-corporate-1`.
* **`node-console-people`**: Direct admin for `cluster-totebox-personnel-1`.

## 4. Workload Definitions
All `cluster-*` workloads execute on the Mesh, utilizing VirtIO for storage and seL4 VMMs for isolation.
