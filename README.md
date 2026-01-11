# C130 Pareto Optimizer - Interactive 3D Visualization Tool
This project was carried out by a group of master's students (including myself) at the University of Naples Federico II for the course "Numerical and Experimental Methods for Aircraft Design".
A real-time 3D visualization and optimization tool for C130 Hercules aircraft design using Pareto front interpolation and interactive parameter exploration.
More deatils can be found in the projects section of my Linkedin profile: www.linkedin.com/in/francesco-sessa-aer

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![Python](https://img.shields.io/badge/python-3.11-blue.svg)

## 📋 Overview

This application provides an interactive graphical interface for exploring multi-objective aircraft design optimization results. It combines:
- **Real-time 3D visualization** using PyVista and OpenVSP
- **Interactive parameter control** via Tkinter sliders
- **Pareto front interpolation** for constrained and unconstrained optimization

The tool allows engineers and researchers to visualize trade-offs between different design objectives (e.g., span, chord, wing position) and instantly see the resulting aircraft configuration in 3D.


https://github.com/user-attachments/assets/ea178e4f-2317-4cf3-af54-b785104a1977


## ✨ Features
- You can choose to display 3 types of optimization:
  - 2 Design Variable optimization (span & chord)
  - 3 Design Variable optimization (span, chord & wing position)
  - Constrained and unconstrained Pareto fronts

## 💻 System Requirements
### Operating System
- Windows 10 or Windows 11 (64-bit)

### Dependencies (Pre-installed in executable)
The standalone executable includes all necessary dependencies. No Python installation required.

## 📥 Installation & Usage
### Option 1: Download Pre-Built Executable (Recommended)
1. **Download** the latest release from the [Releases](../../releases) page
2. **Extract** the entire `C130_Pareto_Optimizer` folder to your desired location
3. **Run** `C130_Pareto_Optimizer.exe`

⚠️ **Important**: Do NOT run only the `.exe` file. The entire folder structure is required, including the `_internal` directory with all dependencies.


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

### Optimization Objectives
The tool visualizes results from optimizations considering:
- Maximum endurance factor
- Structural constraints (inertia/semispan ratio)
- Weight estimation
- Mission time and fuel consumption
- Takeoff distance (FAR25)
- Static stability margin


## 📄 License

This project is provided as-is for educational and research purposes. 

**OpenVSP Notice**: This application includes components from OpenVSP (Open Vehicle Sketch Pad), which is distributed under the NASA Open Source Agreement (NOSA) Version 1.3.



**Note**: This tool is intended for educational and research purposes in aerospace engineering and aircraft design optimization.
