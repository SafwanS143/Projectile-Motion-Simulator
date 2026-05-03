# 🎯 Projectile Motion Simulator
### Built with Processing (Java) · Grade 12 Physics & Computer Science Project

A fully interactive 2D projectile motion simulator with a real-time GUI, two distinct simulation modes, and live kinematic readouts. Designed to bridge physics theory and visual computation — you can watch the math play out in real time.

---

## 📸 Overview

This simulator models projectile motion under constant gravitational acceleration. A cannon fires a projectile toward a target (visualized as a horizontal bar), and the program calculates, animates, and reports the full kinematic breakdown of the trajectory — instantaneous velocity components, speed, and elapsed time — all rendered live as the projectile travels.

---

## 🕹️ Modes

### Mode 1 — Verify & Fire
> *"Will this shot hit the target?"*

You provide:
- **Launch angle** (degrees)
- **Initial speed** (m/s)

The simulator will:
- Determine whether the projectile will **hit or miss** the target
- Fire the projectile and animate the full trajectory
- Display live readouts throughout the flight:
  - Instantaneous velocity vector
  - Horizontal velocity component (`vₓ`)
  - Vertical velocity component (`vᵧ`)
  - Current speed (magnitude)
  - Elapsed time
  - Total flight time (displayed on landing)

---

### Mode 2 — Solve & Fire
> *"What speed do I need to hit the target?"*

You provide:
- **Launch angle** (degrees)

The simulator will:
- **Calculate the required initial speed** to hit the target at that angle
- Determine if a valid solution exists (some angles won't reach the target regardless of speed)
- Fire the projectile if a solution is found
- Display the same full live kinematic readouts as Mode 1

---

## 🎮 Customization

In both modes, you can freely reposition:
- 🔫 **The cannon** — drag or set its coordinates on the canvas
- 🎯 **The target** — a flat horizontal bar (think Breakout paddle) that can be placed anywhere on the field

This lets you explore a wide range of scenarios: point-blank shots, long-range arcs, low-angle drives, high-angle lofts, and more.

---

## 📊 Live Kinematic Display

While the projectile is in flight, the HUD updates every frame with:

| Readout | Description |
|---|---|
| `vₓ` | Horizontal velocity (constant throughout flight) |
| `vᵧ` | Vertical velocity (changes due to gravity) |
| `\|v\|` | Instantaneous speed (magnitude of velocity vector) |
| `t` | Elapsed time since launch |
| `Δt` | Total flight duration (shown on impact) |

All values are derived from the standard kinematic equations applied frame-by-frame.

---

## ⚙️ Physics Model

The simulator uses standard 2D projectile motion equations under constant gravitational acceleration:

```
x(t)  = x₀ + v₀·cos(θ)·t
y(t)  = y₀ + v₀·sin(θ)·t − ½·g·t²

vₓ(t) = v₀·cos(θ)            (constant)
vᵧ(t) = v₀·sin(θ) − g·t     (linear decay)
|v(t)| = √(vₓ² + vᵧ²)       (instantaneous speed)
```

Where:
- `v₀` = initial speed
- `θ` = launch angle
- `g` = gravitational acceleration (9.8 m/s²)
- `t` = elapsed time

In **Mode 2**, the required initial speed is solved analytically from the target's known `(x, y)` displacement and the chosen launch angle.

---

## 🛠️ Built With

| Tool | Purpose |
|---|---|
| [Processing](https://processing.org/) | Core graphics and simulation engine |
| [G4P](http://www.lagers.org.uk/g4p/) | GUI elements (sliders, buttons, input fields) |
| Java (via Processing) | Underlying language |

---

## 🚀 Getting Started

### Prerequisites
- [Processing 3+](https://processing.org/download) installed on your machine
- ControlP5 library installed via Processing's Library Manager

### Installing G4P
1. Open Processing
2. Go to **Sketch → Import Library → Manage Libraries**
3. Search for **G4P**
4. Click **Install**

### Running the Simulator
1. Clone or download this repository
2. Open `ProjectileMotionSimulator.pde` in Processing
3. Press the **▶ Run** button (or `Ctrl+R`)

---

## 📁 Project Structure

```
Projectile-Motion-Simulator/
│
├── Projectile_Motion_Simulator.pde   # Main sketch — setup, draw loop, simulation logic
├── Projectile.pde                    # Projectile class — position, velocity, update
├── gui.pde                           # G4P interface — sliders, buttons, HUD
├── myFunctions.pde                   # Helper/utility functions
├── GUI_BUILDER_DATA/                 # G4P GUI builder configuration files
├── data/
│   ├── cannon.png                    # Cannon sprite asset
│   ├── demoData.txt                  # Sample simulation data
│   ├── list_259944                   # G4P generated resource
│   └── list_601711                   # G4P generated resource
└── README.md
```

---

## 💡 Key Concepts Demonstrated

- **Kinematic equations** applied in discrete time steps (Euler integration)
- **Coordinate system transformation** between physics units and pixel space
- **Analytical problem-solving** — deriving `v₀` from target geometry in Mode 2
- **Real-time GUI programming** with event-driven controls
- **Object-oriented design** in a Java-based environment
- **Collision detection** between a moving point and a static horizontal segment

---

## 🔮 Potential Extensions

If this project were to be continued:
- [ ] Air resistance / drag modeling
- [ ] Multiple simultaneous projectiles
- [ ] Moving targets
- [ ] Variable gravity (Moon, Mars modes)
- [ ] Export trajectory data to CSV
- [ ] Angle/speed optimization solver (find the *best* shot)

---

## 👤 Author

**Safwan**
Developed as an educational physics simulation project.

---

## 📄 License

This project was created for educational purposes. Feel free to reference or build on it with credit.
