🏢 OpenSmartBuilding
Open-source Building Management System — monitorizare și control în timp real pentru clădiri inteligente.
![License](https://img.shields.io/badge/license-MIT-green)
![Version](https://img.shields.io/badge/version-1.1.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Blog](https://img.shields.io/badge/blog-HubInfraTech-orange)
> Proiect realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech
---
🎯 Ce este OpenSmartBuilding?
OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri — de la HVAC și solar până la antiincendiu, efracție și control acces IP.
Dashboard-ul este inspirat din Grafana — dark theme, grafice live, date în timp real și navigare rapidă între toate subsistemele.
---
⚡ Instalare rapidă
Orice PC devine BMS în 3 pași:
```bash
# 1. Clonează repo-ul
git clone https://github.com/MariusMihalache/OpenSmartBuilding.git

# 2. Intră în folder
cd OpenSmartBuilding

# 3. Deschide în browser
open osb_enterprise_fixed.html
# sau pe Windows:
start osb_enterprise_fixed.html
```
Nu necesită instalare, server sau dependențe. Funcționează direct din browser.
---
🖥️ Fișier principal
Fișier	Descriere
`osb_enterprise_fixed.html`	Dashboard principal — toate sistemele, schema P&ID AHU, control live
---
🔧 Changelog
v1.1.0
✅ Fix scroll orizontal pe schema P&ID AHU-1 (era blocat de `overflow-x: hidden`)
✅ Scrollbar dark theme — bara de jos nu mai apare albă
✅ Container SVG P&ID cu `overflow-x: auto` pentru navigare stânga/dreapta
✅ Stilizare globală scrollbar (`scrollbar-color`, `scrollbar-width`) compatibil Chrome + Firefox
v1.0.0
🚀 Lansare inițială dashboard BMS enterprise
Schema P&ID completă AHU-1 cu animații flux aer
Control HVAC, Solar, Chilere, Termică, Pompe, Iluminat
Antiincendiu, Efracție, Control Acces IP
Date live simulate cu animații
---
🖥️ Sisteme monitorizate
Sistem	Descriere
🌡️ HVAC / AHU	Schema P&ID detaliată, aspirație/refulare, baterii, filtre, VFD
☀️ Solar	Producție fotovoltaică, status panouri individuale
❄️ Chilere	Temperatura agent frigorific, cascadare automată
🔥 Termică	Centrală termică, zone, tur/retur, gaz
💧 Pompe	Grupuri pompare, RPM, presiuni, debite
💡 Iluminat	Control ON/OFF pe zone, consum energie
🚨 Antiincendiu	Detectori fum/temp, sprinklere, ieșiri urgență
🔓 Efracție	Senzori mișcare/uși, CCTV, alarme
🪪 Control Acces	Rețea IP, jurnal acces, uși online
🌤️ Meteo	Vânt, temperatură și umiditate exterior
---
📡 Protocoale suportate
Modbus TCP — echipamente IP (port 502)
Modbus RTU — RS-485 (max 32 noduri, 1200m)
M-Bus — contoare, termostate, senzori (via gateway → Modbus)
BACnet/IP — sisteme HVAC premium
MQTT — integrare IoT și cloud
REST API — integrare aplicații externe
---
🔌 Integrare cu echipamente reale
```javascript
// Exemplu conectare Modbus TCP
const modbus = new ModbusClient('192.168.1.100', 502);
modbus.readHoldingRegisters(0, 10); // citire 10 regiștri
```
---
📚 Articol tehnic complet
👉 Building Management System: Creierul Clădirii Inteligente
---
📄 Licență
MIT License — liber de folosit, modificat și distribuit.
---
OpenSmartBuilding — HubInfraTech
