# PowerPilot

> **PowerPilot** — Wi‑Fi energy meter for single‑ and three‑phase (120 V/230 V, up to 500 A) systems, streaming real‑time watts, kWh, voltage, current & frequency via MQTT/REST into PostgreSQL.

---

```markdown
# PowerPilot

PowerPilot is a Wi‑Fi energy meter built for accurate, IEC‑compliant monitoring of electrical systems — single‑phase and three‑phase (WYE/DELTA) up to 500 A at 120 V/230 V. It measures real‑time RMS voltage, current, active/reactive/apparent power, kWh, and frequency, then securely streams data via MQTT or HTTP into a Dockerized backend (Debian → Django REST → PostgreSQL) for local or cloud storage, visualization, and analytics.

## 🚀 Key Features

- ✅ Supports single‑phase & three‑phase configurations  
- ✅ Configurable for North American (120 V) & European (230 V) standards  
- ✅ High‑accuracy ADE7758 energy‑meter IC + 500 A split‑core CT sensors  
- ✅ ESP32 firmware with OTA, MQTT + REST API support  
- ✅ Docker Compose stack: Django, PostgreSQL, Nginx  
- ✅ React dashboard for live monitoring & historical reporting  
- ✅ Modular design: add LoRaWAN, Modbus, Home Assistant integrations  
- ✅ IEC/UL‑compliant safety (isolated supplies, surge protection)

Perfect for DIY, commercial, and renewable‑energy monitoring applications — take control of your energy usage and unlock actionable insights today!

---

## 🚩 Quickstart

1. Clone this repo & flash ESP32 firmware  
   ```bash
   cd firmware && platformio run --target upload
   ```
2. Deploy backend  
   ```bash
   cd server && docker-compose up -d
   ```
3. Configure Wi‑Fi + server URL in `config.json`  
4. Browse dashboard at `http://localhost:8000`

See [docs/INSTALL.md](docs/INSTALL.md) for full hardware BOM, calibration guide, API reference, and advanced setup.

## 📄 License

MIT © 2025 PRECEPT SYSTEMS (PTY) LTD  
```
