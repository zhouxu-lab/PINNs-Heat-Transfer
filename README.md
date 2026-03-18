# PINN Simulation: 2D Heat Transfer in Food Processing

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/zhouxu-lab/PINNs-Heat-Transfer/blob/main/PINN_2D_Heat_Transfer.ipynb)

This repository implements a **Physics-Informed Neural Network (PINN)** to model transient 2D heat transfer in a food product during oven heating — without traditional mesh-based methods.

Source code for the book chapter *"Digital Twins and Physics-Informed Neural Networks in Food Processing"* (AI for Food Science).

---

## Physics Model

**Governing equation:**

$$\frac{\partial T}{\partial t} = \alpha \left( \frac{\partial^2 T}{\partial x^2} + \frac{\partial^2 T}{\partial y^2} \right)$$

where $\alpha = k / (\rho\, c_p)$ is the thermal diffusivity.

| Parameter | Symbol | Value | Unit |
| :--- | :---: | :---: | :--- |
| Thermal Conductivity | $k$ | 0.45 | W/(m·K) |
| Density | $\rho$ | 1 050 | kg/m³ |
| Specific Heat | $c_p$ | 3 300 | J/(kg·K) |
| **Thermal Diffusivity** | $\alpha$ | 1.30 × 10⁻⁷ | m²/s |

- **Domain:** 10 cm × 10 cm cross-section
- **Initial Condition:** Uniform 25 °C
- **Boundary Conditions:** 180 °C on all edges
- **Duration:** 60 minutes

## Quick Start

### Option 1 — Google Colab (recommended)

Click the **Open in Colab** badge above. No local setup needed.

### Option 2 — Local

```bash
git clone https://github.com/zhouxu-lab/PINNs-Heat-Transfer.git
cd PINNs-Heat-Transfer
pip install -r requirements.txt
jupyter notebook PINN_2D_Heat_Transfer.ipynb
```

## Results

The PINN reconstructs the temperature profile over 60 minutes of heating:

- **Loss convergence** — PDE, IC, and BC residuals all decrease over training
- **Temperature heatmaps** — Thermal penetration from edges to centre at 0, 10, 30, 60 min
- **Centre-point history** — Time-temperature curve at the geometric centre (coldest point)

---

*Author: Xu Zhou — xbz5414@psu.edu*
