# Traffic Signal Optimization using Deep Learning + PSO

This repository contains a project on Traffic Signal Optimization using Deep Learning and Particle Swarm Optimization (PSO). The project includes:
- A **SUMO-based simulation** for traffic optimization.
- A **Pygame-based simulation** of Sector 17, Chandigarh, for realistic traffic visualization.
- Implementation of **Deep Learning + PSO** for optimizing traffic signals.

## Features
- **Traffic simulation** for Sector 17, Chandigarh.
- **Deep Learning-based optimization** for adaptive traffic light control.
- **Particle Swarm Optimization (PSO)** to enhance traffic flow.
- **Visualization with Pygame** for interactive traffic scenarios.
- **SUMO integration** for realistic traffic network simulation.
- **Traffic data extraction** from the Pygame simulation for deep learning training.
- **OSMnx integration** for fetching real-world road network data.

## Installation
Ensure you have Python installed (preferably Python 3.8+). Install the required dependencies using:

```bash
pip install numpy pandas tensorflow torch torchvision sumo-tools pygame matplotlib opencv-python networkx scipy osmnx
```

For SUMO, ensure SUMO is installed and added to the system path:

```bash
sudo apt-get install sumo  # Linux
choco install sumo         # Windows (via Chocolatey)
```

## Project Structure
```
├── sumo_files/               # SUMO network files (.net.xml, .rou.xml, etc.)
├── pygame_simulation/        # Pygame simulation for Sector 17
├── deep_learning_model/      # Deep learning model for traffic optimization
├── PSO_optimization/         # Particle Swarm Optimization implementation
├── data/
│   ├── traffic_data.csv      # Extracted traffic data from Pygame simulation
├── main.py                   # Main script to run simulations
├── README.md                 # Project documentation
```

## Running the Project
### 1. Running the SUMO Simulation
```bash
python sumo_simulation.py
```

### 2. Running the Pygame Simulation
```bash
python pygame_simulation.py
```

### 3. Running the Traffic Optimization Model
```bash
python optimize_traffic.py
```

## Traffic Data (`traffic_data.csv`)
The `traffic_data.csv` file contains traffic flow data extracted from the Pygame simulation. This data includes information such as:
- Vehicle count at each signal
- Average waiting time per vehicle
- Signal transition times
- Road congestion levels

This dataset is used to train the deep learning model for traffic signal optimization.

## SUMO Files
The `sumo_files/` directory contains all required `.xml` files for running the SUMO simulation.
- **Network file (`.net.xml`)**: Defines roads and intersections.
- **Route file (`.rou.xml`)**: Defines vehicle routes.
- **Configuration file (`.sumocfg`)**: Configures the SUMO simulation.

## Using OSMnx for Fetching Real-World Data
This project uses **OSMnx** to fetch real-world road network data for Sector 17, Chandigarh, directly from OpenStreetMap. OSMnx enables:
- Importing real-world road networks.
- Converting road data into graph structures for simulation.
- Visualizing road layouts and intersections.

To fetch road network data, use:
```python
import osmnx as ox
G = ox.graph_from_place("Sector 17, Chandigarh, India", network_type='drive')
ox.plot_graph(G)
```
This ensures realistic road network integration for better traffic simulation.




## License
This project is licensed under the MIT License.

