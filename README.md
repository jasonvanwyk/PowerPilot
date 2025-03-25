```markdown
# PowerPilot

A Wi‑Fi energy meter for single‑ and three‑phase (120 V/230 V, up to 500 A) installations — measuring voltage, 
current, active/reactive/apparent power, kWh, and frequency in real time and streaming data via MQTT/REST 
into a Dockerized PostgreSQL backend.

---

## 🚀 Key Features

- Accurate IEC‑compliant measurement for single‑phase & three‑phase (WYE/DELTA) systems  
- Configurable for North American (120 V) or European (230 V) voltages  
- High‑precision ADE7758 energy‑meter IC + 500 A split‑core CT sensors  
- ESP32 firmware with OTA, MQTT & REST API support  
- Docker Compose stack (Debian → Django REST → PostgreSQL → Nginx)  
- React dashboard for live & historical visualization  
- Modular hardware design: LoRaWAN, Modbus, Home Assistant ready  
- IEC/UL‑compliant safety (isolated supplies, MOV/TVS surge protection)  

---

## 📐 System Architecture

```text
┌────────────┐    WiFi    ┌────────────┐    HTTP/MQTT    ┌─────────────┐
│ PowerPilot │───────────▶│ Mosquitto  │───────────────▶│ Django API  │
│ (ESP32 +   │            │ Broker     │               │ + PostgreSQL│
│ ADE7758)   │            └────────────┘               └─────────────┘
│            │                                             ▲
└────────────┘                                             │
                                                           ▼
                                                     React Dashboard
```

---

## 📂 Repository Layout

```
/
├── docs/                   # Detailed documentation (setup, hardware, circuitry)
│   ├── INSTALL.md
│   ├── HARDWARE.md
│   └── CIRCUIT.md
├── firmware/               # ESP32 code (PlatformIO)
├── server/                 # Dockerized backend
│   └── docker-compose.yml
├── frontend/               # React dashboard
└── README.md
```

---

## 🚩 Quickstart

1️⃣ **Flash device firmware**  
```bash
cd firmware
platformio run --target upload
```

2️⃣ **Launch backend & dashboard**  
```bash
cd server
docker-compose up -d
cd ../frontend && npm install && npm start
```

3️⃣ **Configure**  
Edit `firmware/src/config.h` for Wi‑Fi + API endpoint.

4️⃣ **Visit**  
Open http://localhost:8000 to view real‑time data.

For full instructions — see 👉 `docs/INSTALL.md`

---

## 📅 Roadmap

1. PCB prototyping (single‑phase + three‑phase)  
2. Calibration & IEC compliance testing  
3. API v1.0 + feature‑complete React UI  
4. Cloud integration (AWS/GCP)  

---

## 🤝 Contributing

1. Fork & create a feature branch  
2. Commit changes with clear messages  
3. Open a pull request for review  
4. Merge upon approval  

Please read `docs/CONTRIBUTING.md` for full guidelines.

---

## 📄 License

MIT © 2025 Jason van Wyk  
```
