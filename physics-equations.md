# 📐 Projectile Motion: Physics Equations & Derivations

## Overview
Projectile motion is the motion of an object thrown or projected into the air, subject only to the force of gravity. This document explains the physics and mathematics used in the simulator.

---

## 1. Fundamental Equations

### 1.1 Position Equations (Kinematic)

**Horizontal Position:**
```
x(t) = v₀ₓ · t
x(t) = v₀ cos(θ) · t
```
- **x(t):** Horizontal position at time t
- **v₀ₓ:** Initial horizontal velocity component
- **v₀:** Initial velocity magnitude
- **θ:** Launch angle
- **t:** Time elapsed

**Vertical Position:**
```
y(t) = y₀ + v₀ᵧ · t - ½g · t²
y(t) = y₀ + v₀ sin(θ) · t - ½g · t²
```
- **y(t):** Vertical position at time t
- **y₀:** Initial height above ground
- **v₀ᵧ:** Initial vertical velocity component
- **g:** Gravitational acceleration (≈ 9.81 m/s² on Earth)

---

## 2. Velocity Equations

### 2.1 Velocity Components

**Horizontal Velocity (constant):**
```
vₓ(t) = v₀ cos(θ)
```
No horizontal acceleration; horizontal velocity remains constant.

**Vertical Velocity (affected by gravity):**
```
vᵧ(t) = v₀ sin(θ) - g · t
```
Vertical velocity decreases linearly with time due to gravitational acceleration.

### 2.2 Total Velocity Magnitude

```
v(t) = √[vₓ(t)² + vᵧ(t)²]
v(t) = √[(v₀ cos(θ))² + (v₀ sin(θ) - g·t)²]
```

### 2.3 Velocity Direction (Angle)

```
α(t) = arctan(vᵧ(t) / vₓ(t))
α(t) = arctan[(v₀ sin(θ) - g·t) / (v₀ cos(θ))]
```

---

## 3. Key Parameters

### 3.1 Maximum Height

**Derivation:**
At maximum height, vertical velocity equals zero:
```
vᵧ(t_max) = 0
v₀ sin(θ) - g · t_max = 0
t_max = v₀ sin(θ) / g
```

Substituting back into y(t):
```
h_max = y₀ + v₀ sin(θ) · (v₀ sin(θ)/g) - ½g · (v₀ sin(θ)/g)²
h_max = y₀ + (v₀ sin(θ))² / g - (v₀ sin(θ))² / (2g)
h_max = y₀ + (v₀ sin(θ))² / (2g)
```

**Formula:**
```
h_max = y₀ + (v₀²sin²(θ)) / (2g)
```

**Key Insight:** Maximum height depends on:
- Initial velocity (v₀²)
- Launch angle (sin²(θ)) - maximum at 90°
- Gravity (1/g)

### 3.2 Time to Maximum Height

```
t_max = v₀ sin(θ) / g
```

### 3.3 Total Flight Time (Time of Flight)

**Derivation:**
Projectile hits ground when y(t) = 0:
```
0 = y₀ + v₀ sin(θ) · t - ½g · t²
```

Rearranging (standard form quadratic equation):
```
½g · t² - v₀ sin(θ) · t - y₀ = 0
```

Using quadratic formula:
```
t = [v₀ sin(θ) ± √((v₀ sin(θ))² + 2g·y₀)] / g
```

Taking positive root:
```
t_flight = [v₀ sin(θ) + √((v₀ sin(θ))² + 2g·y₀)] / g
```

**Special Case (y₀ = 0):**
```
t_flight = 2v₀ sin(θ) / g
```
This is exactly twice the time to maximum height.

### 3.4 Horizontal Range (Distance)

**Derivation:**
Range is the horizontal distance when y(t) = 0 (at ground level):
```
R = x(t_flight) = v₀ cos(θ) · t_flight
```

For y₀ = 0:
```
R = v₀ cos(θ) · [2v₀ sin(θ) / g]
R = 2v₀² cos(θ) sin(θ) / g
R = v₀² sin(2θ) / g     [using sin(2θ) = 2sin(θ)cos(θ)]
```

**Formula:**
```
R = v₀² sin(2θ) / g  (when y₀ = 0)
```

**Key Insights:**
- Maximum range at θ = 45° (since sin(90°) = 1)
- Maximum range is v₀² / g
- Complementary angles (θ and 90° - θ) give same range
- Range inversely proportional to gravity

### 3.5 Impact Velocity

**Horizontal Component (unchanged):**
```
vₓ_impact = v₀ cos(θ)
```

**Vertical Component at impact:**
```
vᵧ_impact = v₀ sin(θ) - g · t_flight
```

**Magnitude:**
```
v_impact = √[vₓ_impact² + vᵧ_impact²]
```

**Alternative (Energy Method):**
Using conservation of energy:
```
v_impact = √[v₀² + 2g(y₀)]
```
if launched horizontally. For angled launches:
```
v_impact² = v₀² + 2g(y₀ - y_final)
```

### 3.6 Impact Angle

```
α_impact = arctan(|vᵧ_impact| / vₓ_impact)
```

Measured from horizontal. Always steeper than launch angle (except for horizontal launch).

---

## 4. Trajectory Equation

**Parametric Form (time-based):**
```
x = v₀ cos(θ) · t
y = y₀ + v₀ sin(θ) · t - ½g · t²
```

**Cartesian Form (height vs. distance):**
Eliminating time t from parametric equations:
```
t = x / (v₀ cos(θ))
```

Substituting into y equation:
```
y = y₀ + x·tan(θ) - (g·x²) / (2v₀²cos²(θ))
y = y₀ + x·tan(θ) - (g·x²(1 + tan²(θ))) / (2v₀²)
```

**Simplified Form (y₀ = 0):**
```
y = x·tan(θ) - (g·x²) / (2v₀²cos²(θ))
```

This is a **parabola** (quadratic equation in x).

---

## 5. Special Cases

### 5.1 Horizontal Launch (θ = 0°)
```
x(t) = v₀ · t
y(t) = y₀ - ½g · t²

Flight time: t = √(2y₀/g)
Range: R = v₀ · √(2y₀/g)
Impact velocity: v = √(v₀² + 2g·y₀)
```

### 5.2 Vertical Launch (θ = 90°)
```
x(t) = 0
y(t) = y₀ + v₀·t - ½g·t²

Max height: h = y₀ + v₀²/(2g)
Flight time: t = (v₀ + √(v₀² + 2g·y₀)) / g
Range: R = 0 (lands at same spot)
```

### 5.3 Launch and Landing at Same Height (y₀ = 0)
```
Max height: h_max = (v₀ sin(θ))² / (2g)
Flight time: t = 2v₀ sin(θ) / g
Range: R = v₀² sin(2θ) / g
Time to max: t_max = v₀ sin(θ) / g = t_flight / 2
```

---

## 6. Effects of Parameters

### 6.1 Effect of Initial Velocity (v₀)
- **Range:** Proportional to v₀²
- **Max Height:** Proportional to v₀²
- **Flight Time:** Proportional to v₀

**Conclusion:** Doubling initial velocity quadruples the range and max height.

### 6.2 Effect of Launch Angle (θ)
- **Range:** Maximum at 45° (R = v₀²/g)
- **Max Height:** Increases with θ (maximum at 90°)
- **Flight Time:** Increases with θ

**Angle Pairs with Same Range:**
- θ and (90° - θ) give the same range
- Example: 30° and 60°, 20° and 70°, etc.

### 6.3 Effect of Gravity (g)
- **Range:** Inversely proportional (R ∝ 1/g)
- **Max Height:** Inversely proportional (h ∝ 1/g)
- **Flight Time:** Inversely proportional (t ∝ 1/√g)

**Moon Example:** g_moon = 1.62 m/s² (≈ 1/6 Earth)
- Same v₀ gives ~6 times greater range
- Same v₀ gives ~6 times greater height
- Same v₀ gives ~2.4 times longer flight time

### 6.4 Effect of Initial Height (y₀)
- **Range:** Increases (more time in air)
- **Max Height:** Higher absolute maximum
- **Flight Time:** Increases

**Formula with y₀:**
```
t_flight = [v₀ sin(θ) + √((v₀ sin(θ))² + 2g·y₀)] / g
```

---

## 7. Air Resistance Considerations

### 7.1 Drag Force

**Quadratic Drag Force:**
```
F_drag = ½ · ρ · v² · C_d · A
```

Where:
- **ρ:** Air density (~1.225 kg/m³ at sea level)
- **v:** Velocity magnitude
- **C_d:** Drag coefficient (0.47 for sphere)
- **A:** Cross-sectional area (πr²)

### 7.2 Equations of Motion with Drag

**Acceleration Components:**
```
aₓ = -(ρ · C_d · A) / (2m) · v · vₓ
aᵧ = -g - (ρ · C_d · A) / (2m) · v · vᵧ
```

**Effects:**
- Trajectory is no longer parabolic
- Maximum height reduced
- Range significantly reduced
- Impact velocity lower
- Trajectory more asymmetric

### 7.3 Drag Coefficient (C_d) Values
- Sphere: 0.47
- Cylinder: 1.15
- Cube: 1.05
- Smooth sphere (golf ball): 0.1-0.2 (with dimples)

---

## 8. Numerical Implementation

### 8.1 Algorithm for Projectile Motion

```
1. Parse input parameters (v₀, θ, y₀, g)
2. Convert angle to radians: θ_rad = θ * π/180
3. Calculate velocity components:
   - vₓ = v₀ * cos(θ_rad)
   - vᵧ = v₀ * sin(θ_rad)
4. Calculate flight time using quadratic formula
5. Generate trajectory points:
   For t from 0 to t_flight with small steps Δt:
       x = vₓ * t
       y = y₀ + vᵧ * t - 0.5 * g * t²
       Store (x, y) point
6. Calculate all result parameters
7. Render animation using stored points
```

### 8.2 Numerical Integration for Air Resistance

```
1. Initial conditions: x=0, y=y₀, vₓ=v₀cos(θ), vᵧ=v₀sin(θ)
2. Time step: Δt (typically 0.01s)
3. Loop while y ≥ 0:
   a. Calculate velocity magnitude: v = √(vₓ² + vᵧ²)
   b. Calculate drag acceleration
   c. Update velocities using: v_new = v_old + a * Δt
   d. Update positions using: x_new = x_old + vₓ * Δt
   e. Store point (x, y)
   f. Increment t by Δt
```

---

## 9. Verification & Validation

### 9.1 Quick Checks
For v₀ = 20 m/s, θ = 45°, y₀ = 0, g = 9.81:
- **Max Height:** h = (20² × sin²(45°)) / (2 × 9.81) ≈ 10.2 m ✓
- **Flight Time:** t = 2 × 20 × sin(45°) / 9.81 ≈ 2.89 s ✓
- **Range:** R = 20² × sin(90°) / 9.81 ≈ 40.8 m ✓

### 9.2 Energy Conservation (no air resistance)
```
Total Energy = KE + PE = constant

Initial: E₀ = ½mv₀² + mgy₀
At any time: E = ½m(vₓ² + vᵧ²) + mgy
At impact: E = ½mv_impact² + 0 = E₀
```

---

## 10. Further Reading

### Books
- "Classical Mechanics" - John R. Taylor
- "Introduction to Classical Mechanics" - David Morin
- "Physics for Scientists and Engineers" - Serway & Jewett

### Online Resources
- Khan Academy: Projectile Motion
- MIT OpenCourseWare: Physics I
- PhET Interactive Simulations

### Relevant Topics
- Vectors and components
- Kinematics
- Dynamics and forces
- Energy and work
- Circular motion
- Orbital mechanics

---

**Last Updated:** 2024  
**Author:** Zubair Ahmed
