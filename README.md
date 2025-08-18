# 🟣 Purple-38er — ZX81+38 Clone (Rev 1.10)

A personal build of the **ZX81+38** clone using purple PCBs and tactile switch keys. This project documents the assembly, troubleshooting, and validation of a modern recreation of the Sinclair ZX81 using standard logic ICs and through-hole components.

---

## 🧰 Project Overview

- **Board Revision**: ZX81+38 Rev 1.10  
- **Design Origin**: Mahjongg’s open-source ZX81+38  
- **Build Variant**: Purple PCB with tactile switch keyboard  
- **Objective**: Achieve reliable boot with “K” prompt, stable composite video, and verified ROM/RAM operation

---

## 🔧 Key Components

| Component        | Value / Type             | Notes                                  |
|------------------|--------------------------|----------------------------------------|
| Crystal          | 13 MHz                   | Required for correct video timing      |
| CPU              | Z80A                     | Clocked at 3.25 MHz (÷4 from crystal)  |
| ROM              | 27C256 OTP EPROM         | One-time programmable; verified in chip tester |
| RAM              | HM62256BLP-7             | Stable operation confirmed             |
| RP2              | 22kΩ bussed network      | Pull-ups for D0–D7; critical for boot  |
| 74HCU04          | Unbuffered inverter      | Required for crystal oscillator        |

---

## 🧪 Troubleshooting Log

- **White Screen / No “K” Prompt**:
  - All chips tested in alternate board—confirmed working  
  - RP2 replaced with 22kΩ bussed network—resolved boot issue  
  - Clock verified: 13 MHz at 74HCU04 pin 2, 3.25 MHz at Z80 pin 6

- **ROM Activity**:
  - /CS and /OE toggling observed  
  - Address and data bus activity confirmed

- **Video Output**:
  - Composite waveform present at RCA jack  
  - Sync stable after oscillator validation

---

## 📝 Build Notes

- All decoupling capacitors (100 nF) installed near ICs  
- Socketed chips reseated during debugging  
- Board now boots reliably with “K” prompt and clean composite output

---

## 📷 Visuals

The `images/` folder contains a detailed visual archive of the design and build process:

| Subfolder            | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `Assembly/`          | Final integration of keyboard and main PCB into the 3D-printed case         |
| `Case 3D/`           | 3D design views of the enclosure                                            |
| `Case Printed Raw/`  | Photos of the finished, unassembled printed case                            |
| `Keyboard 3D/`       | 3D renderings of the keyboard layout and switch matrix                      |
| `Keyboard Build/`    | Step-by-step documentation of keyboard assembly                             |
| `Keycaps/`           | Design files and visuals for custom keycaps                                 |
| `PCB 3D/`            | 3D views of the main PCB layout and component placement                     |
| `PCB Build/`         | Photo documentation of the main PCB assembly process                        |

---

## 🛠 Assembly Notes

- **USB Power Connector**:  
  Insulate the top of the USB connector to prevent contact with the tactile switches.

- **Capacitor C9**:  
  Angle C9 flat 90 degrees away from the main board to avoid shorting against the underside of the tactile switches.
  
  ⚠️ These issues caused keyboard failure when the case was closed.

---

## 📚 References

- [ZX81+38 Original Repository](https://github.com/mahjongg2/ZX81plus38)  
- [RevSpace Project Page](https://revspace.nl/ZX81plus38_simple_to_build_ZX-81_clone)  
- [Forum64 Build Threads](https://www.forum64.de)

---


