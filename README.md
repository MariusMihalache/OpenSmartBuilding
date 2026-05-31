# OpenSmartBuilding — BMS Open Source v2

**OpenSmartBuilding** este un sistem de management al clădirilor (BMS) open-source dezvoltat de [HubInfraTech](https://blog.hubinfratech.ro), conceput pentru monitorizarea și controlul instalațiilor tehnice din clădiri educaționale, industriale și comerciale.

> Proiect activ · MIT License · Modbus TCP/IP · **Proiect Școală**

---

## 🖥️ Demo live

👉 [mariusmihalache.github.io/OpenSmartBuilding](https://mariusmihalache.github.io/OpenSmartBuilding/)

---

## 📋 Ce conține versiunea 2

### Un singur fișier — `osb_enterprise.html`

Tot dashboardul este **un singur fișier HTML** care include:

#### Tab-uri principale
| Tab | Conținut |
|-----|----------|
| **Overview** | Sisteme critice și secundare cu valori live |
| **Systems** | Gauge-uri, grafice 12h, ventilație, iluminat |
| **Analytics** | Tendințe temperatură, energie, presiune |
| **Alarms** | Jurnal alarme CRIT / WARN / INFO |
| **Sală Tehnică** | Schema P&ID instalație termică interactivă |
| **AHU-1** | Schema P&ID centrală de tratare aer |

#### Sală Tehnică — Schema P&ID termică
- Cazane de condensare **CAZ-01** (activ) și **CAZ-02** (standby/cascadă)
- Pompe **P-01** primară și **P-02** secundară cu animație impeller
- **Butelie egalizare presiuni BUT-01** cu degazor, termometru, manometru
- Distribuitor tur / colector retur cu 4 zone
- Electrovane zone **EV-1..4** (Cls. 1-4, Sala Sport, Cantină, Corp B)
- Vas de expansiune **VE-01** 60L
- Senzori temperatură și presiune cu valori live
- Alimentare gaze naturale

#### AHU-1 — Schema P&ID centrală tratare aer
- **Filtru G4** și **Filtru F7** cu indicatori ΔP live
- **Baterie încălzire HW** și **Baterie răcire CW** cu temperaturi live
- **Ventilator VFD** — 6 strategii (AUTO CO₂, AUTO T°, NOAPTE, URGENȚĂ, MANUAL, OPRIT)
- **DMP-01** clapetă intrare aer proaspăt
- **DMP-03** clapetă amestec aer proaspăt + viciat
- **DMP-02** clapetă refulare
- **EV-HW** și **EV-CW** electrovane cu poziție live sub tag ISA
- **VAV-A / VAV-B / VAV-C** pe ductul de supply
- Panou de control lateral cu log comenzi live

---

## 🔔 Sistem alarme

- Bară alarme active în timp real (CRIT / WARN / INFO)
- Panel lateral cu toate alarmele active
- Drawer detalii cu istoric eveniment și acțiuni recomandate
- Toast-uri automate la depășire praguri (CO₂, consum, vânt, presiune)

---

## 🔌 Integrare Modbus TCP/IP

```
Host:  192.168.1.100
Port:  502
```

Când backend-ul Python este **offline** → interfața rulează în **mod simulare** cu date generate automat la 2.5 secunde.

---

## 📁 Structura proiectului

```
OpenSmartBuilding/
├── index.html              # Hyperion v1 — pagina principală
├── osb_enterprise.html     # Enterprise BMS v2 — tot într-un fișier
└── README.md
```

---

## 🚀 Utilizare

```bash
git clone https://github.com/MariusMihalache/OpenSmartBuilding.git
cd OpenSmartBuilding
# Deschide osb_enterprise.html in browser
```

Nu necesită server, build tools sau dependențe externe. Funcționează direct din browser.

---

## 🛠️ Tehnologii

| Tehnologie | Utilizare |
|------------|-----------|
| HTML / CSS / SVG | Interfață și scheme P&ID |
| JavaScript vanilla | Logică, animații, simulare date |
| Chart.js | Grafice tendințe |
| JetBrains Mono + Inter | Tipografie |
| Tabler Icons | Iconografie |
| Modbus TCP/IP | Comunicare echipamente reale |
| Python + pymodbus | Backend (în dezvoltare) |

---

## 📡 Roadmap

- [x] Dashboard Enterprise v2 cu alarme
- [x] Schema P&ID instalație termică interactivă
- [x] Schema P&ID AHU-01 integrată
- [x] Sistem alarme cu drawer detalii
- [x] Simulare date live
- [ ] Backend Python + pymodbus pe mini PC
- [ ] Date reale Modbus de la echipamente
- [ ] Schema P&ID AHU-02
- [ ] Schema detaliată chilere CH-01..04
- [ ] Istoric date time-series
- [ ] Notificări email / SMS la alarme

---

## 👤 Autor

**Mihalache Ionut Marius** — [HubInfraTech](https://blog.hubinfratech.ro)

---

## 📄 Licență

MIT License — liber de utilizat, modificat și distribuit.
