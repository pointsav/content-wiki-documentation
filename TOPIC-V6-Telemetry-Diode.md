# PointSav Digital Systems | V6 Strict Pull Diode Architecture

## Engineering Logic
The V6 Telemetry Diode ensures absolute data parity from Tier-2 execution nodes back to local environments. It relies on a mathematical decoupling of processes: 
1. **Engine Ignition**: An asynchronous remote trigger ignites the `omni-matrix-engine.py` to synthesize data.
2. **Diode Extraction**: Rsync operations execute a strictly one-way pull to fetch the `.md` reports and `.csv` ledger assets, preventing local contamination from reaching the remote execution body.

*Note: Vendor (PointSav) and Customer (Woodfine) scripts are strictly isolated at the local execution layer to maintain domain parity.*
