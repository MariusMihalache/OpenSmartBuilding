🏢 OpenSmartBuilding
Open-source Building Management System — monitorizare și control în timp real pentru clădiri inteligente.
![License](https://img.shields.io/badge/license-MIT-green)
![Version](https://img.shields.io/badge/version-2.0.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Blog](https://img.shields.io/badge/blog-HubInfraTech-orange)
> Proiect realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech
---
🎯 Ce este OpenSmartBuilding?
OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri — de la HVAC și solar până la antiincendiu, efracție și control acces IP.
Proiectul evoluează continuu — în prezent la versiunea Enterprise v2, cu interfață de nivel industrial real.
---
🖥️ Versiuni disponibile
v1 — Hyperion Enterprise
Demo live →
Interfață dark inspirată din Grafana — gauge-uri analogice cu ace și zone de alertă, sparklines pe carduri KPI, bare de intensitate luminoasă în lux pe zone, rose diagram pentru direcția vântului, notificări automate la depășirea pragurilor și navigare completă între toate subsistemele.
---
v2 — Enterprise Control System ⭐ NOU
Demo live →
Reproiectare completă a interfeței, concepută pentru utilizare operațională reală — nu un dashboard demonstrativ, ci un sistem de control industrial funcțional.
Ce aduce nou față de v1:
Arhitectură UI orientată pe operare
Panou de alarme persistent în stânga, vizibil permanent — ierarhie strictă CRITICAL / WARNING / INFO cu indicator NEW pentru alarme noi
Global Status Bar sus — status clădire live, consum total, temperatură, CO₂, umiditate, uptime sistem și ceas sincronizat
Alarm Bar activă — alarmele critice apar imediat sub status bar cu buton Acknowledge
Navigare fără schimbare de pagină
Click pe orice sistem sau alarmă deschide un Side Drawer cu detalii tehnice, istoric eveniment și acțiuni recomandate
Dashboard-ul rămâne permanent vizibil — concept control room real
4 view-uri operaționale
Overview — toate sistemele live cu module animate și sparklines
Systems — gauge-uri analogice detaliate, bare ventilație, intensitate luminoasă în lux pe zone
Analytics — grafice cu threshold lines, zone normale marcate, comparații temporale
Alarms — jurnal complet alarme active și istoric
Selector niveluri clădire
Navigare pe etaje: Subsol · Parter · Etaj 1 · Etaj 2 · Curte ext.
Notificări automate
Toast notifications la depășirea pragurilor: CO₂, consum electric, vânt, presiune atmosferică
---
⚡ Instalare rapidă
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
Nu necesită instalare, server sau dependențe. Funcționează direct din browser.
---
🖥️ Sisteme monitorizate
Sistem	Descriere
🌡️ HVAC	Temperatură, ventilație pe zone, CO2, umiditate
☀️ Solar	Producție fotovoltaică, status panouri individuale
❄️ Chilere	Temperatura agent frigorific, cascadare automată
🔥 Termică	Centrală termică, zone, tur/retur, gaz
💧 Pompe	Grupuri pompare, RPM, presiuni, debite
💨 Ventilație	Vânt exterior, umiditate, CO2
💡 Iluminat	Intensitate luminoasă în lux pe zone, consum energie
🚨 Antiincendiu	Detectori fum/temp, sprinklere, ieșiri urgență
🔓 Efracție	Senzori mișcare/uși, CCTV, alarme
🪪 Control Acces	Rețea IP, jurnal acces, uși online
🌤️ Meteo	Vânt, presiune atmosferică, temperatură și umiditate exterior, paratrăsnet
---
📡 Protocoale suportate
Modbus TCP — echipamente IP (port 502)
Modbus RTU — RS-485 (max 32 noduri, 1200m)
M-Bus — contoare, termostate, senzori (via gateway → Modbus)
BACnet/IP — sisteme HVAC premium
MQTT — integrare IoT și cloud
REST API — integrare aplicații externe
---
📁 Structura proiectului
```
OpenSmartBuilding/
├── index.html              ← Dashboard v1 — Hyperion Enterprise
├── osb_enterprise.html     ← Dashboard v2 — Enterprise Control System
├── README.md               ← Documentație
├── pages/
│   ├── hvac.html
│   ├── solar.html
│   ├── chilere.html
│   ├── termica.html
│   ├── pompe.html
│   ├── ventilatie.html
│   ├── iluminat.html
│   ├── antiincendiu.html
│   ├── efractie.html
│   ├── acces.html
│   └── meteo.html
├── js/
│   ├── modbus.js           ← Conector Modbus TCP
│   ├── mbus.js             ← Conector M-Bus gateway
│   └── live-data.js        ← Manager date live
└── docs/
    └── architecture.md     ← Arhitectura sistemului
```
---
🔌 Integrare cu echipamente reale
Conectarea la echipamente reale se face prin fișierele din `/js/`:
```javascript
// Exemplu conectare Modbus TCP
const modbus = new ModbusClient('192.168.1.100', 502);
modbus.readHoldingRegisters(0, 10); // citire 10 regiștri
```
---
📚 Articol tehnic complet
Citește articolul detaliat despre arhitectura BMS, protocoale și implementare reală:
👉 Building Management System: Creierul Clădirii Inteligente
---
📄 Licență
MIT License — liber de folosit, modificat și distribuit.
---
OpenSmartBuilding — HubInfraTech
