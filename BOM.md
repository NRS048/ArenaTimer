# Bill of Materials (BOM)

This document contains the component lists for building the Double-Sided Timer, Single-Sided Timer, Driver Ready Remotes, and Timer Controller. 

*Note: For a **Single-Sided Timer**, you can use the Double-Sided BOM but simply cut the quantities for the display housing, lenses, hardware, and PCBs in half.*

---

## 1. Double-Sided Timer

### 3D Printed Parts
*   **Timer Housing Parts:** 2 full sets (1 set = 1 Left + 1 Right). *PETG recommended, but any material/color works.*
*   **Lenses:** 2 full sets. *PETG recommended for transparency. Each set includes 4 digits, 4 borders, and 2 colons.*
*   **Joiner Blocks:** 4x
*   **Mounting Bracket:** 1x (Optional)

### Hardware & Mechanical
| Component | Qty | Notes / Link |
| :--- | :---: | :--- |
| PCB Mounting Screws | 24+ | 12 per side minimum. [Amazon](https://a.co/d/00hEOAHO) |
| Housing Screws for Joiner Blocks | 16-24 | [Amazon](https://a.co/d/06CnOLYg) |

### Electronics & PCBA
The system uses **4 Display PCBs** ordered from JLCPCB (Black solder mask, full assembly per the PCB BOM found in the `hardware` folder). 

**Only 1 of the 4 PCBs needs to be fully populated** with the ESP32, relay, beeper, screw terminals, and power connector based on your needs. The audio/relay parts are completely optional.

| Component | Qty | Description / Source |
| :--- | :---: | :--- |
| **ESP32 Development Board** | 1 | Main controller board. [Amazon](https://a.co/d/0hX7Juhc) |
| **Power Connector** | 1 | Same Sky PJ-082BH. [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/PJ-082BH/3477156) |
| **AC/DC Power Adapter** | 1 | 5V, 60W minimum. [Amazon](https://a.co/d/0fynI0mL) |
| **Beeper** (Optional) | 1 | Same Sky CEM-1203-42. [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CEM-1203-42/412412) |
| **Relay** (Optional) | 1 | Omron/Aratas G5V-2-DC5. [DigiKey](https://www.digikey.com/en/products/detail/aratas-america-llc/G5V-2-DC5/87819) |
| **Screw Terminals** (Optional) | Var | For relay output. Phoenix Contact [socket](https://www.digikey.com/en/products/detail/phoenix-contact/1757255/260475) or [plug](https://www.digikey.com/en/products/detail/phoenix-contact/1757022/260380) |
| **16 AWG Wire** | ~2 ft | For connecting power between the two display sides. |
| **22 AWG Wire** | ~2 ft | For routing signals (`BOUT` > `BIN`, `DOUT` > `DIN`) to the second board. |

---

## 2. Driver Ready Remotes (Qty: 2)

The remote PCBAs are ordered as bare boards. To save costs, manually solder the headers/sockets that come included with the ESP8266 boards. The button circuit is simple and just shorts the `RST` pin of the ESP8266 to ground—this can easily be adapted to larger arcade buttons if desired.

### 3D Printed Parts
*   **Printed Housing:** 2x
*   **Printed Rear Cover:** 2x

### Components
| Component | Qty | Description / Source |
| :--- | :---: | :--- |
| **ESP8266 Board** | 2 | NodeMCU / D1 Mini style. [Amazon](https://a.co/d/02HlLmq1) |
| **Tactile Buttons** | 2 | Same Sky TS14-1212. [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/TS14-1212-120-BK-260-SCR-D/16562671) |
| **Button PCBs** | 2 | Custom bare boards (or custom wiring setup). |
| **Battery Pack** | 2 | Portable power source. [Amazon](https://a.co/d/02QkeaG8) |

---

## 3. Timer Controller

The controller PCBA uses the custom PCB fabrications ordered bare from JLCPCB using the Gerber files located in the `hardware` folder.

### 3D Printed Parts
*   **Printed Housing:** 1x
*   **Printed Rear Cover:** 1x

### Components
| Component | Qty | Description / Source |
| :--- | :---: | :--- |
| **ESP8266 Board** | 1 | NodeMCU / D1 Mini style. [Amazon](https://a.co/d/02HlLmq1) |
| **Tactile Buttons** | 5 | Same Sky TS14-1212. [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/TS14-1212-120-BK-260-SCR-D/16562671) |
| **Controller PCB** | 1 | Custom bare board. |
| **Battery Pack** | 1 | Portable power source. [Amazon](https://a.co/d/02QkeaG8) |

---

## 4. Range Upgrades & Modifications (Optional)

If you need extended wireless range for large track configurations, consider the following modifications:

*   **2.4GHz External Antenna (Untested):** Swap out the standard ESP8266 for a [Wemos D1 Mini Pro with an external antenna connector](https://www.aliexpress.us/item/3256808837639555.html).
*   **LoRA Conversion:** If 2.4GHz ESP-NOW performance is insufficient for your environment, the system can be adapted to LoRA hardware, though this will require additional custom hardware and firmware modifications.