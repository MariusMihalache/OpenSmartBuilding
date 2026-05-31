# 🏢 OpenSmartBuilding

**Open-source Building Management System** — monitorizare și control în timp real pentru clădiri inteligente.

![License](https://img.shields.io/badge/license-MIT-green)
![Version](https://img.shields.io/badge/version-2.0.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Blog](https://img.shields.io/badge/blog-HubInfraTech-orange)

> Proiect realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech

---

## 🎯 Ce este OpenSmartBuilding?

OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri — de la HVAC și solar până la antiincendiu, efracție și control acces IP.

Proiectul are două versiuni de interfață, ambele funcționale direct din browser, fără instalare sau server.

---

## 🖥️ Versiuni disponibile

### v1 — Hyperion Enterprise
**[▶ Demo live](https://mariusmihalache.github.io/OpenSmartBuilding/index.html)**

Interfață dark în stilul Grafana cu gauge-uri analogice cu ace și zone de alertă, sparklines pe carduri KPI, rose diagram pentru direcția vântului, bare de intensitate luminoasă în lux pe zone și notificări automate la depășirea pragurilor.

---

### v2 — Enterprise Control System ⭐ NOU
**[▶ Demo live](https://mariusmihalache.github.io/OpenSmartBuilding/osb_enterprise.html)**

Reproiectare completă pentru utilizare operațională reală — concept control room industrial.

**Ce aduce nou față de v1:**

- **Global Status Bar** — status clădire live, consum, temperatură, CO₂, umiditate și uptime sistem
- **Panou alarme permanent** — ierarhie CRITICAL / WARNING / INFO, vizibil tot timpul, indicator NEW pe alarme noi
- **Alarm Bar activă** — alarmele critice apar imediat sub status bar cu buton Acknowledge
- **Side Drawer** — click pe orice sistem deschide detalii tehnice fără să schimbe pagina
- **4 view-uri**: Overview · Systems · Analytics · Alarms
- **Selector niveluri**: Subsol · Parter · Etaj 1 · Etaj 2 · Curte ext.
- **Schema P&ID interactivă** — schemă sinoptică instalație termică cu:
  - Butelie de egalizare presiuni cu degazor, termometru, manometru și 4 conexiuni ISA
  - 2 cazane condensare cu indicatori stare live
  - Pompe cu impeler animat
  - 4 electrovane cu actuatori și indicator AUTO/MANUAL
  - Distribuitor tur + colector retur
  - Vas de expansiune
  - Senzori temperatură pe conducte cu valori live
  - Flux animat pe conducte tur/retur
- **Panou control acționări** — carduri intuitive cu:
  - Toggle switch ON/OFF pentru cazane și pompe
  - Butoane +/− pentru setpoint temperatură
  - Selector mod AUTO/MANUAL/ECONOMIE/CASCADĂ/ΔP CONST
  - Poziție electrovane 0%/50%/100% cu bară vizuală
  - Log comenzi cu timestamp
  - Pregătit pentru backend Modbus real
- **Grafice cu threshold lines** și detectare vizuală anomalii
- **Notificări automate** la depășirea pragurilor

---

## ⚡ Instalare rapidă

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
| 🌡️ **HVAC** | Temperatură, ventilație pe zone, CO₂, umiditate |
| ☀️ **Solar** | Producție fotovoltaică, status panouri individuale |
| ❄️ **Chilere** | Temperatura agent frigorific, cascadare automată |
| 🔥 **Termică** | Centrală termică, zone, tur/retur, gaz |
| 💧 **Pompe** | Grupuri pompare, RPM, presiuni, debite |
| 💨 **Ventilație** | Vânt exterior, umiditate, CO₂ |
| 💡 **Iluminat** | Intensitate în lux pe zone, consum energie |
| 🚨 **Antiincendiu** | Detectori fum/temp, sprinklere, ieșiri urgență |
| 🔓 **Efracție** | Senzori mișcare/uși, CCTV, alarme |
| 🪪 **Control Acces** | Rețea IP, jurnal acces, uși online |
| 🌤️ **Meteo** | Vânt, presiune atmosferică, temperatură, umiditate, paratrăsnet |

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
├── index.html              ← v1 Hyperion Enterprise
├── osb_enterprise.html     ← v2 Enterprise Control System
├── README.md               ← Documentație
├── js/
│   ├── modbus.js           ← Conector Modbus TCP
│   ├── mbus.js             ← Conector M-Bus gateway
│   └── live-data.js        ← Manager date live
└── docs/
    └── architecture.md     ← Arhitectura sistemului
```

---

## 🔌 Integrare cu echipamente reale

Interfața v2 este pregătită pentru backend real. Un singur fișier `server.py` pe mini PC:

```python
from flask import Flask, request, jsonify
from pymodbus.client import ModbusTcpClient

app = Flask(__name__)
client = ModbusTcpClient('192.168.1.100', port=502)

@app.route('/api/status')
def status():
    return jsonify({'online': True})

@app.route('/api/coil/write', methods=['POST'])
def write_coil():
    data = request.json
    # EV-1=20, EV-2=21, EV-3=22, EV-4=23
    # CAZ-1=1, CAZ-2=2, P1=10, P2=11
    client.write_coil(data['address'], data['value'])
    return jsonify({'success': True})

if __name__ == '__main__':
    client.connect()
    app.run(host='0.0.0.0', port=8080)
```

---

## 📚 Articol tehnic complet

👉 **[Building Management System: Creierul Clădirii Inteligente](https://blog.hubinfratech.ro)**

---

## 📄 Licență

MIT License — liber de folosit, modificat și distribuit.

---

*OpenSmartBuilding — [HubInfraTech](https://blog.hubinfratech.ro)*
