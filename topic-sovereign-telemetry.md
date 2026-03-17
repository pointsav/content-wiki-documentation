# topic-06: Sovereign Telemetry (V4 Intent Beacon)

## 1. Architectural Philosophy
PointSav Digital Systems enforces a strict Zero-Cookie, Zero-State telemetry architecture. The V4 Intent Beacon is engineered to extract maximum behavioral and hardware intelligence from edge clients without violating the structural sovereignty of the user's device. We do not utilize tracking pixels, session IDs, or third-party analytics aggregators. Data is compiled client-side and transmitted asynchronously via `navigator.sendBeacon` upon the `visibilitychange` event.

## 2. Payload Structure & Hardware Optics
The V4 payload captures distinct metrics leveraging native browser APIs, completely circumventing PII collection:
- `user_agent`: Standard device/browser identification.
- `viewport`: Rendering geometry calculated via `window.innerWidth/Height`.
- `timezone`: Extracted via `Intl.DateTimeFormat().resolvedOptions().timeZone` for regional mapping without IP geolocation.
- `device_memory`: Estimated device RAM limits (Hardware Optic).
- `hardware_cores`: CPU thread count (Hardware Optic).
- `dwell_seconds`: Millisecond delta from DOM load to tab-close.
- `scroll_depth`: Maximum vertical scroll percentage.
- `intent_clicks`: An array of highly-specific interaction targets (e.g., Fleet Manifest, WhatsApp initiations).

## 3. Graceful Degradation (Rust Daemon Logic)
The receiving Rust daemon (`telemetry-daemon.rs`) utilizes `Option<T>` serialization for all V4 parameters. This guarantees absolute backward compatibility with aggressively cached V3 clients. If a legacy payload is received, the daemon safely ingests the available data and writes `unknown` or `0` to the missing CSV columns. This prevents kernel panics and maintains immutable ledger alignment across all fleet deployments.

## 4. Chronological Synthesis
The `telemetry-synthesizer.rs` binary utilizes the `chrono` crate to parse the CSV ledger. It generates executive-grade Markdown reports partitioned into strict financial reporting windows: 1D, 1W, 30D, 60D, 90D, YTD, and Inception.
