# BAJA SAE Roll Cage – Modal Analysis

Modal (natural frequency) analysis of a BAJA SAE roll cage tubular space-frame, performed in **Ansys Mechanical Enterprise 2026 R1 (Student)**.

## Overview

The roll cage was modeled as a 1-part, 1-body tubular space frame in **DesignModeler**, imported and cleaned up using Boolean and Connect operations, and assigned a cross-section for the tube members. A **Modal analysis** (no pre-stress) was then run to extract the natural frequencies and corresponding mode shapes.

## Model Details

| Property | Value |
|---|---|
| Software | Ansys Mechanical Enterprise 2026 R1 (Student) |
| Geometry source | DesignModeler (`A: Modal`) |
| Bodies | 1 |
| Edges | 86 |
| Vertices | 55 |
| Cross Sections | 1 |
| Connections | Boolean1, Connect1, Connect2 |
| Analysis Type | Modal (A5), Pre-Stress: None |
| Units | Metric (mm, kg, N, s, mV, mA) |

## Natural Frequencies

| Mode | Frequency (Hz) | Notes |
|---|---|---|
| 1 | 0 | Rigid body mode |
| 2 | 0 | Rigid body mode |
| 3 | 0 | Rigid body mode |
| 4 | 7.4634e-05 | ~ Rigid body mode |
| 5 | 1.1934e-04 | ~ Rigid body mode |
| 6 | 1.6298e-04 | ~ Rigid body mode |
| 7 | 34.02 | First flexible mode |
| 8 | 36.413 | Second flexible mode |
| 9 | 52.892 | Third flexible mode |
| 10 | 54.332 | Fourth flexible mode |
| 11 | ~58.1 | Fifth flexible mode |
| 12 | — | Sixth flexible mode |

> Modes 1–6 are near-zero-frequency rigid body modes, typical of an unconstrained ("free-free") modal analysis. The first meaningful structural (flexible) mode occurs at **34.02 Hz**.

## Total Deformation Results

### Mode 7 (34.02 Hz)
- Maximum Deformation: **6.1236 mm**
- Minimum Deformation: **0.44203 mm**
- Average Deformation: **2.2415 mm**
- Behavior: Max deformation observed near the front upper hoop/side members; min deformation near the lower rear chassis members.

### Mode 8 (36.413 Hz)
- Maximum Deformation: **8.23 mm**
- Minimum Deformation: **0.21444 mm**
- Average Deformation: **2.0031 mm**
- Behavior: Max deformation localized at the upper front hoop junction; min deformation at the lower side-impact/rear members.

## Repository Contents

- `Geometry/` – DesignModeler roll cage CAD model
- `Modal_Analysis/` – Ansys Mechanical project files (`.wbpj`, `.wbpz`)
- `Results/` – Mode shape screenshots and deformation plots
- `README.md` – This file

## How to Reproduce

1. Open the project in **Ansys Workbench 2026 R1**.
2. Navigate to `A: Modal → Model → Modal (A5) → Solution (A6)`.
3. Review `Total Deformation 1–12` under Solution to view each mode shape.
4. Use the **Graph/Tabular Data** panel to view the frequency chart and mode-frequency table.

## Notes / Future Work

- Add boundary conditions (e.g., fixed supports at wheel mounts) for a constrained modal analysis to compare against this free-free study.
- Correlate flexible-mode frequencies against expected excitation sources (engine RPM range, terrain-induced vibration) to check for resonance risk.
- Include material properties, mesh statistics, and element type used in the analysis for full reproducibility.

---
*Update the sections above (material, mesh details, boundary conditions, contributors) with your specific project information before publishing.*
