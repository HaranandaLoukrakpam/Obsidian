# [[Alternating Current (AC) Circuits]]

**Tags:** [[Electrical Engineering]] [[Alternating Current]] [[Circuit Analysis]] [[Engineering Mathematics]]

---

# [[Definition]]

An **[[Alternating Current]] (AC)** is an electric current whose **magnitude and direction change periodically with time**.

Unlike [[Direct Current]], the current reverses its direction after every half cycle.

The most common waveform is the **[[Sinusoidal Waveform]]**.

Current Equation

$$
i(t)=I_m\sin(\omega t+\phi)
$$

Voltage Equation

$$
v(t)=V_m\sin(\omega t+\phi)
$$

where

- $I_m$ = Maximum Current
- $V_m$ = Maximum Voltage
- $\omega$ = Angular Frequency
- $\phi$ = Phase Angle

---

# [[AC Waveform]]

An AC waveform consists of

- [[Positive Half Cycle]]
- [[Negative Half Cycle]]
- [[Peak Value]]
- [[Time Period]]
- [[Frequency]]
- [[Phase Angle]]

---

# [[Time Period]]

The **[[Time Period]]** is the time required to complete one full cycle.

Formula

$$
T=\frac1f
$$

Unit

$$
\text{Second (s)}
$$

---

# [[Frequency]]

The **[[Frequency]]** is the number of complete cycles per second.

Formula

$$
f=\frac1T
$$

Unit

$$
\text{Hertz (Hz)}
$$

Power system frequencies

- India → 50 Hz
- USA → 60 Hz

---

# [[Angular Frequency]]

Angular frequency is

$$
\omega=2\pi f
$$

Unit

$$
\text{rad/s}
$$

---

# [[Peak Value]]

The maximum value attained by an AC quantity.

Examples

$$
V_m
$$

$$
I_m
$$

---

# [[Average Value]]

The average value of a sinusoidal waveform over one half cycle is

Voltage

$$
V_{avg}
=
\frac{2V_m}{\pi}
$$

Current

$$
I_{avg}
=
\frac{2I_m}{\pi}
$$

For one complete cycle

$$
V_{avg}=0
$$

because the positive and negative halves cancel.

---

# [[Root Mean Square (RMS) Value]]

The [[Root Mean Square Value]] is the effective value of an AC quantity.

Voltage

$$
V_{rms}
=
\frac{V_m}{\sqrt2}
$$

Current

$$
I_{rms}
=
\frac{I_m}{\sqrt2}
$$

Importance

- Used in electrical power calculations.
- Household voltage ratings are RMS values.

Example

230 V AC means

$$
230V=V_{rms}
$$

---

# [[Form Factor]]

The ratio of RMS value to Average value.

Formula

$$
\text{Form Factor}
=
\frac{V_{rms}}{V_{avg}}
$$

For a sine wave

$$
1.11
$$

---

# [[Peak Factor]]

Ratio of maximum value to RMS value.

Formula

$$
\text{Peak Factor}
=
\frac{V_m}{V_{rms}}
$$

For a sine wave

$$
1.414
$$

---

# [[Phase Angle]]

The **[[Phase Angle]]** represents the angular displacement between two sinusoidal quantities.

Unit

$$
\text{Degree}
$$

or

$$
\text{Radian}
$$

---

# [[Phasor]]

A **[[Phasor]]** is a rotating vector used to represent sinusoidal voltages and currents.

Advantages

- Simplifies AC calculations.
- Eliminates differential equations.
- Makes circuit analysis easier.

---

# [[Reactance]]

Reactance is the opposition offered by inductors and capacitors to AC.

---

## [[Inductive Reactance]]

Formula

$$
X_L
=
\omega L
=
2\pi fL
$$

Unit

$$
\Omega
$$

Characteristics

- Increases with frequency.
- Current lags voltage by $90^\circ$.

---

## [[Capacitive Reactance]]

Formula

$$
X_C
=
\frac1{\omega C}
=
\frac1{2\pi fC}
$$

Characteristics

- Decreases with frequency.
- Current leads voltage by $90^\circ$.

---

# [[Impedance]]

The total opposition offered to AC.

Symbol

$$
Z
$$

Formula

$$
Z
=
R+jX
$$

Magnitude

$$
|Z|
=
\sqrt{R^2+X^2}
$$

Unit

$$
\Omega
$$

---

# [[AC Circuits]]

## [[Pure Resistive Circuit]]

Voltage and current are in phase.

Phase Difference

$$
0^\circ
$$

Power Factor

$$
1
$$

---

## [[Pure Inductive Circuit]]

Current lags voltage by

$$
90^\circ
$$

Average Power

$$
0
$$

---

## [[Pure Capacitive Circuit]]

Current leads voltage by

$$
90^\circ
$$

Average Power

$$
0
$$

---

# [[Series RLC Circuit]]

Contains

- [[Resistor]]
- [[Inductor]]
- [[Capacitor]]

Impedance

$$
Z
=
\sqrt{R^2+(X_L-X_C)^2}
$$

Phase Angle

$$
\tan\phi
=
\frac{X_L-X_C}{R}
$$

---

# [[Resonance]]

Resonance occurs when

$$
X_L=X_C
$$

Resonant Frequency

$$
f_r
=
\frac1{2\pi\sqrt{LC}}
$$

Properties

- Minimum impedance (parallel circuit differs)
- Maximum current
- Power factor equals 1

Applications

- Radio tuning
- Filters
- Oscillators

---

# [[Power in AC Circuits]]

## [[Active Power]]

Actual power consumed.

Formula

$$
P
=
VI\cos\phi
$$

Unit

$$
\text{Watt}
$$

---

## [[Reactive Power]]

Power exchanged between source and reactive components.

Formula

$$
Q
=
VI\sin\phi
$$

Unit

$$
\text{VAR}
$$

---

## [[Apparent Power]]

Formula

$$
S
=
VI
$$

Unit

$$
\text{VA}
$$

---

# [[Power Triangle]]

Relationship

$$
S^2=P^2+Q^2
$$

---

# [[Power Factor]]

Power Factor

$$
PF=\cos\phi
$$

Types

- [[Lagging Power Factor]]
- [[Leading Power Factor]]
- [[Unity Power Factor]]

Importance

- Higher efficiency
- Lower transmission losses
- Better voltage regulation

Power factor correction

- Capacitor Banks
- Synchronous Condensers

---

# [[Three Phase Systems]]

A [[Three Phase System]] consists of three AC voltages separated by

$$
120^\circ
$$

Advantages

- Constant power
- Higher efficiency
- Smaller conductor size
- Better motor performance

Connections

- [[Star Connection]]
- [[Delta Connection]]

---

## [[Star Connection]]

Relationships

$$
V_L
=
\sqrt3V_P
$$

$$
I_L
=
I_P
$$

---

## [[Delta Connection]]

Relationships

$$
V_L
=
V_P
$$

$$
I_L
=
\sqrt3I_P
$$

---

# [[Applications of AC Circuits]]

- Household power supply
- Industrial motors
- Power transmission
- Electric vehicles
- Renewable energy systems
- Communication systems
- Consumer electronics

---

# [[Formula Sheet]]

## [[Time Period]]

$$
T=\frac1f
$$

---

## [[Frequency]]

$$
f=\frac1T
$$

---

## [[Angular Frequency]]

$$
\omega=2\pi f
$$

---

## [[RMS Value]]

$$
V_{rms}=\frac{V_m}{\sqrt2}
$$

$$
I_{rms}=\frac{I_m}{\sqrt2}
$$

---

## [[Average Value]]

$$
V_{avg}=\frac{2V_m}{\pi}
$$

---

## [[Inductive Reactance]]

$$
X_L=2\pi fL
$$

---

## [[Capacitive Reactance]]

$$
X_C=\frac1{2\pi fC}
$$

---

## [[Impedance]]

$$
Z=\sqrt{R^2+(X_L-X_C)^2}
$$

---

## [[Resonant Frequency]]

$$
f_r=\frac1{2\pi\sqrt{LC}}
$$

---

## [[Active Power]]

$$
P=VI\cos\phi
$$

---

## [[Reactive Power]]

$$
Q=VI\sin\phi
$$

---

## [[Apparent Power]]

$$
S=VI
$$

---

## [[Power Factor]]

$$
PF=\cos\phi
$$

---

# [[Problem Solving Strategy]]

1. Identify the circuit type ([[R]], [[RL]], [[RC]], or [[RLC]]).
2. Calculate [[Reactance]] and [[Impedance]].
3. Determine the [[Phase Angle]].
4. Apply [[Ohm's Law]] for AC circuits.
5. Compute current and voltage.
6. Calculate [[Active Power]], [[Reactive Power]], and [[Apparent Power]].
7. Check the [[Power Factor]].
8. Verify units and final results.

---

# [[Common Mistakes]]

- Confusing peak and RMS values.
- Using DC formulas directly for AC circuits.
- Ignoring the phase angle.
- Mixing resistance with impedance.
- Forgetting that reactance depends on frequency.
- Using incorrect formulas for [[Star Connection]] and [[Delta Connection]].

---

# [[Summary]]

[[Alternating Current]] is the standard form of electrical power used in homes and industries due to its efficient transmission and easy voltage transformation. Understanding concepts such as [[Reactance]], [[Impedance]], [[Resonance]], [[Power Factor]], [[Three Phase Systems]], and [[AC Power]] is essential for analyzing and designing modern electrical systems.

---

# [[Related Notes]]

- [[Basic Electrical Engineering]]
- [[Basic Electronics Engineering]]
- [[Transformer]]
- [[Tags/Electrical Machines]]
- [[Power Systems]]
- [[Electromagnetism]]
- [[Circuit Analysis]]
- [[Engineering Mathematics]]
- [[Complex Numbers]]