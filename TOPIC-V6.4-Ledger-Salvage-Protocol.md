# PointSav Digital Systems | V6.4 Ledger Salvage Protocol

## 1. Architectural Context (The Data Crush)
Under the Sovereign Data Protocol (DS-ADR-06), edge servers log raw network events to `assets/ledger_telemetry.csv`. A "Data Crush" occurs when a malconfigured Tier-1 to Tier-2 synchronization push accidentally overwrites the live cloud ledger with a stale local copy.

Because the V6 Strict Pull Diode architecture downloads and archives daily backups (`RAW_*.csv`) to the local `outbox/` *before* any pushes occur, the crushed data is rarely lost—it is simply scattered across the historical archives.

## 2. The Salvage Mechanism (V6.4 Core)
The `generic-tool-ledger-salvage.py` is a forensic recovery script designed to reconstruct the master ledger from these scattered archives.

1. **Ingestion:** The engine scans the designated target directory's `outbox/` for all `RAW_*.csv` backup files.
2. **Signature Verification:** It aggressively drops any rows that do not meet the minimum 4-column V6 signature (IP, Timestamp, Target URI, Terminal Signature).
3. **Deduplication:** It mathematically strips duplicate events by converting the rows into memory-efficient tuples and passing them through a Python `set`.
4. **Temporal Alignment:** It strictly sorts the remaining unique events via their ISO-8601 timestamps (Index 1).
5. **Egress:** It physically overwrites the target `assets/ledger_telemetry.csv` with the perfectly reconstructed ledger.

## 3. Operational Execution
The tool operates dynamically and requires the user to specify the absolute path to the telemetry module.

**Execution Standard:**
    python3 generic-tool-ledger-salvage.py <absolute_path_to_telemetry_directory>

**Example (Woodfine Management Corp. Environment):**
    python3 generic-tool-ledger-salvage.py /opt/deployments/woodfine-fleet-deployment/media-marketing-landing/app-mediakit-telemetry/

## 4. Post-Salvage Parity 
Once the ledger is locally salvaged, it must be surgically pushed back to the execution body (Tier-2). Operators must immediately verify that their synchronization tools (e.g., `rsync`) have been patched with `--exclude='assets/'` to prevent a recurrent crush.

---
*DOCUMENTATION SIGNATURE: POINT SAV DIGITAL SYSTEMS | FOUNDRY WIKI*
