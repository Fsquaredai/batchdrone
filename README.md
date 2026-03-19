<h1 align="center">
  BatchDrone
</h1>

<h3 align="center">Any sensor, any network, one intelligent dashboard</h3>

<p align="center">
  <a href="https://batchdrone.com"><img src="https://img.shields.io/badge/Website-batchdrone.com-blue?style=flat-square" alt="Website"></a>
  <a href="#license"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License"></a>
  <img src="https://img.shields.io/badge/Status-Production-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/Architecture-5%20Layer-orange?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/Edge-Offline%20First-yellow?style=flat-square" alt="Edge">
</p>

---

## What is BatchDrone?

Factories and farms have sensors everywhere — IP cameras, MQTT sensors, PLCs, audio microphones, cellular cameras — but they're all siloed on different networks with different protocols. Alert fatigue is rampant, financial systems are disconnected, and there's no single view of what's actually happening.

BatchDrone is a **5-layer distributed platform** that unifies any sensor into a single intelligent dashboard. Each edge device learns what "normal" looks like for its zone (zero calibration) and alerts on anomalies using statistical Z-score detection. For farms, it adds AI livestock recognition with per-animal economics. For factories, it connects sensor data directly to ERP and accounting systems.

## 5-Layer Architecture

```
Layer 5: INTEGRATION ─────── Financial Systems (Sage, Xero, SAP, Syspro)
    │
Layer 4: INTELLIGENCE ────── Tracking, Anomaly Rules, AI Recognition
    │
Layer 3: AGGREGATOR ──────── Central Cloud Hub (FastAPI + SQLite)
    │
Layer 2: EDGE DEVICES ────── On-Site Processing (Raspberry Pi, Intel NUC)
    │
Layer 1: SENSORS ─────────── IP Cameras, MQTT, HTTP, GPIO, Audio, WebRTC
```

## The Heartbeat Vector

Every camera zone is continuously analyzed across **6 dimensions** — no calibration required:

| # | Metric | Detects |
|---|--------|---------|
| 1 | **Luminance Mean** | Lights on/off, flashlights, darkness |
| 2 | **Color Entropy** | Smoke, fire, chaotic movement |
| 3 | **Edge Density** | Camera focus loss, lens obstruction |
| 4 | **Texture Uniformity** | Spills, defects, breakage |
| 5 | **Grid Hotspots** | Localized intrusion or movement |
| 6 | **Complexity Score** | Sudden appearance of detailed objects |

**Anomaly detection:** Z-score analysis (>3σ = alert). Each zone self-learns its baseline over 24 hours.

**Smart frame sampling:** ~90% CPU savings by skipping redundant frames.

## Context Engine

Raw anomalies are transformed into plain-English events:

| Signal Combination | Interpretation |
|-------------------|---------------|
| Luminance drop + complexity spike | **Intrusion detected** |
| Color entropy spike + texture change | **Fire/smoke detected** |
| Edge density collapse | **Camera obstruction** |
| Grid hotspot + complexity | **Unauthorized entry in Zone 3** |

Configurable signatures via API. Automatic action dispatch (IoT alarms, API calls, notifications).

## Dual-Vertical Dashboards

### Factory Mode
- Interactive floor plan with drag-drop asset placement
- Multi-sensor aggregation per asset (camera + MQTT + PLC + audio)
- Event rules engine with real-time state colors
- Per-product cost tracking linked to ERP

### Farm Mode
- Leaflet GPS satellite map with camera zones and animal markers
- AI animal recognition (species, breed, sex, color via Grok/OpenAI vision)
- **128-dimensional facial embedding** for individual animal identification
- Herd management with sighting feeds and missing-animal alerts
- Per-animal P&L tracking

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Cloud | FastAPI on GCP Compute Engine |
| Edge | Flask + OpenCV (Raspberry Pi / Intel NUC) |
| Database | SQLite + SQLAlchemy Async (17+ models) |
| Mapping | Leaflet.js with satellite imagery |
| Vision AI | Grok/OpenAI for livestock recognition |
| Deployment | systemd services, JSON queue persistence |
| Protocols | ONVIF, RTSP, MQTT, HTTP, GPIO, WebRTC |

## Who Is This For?

- **Factories** — Manufacturing plants with sensor blind spots and alert fatigue
- **Farms** — Automated headcounts, individual animal tracking, per-animal economics
- **Warehouses** — Perimeter security with anomaly detection
- **Multi-site operations** — Connecting disparate sensors across locations

## What Makes It Different

| Feature | BatchDrone | Traditional CCTV | Generic IoT |
|---------|-----------|------------------|-------------|
| Self-learning | Zero calibration | Manual rule setup | Threshold config |
| Sensor-agnostic | Any protocol, any device | Camera-only | Platform-locked |
| Offline edge | Works without internet | Cloud-dependent | Cloud-dependent |
| Financial integration | Sensor → ERP/Accounting | None | None |
| Explainable alerts | Z-scores + plain English | Motion rectangles | Raw values |

## Getting Started

Visit [batchdrone.com](https://batchdrone.com) to explore the platform and request a demo.

## About

Built by [F² AI](https://fsquared.ai) . Deployed globally on Google Cloud Platform.

## License

MIT
