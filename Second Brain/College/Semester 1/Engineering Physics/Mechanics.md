# [[Mechanics]]

## [[Centre of Mass]]

The [[Centre of Mass]] (CM) of a system of particles is a unique point where the entire mass of the system can be assumed to be concentrated for the purpose of analyzing its translational motion. If an external force is applied at this point, the body will undergo purely translational motion without rotation.

For a system of $n$ discrete particles, the position vector of the centre of mass, $\vec{R}_{cm}$, is given by:

$$\vec{R}_{cm} = \frac{\sum_{i=1}^{n} m_i \vec{r}_i}{\sum_{i=1}^{n} m_i} = \frac{1}{M} \sum_{i=1}^{n} m_i \vec{r}_i$$

**Variables:**

- $\vec{R}_{cm}$: Position vector of the centre of mass ($m$)
    
- $m_i$: Mass of the $i$-th particle ($kg$)
    
- $\vec{r}_i$: Position vector of the $i$-th particle ($m$)
    
- $M$: Total mass of the system ($kg$)
    

For a continuous body, the summation becomes an integral over the volume:

$$\vec{R}_{cm} = \frac{1}{M} \int \vec{r} dm$$

**Physical Significance:** The centre of mass greatly simplifies the analysis of complex systems. Even if a body is rotating or its constituent parts are moving relative to one another, the CM moves exactly as if it were a single particle of mass $M$ acted upon by the net external force.

## [[Conservation of Linear Momentum]]

The [[Linear Momentum]] ($\vec{p}$) of a particle is the product of its mass and velocity ($\vec{p} = m\vec{v}$). According to [[Newton's Second Law of Motion]], the rate of change of linear momentum of a system is directly proportional to the net external force applied to it:

$$\vec{F}_{ext} = \frac{d\vec{P}}{dt}$$

**Principle of Conservation:**

If the net external force acting on a system is zero ($\vec{F}_{ext} = 0$), then the rate of change of the total linear momentum is zero. Therefore, the total linear momentum of the system remains constant.

$$\frac{d\vec{P}}{dt} = 0 \implies \vec{P} = \text{constant}$$

**Variables:**

- $\vec{F}_{ext}$: Net external force ($N$)
    
- $\vec{P}$: Total linear momentum of the system ($kg \cdot m/s$)
    
- $t$: Time ($s$)
    

## [[Moment of Inertia]]

The [[Moment of Inertia]] ($I$) is the rotational analogue of mass. It quantifies a rigid body's resistance to angular acceleration about a specific axis of rotation.

$$I = \sum_{i=1}^{n} m_i r_i^2 \quad \text{(Discrete System)}$$

$$I = \int r^2 dm \quad \text{(Continuous System)}$$

**Variables:**

- $I$: Moment of inertia ($kg \cdot m^2$)
    
- $m_i, dm$: Mass element ($kg$)
    
- $r_i, r$: Perpendicular distance from the axis of rotation ($m$)
    

**Physical Significance:** A larger moment of inertia means it is harder to alter the rotational state of the body (starting, stopping, or changing its rotational speed).

## [[Radius of Gyration]]

The [[Radius of Gyration]] ($k$) is defined as the distance from the axis of rotation to a point where, if the entire mass of the body were concentrated, the body would have the same moment of inertia as its actual distribution.

$$I = Mk^2 \implies k = \sqrt{\frac{I}{M}}$$

**Variables:**

- $k$: Radius of gyration ($m$)
    
- $I$: Moment of inertia ($kg \cdot m^2$)
    
- $M$: Total mass of the body ($kg$)
    

## [[Theorems of Moment of Inertia]]

### [[Parallel Axis Theorem]]

The moment of inertia of a body about any axis is equal to the moment of inertia about a parallel axis passing through its [[Centre of Mass]] plus the product of its mass and the square of the perpendicular distance between the two axes.

$$I = I_{cm} + Md^2$$

### [[Perpendicular Axis Theorem]]

For a planar body (2D lamina), the moment of inertia about an axis perpendicular to its plane is the sum of its moments of inertia about two mutually perpendicular axes lying in its plane and intersecting at the perpendicular axis.

$$I_z = I_x + I_y$$

## [[Moment of Inertia of Standard Continuous Bodies]]

### Derivation: Uniform Circular Disc (about central perpendicular axis)

Consider a uniform circular disc of mass $M$ and radius $R$.

1. **Area mass density:** $\sigma = \frac{M}{\pi R^2}$
    
2. **Elemental ring:** Consider an elemental ring of radius $r$ and thickness $dr$.
    
3. **Area of element:** $dA = 2\pi r dr$
    
4. **Mass of element:** $dm = \sigma dA = (\frac{M}{\pi R^2})(2\pi r dr) = \frac{2M}{R^2} r dr$
    
5. **Moment of inertia of element:** $dI = (dm)r^2 = (\frac{2M}{R^2} r dr)r^2 = \frac{2M}{R^2} r^3 dr$
    
6. **Total Moment of Inertia:** Integrate from $r = 0$ to $r = R$:
    

$$I = \int_{0}^{R} \frac{2M}{R^2} r^3 dr = \frac{2M}{R^2} \left[ \frac{r^4}{4} \right]_{0}^{R} = \frac{2M}{R^2} \frac{R^4}{4} = \frac{1}{2}MR^2$$

### Standard Formulas Table

|**Body**|**Axis of Rotation**|**Moment of Inertia (I)**|
|---|---|---|
|**Circular Disc** (Radius $R$)|Central, perpendicular to plane|$\frac{1}{2}MR^2$|
|**Solid Cylinder** (Radius $R$)|Central geometric axis|$\frac{1}{2}MR^2$|
|**Hollow Cylinder** (Inner $R_1$, Outer $R_2$)|Central geometric axis|$\frac{1}{2}M(R_1^2 + R_2^2)$|
|**Solid Sphere** (Radius $R$)|Central diameter|$\frac{2}{5}MR^2$|
|**Hollow Sphere** (Radius $R$)|Central diameter|$\frac{2}{3}MR^2$|

## [[Kinetic Energy of a Rotating Body]]

When a rigid body rotates about a fixed axis with an [[Angular Velocity]] $\omega$, every particle of mass $m_i$ moves in a circle with linear velocity $v_i = r_i \omega$. The total rotational kinetic energy ($K_{rot}$) is the sum of the kinetic energies of all individual particles.

$$K_{rot} = \sum \frac{1}{2} m_i v_i^2 = \sum \frac{1}{2} m_i (r_i \omega)^2 = \frac{1}{2} \left( \sum m_i r_i^2 \right) \omega^2$$

Substituting the definition of Moment of Inertia:

$$K_{rot} = \frac{1}{2}I\omega^2$$

**Variables:**

- $K_{rot}$: Rotational kinetic energy ($J$)
    
- $I$: Moment of inertia ($kg \cdot m^2$)
    
- $\omega$: Angular velocity ($rad/s$)
    

## [[Relation between Torque and Angular Momentum]]

[[Torque]] ($\vec{\tau}$) is the turning effect of a force, defined as $\vec{\tau} = \vec{r} \times \vec{F}$.

[[Angular Momentum]] ($\vec{L}$) is the moment of linear momentum, defined as $\vec{L} = \vec{r} \times \vec{p}$.

For a rigid body rotating symmetrically about a fixed axis:

$$L = I\omega$$

Differentiating with respect to time:

$$\frac{dL}{dt} = I \frac{d\omega}{dt} = I\alpha$$

From Newton's Second Law for rotation, $\tau = I\alpha$. Therefore, the fundamental relation is:

$$\vec{\tau} = \frac{d\vec{L}}{dt}$$

**Physical Significance:** Torque is the rate of change of angular momentum. If the net external torque is zero, angular momentum is conserved (analogous to linear momentum).

## [[Moment of Inertia of a Diatomic Molecule]]

A diatomic molecule can be modeled as a rigid rotor consisting of two point masses ($m_1$ and $m_2$) separated by a constant bond length $r$. They rotate about their [[Centre of Mass]].

Plaintext

```
    m1                           m2
    (O)--------------------------(O)
      |---- r1 ----|---- r2 ----|
                   CM
```

Distances from the CM:

$r_1 = \frac{m_2}{m_1 + m_2} r$

$r_2 = \frac{m_1}{m_1 + m_2} r$

The Moment of Inertia about the CM is:

$$I = m_1 r_1^2 + m_2 r_2^2$$

Substituting $r_1$ and $r_2$ yields:

$$I = \left( \frac{m_1 m_2}{m_1 + m_2} \right) r^2 = \mu r^2$$

Where $\mu$ is the **Reduced Mass** of the system:

$$\mu = \frac{m_1 m_2}{m_1 + m_2}$$

## [[Rotational Energy State of a Rigid Diatomic Molecule]]

In quantum mechanics, the angular momentum of a rotating system is quantized. The magnitude of angular momentum $L$ for a rigid rotor is restricted to values governed by the rotational quantum number $J$.

$$L^2 = J(J+1)\hbar^2 \quad \text{where } J = 0, 1, 2, ...$$

Here, $\hbar = \frac{h}{2\pi}$ (reduced Planck's constant).

The rotational kinetic energy is given by $E = \frac{L^2}{2I}$. Substituting the quantized $L^2$:

$$E_J = \frac{J(J+1)\hbar^2}{2I} = \frac{h^2}{8\pi^2 I} J(J+1)$$

**Variables:**

- $E_J$: Rotational energy of the $J$-th state ($Joule$)
    
- $h$: Planck's constant ($6.626 \times 10^{-34} J \cdot s$)
    
- $I$: Moment of inertia of the molecule ($kg \cdot m^2$)
    
- $J$: Rotational quantum number (dimensionless integer)
    

**Physical Significance:** Molecules can only exist in specific, discrete rotational energy states. Transitions between these states lead to the absorption or emission of electromagnetic radiation, forming rotational spectra (usually in the microwave region).

## [[Torsional Pendulum]]

A [[Torsional Pendulum]] consists of a rigid body (like a disc) suspended by a wire attached to its centre. When the disc is twisted by an angle $\theta$, the wire exerts a restoring torque proportional to the angle of twist.

$$\tau = -C\theta$$

**Variables:**

- $\tau$: Restoring torque ($N \cdot m$)
    
- $C$: Torsional constant or restoring torque per unit twist ($N \cdot m / rad$)
    
- $\theta$: Angular displacement ($rad$)
    

From the equation of rotational motion, $\tau = I\alpha = I \frac{d^2\theta}{dt^2}$:

$$I \frac{d^2\theta}{dt^2} = -C\theta \implies \frac{d^2\theta}{dt^2} + \left(\frac{C}{I}\right)\theta = 0$$

This is the differential equation for Simple Harmonic Motion (SHM). The angular frequency is $\omega = \sqrt{\frac{C}{I}}$.

The time period of oscillation $T$ is:

$$T = 2\pi \sqrt{\frac{I}{C}}$$

# [[Formula Sheet]]

- **Centre of Mass:** $\vec{R}_{cm} = \frac{1}{M} \sum m_i \vec{r}_i$
    
- **Conservation of Linear Momentum:** $\vec{P}_{initial} = \vec{P}_{final}$ (if $\vec{F}_{ext} = 0$)
    
- **Moment of Inertia:** $I = \sum m_i r_i^2$ or $I = \int r^2 dm$
    
- **Radius of Gyration:** $k = \sqrt{\frac{I}{M}}$
    
- **Parallel Axis Theorem:** $I = I_{cm} + Md^2$
    
- **Perpendicular Axis Theorem:** $I_z = I_x + I_y$
    
- **Rotational Kinetic Energy:** $K = \frac{1}{2}I\omega^2$
    
- **Torque:** $\vec{\tau} = \frac{d\vec{L}}{dt} = I\alpha$
    
- **Angular Momentum:** $L = I\omega$
    
- **Reduced Mass (Diatomic):** $\mu = \frac{m_1 m_2}{m_1 + m_2}$
    
- **Rotational Energy Levels:** $E_J = \frac{h^2}{8\pi^2 I} J(J+1)$
    
- **Time Period of Torsional Pendulum:** $T = 2\pi \sqrt{\frac{I}{C}}$
    

# [[Problem Solving Strategy]]

1. **Identify the Axis:** For any moment of inertia calculation, clearly identify the axis of rotation. The distance $r$ must always be perpendicular to this axis.
    
2. **Use Theorems Wisely:** If the axis doesn't pass through the centre but is parallel to an axis that does, calculate $I_{cm}$ first and apply $I = I_{cm} + Md^2$.
    
3. **Conservation Laws:**
    
    - If no external _force_ is present, apply [[Conservation of Linear Momentum]].
        
    - If no external _torque_ is present, apply Conservation of [[Angular Momentum]] ($I_1\omega_1 = I_2\omega_2$).
        
4. **Energy Approach:** For problems involving changes in speed and height, use the work-energy theorem. Total mechanical energy $E = mgh + \frac{1}{2}mv^2 + \frac{1}{2}I\omega^2$. Remember to link linear and angular velocity using $v = r\omega$ (for rolling without slipping).
    
5. **Diatomic Molecules:** Always compute the reduced mass ($\mu$) before finding the moment of inertia. Convert atomic mass units (amu) to kg if standard SI units are required.
    

# [[Common Mistakes]]

- **Mixing up $v$ and $\omega$:** Not squaring the radius when converting rotational kinetic energy to linear terms ($K_{rot} = \frac{1}{2} (\frac{I}{r^2}) v^2$).
    
- **Misapplying Perpendicular Axis Theorem:** Attempting to use $I_z = I_x + I_y$ on a 3D object like a solid sphere or cylinder. It is exclusively for 2D flat objects (laminae).
    
- **Incorrect "d" in Parallel Axis Theorem:** Using the distance between two random parallel axes. One of the axes _must_ pass through the centre of mass.
    
- **Forgetting to convert units:** In quantum rotational states, the energy differences are tiny. Ensure Planck's constant is in Joules, or use electron-volts ($eV$) based on the problem's requirement.
    

# [[Applications]]

- **Flywheels:** Large discs with high moments of inertia store rotational kinetic energy to smooth out the power output in internal combustion engines.
    
- **Spectroscopy:** Measuring the microwave spectrum of gases allows chemists to determine the precise bond lengths ($r$) of diatomic molecules using the rotational energy level formula.
    
- **Clocks and Timekeeping:** The [[Torsional Pendulum]] is the regulating mechanism in mechanical chronometers and balance-wheel watches, offering highly precise time periods unaffected by gravity.
    
- **Sports Biomechanics:** Divers and gymnasts alter their moment of inertia by tucking or extending their limbs to change their angular velocity in mid-air, relying on the conservation of angular momentum.
    

# [[Summary]]

The mechanics of a system of particles are fundamentally governed by the behavior of the [[Centre of Mass]], allowing complex geometries to be modeled elegantly. When considering rotational dynamics, the [[Moment of Inertia]] serves as the inertial resistance to rotational change, fundamentally linking [[Torque]] and [[Angular Momentum]]. By mastering the Parallel and Perpendicular axis theorems, the rotational properties of macroscopic rigid bodies (like spheres and cylinders) as well as microscopic systems (like diatomic molecules in quantum rotational states) can be effectively analyzed.

# [[Related Notes]]

- [[Classical Mechanics]]
    
- [[Rigid Body Dynamics]]
    
- [[Quantum Mechanics]]
    
- [[Molecular Spectroscopy]]
    
- [[Simple Harmonic Motion]]
    
- [[Work, Energy, and Power]]