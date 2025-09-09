# Radar-Based-Breathing-System
![image](https://github.com/nakulgprbs/Radar-Based-Breathing-System/blob/main/board_overview.png?raw=true)


# DEP Project – Contactless Breathing Monitoring with RFSoC 4x2

## 📌 Project Overview
This project demonstrates the use of the **RFSoC 4x2 development board** for designing and implementing a **contactless radar-based breathing monitoring system**. The work focuses on using high-speed ADCs, DACs, and programmable logic for real-time signal processing in **Neonatal Intensive Care Units (NICUs)**.

## 👨‍💻 Team Members
- Nakul (2022eeb1192)
- Aman Bhagat (2022eeb1152)    

**Supervisor:** Dr. Brijesh Kumbani  
**Institute:** Indian Institute of Technology Ropar  
**Date:** May 12, 2025  

---

## ⚡ Introduction
Premature infants often require continuous monitoring of vital signs such as breathing rate, heart rate, and oxygen saturation. Traditional wired monitoring methods cause discomfort and risk of skin damage.  

This project proposes a **completely contactless radar-based monitoring system** using **continuous wave (CW) radar** and the **RFSoC 4x2 platform**.  

Advantages:
- Non-invasive and contactless  
- Operates through blankets/incubators  
- Low-cost, low-power  
- Unaffected by lighting conditions or skin pigmentation  

---

## 🖥️ Hardware Used
- **Board:** RFSoC 4x2 (AMD-Xilinx Zynq UltraScale+ RFSoC – XCZU48DR)  
- **Framework:** [PYNQ](https://www.rfsoc-pynq.io/index.html) (Python Productivity for Zynq)  
- **Tools:** Vivado, Vitis, Jupyter Lab  

### RFSoC 4x2 Features
- 4 × 14-bit RF ADCs (up to 5 GSPS)  
- 2 × 14-bit RF DACs (up to 9.85 GSPS)  
- Quad-core ARM Cortex-A53 + dual-core Cortex-R5F  
- Dual 4 GB DDR4 memory banks  
- High-speed interfaces (100G QSFP28, USB 3.0, Gigabit Ethernet, DisplayPort)  
- 930K logic cells, 4.2K DSP slices  

---

## ⚙️ Getting Started
1. Insert MicroSD card with PYNQ image.  
2. Set boot mode to **SD**.  
3. Connect USB 3.0 and power cables.  
4. Switch on the board.  
5. Access Jupyter Lab via browser: [http://192.168.3.1/lab](http://192.168.3.1/lab)  
6. Login → username: `xilinx`, password: `xilinx`.  

---

## 🛠️ Methodology
### Transmitter (BPSK/QPSK)
- Data transfer using DMA.  
- Modulation performed in DUT block.  
- Control switches select modulation scheme.  

### Receiver
- QPSK demodulation, filtering, synchronization.  
- CIC & SSR decimation filters.  
- Carrier and frame synchronization.  
- AXI streaming for data processing.  

### Vivado Workflow
1. Create new project in Vivado.  
2. Add and configure RFSoC IP blocks.  
3. Validate design & generate HDL wrapper.  
4. Run synthesis, implementation.  
5. Generate bitstream (`.bit` file).  

---

## 📊 Results
- Successfully set up RFSoC 4x2 board using PYNQ.  
- Designed transmitter/receiver blocks in Vivado.  
- Encountered **bitstream mismatch issue**, preventing successful compilation.  

---

## 🚀 Future Work
- Debug bitstream generation errors.  
- Validate IP configurations.  
- Deploy radar-based system in NICU simulations.  
- Apply machine learning (e.g., Random Forest) for breathing rate estimation.  
- Improve robustness against motion artifacts and interference.  

---

## 📷 Project Image
<p align="center">
  <img src="images/rfsoc_board.png" alt="RFSoC 4x2 Board" width="500"/>
</p>

---

## 🔗 References
- [PYNQ Tutorials](https://www.rfsoc-pynq.io/tutorial.html)  
- [PYNQ Overlays](https://www.rfsoc-pynq.io/overlays.html)  
- [PYNQ Documentation](https://www.rfsoc-pynq.io/index.html)  
- [GitHub – RFSoC Radio](https://github.com/strath-sdr/rfsoc_radio)  
