# 🏢 OpenSmartBuilding

**Open-source Building Management System** — monitorizare și control în timp real pentru clădiri inteligente.

![License](https://img.shields.io/badge/license-MIT-green)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Blog](https://img.shields.io/badge/blog-HubInfraTech-orange)

> Proiect realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech

---

## 🎯 Ce este OpenSmartBuilding?

OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri — de la HVAC și solar până la antiincendiu, efracție și control acces IP.

Dashboard-ul este inspirat din **Grafana** — dark theme, grafice live, date în timp real și navigare rapidă între toate subsistemele.

---

## ⚡ Instalare rapidă

Orice PC devine BMS în 3 pași:

```bash
# 1. Clonează repo-ul
git clone https://github.com/MariusMihalache/OpenSmartBuilding.git

# 2. Intră în folder
cd OpenSmartBuilding

# 3. Deschide în browser
open index.html
# sau pe Windows:
start index.html
```

**Nu necesită instalare, server sau dependențe.** Funcționează direct din browser.

---

## 🖥️ Sisteme monitorizate

| Sistem | Descriere |
|--------|-----------|
| 🌡️ **HVAC** | Temperatură, ventilație pe zone, CO2, umiditate |
| ☀️ **Solar** | Producție fotovoltaică, status panouri individuale |
| ❄️ **Chilere** | Temperatura agent frigorific, cascadare automată |
| 🔥 **Termică** | Centrală termică, zone, tur/retur, gaz |
| 💧 **Pompe** | Grupuri pompare, RPM, presiuni, debite |
| 💨 **Ventilație** | Vânt exterior, umiditate, CO2 |
| 💡 **Iluminat** | Control ON/OFF pe zone, consum energie |
| 🚨 **Antiincendiu** | Detectori fum/temp, sprinklere, ieșiri urgență |
| 🔓 **Efracție** | Senzori mișcare/uși, CCTV, alarme |
| 🪪 **Control Acces** | Rețea IP, jurnal acces, uși online |
| 🌤️ **Meteo** | Vânt, temperatură și umiditate exterior |

---

## 📡 Protocoale suportate

- **Modbus TCP** — echipamente IP (port 502)
- **Modbus RTU** — RS-485 (max 32 noduri, 1200m)
- **M-Bus** — contoare, termostate, senzori (via gateway → Modbus)
- **BACnet/IP** — sisteme HVAC premium
- **MQTT** — integrare IoT și cloud
- **REST API** — integrare aplicații externe

---

## 📁 Structura proiectului

```
OpenSmartBuilding/
├── index.html              ← Dashboard principal
├── README.md               ← Documentație
├── pages/
│   ├── hvac.html           ← Pagina HVAC
│   ├── solar.html          ← Pagina Solar
│   ├── chilere.html        ← Pagina Chilere
│   ├── termica.html        ← Pagina Termică
│   ├── pompe.html          ← Pagina Pompe
│   ├── ventilatie.html     ← Pagina Ventilație
│   ├── iluminat.html       ← Pagina Iluminat
│   ├── antiincendiu.html   ← Pagina Antiincendiu
│   ├── efractie.html       ← Pagina Efracție
│   ├── acces.html          ← Pagina Control Acces
│   └── meteo.html          ← Pagina Meteo
├── js/
│   ├── modbus.js           ← Conector Modbus TCP
│   ├── mbus.js             ← Conector M-Bus gateway
│   └── live-data.js        ← Manager date live
└── docs/
    └── architecture.md     ← Arhitectura sistemului
```

---

## 🔌 Integrare cu echipamente reale

Conectarea la echipamente reale se face prin fișierele din `/js/`:

```javascript
// Exemplu conectare Modbus TCP
const modbus = new ModbusClient('192.168.1.100', 502);
modbus.readHoldingRegisters(0, 10); // citire 10 regiștri
```

---

## 📚 Articol tehnic complet

Citește articolul detaliat despre arhitectura BMS, protocoale și implementare reală:

👉 **[Building Management System: Creierul Clădirii Inteligente](https://blog.hubinfratech.ro)**

---

## 📄 Licență

MIT License — liber de folosit, modificat și distribuit.

---

*OpenSmartBuilding — [HubInfraTech](https://blog.hubinfratech.ro)*
