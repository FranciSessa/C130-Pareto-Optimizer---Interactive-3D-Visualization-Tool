# C130 Pareto Optimizer - Interactive 3D Visualization Tool
This project was carried out by a group of master's students (including myself) at the University of Naples Federico II for the course "Numerical and Experimental Methods for Aircraft Design".
A real-time 3D visualization and optimization tool for C130 Hercules aircraft design using Pareto front interpolation and interactive parameter exploration.
More deatils can be found in the projects section of my Linkedin profile: www.linkedin.com/in/francesco-sessa-aer

## 📋 Overview

This application provides an interactive graphical interface for exploring multi-objective aircraft design optimization results. It combines:
- **Real-time 3D visualization** using PyVista and OpenVSP
- **Interactive parameter control** via Tkinter sliders
- **Pareto front interpolation** for constrained and unconstrained optimization

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![Python](https://img.shields.io/badge/python-3.11-blue.svg)

The tool allows engineers and researchers to visualize trade-offs between different design objectives (e.g., span, chord, wing position) and instantly see the resulting aircraft configuration in 3D. The geometry of the wing has been varied while maintaining constant relative ratios such as the ratio of the tip chord to the root chord.

## ✨ Features
- You can choose to display 3 types of optimization:
  - 2 Design Variable optimization (span & chord)
  - 3 Design Variable optimization (span, chord & wing position)
  - Constrained (on longitudinal stability and maneuverability)  and unconstrained Pareto fronts



https://github.com/user-attachments/assets/7069fbdc-7569-48d0-8684-371e56080ec7




### Optimization Objectives and Constraint

The tool visualizes results from multi-objective optimizations with the following objectives:

| Objective | Type | Description |
|-----------|------|-------------|
| **Max Efficiency (E)** | Maximize | Max Trimmed Aerodynamic Efficiency (L/D ratio) |
| **STO** | Minimize | Takeoff distance according to FAR25 regulations |
| **MWTO** | Minimize | Aircraft total estimated maximum take off weight |
| **Fuel Consumption** | Minimize | Total fuel required for mission |
| **Mission Time** | Minimize | Total mission duration |


| Constraint | Requirement | Purpose |
|------------|-------------|---------|
| **SSM** (Static Margin, sign-reversed) | > 0.15 | Ensures longitudinal static stability |
| **horizontal tailplane volumetric coefficient** (ηh) | 0.7 ≤ ηh ≤ 1.25 | Guarantees longitudinal stability and controllability |

#### Weight Configuration Examples

The optimization uses a weighted sum approach where **relative ratios** determine the importance of each objective, not absolute values. 
- Setting weights `[100, 0, 0, 0, 0]` produces the **same result** as `[2, 0, 0, 0, 0]` (both prioritize only efficiency)
- Setting `[1, 1, 0, 0, 0]` means equal importance between efficiency and STO


⚠️ **Note on 3D Optimization Accuracy**: The 3D optimization mode (including wing X position) has **lower interpolation precision** compared to the 2D mode. Adding the third design variable significantly increased computational time during the response surface generation, requiring a coarser sampling grid. For highest accuracy, use the 2D optimization mode (span & chord only).

## 📥 Installation & Usage
1. **Download** the latest release from the [Releases](../../releases) page
2. **Extract** the entire `C130_Pareto_Optimizer` folder to your desired location
3. **Run** `C130_Pareto_Optimizer.exe`

⚠️ **Important**: Do NOT run only the `.exe` file. The entire folder structure is required, including the `_internal` directory with all dependencies.

## 💻 System Requirements
### Operating System
- Windows 10 or Windows 11 (64-bit)

### Dependencies (Pre-installed in executable)
The standalone executable includes all necessary dependencies. No Python installation required.




## 📁 Project Structure

```
C130_Pareto_Optimizer/
├── C130_Pareto_Optimizer.exe          # Main executable
├── _internal/                          # Dependencies (DO NOT DELETE)
│   ├── openvsp/                       # OpenVSP libraries
│   ├── degen_geom/                    # Geometry processing
│   ├── utilities/                      # Helper modules
│   ├── Interpol2variab/               # 2D interpolation data
│   │   └── interpolators/
│   ├── Interpolations3variab/         # 3D interpolation data
│   │   └── interpolators/
│   ├── result_2Dquinta_prova_ParteoFronts_constrained_SPLINE/
│   │   └── nbi_results.txt
│   ├── result_2Dquinta_prova_ParteoFronts_unconstrained_SPLINE/
│   │   └── nbi_results.txt
│   ├── result_3Dquinta_prova_ParteoFronts_constrained_SPLINE/
│   │   └── nbi_results.txt
│   ├── result_3Dquinta_prova_ParteoFronts_unconstrained_SPLINE/
│   │   └── nbi_results.txt
│   └── [other DLLs and dependencies]
└── c130.vsp3                          # Aircraft model
```

## 🛠️ Technologies Used

- **Python 3.11**: Core programming language
- **PyVista**: 3D visualization and VTK rendering
- **Tkinter**: GUI control panel
- **OpenVSP**: Aircraft geometry modeling
- **NumPy**: Numerical computations
- **SciPy**: RBF interpolation
- **PyInstaller**: Executable packaging

## 📊 Technical Details

### Interpolation Method
- **Algorithm**: Radial Basis Function (RBF) interpolation
- **Kernel**: Thin-plate spline
- **Data Source**: Pre-computed Pareto fronts from multi-objective optimization
 Static stability margin

## 📄 License

This project is provided as-is for educational and research purposes. 

**OpenVSP Notice**: This application includes components from OpenVSP (Open Vehicle Sketch Pad), which is distributed under the NASA Open Source Agreement (NOSA) Version 1.3.



**Note**: This tool is intended for educational and research purposes in aerospace engineering and aircraft design optimization.
