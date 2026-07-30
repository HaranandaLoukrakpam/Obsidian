# [[Basic Quantum Mechanics]]

## [[Photons and Light Waves]]

In classical physics, light was strictly understood as an electromagnetic wave. However, phenomena like the photoelectric effect and blackbody radiation could not be explained using the wave theory of light. This led to the concept of [[Wave-Particle Duality]].

Light behaves both as a continuous wave and as a stream of discrete energy packets called **photons**. The energy of a single photon is directly proportional to the frequency of the light wave:

$$E = h\nu = \frac{hc}{\lambda}$$

**Variables:**

* $E$: Energy of the photon ($J$ or $eV$)
* $h$: Planck's constant ($6.626 \times 10^{-34} J \cdot s$)
* $\nu$: Frequency of the light wave ($Hz$ or $s^{-1}$)
* $c$: Speed of light in vacuum ($3 \times 10^8 m/s$)
* $\lambda$: Wavelength ($m$)

Additionally, a photon possesses [[Momentum]] despite having zero rest mass:

$$p = \frac{E}{c} = \frac{h}{\lambda}$$

## [[Electrons and Matter Waves]]

In 1924, Louis de Broglie proposed that if light waves can exhibit particle-like properties, then material particles (like electrons, protons, and atoms) should exhibit wave-like properties. These are known as [[Matter Waves]].

The de Broglie wavelength of a particle is inversely proportional to its momentum:

$$\lambda = \frac{h}{p} = \frac{h}{mv}$$

**Variables:**

* $\lambda$: de Broglie wavelength ($m$)
* $h$: Planck's constant ($J \cdot s$)
* $p$: Linear momentum of the particle ($kg \cdot m/s$)
* $m$: Mass of the particle ($kg$)
* $v$: Velocity of the particle ($m/s$)

**Physical Significance:** Matter waves explain why electrons in an atom do not spiral into the nucleus; they form standing wave patterns in stable orbits. For macroscopic objects, the mass $m$ is so large that $\lambda$ becomes immeasurably small, which is why we do not observe quantum wave effects in everyday life.

## [[The Schrodinger Equation]]

To describe the propagation of matter waves, Erwin Schrödinger developed a fundamental partial differential equation. It plays the same role in [[Quantum Mechanics]] that Newton's second law ($F = ma$) plays in classical mechanics.

### [[Time-Dependent Schrodinger Equation]]

This form predicts how the quantum state of a physical system changes over time.

$$i\hbar \frac{\partial \Psi(x,t)}{\partial t} = \left[ -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(x,t) \right] \Psi(x,t)$$

**Variables:**

* $i$: Imaginary unit ($\sqrt{-1}$)
* $\hbar$: Reduced Planck's constant ($\hbar = \frac{h}{2\pi}$) ($J \cdot s$)
* $\Psi(x,t)$: Total time-dependent [[Wave Function]] (unitless or $m^{-1/2}$ in 1D)
* $m$: Mass of the particle ($kg$)
* $V(x,t)$: Potential energy field ($J$)

### [[Time-Independent Schrodinger Equation]]

When the potential energy $V$ does not depend on time (i.e., $V(x,t) = V(x)$), the spatial and temporal parts of the wave function can be separated: $\Psi(x,t) = \psi(x)e^{-iEt/\hbar}$. The time-independent form is an eigenvalue equation for the energy $E$:

$$-\frac{\hbar^2}{2m} \frac{d^2\psi(x)}{dx^2} + V(x)\psi(x) = E\psi(x)$$

**Variables:**

* $\psi(x)$: Time-independent wave function (spatial part)
* $E$: Total energy of the particle (eigenvalue) ($J$)

## [[Wave Function]] and [[Meaning of Wave Function]]

The [[Wave Function]], denoted by $\Psi$ (or $\psi$ for the spatial part), is a complex-valued mathematical function that contains all measurable information about the particle.

**Max Born's Interpretation:**
The wave function itself ($\Psi$) has no direct physical meaning. However, its absolute square, $\vert{}\Psi(x,t)\vert{}^2 = \Psi^* \Psi$ (where $\Psi^*$ is the complex conjugate), represents the **probability density** of finding the particle at position $x$ at time $t$.

$$P(x) = \vert{}\Psi(x,t)\vert{}^2$$

To find the probability of finding the particle in a specific region between $a$ and $b$:

$$P_{a \to b} = \int_{a}^{b} \vert{}\Psi(x,t)\vert{}^2 dx$$

## [[Normalization]]

Because the particle must exist *somewhere* in the universe, the total probability of finding the particle across all space must be exactly $1$ ($100\%$).

$$\int_{-\infty}^{\infty} \vert{}\Psi(x)\vert{}^2 dx = 1$$

If a wave function satisfies this integral, it is said to be **normalized**. Any valid wave function can be multiplied by a constant $A$ (normalization constant) to satisfy this condition.

## [[Particle in an Infinite Potential Well]]

Also known as the "Particle in a 1D Box", this is a fundamental model to demonstrate quantum confinement and energy quantization.

**The Model:**
A particle of mass $m$ is trapped in a 1D region from $x = 0$ to $x = L$.

* $V(x) = 0$ for $0 < x < L$
* $V(x) = \infty$ for $x \le 0$ and $x \ge L$

```text
 V(x) = ∞        V(x) = 0        V(x) = ∞
   |                               |
   |                               |
   |                               |
   |_______________________________|
   0                               L      x -->

```

### Derivation of Wave Functions and Energy Levels

Inside the well, $V(x) = 0$, so the [[Time-Independent Schrodinger Equation]] becomes:

$$-\frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2} = E\psi$$

$$\frac{d^2\psi}{dx^2} + k^2\psi = 0 \quad \text{where} \quad k = \frac{\sqrt{2mE}}{\hbar}$$

The general solution to this differential equation is:


$$\psi(x) = A \sin(kx) + B \cos(kx)$$

**Applying Boundary Conditions:**

1. At $x = 0$, the potential is infinite, so the particle cannot be there: $\psi(0) = 0$.

$$\psi(0) = A \sin(0) + B \cos(0) = B \implies B = 0$$



Thus, $\psi(x) = A \sin(kx)$.
2. At $x = L$, the potential is infinite: $\psi(L) = 0$.

$$A \sin(kL) = 0$$



Since $A \neq 0$ (otherwise no particle exists), $\sin(kL) = 0$.

$$kL = n\pi \quad \text{where} \quad n = 1, 2, 3, ...$$



Substituting $k = \frac{n\pi}{L}$ back into our definition of $k$:


$$\frac{n\pi}{L} = \frac{\sqrt{2mE}}{\hbar} \implies E_n = \frac{n^2 \pi^2 \hbar^2}{2mL^2} = \frac{n^2 h^2}{8mL^2}$$

**Physical Significance of $E_n$:** Energy is quantized. The lowest energy state ($n=1$) is called the **zero-point energy**. A quantum particle can never be perfectly at rest ($E_1 > 0$), which satisfies the Heisenberg Uncertainty Principle.

### [[Normalization]] of the Wave Function

To find the constant $A$, apply the normalization condition:

$$\int_{0}^{L} \vert{}A \sin(\frac{n\pi x}{L})\vert{}^2 dx = 1$$

$$A^2 \int_{0}^{L} \frac{1 - \cos(\frac{2n\pi x}{L})}{2} dx = 1$$

$$A^2 \left[ \frac{L}{2} \right] = 1 \implies A = \sqrt{\frac{2}{L}}$$

The normalized eigenfunctions are:


$$\psi_n(x) = \sqrt{\frac{2}{L}} \sin\left(\frac{n\pi x}{L}\right)$$

## [[The Correspondence Principle]]

Niels Bohr formulated the [[Correspondence Principle]], which states that the predictions of quantum mechanics must reduce to classical mechanics in the limit of large quantum numbers ($n \to \infty$).

**Applied to the Infinite Potential Well:**

* In classical mechanics, a particle bouncing back and forth in a box with constant speed has an equal probability of being found anywhere. The classical probability density is uniform: $P_{classical}(x) = 1/L$.
* In quantum mechanics, $P_n(x) = \frac{2}{L} \sin^2(\frac{n\pi x}{L})$.
* For small $n$ (e.g., $n=1, 2$), the particle is highly likely to be found at specific locations (nodes and antinodes).
* As $n \to \infty$, the oscillations of $\sin^2$ become so rapid that any macroscopic measurement averages over many peaks and valleys, yielding an average value of $1/2$ for the sine squared term.
* Thus, $P_{\infty}(x) \approx \frac{2}{L} \times \frac{1}{2} = \frac{1}{L}$, exactly matching classical predictions.

---

## [[Solved Examples]]

**Example: Calculating Probabilities**
A particle in an infinite well of width $L$ is in its ground state ($n=1$). What is the probability of finding the particle in the middle third of the well (from $x = L/3$ to $x = 2L/3$)?

**Solution:**
The wave function is $\psi_1(x) = \sqrt{\frac{2}{L}} \sin(\frac{\pi x}{L})$.
The probability is:


$$P = \int_{L/3}^{2L/3} \vert{}\psi_1(x)\vert{}^2 dx = \frac{2}{L} \int_{L/3}^{2L/3} \sin^2\left(\frac{\pi x}{L}\right) dx$$


Using the identity $\sin^2(\theta) = \frac{1-\cos(2\theta)}{2}$:


$$P = \frac{2}{L} \int_{L/3}^{2L/3} \frac{1 - \cos(\frac{2\pi x}{L})}{2} dx = \frac{1}{L} \left[ x - \frac{L}{2\pi} \sin\left(\frac{2\pi x}{L}\right) \right]_{L/3}^{2L/3}$$


Evaluating the limits:


$$P = \frac{1}{L} \left[ \left( \frac{2L}{3} - \frac{L}{2\pi}\sin\left(\frac{4\pi}{3}\right) \right) - \left( \frac{L}{3} - \frac{L}{2\pi}\sin\left(\frac{2\pi}{3}\right) \right) \right]$$


Given $\sin(4\pi/3) = -\sqrt{3}/2$ and $\sin(2\pi/3) = \sqrt{3}/2$:


$$P = \frac{1}{3} + \frac{\sqrt{3}}{2\pi} \approx 0.333 + 0.276 = 0.609$$


**Answer:** There is roughly a $60.9\%$ chance of finding the particle in the middle third of the box, compared to classical mechanics which predicts exactly $33.3\%$.

---

# [[Formula Sheet]]

| Concept | Formula |
| --- | --- |
| **Photon Energy** | $E = h\nu = \frac{hc}{\lambda}$ |
| **de Broglie Wavelength** | $\lambda = \frac{h}{p} = \frac{h}{mv}$ |
| **Time-Independent Schrodinger Eq.** | $-\frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2} + V(x)\psi = E\psi$ |
| **Probability** | $P_{a \to b} = \int_{a}^{b} \vert{}\Psi\vert{}^2 dx$ |
| **Normalization Condition** | $\int_{-\infty}^{\infty} \vert{}\Psi\vert{}^2 dx = 1$ |
| **Particle in Box (Energy)** | $E_n = \frac{n^2 h^2}{8mL^2}$ |
| **Particle in Box (Wavefunction)** | $\psi_n(x) = \sqrt{\frac{2}{L}} \sin\left(\frac{n\pi x}{L}\right)$ |

---

# [[Problem Solving Strategy]]

1. **Identify the Given State:** Determine if the problem involves a free particle, a photon, or a particle in a well. Note the quantum number $n$.
2. **Select the Right Equations:**
* Use $E=hc/\lambda$ for photons.
* Use $\lambda=h/p$ for massive particles (electrons, protons).
* For potential wells, immediately write down the boundary conditions.


3. **Normalization:** If given an arbitrary wave function $N \cdot f(x)$, solve for the constant $N$ by integrating $\vert{}f(x)\vert{}^2$ over the given boundaries and setting it equal to $1$.
4. **Calculating Probabilities:** Integrate the square of the normalized wave function over the limits specified in the question. Be careful with trigonometric integration.
5. **Dimensional Check:** Ensure energy results are logically sound. For atomic systems, converting Joules to electron-volts ($1 eV = 1.6 \times 10^{-19} J$) makes numbers manageable.

---

# [[Common Mistakes]]

* **Confusing Photons and Electrons:** Using $E = \frac{1}{2}mv^2$ for photons (incorrect, photons have no rest mass) or $E=pc$ for slow-moving electrons (incorrect, $E=p^2/2m$ applies to non-relativistic mass).
* **Forgetting to Square the Wave Function:** Calculating probability as $\int \psi dx$ instead of $\int \vert{}\psi\vert{}^2 dx$.
* **Assuming $n=0$ is Possible in a Box:** The lowest energy state in an infinite well is $n=1$. If $n=0$, then $\psi_0(x) = 0$ everywhere, meaning the particle does not exist.
* **Dropping Constants:** Forgetting the $\sqrt{2/L}$ normalization factor or misplacing $\hbar^2$ versus $h^2$ in the energy formula (note: $\hbar = h/2\pi$, therefore $E_n = \frac{n^2 \pi^2 \hbar^2}{2mL^2} = \frac{n^2 h^2}{8mL^2}$).

---

# [[Applications]]

* **Electron Microscopy:** Because the de Broglie wavelength of high-speed electrons is vastly smaller than the wavelength of visible light, electron microscopes can achieve extreme magnifications and resolve atomic structures.
* **Quantum Dots:** Semiconductor nanoparticles act as highly tunable "particles in a box." By changing the physical size of the dot ($L$), engineers can dictate the quantized energy levels ($E_n$). When electrons transition between these levels, they emit specific colors of light, widely used in modern QLED televisions and biological imaging.
* **Scanning Tunneling Microscopes (STM):** While strictly relying on quantum tunneling (a phenomenon adjacent to the infinite well model), it utilizes the wave nature of electrons mapped by the Schrödinger equation to "see" individual atoms on metal surfaces.

---

# [[Summary]]

Basic [[Quantum Mechanics]] replaces the deterministic trajectories of classical physics with probabilistic wave functions governed by the [[The Schrodinger Equation]]. Light possesses particle-like momentum (photons), while matter possesses wave-like wavelengths (de Broglie waves). The state of a particle is entirely defined by its wave function, which must be normalized so that total probability equals $1$. Confinement of a quantum particle, such as in an infinite potential well, naturally leads to quantized (discrete) energy levels. As energy scales and quantum numbers increase, these bizarre wave-like probability distributions average out, reproducing the expected classical behaviors in accordance with the [[Correspondence Principle]].

---

# [[Related Notes]]

* [[Modern Physics]]
* [[Wave-Particle Duality]]
* [[Quantum Tunneling]]
* [[Heisenberg Uncertainty Principle]]
* [[Bohr Model of the Atom]]
* [[Statistical Mechanics]]