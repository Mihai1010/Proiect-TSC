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

| Categorie | Capsulă | Designator | JLC Part Number | Datasheet |
| :--- | :--- | :--- | :--- | :--- |
| **Capacitors** | **0201** | C1, C2, C3, C4, C5, C7, C8, C9, C11, C12, C13, C16, C17, C18, C19, C22, C23, C27, C29, C30, C31, C32, C34, C37, C38, C42, EPD_C5 | [JLCPCB](https://jlcpcb.com/partdetail/16204-CL05A106MQ5NUNC/C15525) | [Murata GRM011](https://www.snapeda.com/parts/GRM011R60J152KE01L/Murata/view-part/) |
| | **0402** | C6, C14, C15, C20, C21, C24, C25, C33, C39, C43, EPD_C1, EPD_C2, EPD_C6, EPD_C7, EPD_C8, EPD_C9, EPD_C10, EPD_C11, EPD_C12, C2-EP-DR1 | [JLCPCB](https://jlcpcb.com/partdetail/C9900006337) | [Generic 0402](https://jlcpcb.com/parts) |
| **Resistors** | **0201** | R2, R3, R4, R5, R7, R8, R9, R17, R18, R_TYPE_SEL, R1_EP_DR, R2_EP_DR, R2_PWR_EPD, R1_USB, R2_USB | [JLCPCB](https://jlcpcb.com/partdetail/26484-0402WGF1003TCE/C25741) | [Thin Film 0201](https://jlcpcb.com/parts) |
| **Inductors** | **0402** | L1, L2, L3 | [JLCPCB](https://jlcpcb.com/partdetail/6763488-FTC252012SR47MBCA/C5832368) | [FTC252012](https://jlcpcb.com/parts) |
| | **SMD** | L5, L7 | [JLCPCB](https://jlcpcb.com/partdetail/Walsin_TechCorp-WR06X60R4FTL/C168340) | [Wurth 744043680](https://www.we-online.com) |
| **ICs** | **BGA/WLCSP** | U1 (nRF52840) | [JLCPCB](https://jlcpcb.com/parts/componentSearch?searchTxt=nRF52840) | [nRF52840 PS](https://infocenter.nordicsemi.com) |
| | **BGA/WLCSP** | IC1 (BQ25180YBGR) | [JLCPCB](https://jlcpcb.com/parts/componentSearch?searchTxt=BQ25180YBGR) | [BQ25180 DS](https://www.ti.com) |
| | **BGA/WLCSP** | IC2 (DRV2605YZFR) | [JLCPCB](https://jlcpcb.com/partdetail/TexasInstruments-DRV2605YZFR/C81079) | [DRV2605 DS](https://www.ti.com) |
| | **BGA/WLCSP** | IC9 (RT6160AWSC) | [JLCPCB](https://jlcpcb.com/partdetail/RichtekTech-RT6160AWSC/C7065276) | [RT6160 DS](https://www.richtek.com) |
| | **LGA** | IC3 (BMA421) | [JLCPCB](https://jlcpcb.com/partdetail/BoschSensortec-BMA421/C5242966) | [BMA421 DS](https://www.bosch-sensortec.com) |
| | **SON/TDFN** | U3 (MAX17048) | [JLCPCB](https://jlcpcb.com/partdetail/2777647-MAX17048GT10/C2682616) | [MAX17048 DS](https://www.analog.com) |
| **Diodes/FETs** | **SOD-123** | D2, D4, D5 | [JLCPCB](https://jlcpcb.com/partdetail/ST_Semtech-1N4148W/C81598) | [MBR0530](https://www.onsemi.com) |
| | **SOT-23** | Q1 (DMG2305) | [JLCPCB](https://jlcpcb.com/partdetail/TECHPUBLIC-DMG2305UX/C2940629) | [DMG2305 DS](https://www.diodes.com) |
| | **SOT-323** | Q3 (SI1308EDL) | [JLCPCB](https://jlcpcb.com/partdetail/VishayIntertech-SI1308EDL_T1GE3/C469327) | [SI1308 DS](https://www.vishay.com) |
| | **SOT-23-6** | D3 (USBLC6) | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-USBLC62SC6/C7519) | [USBLC6 DS](https://www.st.com) |
| **Connectors** | **FPC 24** | J1 | [JLCPCB](https://jlcpcb.com/partdetail/MOLEX-5034802400/C122434) | [Molex 503480](https://www.molex.com) |
| | **USB-C** | J4 | [JLCPCB](https://jlcpcb.com/partdetail/EverlightElec-16_213SDRC_S530_A3TR8/C71911) | [KH-TYPE-C-16P](https://www.snapeda.com) |
| | **Tag-Connect**| J2 (TC2030) | [JLCPCB](https://jlcpcb.com/partdetail/MicrochipTech-TC2030_CLIP3PACK/C5444772) | [TC2030-IDC]() |
| **User I/O** | **Switch** | SW_DN, SW_ENT, SW_UP | [JLCPCB](https://jlcpcb.com/parts/componentSearch?searchTxt=C115357) | [EVP-AKE31A](https://industrial.panasonic.com) |
| | **Antenna** | ANT1 | [JLCPCB](https://jlcpcb.com/partdetail/JohansonDielectrics-2450AT18B100E/C2917717) | [2450AT18B](https://www.johansontechnology.com) |
| | **Oscillator** | X1, X2 | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-BALNRF01D3/C87765) | [XTAL Datasheet](https://www.snapeda.com) |
| **Mechanical** | **Custom** | Baterie, Display, Shaker | - | [Mechanical Folder](./Mechanical) |

---

## 3. Alocare Pini nRF52840 (Pinout Mapping)
Alocarea pinilor a fost optimizată pentru a facilita rutarea pe cele 4 straturi ale PCB-ului.

---

### Randări și Layout
*În folderul `/Images` regăsiți capturi detaliate:*
1. **Layout 2D:** Vizualizarea rutării pe straturile Top și Bottom.
2. **Randări 3D:** Vizualizarea finală a PCB-ului populat cu componente.
