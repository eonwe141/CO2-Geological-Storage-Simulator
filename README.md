# CO2 Geological Storage Simulator

A Python-based numerical simulator for modeling CO2 injection and storage in deep saline aquifers with multi-mechanism trapping.

## Features

- **3D Grid System**: Structured Cartesian grid with configurable dimensions
- **Multiphase Flow Physics**: CO2-brine flow with permeability and porosity
- **Trapping Mechanisms**:
  - Structural/stratigraphic trapping (mobile CO2)
  - Residual trapping (immobile CO2 in pore space)
  - Solubility trapping (CO2 dissolution in brine using Duan-Sun model)
- **Dynamic Pressure Modeling**: Pressure buildup and dissipation
- **Plume Migration**: CO2 plume extent calculation
- **Visualization**: Publication-quality plots and data export

## Installation

```bash
git clone https://github.com/eonwe141/CO2-Geological-Storage-Simulator.git
cd CO2-Geological-Storage-Simulator
pip install -r requirements.txt
\```

## Quick Start

\```python
import numpy as np
from src.co2_simulator import Grid3D, CO2StorageSimulation

grid = Grid3D(nx=20, ny=20, nz=5, lx=10000, ly=10000, lz=100)

rock_props = {
    'porosity': 0.20,
    'permeability': 100e-15,
    'S_wr': 0.20,
    'S_gr': 0.15,
    'compressibility': 1e-9,
    'P_initial': 30e6,
    'temperature': 353.15
}

fluid_props = {
    'rho_co2': 700,
    'rho_water': 1000,
    'mu_co2': 5e-5,
    'mu_water': 1e-3
}

injection = {
    'rate': 10e9 / (365.25 * 24 * 3600),
    'duration': 40 * 365.25 * 24 * 3600,
    'dt': 0.1 * 365.25 * 24 * 3600
}

sim = CO2StorageSimulation(grid, rock_props, fluid_props, injection)
sim.run_simulation(output_interval=100)
\```

## Results

After 40 years of injection at 10 Mt/year:

| Metric | Value |
|--------|-------|
| Total CO2 Injected | 15.84 Mt |
| Total CO2 Stored | 3.42 Mt |
| Storage Efficiency | 21.6% |
| Structural Trapping | 87.0% |
| Residual Trapping | 13.0% |
| Maximum Pressure | 343.6 MPa |
| Plume Extent | 8.45 km2 |

## Visualizations

The simulator generates the following figures:
- CO2 mass evolution by trapping mechanism
- Pressure and plume extent evolution
- Storage efficiency over time
- Trapping mechanism distribution

## License

MIT License

## Author

**Athar Nisar Padder**
- GitHub: [@eonwe141](https://github.com/eonwe141)

## Citation

If you use this simulator in your research, please cite:
\```
Padder, A.N. (2026). CO2 Geological Storage Simulator. 
GitHub: https://github.com/eonwe141/CO2-Geological-Storage-Simulator
\```

## References
 
1. Brooks R, Corey T. Hydraulic properties of porous media. Hydrology Papers, Colorado State University. 1964;24:37. 
2. Land CS. Calculation of Imbibition Relative Permeability for Two- and Three Phase Flow From Rock Properties. Society of Petroleum Engineers Journal. 1968;8(02):149–156. 
3. Bachu S. Review of CO2 storage efficiency in deep saline aquifers. International Journal of Greenhouse Gas Control. 2015;40:188–202. 
4. Celia MA, Nordbotten JM. Practical Modeling Approaches for Geological Storage of Carbon Dioxide. Groundwater. 2009;47(5):627–638. 
5. Duan Z, Sun R. An improved model calculating CO2 solubility in pure water and aqueous NaCl solutions from 273 to 533 K and from 0 to 2000 bar. Chemical Geology. 2003;193(3):257–271. 
