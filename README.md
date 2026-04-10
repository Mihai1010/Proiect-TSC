# Proiect InkTime

**Autor:** Necula Mihai 331 AB

---

## 1. Diagramă Bloc
Arhitectura sistemului este centrată pe SoC-ul nRF52840, care gestionează procesarea datelor, interfața cu utilizatorul și comunicația wireless.


**Descriere Flux:**
* **Procesare:** nRF52840 (MCU) comunică prin I2C cu senzorii și perifericele.
* **Alimentare:** Gestionată de BQ25180 (Charger) și monitorizată de MAX17048 (Fuel Gauge).
* **Afișaj:** Ecran E-Paper controlat prin circuitul de boost dedicat.
* **Interfață:** 3 butoane pentru navigare și un motor haptic pentru feedback.

---

## 2. Bill of Materials (BOM)
Componentele au fost selectate pentru a asigura un consum redus de energie și dimensiuni compacte.

| Componentă | Model | Funcție | Link Achiziție (JLC) | Datasheet |
| :--- | :--- | :--- | :--- | :--- |
| **MCU** | Nordic nRF52840 | Microcontroller + Bluetooth |  |  |
| **Charger** | TI BQ25180 | Încărcător baterie Li-Po |  |  |
| **Fuel Gauge** | MAX17048G+T10 | Monitorizare stare baterie |  |  |
| **Haptic** | TI DRV2605YZFR | Driver motor vibrații |  |  |
| **IMU** | BMA421 | Accelerometru (Gesturi) |  |  |
| **Antena** | 2450AT18B100E | Antenă Chip 2.4GHz | |  |

---

## 4. Alocare Pini nRF52840 (Pinout Mapping)
Alocarea pinilor a fost optimizată pentru a facilita rutarea pe cele 4 straturi ale PCB-ului.

| Pin nRF52840 | Funcție | Componentă | Justificare |
| :--- | :--- | :--- | :--- |
| **P0.26 / P0.27** | SDA / SCL | I2C Bus (Senzori) | Magistrală partajată pentru IMU, Fuel Gauge și Haptic. |
| **P0.02** | AIN0 | Divizor Baterie | Intrare analogică pentru monitorizarea tensiunii acumulatorului. |
| **P0.18** | RESET | Debug | Pin dedicat pentru reset hardware prin interfața SWD. |
| **P0.09 / P0.10** | NFC1 / NFC2 | Butoane (GPIO) | Reconfigurați ca GPIO pentru a maximiza porturile digitale disponibile. |

---

## 5. Detalii Implementare și Review
* **Design PCB:** Cablajul este realizat pe 4 straturi. Stratul 2 este plan de masă (GND) continuu pentru protecție EMI.
* **Antenă:** Circuitul de matching PI este calculat pentru o impedanță de 50 Ohmi, conectat la antena chip.
* **Integrare Mecanică:** Dispozitivul include o carcasă compactă, cu butoane montate pe lateral (SW_UP, SW_ENT, SW_DN) pentru navigare facilă.

### Randări și Layout
*În folderul `/Images` regăsiți capturi detaliate:*
1. **Layout 2D:** Vizualizarea rutării pe straturile Top și Bottom.
2. **Randări 3D:** Vizualizarea finală a PCB-ului populat cu componente.
