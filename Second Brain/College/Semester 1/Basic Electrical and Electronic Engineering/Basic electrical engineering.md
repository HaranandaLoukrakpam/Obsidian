# [[Basic Electrical Engineering]]

**Tags:** [[Electrical Engineering]] [[Engineering]] [[Basic Electrical Engineering]] [[Physics]] [[Engineering Mathematics]]

---

# [[Definition]]

**[[Basic Electrical Engineering]]** is the branch of engineering concerned with the study of **electricity**, **electrical circuits**, **electrical machines**, and the generation, transmission, distribution, and utilization of electrical energy.

It forms the foundation for advanced subjects such as [[Power Systems]], [[Tags/Electrical Machines]], [[Control Systems]], [[Electronics]], and [[Renewable Energy]].

---

# [[Fundamental Electrical Quantities]]

## [[Electric Charge]]

[[Electric Charge]] is the fundamental property of matter responsible for electrical phenomena.

SI Unit

$$
\text{Coulomb (C)}
$$

Symbol

$$
Q
$$

Relationship

$$
Q=It
$$

where

- $Q$ = Charge (C)
- $I$ = Current (A)
- $t$ = Time (s)

---

## [[Electric Current]]

[[Electric Current]] is the rate of flow of electric charge.

Formula

$$
I=\frac{Q}{t}
$$

SI Unit

$$
\text{Ampere (A)}
$$

Types

- [[Direct Current]]
- [[Alternating Current]]

---

## [[Voltage]]

[[Voltage]] (or [[Potential Difference]]) is the work done to move a unit charge between two points.

Formula

$$
V=\frac{W}{Q}
$$

where

- $W$ = Work Done
- $Q$ = Charge

SI Unit

$$
\text{Volt (V)}
$$

---

## [[Resistance]]

[[Resistance]] is the property of a material that opposes the flow of electric current.

Formula

$$
R=\frac{V}{I}
$$

SI Unit

$$
\Omega
$$

Factors affecting resistance

- Length
- Cross-sectional area
- Material
- Temperature

Also,

$$
R=\rho\frac{L}{A}
$$

where

- $\rho$ = Resistivity
- $L$ = Length
- $A$ = Area

---

## [[Conductance]]

[[Conductance]] measures how easily current flows.

Formula

$$
G=\frac1R
$$

Unit

$$
\text{Siemens (S)}
$$

---

# [[Electrical Power]]

Electrical power is the rate at which electrical energy is converted.

Formula

$$
P=VI
$$

Using [[Ohm's Law]]

$$
P=I^2R
$$

or

$$
P=\frac{V^2}{R}
$$

Unit

$$
\text{Watt (W)}
$$

---

# [[Electrical Energy]]

Electrical energy is the total electrical work done.

Formula

$$
E=Pt
$$

Unit

- Joule (J)
- Kilowatt-hour (kWh)

Relationship

$$
1\text{ kWh}=3.6\times10^6\text{ J}
$$

---

# [[Ohm's Law]]

## [[Statement]]

At constant temperature, the current through a conductor is directly proportional to the applied voltage.

Formula

$$
V=IR
$$

Triangle

```
    V
   ----
   I  R
```

Applications

- Circuit analysis
- Electrical measurements
- Power calculations

Limitations

- Not applicable to nonlinear devices.
- Temperature must remain constant.

---

# [[Electrical Components]]

## [[Resistor]]

A [[Resistor]] opposes current flow.

Symbol

```
──/\/\/──
```

Applications

- Current limiting
- Voltage division
- Biasing circuits

---

## [[Capacitor]]

A [[Capacitor]] stores electrical energy in an electric field.

Formula

$$
Q=CV
$$

Unit

$$
\text{Farad (F)}
$$

Energy Stored

$$
E=\frac12CV^2
$$

Applications

- Filters
- Coupling
- Timing circuits

---

## [[Inductor]]

An [[Inductor]] stores energy in a magnetic field.

Voltage equation

$$
V=L\frac{di}{dt}
$$

Energy Stored

$$
E=\frac12LI^2
$$

Unit

$$
\text{Henry (H)}
$$

Applications

- Filters
- Transformers
- Motors

---

# [[Kirchhoff's Laws]]

## [[Kirchhoff's Current Law]]

### [[Statement]]

The algebraic sum of currents entering and leaving a junction is zero.

Formula

$$
\sum I=0
$$

Example

Incoming currents

$$
I_1+I_2
$$

Outgoing current

$$
I_3
$$

Then

$$
I_1+I_2=I_3
$$

Applications

- Node analysis
- Current calculations

---

## [[Kirchhoff's Voltage Law]]

### [[Statement]]

The algebraic sum of all voltages around any closed loop is zero.

Formula

$$
\sum V=0
$$

Applications

- Loop analysis
- Circuit solving

---

# [[Series Circuits]]

Components connected one after another.

Current

$$
I=I_1=I_2=I_3
$$

Equivalent Resistance

$$
R_{eq}=R_1+R_2+R_3+\cdots
$$

Voltage

$$
V=V_1+V_2+V_3
$$

Characteristics

- Same current
- Different voltage drops

---

# [[Parallel Circuits]]

Components connected across the same voltage.

Voltage

$$
V=V_1=V_2=V_3
$$

Equivalent Resistance

$$
\frac1{R_{eq}}
=
\frac1{R_1}
+
\frac1{R_2}
+\cdots
$$

Current

$$
I=I_1+I_2+I_3
$$

Characteristics

- Same voltage
- Different currents

---

# [[Voltage Divider Rule]]

For resistors in series

$$
V_x
=
\frac{R_x}{R_T}V
$$

Applications

- Sensor circuits
- Reference voltages
- Electronic design

---

# [[Current Divider Rule]]

For parallel resistors

$$
I_x
=
I
\frac{R_{other}}{R_1+R_2}
$$

Applications

- Parallel branch analysis

---

# [[Network Theorems]]

Important circuit analysis techniques include

- [[Superposition Theorem]]
- [[Thevenin's Theorem]]
- [[Norton's Theorem]]
- [[Maximum Power Transfer Theorem]]
- [[Millman's Theorem]]
- [[Reciprocity Theorem]]

---

# [[Superposition Theorem]]

Applicable only to linear circuits.

Statement

The response in any element is the algebraic sum of responses produced by each independent source acting alone.

---

# [[Thevenin's Theorem]]

Any linear two-terminal network can be replaced by

- One voltage source

$$
V_{th}
$$

- One resistance

$$
R_{th}
$$

connected in series.

Applications

- Simplifies complex circuits.

---

# [[Norton's Theorem]]

Any linear network can be represented by

- One current source

$$
I_N
$$

- One resistance

$$
R_N
$$

connected in parallel.

Relationship

$$
R_N=R_{th}
$$

---

# [[Maximum Power Transfer Theorem]]

Maximum power is transferred when

$$
R_L=R_{th}
$$

where

- $R_L$ = Load Resistance
- $R_{th}$ = Thevenin Resistance

Applications

- Audio systems
- Communication systems
- Impedance matching

---

# [[Applications of Basic Electrical Engineering]]

## [[Residential Electrical Systems]]

- House wiring
- Circuit breakers
- Power distribution

---

## [[Industrial Engineering]]

- Motors
- Transformers
- Automation
- Manufacturing

---

## [[Electronics]]

- Power supplies
- Embedded systems
- Control circuits

---

## [[Renewable Energy]]

- Solar systems
- Wind power
- Battery storage

---

# [[Formula Sheet]]

## [[Ohm's Law]]

$$
V=IR
$$

---

## [[Current]]

$$
I=\frac{Q}{t}
$$

---

## [[Charge]]

$$
Q=It
$$

---

## [[Power]]

$$
P=VI
$$

$$
P=I^2R
$$

$$
P=\frac{V^2}{R}
$$

---

## [[Energy]]

$$
E=Pt
$$

---

## [[Resistance]]

$$
R=\rho\frac{L}{A}
$$

---

## [[Capacitor]]

$$
Q=CV
$$

---

## [[Inductor]]

$$
V=L\frac{di}{dt}
$$

---

# [[Problem Solving Strategy]]

1. Identify the given quantities.
2. Draw the circuit diagram.
3. Apply [[Ohm's Law]].
4. Use [[Kirchhoff's Laws]].
5. Simplify series and parallel networks.
6. Apply appropriate [[Network Theorems]].
7. Calculate power and energy.
8. Verify units and results.

---

# [[Common Mistakes]]

- Confusing current with voltage.
- Incorrect application of [[Kirchhoff's Voltage Law]].
- Adding parallel resistances directly.
- Forgetting unit conversions.
- Using incorrect sign conventions.
- Ignoring power dissipation.

---

# [[Summary]]

[[Basic Electrical Engineering]] provides the fundamental principles required to understand electrical circuits and electrical energy. Core concepts such as [[Ohm's Law]], [[Kirchhoff's Laws]], [[Series Circuits]], [[Parallel Circuits]], [[Electrical Power]], and [[Network Theorems]] form the basis for advanced studies in [[Power Systems]], [[Tags/Electrical Machines]], [[Control Systems]], and [[Electronics]].

---

# [[Related Notes]]

- [[Basic Electronics Engineering]]
- [[Alternating Current]]
- [[Direct Current]]
- [[Tags/Electrical Machines]]
- [[Transformer]]
- [[Power Systems]]
- [[Control Systems]]
- [[Engineering Physics]]
- [[Engineering Mathematics]]
- [[Circuit Analysis]]
- [[Network Theorems]]
- [[Electromagnetism]]
