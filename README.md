# Linear Diode-Based Electronic Thermometer Design

A precision linear electronic temperature sensor and signal conditioning circuit designed and simulated using PSpice/LTspice as part of the Electronics I course at Sharif University of Technology.

##  Project Overview
Semiconductor diodes exhibit a highly consistent negative temperature coefficient of approximately $-2\,\text{mV}/^\circ\text{C}$ in forward-bias mode. This project utilizes this thermal sensitivity to measure temperatures across a broad range of $-100^\circ\text{C}$ to $+100^\circ\text{C}$. 

To overcome low sensitivity ($2\,\text{mV}/^\circ\text{C}$) and non-zero DC offset voltage ($V_{DC} \approx 607\,\text{mV}$ at $0^\circ\text{C}$), an inverting Op-Amp differential bridge signal conditioning architecture was engineered.

---

##  Key System Specifications & Features

* **Temperature Sensing Range:** $-100^\circ\text{C}$ to $+100^\circ\text{C}$
* **Sensing Element:** Forward-biased diode (`Dbreak`)
* **Output Sensitivity:** Scaled from $2\,\text{mV}/^\circ\text{C}$ to **$100\,\text{mV}/^\circ\text{C}$** via amplifier stage
* **DC Offset Cancellation:** Voltage divider bridge network to eliminate $607\,\text{mV}$ offset at $0^\circ\text{C}$
* **Amplifier Stage:** Inverting Op-Amp configuration ($\text{LM741}$) with closed-loop gain $A_v = -50$ ($R_1 = 100\,\text{k}\Omega, R_2 = 5\,\text{M}\Omega$)
* **Linearity:** High linear voltage response from $-10\,\text{V}$ (at $-100^\circ\text{C}$) to $+10\,\text{V}$ (at $+100^\circ\text{C}$)

---

##  Circuit Architecture & Analysis

1. **Diode Sensing Element:** Exploits $\frac{\Delta V}{\Delta T} \approx -2\,\text{mV}/^\circ\text{C}$ forward characteristic.
2. **Offset Cancellation Bridge:** Resistor voltage divider eliminates the baseline $607\,\text{mV}$ DC diode forward drop at $0^\circ\text{C}$, yielding $0\,\text{V}$ output at $0^\circ\text{C}$.
3. **Op-Amp Signal Conditioning:** Inverting active gain stage boosts thermal sensitivity by 50x:
   $$\frac{\Delta V_{out}}{\Delta T} = (-2\,\text{mV}/^\circ\text{C}) \times (-50) = +100\,\text{mV}/^\circ\text{C}$$

---
