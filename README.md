🏢 OpenSmartBuilding
Open-source Building Management System — monitorizare și control în timp real pentru clădiri inteligente.
![License](https://img.shields.io/badge/license-MIT-green)
[![Version](https://img.shields.io/badge/version-2.0-blue)]()
[![Status](https://img.shields.io/badge/status-activ-brightgreen)]()
![Blog](https://img.shields.io/badge/blog-HubInfraTech-orange)
> Proiect realizat de **[Mihalache Ionut Marius](https://blog.hubinfratech.ro)** — HubInfraTech
---
🎯 Ce este OpenSmartBuilding?
OpenSmartBuilding este un BMS (Building Management System) open-source care centralizează monitorizarea și controlul tuturor instalațiilor tehnice ale unei clădiri — de la HVAC și solar până la antiincendiu, efracție și control acces IP.
Dashboard-ul este inspirat din Grafana — dark theme, grafice live, date în timp real și navigare rapidă între toate subsistemele.
---
🖥️ Demo live
Versiune	Link
Hyperion v1	👉 mariusmihalache.github.io/OpenSmartBuilding
Enterprise v2	👉 mariusmihalache.github.io/OpenSmartBuilding/osb_enterprise.html
---
⚡ Instalare rapidă
```bash
git clone https://github.com/MariusMihalache/OpenSmartBuilding.git
cd OpenSmartBuilding
# Deschide osb_enterprise.html in browser
```
Nu necesită instalare, server sau dependențe. Funcționează direct din browser.
---
📁 Fișiere
Fișier	Descriere
`index.html`	Hyperion v1 — dashboard clasic
`osb_enterprise.html`	Enterprise v2 — dashboard complet cu toate sistemele
`README.md`	Documentație
---
🖥️ Enterprise v2 — ce conține
Un singur fișier HTML cu 6 tab-uri:
Overview
Sisteme critice: HVAC climatizare + Energie consum
KPI strip: temperatură exterior, vânt, presiune, chilere, pompe
Sisteme secundare: Solar, Termică, Chilere, Pompe, Antiincendiu, Efracție, Control Acces
Systems
Gauge-uri: temperatură interior, CO₂, umiditate, consum, solar
Grafice 12h temperatură + CO₂ și consum vs solar
Debite ventilație pe zone
Intensitate luminoasă pe zone (lux)
Analytics
Tendințe temperatură cu threshold-uri
Tendințe consum energie cu alerte
Presiune atmosferică 12h
Alarms
Jurnal alarme active CRIT / WARN / INFO
Istoric 24h
Drawer detalii cu istoricul evenimentului
Sală Tehnică — Schema P&ID termică interactivă
CAZ-01 cazan condensare activ + CAZ-02 standby/cascadă
P-01 pompă primară + P-02 pompă secundară cu animație
BUT-01 butelie egalizare presiuni 60L cu degazor
Distribuitor tur / colector retur cu 4 zone
EV-1..4 electrovane zone (Cls. 1-4, Sala Sport, Cantină, Corp B)
VE-01 vas expansiune 60L
Senzori temperatură și presiune live
Click pe orice echipament → detalii Modbus
AHU-1 — Schema P&ID centrală tratare aer
Filtru G4 + Filtru F7 cu ΔP live
Baterie încălzire HW + Baterie răcire CW cu temperaturi live
Ventilator VFD — 6 strategii control (AUTO CO₂, AUTO T°, NOAPTE, URGENȚĂ, MANUAL, OPRIT)
DMP-01 clapetă intrare · DMP-03 clapetă amestec · DMP-02 clapetă refulare
EV-HW și EV-CW electrovane cu poziție live
VAV-A / VAV-B / VAV-C pe ductul de supply
Panou control lateral cu log comenzi
---
🔔 Sistem alarme
Bară alarme active permanent vizibilă
Panel stânga cu toate alarmele active filtrate CRIT / WARN / INFO
Toast-uri automate la depășire praguri (CO₂ > 900ppm, consum > 42kW, vânt puternic)
Drawer detalii cu istoric eveniment și acțiuni recomandate
---
🔌 Integrare Modbus TCP/IP
```
Host:  192.168.1.100
Port:  502
```
Când backend-ul Python este offline → interfața rulează în mod simulare cu date generate automat la 2.5 secunde.
Backend Python + pymodbus pe mini PC — în dezvoltare.
---
🛠️ Tehnologii
Tehnologie	Utilizare
HTML / CSS / SVG	Interfață și scheme P&ID
JavaScript vanilla	Logică, animații, simulare date
Chart.js	Grafice tendințe
JetBrains Mono + Inter	Tipografie
Tabler Icons	Iconografie
Modbus TCP/IP	Comunicare echipamente reale
Python + pymodbus	Backend (în dezvoltare)
---
📡 Roadmap
[x] Dashboard Hyperion v1
[x] Dashboard Enterprise v2
[x] Schema P&ID instalație termică interactivă
[x] Schema P&ID AHU-01 integrată
[x] Sistem alarme cu drawer detalii
[x] Simulare date live
[ ] Backend Python + pymodbus
[ ] Date reale Modbus de la echipamente
[ ] Schema P&ID AHU-02
[ ] Schema detaliată chilere CH-01..04
[ ] Istoric date time-series
[ ] Notificări email / SMS la alarme
---
📚 Articol tehnic
👉 blog.hubinfratech.ro
---
📄 Licență
MIT License — liber de folosit, modificat și distribuit.
---
OpenSmartBuilding — HubInfraTech
