# 2.4Ghz_PLL
## PLL Specifications

### System-Level
| Parameter | Value |
|---|---|
| Output Frequency | 2.4 GHz |
| Reference Frequency (fref) | 75 MHz |
| Division Ratio (N) | 32 |
| Supply Voltage (VDD) | 1 V |
| Technology | GPDK 90nm (nmos1v/pmos1v) |
| Lock Time | ~1.5 - 2  µs |
| Vctrl Ripple (locked) | ~6 mV p-p |
| Area | 86.5µm x 58µm |

<img width="1060" height="1242" alt="Screenshot 2026-06-27 162939" src="https://github.com/user-attachments/assets/e01ad98c-44e5-42b2-82a9-714baf69e75b" />


### CS-VCO (Ring Oscillator)
| Parameter | Pre-Layout | Post-Layout |
|---|---|---|
| Frequency Range | 0.7 – 4.5 GHz | 1.29 – 3.5 GHz |
| Tuning Range | — | 92% |
| Kvco @ 2.4GHz | ~10 GHz/V | ~7 GHz/V |
| Phase Noise @ 1MHz offset | -77 dBc/Hz | -74 dBc/Hz |
| Stages | 3 (current-starved) |
| Bias | Self-biased PMOS (diode-connected + resistor) |

### Charge Pump
| Parameter | Value |
|---|---|
| Topology | Self-biased cascode current mirror, resistor reference (no IDC) |
| Icp | 20 µA |
| Mismatch (at Vout=0.5V) | 1.9% (characterized at 10µA; re-verify at 20µA) |
| Transistor Count | 5P + 5N (mirror + cascode + switches) |

### Loop Filter (Passive Lead-Lag)
| Parameter | Value |
|---|---|
| R1 | 7.2 kΩ |
| C1 | 36 pF (nmoscap1v) |
| C2 | 6 pF (mimcap) |
| ωn | 1.75 MHz |
| ζ | 1.43 |
| Phase Margin | ~71° (calculated) |

### TSPC Divide-by-32
| Parameter | Value |
|---|---|
| Stages | 5 cascaded TSPC FFs |
| NMOS sizing | W=1µm, L=100nm |
| PMOS sizing | W=2µm, L=100nm |

### TSPC PFD
| Parameter | Value |
|---|---|
| Topology | TSPC D-FF based, NAND reset (UP·DN) |
| Output | QB (not Q) |
| Reference | Based on TSPC-PFD architecture (Challagundla et al.) |

### VCO Output Buffer
| Stage | NMOS | PMOS |
|---|---|---|
| 1 | 1µm/100nm | 2µm/100nm |
| 2 | 2µm/100nm | 4µm/100nm |
