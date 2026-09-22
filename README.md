# 🚀 Projectile Motion Simulator

An interactive, physics-based projectile motion calculator and simulator with real-time animation, visualization, and comprehensive physics calculations.

**Created by:** Zubair Ahmed
**Version:** 1.0

---

## ✨ Features

### 🎯 Interactive Calculator
- **Adjustable Parameters:**
  - Initial velocity (0.1 - 100 m/s)
  - Launch angle (0° - 90°)
  - Initial height (0 - 500 m)
  - Gravity customization (0.1 - 50 m/s²)
  - Air resistance toggle (beta feature)

- **Real-time Updates:**
  - Dual input methods: Number inputs and range sliders
  - Instant parameter synchronization
  - Live visual feedback

### 📊 Physics Calculations
Automatically calculates and displays:
- **Maximum height** reached by projectile
- **Time to maximum height**
- **Total flight time**
- **Horizontal range** (distance traveled)
- **Impact velocity** (speed at ground impact)
- **Impact angle** (angle at which projectile hits ground)

### 🎬 Animation & Visualization
- **Smooth animated trajectory** with real-time position tracking
- **Velocity vector** display (green arrow showing direction and magnitude)
- **Interactive canvas** showing:
  - Grid system with distance markers
  - Coordinate axes with labels
  - Ground and landscape visualization
  - Initial position and impact point markers
  - Real-time position, height, and velocity data

- **Animation Controls:**
  - Play/Pause functionality
  - Adjustable animation speed (0.25x - 3x)
  - Reset button for quick resets
  - Smooth frame-by-frame rendering

### 🔬 Physics Features
- **Accurate Kinematic Equations:**
  - y(t) = y₀ + v₀sin(θ)·t - ½g·t²
  - x(t) = v₀cos(θ)·t
  - h_max = y₀ + (v₀sin(θ))²/(2g)
  - Range = v₀²sin(2θ)/g

- **Optional Air Resistance** (Beta):
  - Drag force calculations
  - Realistic trajectory modeling
  - Adjustable parameters

### 🎮 Preset Scenarios
Quick-load common physics scenarios:
- **45° Classic:** Standard textbook example
- **Max Range:** Optimal angle for maximum distance
- **High Arc:** Steep trajectory (75°)
- **Low Angle:** Shallow trajectory (15°)
- **Tower Drop:** Vertical launch from height (90°)
- **Moon Shot:** Lunar gravity simulation (g = 1.62 m/s²)

### 🌓 User Interface
- **Professional Design:**
  - Clean, modern interface
  - Responsive layout (desktop and mobile)
  - Dark/Light mode toggle
  - Smooth transitions and animations
  - Intuitive controls

- **Educational Elements:**
  - Physics equation display
  - Quick start guide
  - Detailed result cards with units
  - Visual feedback for all interactions

---

## 🚀 Quick Start

### Option 1: Direct Use
1. Download or clone the repository
2. Open `index.html` in any modern web browser
3. Adjust parameters using sliders or number inputs
4. Click "Launch" to start the simulation
5. Watch the animation play out in real-time

### Option 2: Online
Simply open the `index.html` file with your browser - no installation needed!

### Step-by-Step Guide
1. **Set Initial Conditions:**
   - Enter velocity (how fast the projectile is launched)
   - Set launch angle (0° = horizontal, 90° = vertical)
   - Optional: Set initial height above ground
   - Optional: Adjust gravity (for Earth or other planets)

2. **Launch the Simulation:**
   - Click the "🎯 Launch" button
   - Watch the red projectile animate along the trajectory
   - Green arrows show velocity vector
   - Results update in real-time

3. **Analyze Results:**
   - Check calculated physics values in the results panel
   - Maximum height reached
   - Total flight time
   - Horizontal distance covered
   - Impact velocity

4. **Experiment:**
   - Pause animation to study specific points
   - Adjust speed multiplier for detailed observation
   - Try different presets to understand physics principles
   - Toggle air resistance to see its effects

---

## 📐 Physics Background

### Projectile Motion Basics
Projectile motion is the motion of an object thrown or projected into the air, subject to gravity. It combines:
- **Horizontal motion:** Constant velocity (no acceleration)
- **Vertical motion:** Constant acceleration (gravity)

### Key Equations Used

**Position Equations:**
```
x(t) = v₀ cos(θ) × t
y(t) = y₀ + v₀ sin(θ) × t - ½g × t²
```

**Velocity Equations:**
```
vₓ(t) = v₀ cos(θ)
vᵧ(t) = v₀ sin(θ) - g × t
```

**Key Parameters:**
```
Maximum Height: h_max = y₀ + (v₀ sin(θ))² / (2g)
Time to Max Height: t_max = v₀ sin(θ) / g
Flight Time: Solve y(t) = 0 for t
Range: R = v₀² sin(2θ) / g  [when y₀ = 0]
```

### Air Resistance (Beta Feature)
When enabled, the simulator accounts for:
- Drag force proportional to velocity squared
- Sphere drag coefficient (Cd ≈ 0.47)
- Air density effects
- Realistic curved trajectories

---

## 🛠️ Technical Details

### Technology Stack
- **HTML5:** Structure and semantic markup
- **CSS3:** Modern styling with CSS variables and animations
- **JavaScript (Vanilla):** Pure physics engine, no external dependencies
- **Canvas API:** Graphics rendering and animation

### Browser Compatibility
- Chrome/Chromium 60+
- Firefox 55+
- Safari 11+
- Edge 79+
- Mobile browsers (iOS Safari, Chrome Mobile)

### File Structure
```
projectile-motion-simulator/
├── README.md                    # This file - documentation
├── LICENSE                      # MIT License
├── index.html                   # Complete application (all-in-one)
└── docs/
    └── physics-equations.md     # Detailed physics explanations
```

### Code Architecture

**Physics Engine (`ProjectileSimulator`):**
- Handles all kinematic calculations
- Two calculation modes: with/without air resistance
- Stores trajectory points and results
- Updates in real-time

**Animation Engine (`AnimationEngine`):**
- Renders canvas graphics
- Manages animation loop using requestAnimationFrame
- Controls animation speed and pause/play
- Draws trajectories, projectile, and UI elements

**UI Controller:**
- Event listeners for all inputs
- Synchronizes number inputs with range sliders
- Theme management
- Preset loading

---

## 🎨 Customization

### Colors
Edit CSS variables in the `<style>` section:
```css
:root {
    --primary-color: #2563eb;      /* Blue */
    --secondary-color: #1e40af;    /* Dark Blue */
    --success-color: #10b981;      /* Green */
    --danger-color: #ef4444;       /* Red */
    /* ... more colors ... */
}
```

### Physics Parameters
Modify default values in JavaScript:
```javascript
this.v0 = 20;           // Initial velocity
this.angle = 45;        // Launch angle
this.h0 = 0;            // Initial height
this.g = 9.81;          // Gravity
this.dragCoefficient = 0.47;  // For air resistance
```

### Presets
Add new scenarios in the `loadPreset()` function:
```javascript
const presets = {
    'custom': { v0: 25, angle: 60, h0: 10, g: 9.81 }
};
```

---

## 🔬 Educational Use Cases

This simulator is perfect for:

1. **Physics Classrooms:**
   - Teaching projectile motion concepts
   - Understanding trajectory equations
   - Exploring effects of angle, velocity, and gravity
   - Comparing theoretical vs. simulated values

2. **Engineering Courses:**
   - Kinematics and dynamics
   - Trajectory analysis
   - Air resistance and real-world effects
   - Mathematical modeling

3. **Self-Learning:**
   - Interactive experimentation
   - Visual understanding of physics
   - Quick scenario testing
   - Equation verification

4. **Research & Analysis:**
   - Testing physics models
   - Data collection for projectile motion
   - Comparing calculation methods

---

## 🐛 Known Limitations

- **Air Resistance:** Simplified sphere drag model (approximate for real objects)
- **Maximum Height Display:** Calculated value shown (may reach beyond canvas)
- **Precision:** Limited to floating-point precision (~10 significant figures)
- **Very High Trajectories:** Canvas scaling optimizes for typical cases

---

## 🔮 Future Enhancements

- [ ] Multiple simultaneous projectiles
- [ ] Trajectory comparison mode
- [ ] Export simulation data (CSV/JSON)
- [ ] Custom gravity presets (planets/moons)
- [ ] Collision detection with obstacles
- [ ] Advanced air resistance model (include spin)
- [ ] Data visualization and graphing tools
- [ ] Mobile app version

---

## 📝 License

This project is licensed under the MIT License - see the `LICENSE` file for details.

MIT License © 2024 Zubair Ahmed

---

## 🤝 Contributing

Contributions are welcome! Ways you can contribute:

1. **Bug Reports:** Open an issue describing the problem
2. **Feature Requests:** Suggest new features or improvements
3. **Code Improvements:** Fork the repository and submit pull requests
4. **Documentation:** Improve or translate documentation
5. **Educational Content:** Add tutorials or physics explanations

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

---

## 📧 Contact & Support

**Author:** Zubair Ahmed
**Email:** Contact through GitHub

For issues, questions, or suggestions, please open an issue on the GitHub repository.

---

## 🙏 Acknowledgments

- Physics principles from classical mechanics
- Canvas rendering techniques and best practices
- Community feedback and testing

---

## 📚 Additional Resources

### Physics References
- "Classical Mechanics" by John R. Taylor
- Khan Academy: Projectile Motion
- MIT OpenCourseWare: Physics I

### Web Technologies
- MDN Web Docs: Canvas API
- W3C Standards: HTML5 & CSS3
- JavaScript.info: Modern JavaScript

---

**Version History:**
- **v1.0** (2024): Initial release with core features, presets, dark mode, and air resistance

---

Happy Simulating! 🚀
