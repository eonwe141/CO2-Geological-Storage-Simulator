# CO2 Geological Storage Simulator

A Python-based numerical simulator for modeling CO2 injection and storage in deep saline aquifers with multi-mechanism trapping.


## 📖 Publication

**Padder, A.** (2026). *Numerical Simulation of CO₂ Geological Storage in Deep Saline Aquifers: A Multiphase Flow Approach with Coupled Trapping Mechanisms* (1.0.0). Zenodo.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18259641.svg)](https://doi.org/10.5281/zenodo.18259641)

**Full Paper:** [https://doi.org/10.5281/zenodo.18259641](https://doi.org/10.5281/zenodo.18259641)

---

## 🎯 Key Features

### ✅ **Multi-Mechanism CO2 Trapping**
- **Structural trapping**: Buoyancy-driven CO2 accumulation beneath caprock
- **Residual trapping**: Immobilization through capillary effects
- **Solubility trapping**: CO2 dissolution in formation brine
- **Mineral trapping**: Long-term geochemical sequestration

### 📊 **Simulation Capabilities**

| Feature | Specification | Significance |
|---------|--------------|--------------|
| **Grid Resolution** | 40×40×8 cells | High-resolution 3D modeling |
| **Injection Rate** | 20 Mt/year | Industrial-scale operations |
| **Simulation Period** | 50 years | Long-term storage assessment |
| **Aquifer Depth** | 1000-1200 m | Supercritical CO2 conditions |
| **Storage Efficiency** | 2.5% of pore volume | Optimized capacity utilization |

### ⚙️ **Technical Highlights**
- ✅ **Coupled multiphase flow**: Two-phase (CO2-brine) system with phase transitions
- ✅ **Brooks-Corey model**: Relative permeability and capillary pressure
- ✅ **Finite difference method**: Implicit pressure, explicit saturation (IMPES)
- ✅ **Real-time visualization**: Saturation, pressure, and trapping mechanism evolution

---

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/eonwe141/CO2-Geological-Storage-Simulator.git
cd CO2-Geological-Storage-Simulator

# Install dependencies
pip install -r requirements.txt
Requirements
python
numpy>=1.21.0
matplotlib>=3.4.0
scipy>=1.7.0
pandas>=1.3.0
💻 Usage
Basic Simulation
python
from co2_storage_simulator import CO2Simulator

# Initialize simulator
sim = CO2Simulator(
    grid_size=(40, 40, 8),
    injection_rate=20,  # Mt/year
    duration=50  # years
)

# Run simulation
results = sim.run()

# Visualize results
sim.plot_saturation()
sim.plot_pressure()
sim.plot_trapping_mechanisms()
Advanced Configuration
python
# Custom reservoir parameters
sim = CO2Simulator(
    permeability=100,  # mD
    porosity=0.25,
    depth_range=(1000, 1200),  # meters
    temperature=45,  # °C
    salinity=0.1  # mol/L NaCl
)
📈 Results
Key Achievements
🎯 Storage Capacity: 25 Mt CO2 over 50 years
📊 Trapping Distribution:

Structural: 65%

Residual: 22%

Solubility: 10%

Mineral: 3%

🔬 Validation: Results consistent with field-scale CO2 storage projects (Sleipner, Norway)

Visualization Outputs
The simulator generates:

CO2 saturation distribution maps

Pressure evolution profiles

Trapping mechanism time series

Storage efficiency metrics

📚 Dataset & Methodology
Physical Model
Reference Aquifer: Deep saline formation (1000-1200 m depth)
Properties:

Porosity: 0.25

Permeability: 100 mD

Temperature: 45°C

Initial Pressure: 110 bar

Governing Equations
The simulator solves:

Mass conservation for CO2 and brine phases

Darcy's law for multiphase flow

Phase equilibrium (Henry's law for solubility)

Geochemical reactions (simplified mineral trapping)

Numerical Scheme
Spatial discretization: Finite differences (40×40×8 grid)

Temporal integration: IMPES (Implicit Pressure, Explicit Saturation)

Time step: Adaptive (0.01-1 year)

Convergence criterion: 10⁻⁶ relative error

📖 Citation
If you use this simulator in your research, please cite:

text
@software{padder2026co2storage,
  title={Numerical Simulation of CO₂ Geological Storage in Deep Saline Aquifers: 
         A Multiphase Flow Approach with Coupled Trapping Mechanisms},
  author={Padder, A.},
  year={2026},
  version={1.0.0},
  publisher={Zenodo},
  doi={10.5281/zenodo.18259641},
  url={https://doi.org/10.5281/zenodo.18259641}
}
APA Format:

text
Padder, A. (2026). Numerical Simulation of CO₂ Geological Storage in Deep Saline 
Aquifers: A Multiphase Flow Approach with Coupled Trapping Mechanisms (1.0.0). 
Zenodo. https://doi.org/10.5281/zenodo.18259641

🤝 Contributing
Contributions are welcome! Please:

Fork the repository

Create a feature branch (git checkout -b feature/improvement)

Commit changes (git commit -m 'Add new feature')

Push to branch (git push origin feature/improvement)

Open a Pull Request

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🔗 Links
Publication: DOI: 10.5281/zenodo.18259641

GitHub Repository: eonwe141/CO2-Geological-Storage-Simulator

Version: 1.0.0

🙏 Acknowledgments
This research presents a comprehensive numerical framework for CO2 geological storage simulation with coupled trapping mechanisms, designed for academic research and educational purposes.
