# Diffusion-Controlled Carburization Simulator

An interactive web application for simulating carbon diffusion during carburization using **Fick's Second Law**.

The simulator compares a numerical **Explicit Finite Difference Method (FDM)** with the classical analytical **error-function solution**, allowing users to visualize carbon concentration profiles, estimate effective case depth, and validate numerical accuracy.

---

## Features

### Carbon Diffusion Simulation
- Explicit Finite Difference (FDM) solver
- Analytical Error Function solution
- Side-by-side comparison of numerical and analytical profiles
- Adjustable carburization temperature
- Adjustable carburization time
- Custom model depth
- Multiple steel grades

### Case Depth Prediction
- Effective case depth based on hardness criterion (HV)
- Case depth using user-defined carbon limit
- Automatic interpolation of case depth
- Analytical vs numerical comparison

### Material Database
Included steel grades:
- AISI 1018
- AISI 1020
- AISI 8620
- 20MnCr5
- AISI 4320
- AISI 4140

Each steel grade includes alloy correction factors for diffusivity.

---

## Interactive Visualizations

### Carbon Concentration Profile
Displays:

- FDM solution
- Analytical solution
- Effective case depth
- Carbon threshold
- Multiple temperature/time comparisons

### Arrhenius Plot

Shows:

- ln(D) vs 1000/T
- Temperature dependence of diffusivity
- Activation energy relationship

---

## Validation Tools

The simulator automatically calculates:

- Maximum profile difference
- Average error
- RMSE
- Maximum percentage error
- Semi-infinite assumption validity
- Characteristic diffusion distance

---

## Profile Query Tool

Query either:

- Carbon concentration at a given depth
- Depth corresponding to a target carbon concentration

Results include:

- FDM prediction
- Analytical prediction
- Percentage error
- Estimated hardness
- Predicted microstructure

---

## Microstructure Prediction

Based on local carbon concentration after quenching:

| Carbon (%) | Predicted Structure |
|------------|---------------------|
| > 0.80 | High Carbon Martensite |
| 0.40 – 0.80 | Martensite + Bainite |
| 0.20 – 0.40 | Ferrite + Pearlite |
| < 0.20 | Ferritic Core |

*These predictions are qualitative.*

---

## Export

Simulation results can be exported as CSV including:

- Distance
- FDM carbon concentration
- Analytical carbon concentration
- Hardness estimate
- Predicted microstructure

---

## Mathematical Model

The simulator implements:

### Fick's Second Law

\[
\frac{\partial C}{\partial t}
=
D
\frac{\partial^2 C}{\partial x^2}
\]

### Explicit Finite Difference

\[
C_i^{n+1}
=
C_i^n
+
r
(C_{i+1}^n-2C_i^n+C_{i-1}^n)
\]

where

\[
r=\frac{D\Delta t}{\Delta x^2}
\]

### Analytical Solution

\[
\frac{C-C_0}{C_s-C_0}
=
1-
erf\left(
\frac{x}{2\sqrt{Dt}}
\right)
\]

### Arrhenius Relation

\[
D
=
D_0
\exp
\left(
-\frac{Q}{RT}
\right)
\]

---

## Technologies Used

- HTML5
- CSS3
- Vanilla JavaScript
- HTML Canvas API

No external libraries or frameworks are required.

---

## Running Locally

Clone the repository

```bash
git clone https://github.com/yourusername/carburization-simulator.git
```

Open the project folder.

Simply open

```
index.html
```

in any modern web browser.

No installation or server is required.

---

## Educational Purpose

This simulator is intended for:

- Metallurgical Engineering students
- Materials Science students
- Heat Treatment courses
- Diffusion and Kinetics courses
- Numerical Methods demonstrations

---

## Limitations

The model assumes:

- One-dimensional diffusion
- Constant surface carbon concentration
- Constant diffusivity for a selected temperature
- Semi-infinite solid for analytical solution
- Idealized post-quench microstructure estimation

Results should be considered educational and illustrative rather than industrial design data.

---

## Future Improvements

- Variable diffusivity with carbon concentration
- Boost-diffuse carburizing cycles
- Gas carburizing atmosphere simulation
- Nitriding module
- Alloy-dependent diffusion models
- TTT/CCT diagram integration
- 2D diffusion simulation
- Experimental data import
- PDF report generation

---

## License

This project is intended for educational and academic use.
