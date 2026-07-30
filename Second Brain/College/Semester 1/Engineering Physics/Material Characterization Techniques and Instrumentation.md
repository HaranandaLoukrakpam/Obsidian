# [[Material Characterization Techniques]]

## [[X-ray Diffractometer]] (XRD)

The [[X-ray Diffractometer]] is a non-destructive analytical instrument used to identify the crystalline phases present in a material and to measure structural properties like strain, preferred orientation, and crystallite size.

### [[Principle]]

XRD is based on the constructive interference of monochromatic X-rays scattered by the periodic arrangement of atoms in a crystal lattice. This phenomenon is governed by [[Bragg's Law]]:

$$n\lambda = 2d \sin \theta$$

**Variables:**

- $n$: Order of reflection (an integer, usually $1$)
    
- $\lambda$: Wavelength of the incident X-ray ($m$ or $\text{\AA}$)
    
- $d$: Interplanar spacing between atomic layers in the crystal ($m$ or $\text{\AA}$)
    
- $\theta$: Bragg angle (angle of incidence relative to the crystal plane)
    

When the path difference ($2d \sin \theta$) equals an integer multiple of the wavelength ($n\lambda$), the scattered waves constructively interfere, producing a high-intensity diffraction peak.

### [[Construction]]

An XRD system consists of three basic elements:

1. **X-ray Tube:** Generates X-rays (often using a Copper target, $Cu-K\alpha$ radiation, $\lambda = 1.54 \text{\AA}$) via electron bombardment.
    
2. **Sample Holder:** A [[Goniometer]] that holds the sample and precisely controls its rotation.
    
3. **X-ray Detector:** Counts the number of scattered photons.
    

### [[Working]]

The cathode ray tube generates X-rays which are collimated and directed onto the sample. As the sample and detector are rotated, the intensity of the reflected X-rays is recorded as a function of the angle $2\theta$. When the geometry satisfies Bragg's Law, constructive interference occurs, and a peak in intensity is recorded on a [[Diffractogram]].

### [[Scherrer Equation]]

The width of the diffraction peak can be used to determine the average crystallite size of nano-materials using the [[Scherrer Equation]]:

$$D = \frac{K\lambda}{\beta \cos \theta}$$

**Variables:**

- $D$: Mean size of the ordered (crystalline) domains (nm)
    
- $K$: Dimensionless shape factor (typically $0.9$)
    
- $\lambda$: X-ray wavelength (nm)
    
- $\beta$: Line broadening at half the maximum intensity (FWHM), measured in **radians**
    
- $\theta$: Bragg angle (degrees or radians, but take the cosine of the angle)
    

**Physical Significance:** Smaller crystals contain fewer diffracting planes, leading to incomplete destructive interference slightly off the exact Bragg angle. This causes the diffraction peaks to broaden. Therefore, peak width ($\beta$) is inversely proportional to crystallite size ($D$).

## [[Atomic Force Microscope]] (AFM)

### [[Principle]]

The [[Atomic Force Microscope]] operates by measuring the intermolecular forces (such as [[Van der Waals Forces]]) between a highly sharp probe tip and the surface of the sample. Unlike optical or electron microscopes, AFM does not use lenses or beam irradiation to form an image; it "feels" the surface topography.

### [[Construction]]

1. **Micro-cantilever:** A flexible microscopic diving board with a sharp tip (radius $< 10$ nm) at its end.
    
2. **Laser:** Focused on the back of the cantilever.
    
3. **Position Sensitive Photodiode (PSPD):** Detects the reflection of the laser beam.
    
4. **Piezoelectric Scanner:** Moves the sample (or tip) in the x, y, and z directions with sub-nanometer precision.
    

**ASCII Diagram of AFM:**

Plaintext

```
      Laser
        \       Photodiode Array
         \         /
          \       / (Reflection)
           \     /
       _____\___/____ Cantilever
            |
            V Tip
   _~_~_~_~_~_~_~_~_~_ Sample Surface
   [ Piezoelectric Scanner ]
```

### [[Working]]

As the tip is brought extremely close to the sample surface, forces between the tip and sample cause the cantilever to deflect according to [[Hooke's Law]] ($F = -kx$). The laser beam reflects off the back of the cantilever onto the photodiode. Even a sub-nanometer deflection of the cantilever translates into a measurable shift of the laser spot on the photodiode. A feedback loop adjusts the z-height of the piezo scanner to maintain a constant force or height, mapping the 3D topography pixel by pixel.

### [[Applications]]

- High-resolution 3D surface topography down to the atomic scale.
    
- Measuring surface roughness.
    
- Mapping magnetic, electrical, or mechanical properties at the nanoscale.
    

## [[X-ray Photoelectron Spectroscope]] (XPS)

### [[Principle]]

XPS is a surface-sensitive quantitative spectroscopic technique based on the [[Photoelectric Effect]]. When a material is irradiated with X-rays, core-level electrons are ejected. The kinetic energy of these emitted electrons is measured, which allows for the calculation of their [[Binding Energy]].

$$E_k = h\nu - E_B - \Phi$$

**Variables:**

- $E_k$: Kinetic energy of the emitted photoelectron ($eV$)
    
- $h\nu$: Energy of the incident X-ray photon ($eV$)
    
- $E_B$: Binding energy of the electron specific to the element and its orbital ($eV$)
    
- $\Phi$: Work function of the spectrometer ($eV$)
    

### [[Construction]]

1. **X-ray Source:** Typically $Mg-K\alpha$ or $Al-K\alpha$ sources.
    
2. **Ultra-High Vacuum (UHV) Chamber:** Essential to prevent electrons from colliding with gas molecules and to keep the sample surface free of contaminants.
    
3. **Electron Energy Analyzer:** Usually a concentric hemispherical analyzer (CHA) that separates electrons based on their kinetic energy.
    
4. **Electron Detector:** An electron multiplier to count the electrons.
    

### [[Working]]

The sample is placed in the UHV chamber and bombarded with soft X-rays. Emitted photoelectrons enter the energy analyzer, where a voltage sweeps to allow only electrons of specific kinetic energies to reach the detector at a time. The resulting spectrum plots electron counts versus Binding Energy.

### [[Applications]]

- Identifying elemental composition of the surface (top $1-10$ nm).
    
- Determining the **chemical state** or oxidation state of elements (e.g., distinguishing between $Fe^{2+}$ and $Fe^{3+}$ based on binding energy shifts).
    
- Empirical formula determination.
    

## [[Scanning Electron Microscope]] (SEM)

### [[Principle]]

The [[SEM]] uses a focused beam of high-energy electrons to generate a variety of signals at the surface of solid specimens. The signals derive from electron-sample interactions and reveal information about the sample including external morphology (texture) and chemical composition.

The two main signals are:

- **Secondary Electrons (SE):** Ejected from the conduction/valence bands near the surface; excellent for topographical imaging.
    
- **Backscattered Electrons (BSE):** High-energy beam electrons reflected out of the sample; highly sensitive to the atomic number ($Z$), providing compositional contrast.
    

### [[Construction]]

1. **Electron Gun:** Generates electrons via thermionic emission (e.g., Tungsten filament) or field emission.
    
2. **Electromagnetic Lenses:** Condenser and objective lenses focus the electron beam into a tight spot.
    
3. **Scanning Coils:** Deflect the beam horizontally and vertically to raster scan the sample.
    
4. **Detectors:** Everhart-Thornley detector for SEs, solid-state detectors for BSEs.
    

### [[Working]]

An electron beam is accelerated in a vacuum and focused to a spot $1-5$ nm in diameter. The scanning coils sweep this beam across the sample surface in a rectangular raster pattern. As the beam hits each point, secondary electrons are emitted, collected by the detector, and converted into a voltage signal. This signal dictates the brightness of the corresponding pixel on a computer monitor, constructing a high-depth-of-field 3D-like image.

### [[Applications]]

- High-resolution imaging of surface topography and morphology.
    
- Defect and fracture analysis in metallurgy and material science.
    
- Quality control in semiconductor manufacturing.
    

## [[Transmission Electron Microscope]] (TEM)

### [[Principle]]

Unlike SEM, which looks _at_ the surface, the [[TEM]] transmits electrons _through_ an ultra-thin sample ($< 100$ nm thick). Because the [[de Broglie Wavelength]] of high-energy electrons is incredibly small (fractions of an Angstrom), TEM can achieve atomic-level resolution, vastly exceeding that of light microscopes.

### [[Construction]]

1. **Electron Gun:** Operates at very high acceleration voltages ($100-300$ kV).
    
2. **Condenser Lenses:** Focus the beam uniformly onto the sample.
    
3. **Sample Stage:** Holds the ultra-thin specimen.
    
4. **Objective Lens:** Forms the initial intermediate image (the most critical lens for resolution).
    
5. **Projector Lenses:** Magnifies the image onto a fluorescent screen or a CCD/CMOS camera.
    

### [[Working]]

The high-velocity electron beam passes through the ultra-thin sample. Regions of the sample that are thicker or contain atoms with higher atomic numbers scatter more electrons and appear darker in the final image. Regions that are thinner or consist of lighter atoms transmit more electrons and appear brighter.

### [[Applications]]

- Direct imaging of crystal lattices and atomic columns.
    
- Studying crystallographic defects (dislocations, grain boundaries).
    
- Internal structure analysis of nanoparticles, viruses, and cells.
    

## [[Numerical Problems]]

### Example 1: Crystal Size via Scherrer Equation

**Problem:** In an XRD experiment using $Cu-K\alpha$ radiation ($\lambda = 0.154 \text{ nm}$), a diffraction peak is observed at $2\theta = 45^\circ$. The Full Width at Half Maximum (FWHM) of the peak is measured to be $0.3^\circ$. Calculate the average crystallite size. Assume the shape factor $K = 0.9$.

**Solution:**

1. **Convert FWHM ($\beta$) to radians:**
    
    $$\beta = 0.3^\circ \times \left( \frac{\pi}{180} \right) = 0.3 \times 0.01745 = 5.236 \times 10^{-3} \text{ radians}$$
    
2. **Determine $\theta$:**
    
    The peak is at $2\theta = 45^\circ$, so $\theta = 22.5^\circ$.
    
3. **Apply the [[Scherrer Equation]]:**
    
    $$D = \frac{K\lambda}{\beta \cos \theta}$$
    
    $$D = \frac{0.9 \times 0.154 \text{ nm}}{(5.236 \times 10^{-3}) \times \cos(22.5^\circ)}$$
    
    $$D = \frac{0.1386}{(5.236 \times 10^{-3}) \times 0.9239} = \frac{0.1386}{4.837 \times 10^{-3}}$$
    
    $$D \approx 28.65 \text{ nm}$$
    
    **Answer:** The average crystallite size is approximately $28.65 \text{ nm}$.
    

### Example 2: XPS Binding Energy

**Problem:** An XPS system uses an $Al-K\alpha$ X-ray source with an energy of $1486.6 \text{ eV}$. An electron is ejected with a measured kinetic energy of $950.0 \text{ eV}$. If the work function of the spectrometer is $4.5 \text{ eV}$, what is the binding energy of the core electron?

**Solution:**

1. **Apply the Photoelectric Equation for XPS:**
    
    $$E_k = h\nu - E_B - \Phi$$
    
2. **Rearrange for Binding Energy ($E_B$):**
    
    $$E_B = h\nu - E_k - \Phi$$
    
3. **Substitute the values:**
    
    $$E_B = 1486.6 \text{ eV} - 950.0 \text{ eV} - 4.5 \text{ eV}$$
    
    $$E_B = 532.1 \text{ eV}$$
    
    **Answer:** The binding energy is $532.1 \text{ eV}$ (which corresponds to the $O_{1s}$ peak, indicating the presence of Oxygen).
    

# [[Formula Sheet]]

- **Bragg's Law (XRD):** $n\lambda = 2d \sin \theta$
    
- **Scherrer Equation (XRD):** $D = \frac{K\lambda}{\beta \cos \theta}$
    
- **XPS Photoelectric Equation:** $E_B = h\nu - E_k - \Phi$
    
- **de Broglie Wavelength (Electron Microscopes):** $\lambda = \frac{h}{\sqrt{2m_e E_k}}$
    
- **Hooke's Law (AFM):** $F = -kx$
    

# [[Problem Solving Strategy]]

1. **XRD Problems:**
    
    - Look closely at whether the problem gives you $\theta$ or $2\theta$. The x-axis of a diffractogram is always $2\theta$, but Bragg's Law and Scherrer's equation use strictly $\theta$.
        
    - **CRITICAL STEP:** The peak broadening parameter $\beta$ (FWHM) is almost always given in degrees. You **must** convert it to radians ($\times \pi/180$) before using it in the Scherrer equation.
        
2. **XPS Problems:**
    
    - Ensure all energies are in the same units (usually $eV$).
        
    - Do not forget to subtract the spectrometer work function ($\Phi$) if it is provided. If not provided, it is usually assumed to be calibrated out ($0$).
        
3. **Microscopy Constraints:**
    
    - If a problem asks to calculate the theoretical resolution of an electron microscope, calculate the velocity/energy of the electron first, then find its [[de Broglie Wavelength]]. Resolution limits are roughly proportional to this wavelength.
        

# [[Common Mistakes]]

- **Scherrer Equation Unit Failure:** Forgetting to convert the FWHM ($\beta$) from degrees to radians. This leads to a massive mathematical error (off by a factor of ~57).
    
- **Mixing up SEM and TEM:**
    
    - SEM looks at the _surface_ (topography, bulk samples).
        
    - TEM looks _through_ the sample (internal structure, requires ultra-thin samples).
        
- **Misinterpreting AFM:** Thinking AFM uses light or electrons to image. AFM is a physical probe technique; it measures _force_, not optics or particles.
    
- **XPS Miscalculation:** Confusing Binding Energy with Kinetic Energy. Binding energy is inherent to the atom (used for identification); Kinetic energy is just the leftover energy after the electron escapes.
    

# [[Applications]]

- **Nanotechnology R&D:** Using [[XRD]] to confirm the crystal structure of newly synthesized quantum dots, followed by [[TEM]] to actually visualize the atomic lattice planes.
    
- **Failure Analysis:** Engineers use [[SEM]] to look at the fracture surfaces of metallic components to determine if they failed due to fatigue, brittle fracture, or ductile tearing.
    
- **Catalysis & Surface Chemistry:** Using [[XPS]] to determine if a surface catalyst has degraded by checking the oxidation state of the active metal sites.
    
- **Biomedical Engineering:** Using [[AFM]] to measure the stiffness of biological cell membranes or to map the surface topology of bio-compatible implant coatings.
    

# [[Summary]]

Material characterization bridges the gap between material synthesis and application. [[X-ray Diffractometer]] utilizes Bragg's law to yield bulk crystallographic data and crystallite size. For surface analysis, the [[Atomic Force Microscope]] maps 3D topography using intermolecular forces, while the [[X-ray Photoelectron Spectroscope]] utilizes the photoelectric effect to determine exact elemental composition and oxidation states. When direct imaging is required, the [[Scanning Electron Microscope]] provides deep-focus topographical views via secondary electrons, and the [[Transmission Electron Microscope]] penetrates ultra-thin samples to reveal the ultimate atomic-level internal structure.

# [[Related Notes]]

- [[Solid State Physics]]
    
- [[Crystallography]]
    
- [[Quantum Mechanics]]
    
- [[Photoelectric Effect]]
    
- [[Optics and Diffraction]]
    
- [[Nanophysics]]