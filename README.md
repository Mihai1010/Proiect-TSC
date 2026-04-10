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

## 3. Alocare Pini nRF52840 (Pinout Mapping)
Alocarea pinilor a fost optimizată pentru a facilita rutarea pe cele 4 straturi ale PCB-ului.

---

### Randări și Layout
*În folderul `/Images` regăsiți capturi detaliate:*
1. **Layout 2D:** Vizualizarea rutării pe straturile Top și Bottom.
2. **Randări 3D:** Vizualizarea finală a PCB-ului populat cu componente.
