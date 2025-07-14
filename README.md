# Autonomous Exploration on Mars

This project simulates the behavior of an intelligent robotic agent operating on the Martian surface. Inspired by NASA’s Perseverance Rover, the exploration is divided into three phases:

1. **Environment Characterization**
2. **Route Planning using Search Algorithms**
3. **Charging Station Optimization**


---

## 1. Environment Characterization

We analyzed the **Perseverance Rover's** real-world components and modeled its operation as an intelligent agent. Topics explored:

- **Sensors**: Cameras (Mastcam-Z, SuperCam), spectrometers, temperature, pressure, etc.
- **Actuators**: Robotic arm, wheels, motors for mobility and sampling.
- **Computational capabilities**: Space-optimized CPUs (radiation-hardened, low power).
- **Agent Properties**:
  - Single-agent, goal-based
  - Partially observable, stochastic, sequential
  - Dynamic, continuous, and unknown environment

We also defined a PEAS description and evaluated possible agent architectures (e.g., utility-based vs. goal-based) under real hardware constraints.

---

##  2. Route Planning with Search Algorithms

We implemented and benchmarked multiple informed and uninformed search algorithms on simulated maps of Mars:

- **Algorithms tested**:
  - A* Search
  - Uniform Cost Search
  - Greedy Best-First Search
  - Breadth-First Search
  - Limited Depth Search

- **Evaluation Metrics**:
  - Path distance
  - Computation time
  - Terrain constraints (limited elevation gain)

- **Insights**:
  - A* found optimal paths but was slower.
  - Greedy search was fast but returned longer routes.
  - DFS was inefficient and unreliable for large maps.
  - Route planning quality highly depends on terrain, goal location, and algorithm choice.

---

## 3. Charging Station Optimization

We tackled a **Constraint Satisfaction Problem (CSP)** to place charging stations under realistic conditions:

### CSP Problem (Backtracking):
- **Variables**: Coordinates of 8 charging stations
- **Constraints**:
  - No placement in restricted (gray) areas
  - Distance between stations ≥ 1 km
  - Distance to nearest station ≤ 3 km

### Local Search Optimization:
To **maximize coverage**, we used:
- **Greedy Search**
- **Simulated Annealing**

Both aimed to optimize **visibility** (area within 2km radius). Greedy search surprisingly outperformed simulated annealing in most trials, likely due to a low number of local optima.

---

## Key Learnings

- **Backtracking** is excellent for satisfying strict spatial constraints, though not necessarily optimal.
- **Local search algorithms** can be adapted to terrain optimization if designed carefully.
- **Agent design** for real-world conditions must consider computational limitations, noisy sensors, and dynamic environments.
- Modeling agent behavior with PEAS and search strategies builds strong foundations for intelligent autonomy in extraterrestrial environments.

---

## Tech Stack

- `Python`, `Matplotlib`, `NumPy`
- Custom grid/map generators
- Image-to-grid coordinate mapping
- SimpleAI library for CSP modeling
- Visualization of routes and station placements

---

## Authors

- **Daniel Alberto Sánchez Fortiz**   
- **Diego Vértiz Padilla**  
- **Gustavo Andrés Aguilar Torreblanca**  
