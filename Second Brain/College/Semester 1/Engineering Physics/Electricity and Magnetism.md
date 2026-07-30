# [[Electricity and Magnetism]]

## [[Electricity]]

### [[Basic Definitions]]

* **Electric Charge ($q$):** The fundamental property of matter that causes it to experience a force when placed in an electromagnetic field. Measured in Coulombs ($C$).
* **Electric Current ($I$):** The rate of flow of electric charge through a cross-sectional area.

$$I = \frac{dq}{dt}$$



**Variables:** $I$ (Current in Amperes, $A$), $q$ (Charge in Coulombs, $C$), $t$ (Time in seconds, $s$).
* **Voltage or Potential Difference ($V$):** The work done per unit charge to move a charge between two points.

$$V = \frac{dW}{dq}$$



**Variables:** $V$ (Voltage in Volts, $V$), $W$ (Work in Joules, $J$).
* **Power ($P$):** The rate at which electrical energy is transferred by an electric circuit.

$$P = VI = I^2R = \frac{V^2}{R}$$



**SI Unit:** Watts ($W$).

### [[Voltage and Current Sources]]

* **Ideal Voltage Source:** Maintains a constant voltage across its terminals regardless of the current drawn. Internal resistance is zero.
* **Practical Voltage Source:** Modeled as an ideal voltage source in series with an internal resistance ($r$). Terminal voltage drops as load current increases ($V_T = V - Ir$).
* **Ideal Current Source:** Delivers a constant current regardless of the voltage across its terminals. Internal resistance is infinite.
* **Practical Current Source:** Modeled as an ideal current source in parallel with an internal resistance.

### [[Basic Circuit Components]]

| Component | Symbol | Governing Equation | Physical Significance | Energy Storage |
| --- | --- | --- | --- | --- |
| **Resistor** | $R$ | $V = IR$ | Opposes current flow | Dissipates as heat |
| **Capacitor** | $C$ | $I = C \frac{dV}{dt}$ | Opposes change in voltage | Stores in Electric Field |
| **Inductor** | $L$ | $V = L \frac{dI}{dt}$ | Opposes change in current | Stores in Magnetic Field |

### [[Ohm's Law]]

At a constant temperature, the current flowing through a linear conductor is directly proportional to the potential difference applied across its ends.

$$V = IR$$

**Variables:**

* $V$: Voltage across the conductor ($V$)
* $I$: Current flowing through the conductor ($A$)
* $R$: Resistance of the conductor ($\Omega$, Ohms)

### [[Series and Parallel Resistance Circuits]]

**Series Circuit:**
Resistors are connected end-to-end. The same current flows through all resistors.


$$R_{eq} = R_1 + R_2 + ... + R_n$$

**Parallel Circuit:**
Resistors are connected across the same two nodes. The same voltage appears across all resistors.


$$\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + ... + \frac{1}{R_n}$$

### [[Kirchhoff's Laws]]

**Kirchhoff's Current Law (KCL):**
Based on the conservation of charge. The algebraic sum of all currents entering and leaving a node is zero.


$$\sum I_{in} = \sum I_{out}$$

**Kirchhoff's Voltage Law (KVL):**
Based on the conservation of energy. The algebraic sum of all voltages (drops and rises) around any closed loop in a circuit is zero.


$$\sum V = 0$$

### [[Nodal Analysis]] and [[Mesh Analysis]]

* **[[Nodal Analysis]]:** Based on KCL. Assign a reference node (Ground, $0V$). Assign node voltages ($V_1, V_2$) to other nodes. Apply KCL at each principal node expressing currents in terms of node voltages using Ohm's Law. Solve the simultaneous equations for node voltages.
* **[[Mesh Analysis]]:** Based on KVL. A mesh is a loop that contains no other loops. Assign a mesh current ($I_1, I_2$) to each mesh. Apply KVL around each mesh expressing voltage drops in terms of mesh currents. Solve for mesh currents.

---

### Solved Example: Mesh Analysis

**Problem:** A circuit has two meshes. Mesh 1 has a $10V$ source in series with a $2\Omega$ resistor, sharing a $3\Omega$ central resistor with Mesh 2. Mesh 2 completes its loop with a $4\Omega$ resistor. Find mesh currents $I_1$ and $I_2$.

**Solution:**

1. Apply KVL to Mesh 1 (assuming clockwise current $I_1$):

$$10 - 2I_1 - 3(I_1 - I_2) = 0 \implies 5I_1 - 3I_2 = 10 \quad \text{--- (Eq 1)}$$


2. Apply KVL to Mesh 2 (assuming clockwise current $I_2$):

$$-3(I_2 - I_1) - 4I_2 = 0 \implies -3I_1 + 7I_2 = 0 \implies I_1 = \frac{7}{3}I_2 \quad \text{--- (Eq 2)}$$


3. Substitute Eq 2 into Eq 1:

$$5\left(\frac{7}{3}I_2\right) - 3I_2 = 10 \implies \frac{35}{3}I_2 - \frac{9}{3}I_2 = 10 \implies \frac{26}{3}I_2 = 10$$


$$I_2 = \frac{30}{26} \approx 1.15 \text{ A}$$


4. Find $I_1$:

$$I_1 = \frac{7}{3}(1.15) \approx 2.69 \text{ A}$$



---

## [[Magnetism]]

### [[Origin of Magnetic Moment]]

Magnetism in materials originates from the motion of electrons within atoms. There are two primary sources:

1. **Orbital Magnetic Moment:** Created by the revolution of electrons around the nucleus (acting like a tiny current loop).
2. **Spin Magnetic Moment:** Created by the intrinsic quantum mechanical spin of the electron on its own axis. This is the dominant contributor to macroscopic magnetism.

### [[Bohr Magneton]]

The [[Bohr Magneton]] ($\mu_B$) is the fundamental quantum of magnetic moment, representing the orbital magnetic moment of an electron in the lowest energy state (ground state) of a hydrogen atom.

$$\mu_B = \frac{eh}{4\pi m_e}$$

**Variables:**

* $\mu_B$: Bohr magneton ($9.274 \times 10^{-24} J/T$ or $A \cdot m^2$)
* $e$: Elementary charge ($1.602 \times 10^{-19} C$)
* $h$: Planck's constant ($6.626 \times 10^{-34} J \cdot s$)
* $m_e$: Rest mass of an electron ($9.109 \times 10^{-31} kg$)

### [[Classification of Magnetism]]

Materials are classified based on their response to an external magnetic field ($H$).

| Type | Response to External Field | Unpaired Electrons? | Examples |
| --- | --- | --- | --- |
| **Diamagnetic** | Weakly repelled | No (All paired) | Bismuth, Copper, Water |
| **Paramagnetic** | Weakly attracted | Yes (Randomly oriented) | Aluminum, Platinum |
| **Ferromagnetic** | Strongly attracted | Yes (Parallel alignment) | Iron, Cobalt, Nickel |

### [[Anti-ferromagnetic Materials]] and [[Ferrites]]

* **[[Anti-ferromagnetic Materials]]:** Neighboring atomic magnetic moments align in a perfectly anti-parallel manner, canceling each other out completely. Net magnetization is zero. (e.g., Manganese oxide, MnO).
* **[[Ferrites]] (Ferrimagnetic Materials):** Neighboring magnetic moments align anti-parallel, but they are of unequal magnitudes. This results in a net spontaneous magnetization. They have high electrical resistivity, reducing eddy current losses, making them ideal for high-frequency applications like transformer cores.

### [[Domain Theory]]

Proposed by Weiss, [[Domain Theory]] explains ferromagnetism. A ferromagnetic material is divided into small microscopic regions called **magnetic domains**.

* Within each domain, all atomic magnetic moments are perfectly aligned, meaning the domain is magnetically saturated.
* In an unmagnetized state, the domains are randomly oriented, canceling out macroscopic magnetization.
* When an external field is applied, domains aligned with the field grow at the expense of others (Domain Wall Motion), and domain magnetization vectors rotate toward the field direction (Domain Rotation).

### [[Hysteresis]]

When a ferromagnetic material is subjected to a varying magnetic field intensity ($H$), the magnetic flux density ($B$) does not trace the same path during magnetization and demagnetization. This lag of $B$ behind $H$ is called [[Hysteresis]].

**ASCII Hysteresis Loop (B-H Curve):**

```text
           B (Flux Density)
           ^
           |      . - ~ ~ - .  <-- Saturation
           |    /             \
 Retentivity|   /               |
      (Br) +-|--/                 |
           | /                  |
           |/                   V
-----------+--------------------+--------> H (Field Intensity)
          /|-                   |
        /  |                    |
      |    |                    |
      |    \                   /
       \    \                 /
         ` - \ _ _ _ _ _ _ _ /
           |

```

* **Retentivity ($B_r$):** The residual magnetic flux density remaining in the material when the external field $H$ is reduced to zero.
* **Coercivity ($H_c$):** The reverse magnetic field intensity required to completely demagnetize the material ($B=0$).

### [[Soft and Hard Magnetic Materials]]

| Property | Soft Magnetic Materials | Hard Magnetic Materials |
| --- | --- | --- |
| **Coercivity ($H_c$)** | Low (easy to demagnetize) | High (hard to demagnetize) |
| **Retentivity ($B_r$)** | High | High |
| **Hysteresis Loop** | Narrow (low energy loss) | Broad (high energy loss) |
| **Applications** | Transformers, AC motors | Permanent magnets, Hard drives |

### [[Applications of Magnetism]]: Magnetic Storage

* **Magnetic Recording and Readout:** Data is stored on a magnetic medium (like a disc or tape) containing tiny magnetic grains. A write head (a small electromagnet) generates a localized magnetic field that aligns the domains of these grains to represent binary `1`s or `0`s (remanent magnetization). A read head senses the changing magnetic flux as the medium moves past it, inducing a voltage pulse (via Faraday's Law) that is decoded back into binary data.
* **Magnetic Tapes:** Used sequential access. A long strip of plastic coated with a fine magnetic powder (like Iron oxide or Chromium dioxide). Highly durable, used for archival storage.
* **Floppy Discs:** A flexible magnetic disk enclosed in a plastic square. Uses concentric tracks and sectors for random access. Now obsolete due to low capacity.
* **Magnetic Disc Drives (Hard Disk Drives - HDDs):** Consists of rigid platters coated with magnetic material spinning at high speeds. A read/write head floats nanometers above the surface on an air bearing. Utilizes [[Hard Magnetic Materials]] to ensure data is retained permanently without power.

---

# [[Formula Sheet]]

* **Ohm's Law:** $V = IR$
* **Electric Power:** $P = VI = I^2R = \frac{V^2}{R}$
* **Equivalent Resistance (Series):** $R_{eq} = R_1 + R_2 + ... + R_n$
* **Equivalent Resistance (Parallel):** $\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + ... + \frac{1}{R_n}$
* **Bohr Magneton:** $\mu_B = \frac{eh}{4\pi m_e}$
* **Current in Capacitor:** $I = C \frac{dV}{dt}$
* **Voltage in Inductor:** $V = L \frac{dI}{dt}$

---

# [[Problem Solving Strategy]]

1. **For Circuit Analysis (Electricity):**
* **Identify the Goal:** Determine if you need a specific voltage, current, or power.
* **Simplify:** Combine any obvious series or parallel resistors before applying complex laws.
* **Choose a Method:** Use [[Nodal Analysis]] if there are fewer nodes than meshes, especially if current sources are present. Use [[Mesh Analysis]] if there are fewer meshes than nodes, especially with many voltage sources.
* **Sign Convention:** Be strictly consistent. For KVL, if you enter a battery at the negative terminal, write it as $-V$. For resistors, current flowing in the direction of your loop causes a voltage drop ($-IR$).


2. **For Magnetism Problems:**
* **Identify the Material:** Knowing if a material is Soft or Hard immediately tells you its hysteresis properties (narrow vs broad loop).
* **Units:** Be extremely careful with SI units in magnetism (Tesla for $B$, Ampere/meter for $H$, Amperes for $I$).



---

# [[Common Mistakes]]

* **Treating Voltage as an Absolute:** Voltage is always a *difference* between two points. In Nodal Analysis, forgetting to subtract the reference node voltage (which is $0V$) conceptually confuses students.
* **Misidentifying Series/Parallel:** Components are only in series if the *exact same* current flows through both. If a node branches off between them, they are not in series.
* **Confusing $B$ and $H$:** Magnetic Field Intensity ($H$) is what you apply (via a coil/current). Magnetic Flux Density ($B$) is the material's response. They are related by $B = \mu H$.
* **Misunderstanding Retentivity vs Coercivity:** Retentivity is the "memory" of the magnet ($B$ when $H=0$). Coercivity is the "stubbornness" or force needed to erase that memory ($H$ when $B=0$).

---

# [[Applications]]

* **Power Grids:** Applying [[Kirchhoff's Laws]] and [[Mesh Analysis]] is fundamental to routing power efficiently across city grids.
* **Transformers:** Utilize [[Soft Magnetic Materials]] (like silicon steel or ferrites) to minimize hysteresis losses while stepping up/down AC voltages.
* **Data Storage:** The entire modern cloud infrastructure still relies heavily on high-density Hard Disk Drives (HDDs), which utilize [[Hard Magnetic Materials]] and giant magnetoresistance (read heads) for massive data storage.
* **Medical Imaging:** MRI machines rely on the magnetic moments of protons (similar principles to electron spin) interacting with enormous external magnetic fields.

---

# [[Summary]]

The study of [[Electricity and Magnetism]] bridges fundamental physics with applied electrical engineering. [[Electricity]] governs how charge moves to do work, modeled using precise tools like [[Ohm's Law]], [[Mesh Analysis]], and [[Nodal Analysis]]. Conversely, [[Magnetism]] arises from the quantum mechanical properties of electrons (like the [[Bohr Magneton]]). Understanding how these magnetic moments interact macroscopically allows us to classify materials through [[Domain Theory]] and [[Hysteresis]]. By tuning these properties, engineers create [[Soft Magnetic Materials]] for efficient energy transfer and [[Hard Magnetic Materials]] for permanent data storage in technologies like magnetic disc drives.

---

# [[Related Notes]]

* [[Electromagnetism]]
* [[Circuit Theory]]
* [[Solid State Physics]]
* [[Faraday's Law of Induction]]
* [[Quantum Mechanics]]
* [[Material Science]]