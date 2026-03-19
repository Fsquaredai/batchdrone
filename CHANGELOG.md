# Changelog

All notable changes to BatchDrone will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [4.0.0] — 2026-03-19

### Added
- 5-layer distributed architecture: Sensors → Edge → Aggregator → Intelligence → Integration
- Heartbeat Vector: 6-metric continuous zone analysis (luminance, entropy, edge density, texture, grid hotspots, complexity)
- Z-score anomaly detection (>3σ triggers) with self-learning baselines
- Smart frame sampling (~90% CPU savings)
- Context Engine: raw anomalies → plain-English events with configurable signatures
- Factory dashboard: interactive floor plan, drag-drop assets, multi-sensor aggregation, event rules
- Farm dashboard: Leaflet GPS map, AI livestock recognition, 128-dimensional facial embeddings, herd management
- Per-animal P&L tracking for farms
- ERP/Accounting integration for factories (Sage, Xero, SAP, Syspro)
- Offline-first edge devices with JSON queue sync
- Browser-as-sensor via WebRTC
- Protocol support: ONVIF, RTSP, MQTT, HTTP, GPIO, audio, 4G/cellular
