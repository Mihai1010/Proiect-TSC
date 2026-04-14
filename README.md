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
| **Capacitors** | **0201** | C1, C2, C3, C4, C5, C7, C8, C9, C11, C12, C13, C16, C17, C18, C19, C22, C23, C27, C29, C30, C31, C32, C34, C37, C38, C42, EPD_C5 | [JLCPCB](https://jlcpcb.com/partdetail/16204-CL05A106MQ5NUNC/C15525) | [DataSheet](https://www.jotrin.jp/userfiles/downloadfile/CL05A106MQ5NUNC/CL05A106MQ5NUNC.pdf) |
| | **0402** | C6, C14, C15, C20, C21, C24, C25, C33, C39, C43, EPD_C1, EPD_C2, EPD_C6, EPD_C7, EPD_C8, EPD_C9, EPD_C10, EPD_C11, EPD_C12, C2-EP-DR1 | [JLCPCB](https://jlcpcb.com/partdetail/C9900006337) | [DataSheet](https://jlcpcb.com/parts) |
| **Resistors** | **0201** | R2, R3, R4, R5, R7, R8, R9, R17, R18, R_TYPE_SEL, R1_EP_DR, R2_EP_DR, R2_PWR_EPD, R1_USB, R2_USB | [JLCPCB](https://jlcpcb.com/partdetail/26484-0402WGF1003TCE/C25741) | [DataSheet](https://www.royalohm.com/assets/pdf/products/smd/1.pdf) |
| **Inductors** | **0402** | L1, L2, L3 | [JLCPCB](https://jlcpcb.com/partdetail/6763488-FTC252012SR47MBCA/C5832368) | [DataSheet](https://www.lcsc.com/datasheet/C5832368.pdf) |
| | **SMD** | L5, L7 | [JLCPCB](https://jlcpcb.com/partdetail/Walsin_TechCorp-WR06X60R4FTL/C168340) | [DataSheet](https://eu.mouser.com/datasheet/3/317/1/ASC_WR.pdf) |
| **ICs** | **BGA/WLCSP** | U1 (nRF52840) | [JLCPCB](https://jlcpcb.com/partdetail/NordicSemicon-NRF52840_QIAAR/C190794) | [DataSheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6470/NRF52840-QIAA-R.pdf) |
| | **BGA/WLCSP** | IC1 (BQ25180YBGR) | [JLCPCB](https://jlcpcb.com/partdetail/TexasInstruments-BQ25180YBGR/C3682423) | [DataSheet](https://www.ti.com/cn/lit/ds/symlink/bq25180.pdf?ts=1776165850601) |
| | **BGA/WLCSP** | IC2 (DRV2605YZFR) | [JLCPCB](https://jlcpcb.com/partdetail/TexasInstruments-DRV2605YZFR/C81079) | [DataSheet](https://www.ti.com/cn/lit/ds/symlink/drv2605.pdf?ts=1776155639464&ref_url=https%253A%252F%252Fso.szlcsc.com%252F) |
| | **BGA/WLCSP** | IC9 (RT6160AWSC) | [JLCPCB](https://jlcpcb.com/partdetail/RichtekTech-RT6160AWSC/C7065276) | [DataSheet](https://www.alldatasheet.com/datasheet-pdf/pdf/1709403/RICHTEK/RT6160AWSC.html) |
| | **LGA** | IC3 (BMA421) | [JLCPCB](https://jlcpcb.com/partdetail/BoschSensortec-BMA421/C5242966) | [DataSheet](https://www.alldatasheet.com/datasheet-pdf/pdf/1137426/BOSCH/BMA421.html) |
| | **SON/TDFN** | U3 (MAX17048) | [JLCPCB](https://jlcpcb.com/partdetail/2777647-MAX17048GT10/C2682616) | [DataSheet](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX17048-MAX17049.pdf) |
| **Diodes/FETs** | **SOD-123** | D2, D4, D5 | [JLCPCB](https://jlcpcb.com/partdetail/ST_Semtech-1N4148W/C81598) | [DataSheet](https://www.mccsemi.com/pdf/Products/1N4148W(SOD-123).pdf) |
| | **SOT-23** | Q1 (DMG2305) | [JLCPCB](https://jlcpcb.com/partdetail/TECHPUBLIC-DMG2305UX/C2940629) | [DataSheet](https://www.mouser.com/datasheet/2/115/DMG2305UX-266242.pdf) |
| | **SOT-323** | Q3 (SI1308EDL) | [JLCPCB](https://jlcpcb.com/partdetail/VishayIntertech-SI1308EDL_T1GE3/C469327) | [DataSheet]([https://www.vishay.com](https://www.vishay.com/docs/63399/si1308edl.pdf)) |
| | **SOT-23-6** | D3 (USBLC6) | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-USBLC62SC6/C7519) | [DataSheet]([https://www.st.com](https://www.st.com/resource/en/datasheet/usblc6-2.pdf)) |
| **Connectors** | **FPC 24** | J1 | [JLCPCB](https://jlcpcb.com/partdetail/MOLEX-5034802400/C122434) | [DataSheet](https://www.molex.com/content/dam/molex/molex-dot-com/products/automated/en-us/salesdrawingpdf/503/503480/5034802400_sd.pdf?inline) |
| | **USB-C** | J4 | [JLCPCB](https://jlcpcb.com/partdetail/EverlightElec-16_213SDRC_S530_A3TR8/C71911) | [DataSheet](https://www.endrich.com/Datenbl%C3%A4tter/Lichtl%C3%B6sungen/Everlight/Single%20Color%20LED/16-213SDRCS530-A3TR8.pdf) |
| | **Tag-Connect**| J2 (TC2030) | [JLCPCB](https://jlcpcb.com/partdetail/MicrochipTech-TC2030_CLIP3PACK/C5444772) | [DataSheet](https://www.farnell.com/datasheets/2818736.pdf) |
| **User I/O** | **Switch** | SW_DN, SW_ENT, SW_UP | [JLCPCB](https://jlcpcb.com/partdetail/ALPSALPINE-SKRKAEE020/C115357) | [DataSheet](https://www.tme.eu/Document/305984bf119cfa40f7a209117dc97838/SKRKAEE020.PDF) |
| | **Antenna** | ANT1 | [JLCPCB](https://jlcpcb.com/partdetail/JohansonDielectrics-2450AT18B100E/C2917717) | [DataSheet](https://www.johansontechnology.com/docs/1187/2450AT18B100_X8XXogU.pdf) |
| | **Oscillator** | X1, X2 | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-BALNRF01D3/C87765) | [DataSheet](https://www.st.com/resource/en/datasheet/bal-nrf01d3.pdf) |
| **Mechanical** | **Custom** | Baterie, Display, Shaker | - | [Mechanical Folder](./Mechanical) |

---

## 3. Alocare Pini nRF52840 (Pinout Mapping)
Alocarea pinilor a fost optimizată pentru a facilita rutarea pe cele 4 straturi ale PCB-ului.

---

### Randări și Layout
*În folderul `/Images` regăsiți capturi detaliate:*
1. **Layout 2D:** Vizualizarea rutării pe straturile Top și Bottom.
2. **Randări 3D:** Vizualizarea finală a PCB-ului populat cu componente.
