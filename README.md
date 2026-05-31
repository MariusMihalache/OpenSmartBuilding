🏢 OpenSmartBuilding
Open-source Building Management System — monitorizare și control în timp real pentru clădiri inteligente.
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
[![Status](https://img.shields.io/badge/status-activ-brightgreen)]()
[![HTML](https://img.shields.io/badge/HTML-100%25-orange)]()
![Blog](https://img.shields.io/badge/blog-HubInfraTech-blue)
> Realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech
---
🔴 Live Demo
👉 Hyperion v1 — `index.html`
👉 Enterprise v2 — `osb_enterprise.html`
---
📋 Descriere
OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri.
Interfața este inspirată din Grafana — dark theme, grafice live, scheme P&ID interactive și navigare rapidă între subsisteme. Funcționează direct din browser, fără server, fără dependențe.
---
📁 Fișiere
Fișier	Descriere
`index.html`	Hyperion v1 — dashboard clasic
`osb_enterprise.html`	Enterprise v2 — dashboard complet
---
🖥️ Enterprise v2 — tab-uri
Tab	Conținut
Overview	Sisteme critice și secundare cu valori live
Systems	Gauge-uri, grafice 12h, ventilație, iluminat lux
Analytics	Tendințe temperatură, energie, presiune atmosferică
Alarms	Jurnal alarme CRIT / WARN / INFO cu drawer detalii
Sală Tehnică	Schema P&ID instalație termică interactivă
AHU-1	Schema P&ID centrală de tratare aer
---
🔧 Sisteme monitorizate
Sistem	Parametri
🌡️ HVAC	Temperatură, CO₂, umiditate, ventilație pe zone
☀️ Solar	Producție kW, status panouri individuale
❄️ Chilere	Temperatură agent, cascadare automată
🔥 Termică	Cazane, tur/retur, pompe, distribuitor, zone
💨 AHU-1	Filtre, baterii, ventilator VFD, clapete, VAV-uri
💧 Pompe	RPM, presiuni, debite
🚨 Antiincendiu	Detectori fum/temp, sprinklere
🔓 Efracție	Senzori mișcare, CCTV, alarme
🪪 Control Acces	Uși IP, jurnal acces, prezențe
---
🔌 Integrare Modbus TCP/IP
```
Host : 192.168.1.100
Port : 502
```
Când backend-ul este offline → mod simulare cu date generate la 2.5s.  
Backend Python + pymodbus pe mini PC — în dezvoltare.
---
🚀 Utilizare
```bash
git clone https://github.com/MariusMihalache/OpenSmartBuilding.git
cd OpenSmartBuilding
# Deschide osb_enterprise.html in browser
```
---
📡 Roadmap
[x] Hyperion v1
[x] Enterprise v2 cu alarme și P&ID
[x] Schema P&ID instalație termică interactivă
[x] Schema P&ID AHU-01
[ ] Backend Python + pymodbus
[ ] Date reale Modbus
[ ] Schema AHU-02
[ ] Chilere CH-01..04
[ ] Notificări email / SMS
---
📄 Licență
MIT License — liber de folosit, modificat și distribuit.
---
HubInfraTech · blog.hubinfratech.ro
