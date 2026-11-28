# Unit I – Physical Layer Supplement

## Signals, Data Rate Limits, Encoding, Modulation and Multiplexing

## 1. Data and Signals

### 1.1 Introduction

The [[Physical Layer]] is the first layer of the [[OSI Model]]. It is responsible for transmitting raw bits from one device to another through a physical transmission medium.

Data represents information, while signals are the electrical, electromagnetic, or optical representations used to transmit that information.

**Types of Data:**

1. **Analog Data:** Continuous information that changes smoothly over time.
    
    - Examples: Human voice, temperature, sound.
        
2. **Digital Data:** Information represented using discrete values, usually binary 0 and 1.
    
    - Examples: Text files, digital images, computer data.
        

**Types of Signals:**

1. **Analog Signal:** A continuously varying signal that can have infinitely many values within a range.
    
2. **Digital Signal:** A signal that uses discrete levels to represent information.
    

|Feature|Analog Signal|Digital Signal|
|---|---|---|
|Nature|Continuous|Discrete|
|Values|Infinite possible values within a range|Limited signal levels|
|Noise sensitivity|More susceptible to accumulated noise and distortion|Can be regenerated to restore discrete levels|
|Example|Radio wave|Binary electrical pulses|

### 1.2 Periodic and Non-Periodic Signals

**Periodic Signal:**

A signal that repeats its pattern after a fixed interval of time.

Example: A continuous sine wave.

**Non-Periodic Signal:**

A signal that does not repeat its pattern at regular intervals.

Example: A sequence of irregular digital pulses.

### 1.3 Sine Wave and Its Parameters

A sine wave is a basic periodic analog signal.

It is represented by:

$$  
s(t)=A\sin(2\pi ft+\phi)  
$$

Where:

- (A) = Amplitude.
    
- (f) = Frequency.
    
- (t) = Time.
    
- (\phi) = Phase.
    

**Important Parameters:**

1. **Amplitude (A):**
    
    - Maximum height of a signal from its zero reference.
        
    - Measured in volts or other appropriate units.
        
2. **Frequency (f):**
    
    - Number of complete cycles per second.
        
    - Measured in Hertz (Hz).
        
3. **Period (T):**
    
    - Time required to complete one cycle.
        
    - Measured in seconds.
        

$$  
T=\frac{1}{f}  
$$

4. **Phase ((\phi)):**
    
    - Describes the relative position of a waveform in time.
        
    - Measured in degrees or radians.
        

**Example:**

If a signal has a frequency of 100 Hz:

$$  
T=\frac{1}{100}=0.01\text{ seconds}  
$$

Therefore, one complete cycle takes 0.01 seconds.

### 1.4 Composite Signals and Fourier Analysis

A [[Composite Signal]] is a signal formed by combining multiple sine waves with different frequencies, amplitudes, and phases.

Most practical signals, including voice and digital pulses, are composite signals.

**Fourier Analysis:**

[[Fourier Analysis]] is a mathematical technique used to represent a complex signal as a combination of simpler sine and cosine waves.

**Important concepts:**

- A composite signal may contain multiple frequency components.
    
- Each component has its own amplitude and frequency.
    
- The range of frequencies present determines the signal's bandwidth.
    

**Example:**

A composite signal may contain frequencies of 100 Hz, 200 Hz, and 300 Hz.

Its frequency range is from 100 Hz to 300 Hz.

### 1.5 Signal Bandwidth

[[Bandwidth]] is the range of frequencies occupied by a signal or supported by a channel.

For a band-limited signal:

$$  
B=f_{\text{high}}-f_{\text{low}}  
$$

Where:

- (f_{\text{high}}) = Highest frequency.
    
- (f_{\text{low}}) = Lowest frequency.
    

**Example:**

If a signal contains frequencies from 100 Hz to 500 Hz:

$$  
B=500-100=400\text{ Hz}  
$$

**Important:** Signal bandwidth and channel bandwidth are related but are not necessarily identical.

### 1.6 Bit Rate and Bit Length

**Bit Rate:**

[[Bit Rate]] is the number of bits transmitted per second.

It is measured in bits per second (bps).

$$  
\text{Bit Rate}=\frac{\text{Number of Bits}}{\text{Time}}  
$$

**Bit Length:**

[[Bit Length]] is the physical distance occupied by one bit in a transmission medium.

$$  
\text{Bit Length}=\frac{\text{Propagation Speed}}{\text{Bit Rate}}  
$$

**Example:**

If propagation speed is (2\times10^8) m/s and bit rate is (10^6) bps:

$$  
\text{Bit Length}=\frac{2\times10^8}{10^6}  
$$

$$  
=200\text{ metres}  
$$

### 1.7 Baseband and Broadband Transmission

**Baseband Transmission:**

- Sends digital signals directly through a channel.
    
- The channel bandwidth is used by the transmitted signal.
    
- Commonly uses line coding.
    
- Example: Traditional Ethernet LAN transmission.
    

**Broadband Transmission:**

- Uses modulation to transmit information over a bandpass channel.
    
- Can divide the available frequency range into multiple channels.
    
- Often uses carrier frequencies.
    
- Example: Cable television and broadband cable networks.
    

|Feature|Baseband|Broadband|
|---|---|---|
|Signal|Usually digital pulses|Modulated bandpass signals|
|Transmission|Direct transmission of encoded data|Uses carrier modulation|
|Channel usage|Commonly uses the channel as a whole|Can support multiple frequency channels|
|Example|Traditional Ethernet|Cable broadband|

---

## 2. Data Rate Limits

Data transmission speed is limited by the bandwidth of the channel and the number of signal levels that can be reliably distinguished.

### 2.1 Nyquist Bit Rate – Noiseless Channel

The [[Nyquist Bit Rate]] formula determines the maximum theoretical bit rate of a noiseless channel.

$$  
C=2B\log_2 L  
$$

Where:

- (C) = Maximum bit rate in bps.
    
- (B) = Channel bandwidth in Hz.
    
- (L) = Number of discrete signal levels.
    

**Important:**

- Higher bandwidth allows a higher bit rate.
    
- More signal levels can increase the bit rate.
    
- Increasing signal levels also makes distinguishing between levels more difficult in real systems.
    

**Example 1:**

A noiseless channel has a bandwidth of 3000 Hz and uses 2 signal levels. Calculate the maximum bit rate.

Given:

$$  
B=3000\text{ Hz},\quad L=2  
$$

Using Nyquist formula:

$$  
C=2(3000)\log_2 2  
$$

$$  
C=6000\times1  
$$

<badge color="success">Answer: 6000 bps</badge>

**Example 2:**

A noiseless channel has a bandwidth of 4000 Hz and uses 8 signal levels. Calculate its maximum bit rate.

$$  
C=2(4000)\log_2 8  
$$

$$  
C=8000\times3  
$$

<badge color="success">Answer: 24,000 bps</badge>

### 2.2 Nyquist Sampling vs Nyquist Bit Rate

These are two different concepts.

|Nyquist Bit Rate|Nyquist Sampling Theorem|
|---|---|
|Calculates maximum bit rate of a noiseless channel|Determines minimum sampling frequency for signal reconstruction|
|Uses bandwidth and signal levels|Uses maximum signal frequency|
|(C=2B\log_2L)|(f_s\geq2f_{\max})|

**Additional Note – Shannon Capacity:**

For a noisy channel, the theoretical capacity is given by the Shannon-Hartley theorem:

$$  
C=B\log_2(1+SNR)  
$$

Here, SNR is the signal-to-noise ratio expressed as a linear ratio, not in decibels.

This formula considers the effect of noise, unlike the Nyquist noiseless-channel formula.

---

## 3. Digital-to-Digital Conversion

[[Digital-to-Digital Conversion]] converts digital data into digital signals for transmission over a physical medium.

It is commonly performed using [[Line Coding]].

### 3.1 Line Coding

Line coding is the process of converting binary data into digital signal patterns.

**Main categories:**

1. Unipolar.
    
2. Polar.
    
3. Bipolar.
    
4. Multilevel and Multitransition.
    

### 3.2 Unipolar Encoding

**Unipolar NRZ (Non-Return-to-Zero):**

- Uses only one polarity of voltage and zero voltage.
    
- Binary 1 is represented by a positive voltage.
    
- Binary 0 is represented by zero voltage.
    
- Signal does not return to zero between consecutive 1s.
    

**Example:**

```
Data:       1    0    1    1    0
Signal:     +    0    +    +    0
```

**Advantages:**

- Simple implementation.
    

**Disadvantages:**

- Contains a DC component.
    
- Poor synchronization for long sequences of identical bits.
    

### 3.3 Polar Encoding

Polar encoding uses both positive and negative voltage levels.

#### 1. NRZ-L (Non-Return-to-Zero-Level)

- The voltage level represents the bit value.
    
- One voltage level represents 0.
    
- The opposite voltage level represents 1.
    
- The receiver determines the bit from the signal level.
    

#### 2. NRZ-I (Non-Return-to-Zero-Invert)

- The presence or absence of a transition represents the data.
    
- A transition at the beginning of a bit interval represents binary 1.
    
- No transition represents binary 0.
    

**Important:** NRZ-I is differential encoding because it depends on changes in signal level rather than only the absolute voltage.

#### 3. RZ (Return-to-Zero)

- The signal returns to zero during each bit interval.
    
- A bit is represented using a signal pulse that occupies only part of the bit duration.
    
- Provides better synchronization than NRZ but requires more bandwidth.
    

#### 4. Manchester Encoding

- Each bit interval contains a transition in the middle.
    
- The direction of the transition represents the bit value.
    
- Provides clock synchronization.
    

One common convention is:

- 0 = High-to-Low transition.
    
- 1 = Low-to-High transition.
    

The convention may be reversed in some systems.

#### 5. Differential Manchester Encoding

- Always has a transition in the middle of each bit interval.
    
- The presence or absence of a transition at the beginning represents the bit.
    
- In one common convention:
    
    - 0 = Transition at the beginning.
        
    - 1 = No transition at the beginning.
        

**Comparison of Polar Encoding:**

|Scheme|Representation|Main Feature|
|---|---|---|
|NRZ-L|Voltage level|Simple level-based encoding|
|NRZ-I|Transition or no transition|Differential encoding|
|RZ|Pulse returns to zero|Better synchronization|
|Manchester|Mid-bit transition|Self-clocking|
|Differential Manchester|Mid-bit and optional start transition|Self-clocking and differential|

### 3.4 Bipolar Encoding

Bipolar encoding uses three signal levels:

- Positive voltage (+).
    
- Zero voltage (0).
    
- Negative voltage (-).
    

#### 1. Alternate Mark Inversion (AMI)

- Binary 0 is represented by zero voltage.
    
- Binary 1 is represented by alternating positive and negative voltages.
    
- Consecutive 1s have opposite polarities.
    

**Example:**

```
Data:       1    0    1    1    0    1
Signal:     +    0    -    +    0    -
```

**Advantages:**

- Reduces DC component.
    
- Supports detection of bipolar violations.
    
- Better than simple NRZ for certain synchronization patterns.
    

#### 2. Pseudoternary

- Binary 1 is represented by zero voltage.
    
- Binary 0 is represented by alternating positive and negative voltages.
    

**Example:**

```
Data:       0    1    0    0    1    0
Signal:     +    0    -    +    0    -
```

**Difference:**

|AMI|Pseudoternary|
|---|---|
|0 = Zero voltage|1 = Zero voltage|
|1 = Alternating + and -|0 = Alternating + and -|

### 3.5 Multilevel and Multitransition Encoding

These techniques improve transmission efficiency by representing multiple bits or using multiple signal transitions.

#### 1. 2B1Q (Two Binary, One Quaternary)

- Converts 2 bits into one signal element.
    
- Uses four distinct signal levels.
    
- Each signal element represents 2 bits.
    

$$  
\text{Bits per Signal Element}=\log_2 4=2  
$$

**Example mapping:**

|Bits|Signal Level|
|---|---|
|00|-3|
|01|-1|
|10|+1|
|11|+3|

#### 2. 8B6T (Eight Binary, Six Ternary)

- Converts 8 binary bits into 6 ternary signal elements.
    
- Uses three signal levels: positive, zero, and negative.
    
- Uses suitable code groups to maintain signal balance and transition properties.
    

#### 3. 4D-PAM5

- Uses five-level Pulse Amplitude Modulation.
    
- Transmits symbols across four dimensions, typically four wire pairs in Gigabit Ethernet.
    
- Each dimension uses five possible signal levels.
    
- Designed to transmit data efficiently while maintaining signal properties.
    

#### 4. MLT-3 (Multi-Level Transmit-3)

- Uses three signal levels: +V, 0, and -V.
    
- A binary 1 causes a transition to the next level in a repeating sequence.
    
- A binary 0 causes no transition.
    

**Transition sequence:**

```
+V → 0 → -V → 0 → +V
```

**Advantages:**

- Reduces the maximum signal frequency.
    
- Useful for reducing bandwidth requirements.
    
- Used in 100BASE-TX Ethernet with 4B/5B encoding.
    

### 3.6 Physical-Layer Block Coding

[[Block Coding]] adds extra bits to the original data to improve synchronization and maintain suitable signal properties.

It maps groups of data bits into larger groups of code bits.

#### 1. 4B/5B Encoding

- Converts every 4 data bits into 5 code bits.
    
- Adds one extra bit for every four original bits.
    
- Ensures sufficient transitions for synchronization when used with an appropriate line code.
    

**Example:**

```
Original Data:  4 bits
                    |
                    v
                4B/5B Encoder
                    |
                    v
Encoded Data:   5 bits
```

**Advantages:**

- Improves clock synchronization.
    
- Avoids long sequences of zeros in valid code groups.
    
- Some invalid code groups can help detect transmission errors.
    

**Disadvantage:**

- Increases the number of transmitted bits by 25%.
    

#### 2. 8B/10B Encoding

- Converts 8 data bits into 10 encoded bits.
    
- Uses a carefully designed code set.
    
- Maintains DC balance through running disparity.
    
- Provides sufficient transitions for synchronization.
    
- Some invalid code groups can be detected as coding violations.
    

**Advantages:**

- Better clock synchronization.
    
- DC balance.
    
- Detection of certain coding errors.
    

**Comparison:**

|Feature|4B/5B|8B/10B|
|---|---|---|
|Input|4 bits|8 bits|
|Output|5 bits|10 bits|
|Overhead|25% relative to input|25% relative to input|
|Main purpose|Transition density|Transition density and DC balance|
|Example use|100BASE-TX|Gigabit Ethernet and other serial links|

**Important:** Block coding is not a replacement for general-purpose error detection such as CRC.

### 3.7 Scrambling

[[Scrambling]] replaces long sequences of zeros with special patterns to maintain synchronization and avoid long periods without signal transitions.

It is commonly used with bipolar line coding.

#### 1. B8ZS (Bipolar with 8-Zero Substitution)

- Replaces eight consecutive zeros with a special pattern.
    
- Uses bipolar violations to indicate the substituted pattern.
    
- The receiver recognises the pattern and restores the original eight zeros.
    
- Maintains synchronization.
    

#### 2. HDB3 (High-Density Bipolar 3-Zero)

- Replaces four consecutive zeros with a special pattern.
    
- Uses deliberate bipolar violations.
    
- The substitution pattern depends on the number of non-zero pulses since the previous substitution.
    
- Helps maintain DC balance and synchronization.
    

**Comparison:**

|Feature|B8ZS|HDB3|
|---|---|---|
|Full form|Bipolar 8-Zero Substitution|High-Density Bipolar 3-Zero|
|Replaces|8 consecutive zeros|4 consecutive zeros|
|Based on|AMI|AMI|
|Purpose|Prevents long zero sequences|Prevents long zero sequences|
|Common use|North American digital transmission systems|E-carrier systems|

---

## 4. Analog-to-Digital Conversion

[[Analog-to-Digital Conversion]] converts continuous analog signals into digital binary data.

The two important techniques are:

1. [[Pulse Code Modulation]] (PCM).
    
2. [[Delta Modulation]] (DM).
    

### 4.1 Pulse Code Modulation (PCM)

[[Pulse Code Modulation]] is a technique used to convert analog signals into digital form.

It consists of three main stages:

1. Sampling.
    
2. Quantization.
    
3. Binary Encoding.
    

#### Stage 1: Sampling

Sampling measures the amplitude of an analog signal at regular time intervals.

According to the [[Nyquist Sampling Theorem]], the sampling frequency must be at least twice the highest frequency present in the original signal.

$$  
f_s\geq2f_{\max}  
$$

Where:

- (f_s) = Sampling frequency.
    
- (f_{\max}) = Maximum frequency of the analog signal.
    

**Example:**

If the maximum frequency of a signal is 4000 Hz:

$$  
f_s\geq2(4000)  
$$

$$  
f_s\geq8000\text{ samples/second}  
$$

Therefore, the minimum sampling frequency is 8000 Hz.

#### Stage 2: Quantization

- Converts sampled amplitudes into a finite number of discrete levels.
    
- Each sample is assigned to the nearest available quantization level.
    
- The difference between the original sample and the quantized value is called quantization error.
    

For an n-bit PCM system:

$$  
L=2^n  
$$

Where L is the number of quantization levels.

For example, an 8-bit PCM system has:

$$  
L=2^8=256\text{ levels}  
$$

#### Stage 3: Binary Encoding

- Each quantized sample is converted into a binary code.
    
- The binary code is transmitted through the communication channel.
    

For an n-bit PCM system:

$$  
\text{Bits per Sample}=n  
$$

#### PCM Block Diagram

```
   Analog Input
        |
        v
     Sampling
        |
        v
    Quantization
        |
        v
   Binary Encoding
        |
        v
   Digital Output
```

#### PCM Bit Rate

$$  
R_b=f_s\times n  
$$

Where:

- (R_b) = Bit rate.
    
- (f_s) = Sampling frequency.
    
- (n) = Bits per sample.
    

**Example:**

A signal is sampled at 8000 samples per second using 8 bits per sample.

$$  
R_b=8000\times8  
$$

<badge color="success">Answer: 64,000 bps (64 kbps)</badge>

**Advantages of PCM:**

- Good noise immunity.
    
- Easy digital storage and processing.
    
- Supports digital transmission and regeneration.
    

**Disadvantages:**

- Requires higher bandwidth.
    
- Quantization introduces errors.
    
- Requires more complex conversion hardware than simple analog transmission.
    

### 4.2 Delta Modulation (DM)

[[Delta Modulation]] is a simplified form of analog-to-digital conversion that represents the difference between successive signal samples.

Instead of transmitting the complete sample value, it transmits whether the signal has increased or decreased.

**Working:**

1. The input signal is sampled.
    
2. Each sample is compared with the previous approximation.
    
3. A binary 1 indicates an increase.
    
4. A binary 0 indicates a decrease.
    
5. The receiver reconstructs a staircase approximation of the original signal.
    

**Block Diagram:**

```
      Analog Input
           |
           v
       Comparator
           |
           v
      1-bit Output
           |
           v
     Digital Channel
           |
           v
       Integrator
           |
           v
   Staircase Approximation
```

#### Staircase Approximation

The receiver reconstructs the input signal using fixed-size upward or downward steps.

- Binary 1: Step upward.
    
- Binary 0: Step downward.
    

#### Slope Overload Distortion

Slope overload occurs when the input signal changes faster than the staircase approximation can follow.

**Cause:**

- Step size is too small.
    
- Sampling rate is too low.
    
- Input signal changes rapidly.
    

**Remedy:**

- Increase the step size.
    
- Increase the sampling frequency.
    

**Granular Noise:**

Granular noise occurs when the step size is too large for a slowly varying input signal. The reconstructed signal fluctuates around the original signal.

**PCM vs Delta Modulation**

|Feature|PCM|Delta Modulation|
|---|---|---|
|Data transmitted|Complete quantized sample|Difference between samples|
|Bits per sample|Multiple bits|Usually 1 bit|
|Complexity|Higher|Lower|
|Quantization|Multiple levels|Fixed step approximation|
|Main distortion|Quantization error|Slope overload and granular noise|

---

## 5. Digital-to-Analog Conversion (Modulation)

[[Digital-to-Analog Conversion]] converts digital data into analog signals by modifying a carrier wave.

The three basic techniques are:

1. [[Amplitude Shift Keying]] (ASK).
    
2. [[Frequency Shift Keying]] (FSK).
    
3. [[Phase Shift Keying]] (PSK).
    

[[Quadrature Amplitude Modulation]] (QAM) combines amplitude and phase variations.

### 5.1 Amplitude Shift Keying (ASK)

[[Amplitude Shift Keying]] represents digital data by changing the amplitude of a carrier signal.

- Binary 1: Higher or non-zero amplitude.
    
- Binary 0: Lower or zero amplitude, depending on the scheme.
    

**Features:**

- Simple implementation.
    
- More sensitive to noise affecting signal amplitude.
    
- Used in certain optical and low-complexity communication systems.
    

### 5.2 Frequency Shift Keying (FSK)

[[Frequency Shift Keying]] represents digital data by changing the frequency of the carrier signal.

- Binary 1: One frequency.
    
- Binary 0: Another frequency.
    

**Features:**

- Better resistance to amplitude noise than ASK.
    
- Requires different frequencies for different bit values.
    
- Used in some radio and low-speed communication systems.
    

### 5.3 Phase Shift Keying (PSK)

[[Phase Shift Keying]] represents digital data by changing the phase of the carrier signal.

#### BPSK (Binary Phase Shift Keying)

- Uses two different phase values.
    
- Each symbol represents one bit.
    
- Commonly uses a phase difference of 180 degrees.
    

$$  
\text{Bits per Symbol}=\log_2 2=1  
$$

#### QPSK (Quadrature Phase Shift Keying)

- Uses four different phase states.
    
- Each symbol represents two bits.
    
- Provides twice the bit capacity of BPSK at the same symbol rate.
    

$$  
\text{Bits per Symbol}=\log_2 4=2  
$$

**Comparison:**

|Technique|Number of States|Bits per Symbol|
|---|---|---|
|BPSK|2|1|
|QPSK|4|2|

### 5.4 Quadrature Amplitude Modulation (QAM)

[[Quadrature Amplitude Modulation]] combines changes in both amplitude and phase to represent digital data.

It uses two carrier components:

- In-phase (I).
    
- Quadrature (Q).
    

These components are 90 degrees apart.

**Features:**

- Supports high data rates.
    
- Uses multiple amplitude and phase combinations.
    
- Commonly used in Wi-Fi, cable networks, and cellular communication.
    

#### QAM Constellation Diagram

A constellation diagram represents possible signal symbols as points on a two-dimensional plane.

- Horizontal axis = In-phase component (I).
    
- Vertical axis = Quadrature component (Q).
    
- Each point represents a symbol.
    

**Common QAM Types:**

|Modulation|Number of Symbols|Bits per Symbol|
|---|---|---|
|16-QAM|16|4|
|64-QAM|64|6|
|256-QAM|256|8|

General formula:

$$  
\text{Bits per Symbol}=\log_2 M  
$$

Where M is the number of distinct symbols.

**Example:**

For 16-QAM:

$$  
\log_2 16=4\text{ bits per symbol}  
$$

**Comparison of Digital Modulation Techniques**

|Technique|Parameter Changed|Main Feature|
|---|---|---|
|ASK|Amplitude|Simple but noise-sensitive|
|FSK|Frequency|Uses different carrier frequencies|
|BPSK|Phase|Two phase states|
|QPSK|Phase|Four phase states|
|QAM|Amplitude and phase|High spectral efficiency|

---

## 6. Analog-to-Analog Conversion

[[Analog-to-Analog Conversion]] converts analog information into an analog signal by modifying a carrier wave.

The three main techniques are:

1. [[Amplitude Modulation]] (AM).
    
2. [[Frequency Modulation]] (FM).
    
3. [[Phase Modulation]] (PM).
    

### 6.1 Amplitude Modulation (AM)

In [[Amplitude Modulation]], the amplitude of the carrier wave changes according to the message signal.

- Carrier frequency remains constant.
    
- Carrier amplitude varies.
    
- Used in AM radio broadcasting.
    

**Advantages:**

- Simple implementation.
    
- Requires relatively simple receivers.
    

**Disadvantages:**

- More affected by amplitude noise.
    
- Less power-efficient than many alternatives.
    

### 6.2 Frequency Modulation (FM)

In [[Frequency Modulation]], the frequency of the carrier wave changes according to the message signal.

- Carrier amplitude remains approximately constant.
    
- Carrier frequency varies.
    
- Used in FM radio broadcasting.
    

**Advantages:**

- Better resistance to amplitude noise.
    
- Generally provides better audio quality than conventional AM broadcasting.
    

**Disadvantages:**

- Requires more bandwidth.
    
- More complex circuitry.
    

### 6.3 Phase Modulation (PM)

In [[Phase Modulation]], the phase of the carrier wave changes according to the message signal.

- Carrier amplitude remains constant.
    
- Carrier phase varies.
    
- Used in communication systems and as a basis for digital phase modulation.
    

### 6.4 AM vs FM vs PM

|Feature|AM|FM|PM|
|---|---|---|---|
|Full form|Amplitude Modulation|Frequency Modulation|Phase Modulation|
|Changed parameter|Amplitude|Frequency|Phase|
|Carrier amplitude|Varies|Constant|Constant|
|Noise resistance|Lower|Higher against amplitude noise|Depends on modulation and receiver|
|Example|AM radio|FM radio|Communication systems|

**Remember:**

- AM = Amplitude changes.
    
- FM = Frequency changes.
    
- PM = Phase changes.
    

---

## 7. Multiplexing and Spread Spectrum

### 7.1 Multiplexing

[[Multiplexing]] is a technique that combines multiple independent signals and transmits them over a single communication channel.

At the receiving end, a demultiplexer separates the combined signals.

**Basic Working:**

```
 Signal 1 ----\
 Signal 2 -----\
 Signal 3 ------> Multiplexer
 Signal 4 -----/       |
                       |
                 Shared Channel
                       |
                       v
                  Demultiplexer
                       |
              -----------------
              |   |   |       |
              v   v   v       v
             S1  S2  S3      S4
```

**Advantages:**

- Efficient use of communication channels.
    
- Reduces transmission costs.
    
- Supports multiple simultaneous communications.
    
- Improves bandwidth utilisation.
    

### 7.2 Time Division Multiplexing (TDM)

[[Time Division Multiplexing]] allows multiple signals to share a channel by assigning different time slots to each signal.

Each source transmits during its allocated time slot.

#### 1. Synchronous TDM

- Each input device receives a fixed time slot.
    
- Time slots are assigned in a repeating frame.
    
- A slot may remain unused if its device has no data to transmit.
    
- Requires synchronisation between sender and receiver.
    

**Example:**

```
Frame:
| A | B | C | A | B | C |
```

#### 2. Statistical TDM

- Time slots are assigned dynamically.
    
- Only devices with data to transmit receive slots.
    
- More efficient when input devices have irregular traffic.
    
- Requires addressing or identification information so the receiver knows which device sent each slot.
    

**Synchronous TDM vs Statistical TDM**

|Feature|Synchronous TDM|Statistical TDM|
|---|---|---|
|Slot allocation|Fixed|Dynamic|
|Empty slots|May occur|Generally avoided|
|Efficiency|Lower for irregular traffic|Higher for bursty traffic|
|Address information|Often not required in each fixed slot|Needed to identify data sources|

### 7.3 Wavelength Division Multiplexing (WDM)

[[Wavelength Division Multiplexing]] is a multiplexing technique used in optical fibre communication.

It transmits multiple optical signals simultaneously through a single fibre using different wavelengths of light.

**Working:**

1. Multiple optical signals are generated at different wavelengths.
    
2. A multiplexer combines them into one optical fibre.
    
3. The signals travel simultaneously through the fibre.
    
4. A demultiplexer separates the wavelengths at the receiving end.
    

**Diagram:**

```
 Light λ1 ----\
 Light λ2 -----\
 Light λ3 ------> Optical MUX
 Light λ4 -----/       |
                       |
                  Optical Fibre
                       |
                       v
                 Optical DEMUX
                       |
              -----------------
              |   |   |       |
              v   v   v       v
             λ1  λ2  λ3      λ4
```

**Advantages:**

- Increases fibre capacity.
    
- Supports multiple simultaneous channels.
    
- Makes efficient use of optical fibre infrastructure.
    

**Types:**

- CWDM – Coarse Wavelength Division Multiplexing.
    
- DWDM – Dense Wavelength Division Multiplexing.
    

### 7.4 Spread Spectrum

[[Spread Spectrum]] is a communication technique in which a signal is spread over a bandwidth wider than the minimum required for transmitting the information.

It uses a spreading code or frequency-changing mechanism.

**Advantages:**

- Provides resistance to certain types of interference.
    
- Can improve communication reliability.
    
- Supports multiple users in some systems.
    
- Can make signals harder to detect without the appropriate receiver configuration.
    

Two major techniques are:

#### 1. Frequency Hopping Spread Spectrum (FHSS)

[[Frequency Hopping Spread Spectrum]] rapidly changes the carrier frequency according to a predefined hopping sequence.

**Working:**

1. The transmitter and receiver share a hopping sequence.
    
2. The transmitter changes frequencies according to the sequence.
    
3. The receiver follows the same sequence.
    
4. Both devices communicate on matching frequencies at the appropriate times.
    

**Advantages:**

- Can resist narrowband interference.
    
- Reduces the effect of interference on a single frequency.
    
- Provides some resistance to interception.
    

#### 2. Direct Sequence Spread Spectrum (DSSS)

[[Direct Sequence Spread Spectrum]] spreads data using a high-rate sequence of chips.

**Working:**

1. The original data bits are combined with a pseudorandom chip sequence.
    
2. The resulting signal occupies a wider frequency band.
    
3. The receiver uses the same sequence to despread the signal.
    
4. The original data is recovered.
    

**Advantages:**

- Provides resistance to narrowband interference.
    
- Supports signal recovery using the correct spreading code.
    
- Used in certain wireless communication technologies.
    

**FHSS vs DSSS**

|Feature|FHSS|DSSS|
|---|---|---|
|Full form|Frequency Hopping Spread Spectrum|Direct Sequence Spread Spectrum|
|Technique|Changes carrier frequency|Spreads data using chip sequences|
|Operation|Hops between frequencies|Uses a wider bandwidth continuously|
|Main benefit|Resistance to narrowband interference|Processing gain against interference|
|Example|Bluetooth Classic uses frequency hopping|IEEE 802.11b uses DSSS-based techniques|

---

## 8. Important Formula Sheet

### 8.1 Sine Wave Period and Frequency

$$  
T=\frac{1}{f}  
$$

$$  
f=\frac{1}{T}  
$$

### 8.2 Signal Bandwidth

$$  
B=f_{\text{high}}-f_{\text{low}}  
$$

### 8.3 Bit Length

$$  
\text{Bit Length}=\frac{\text{Propagation Speed}}{\text{Bit Rate}}  
$$

### 8.4 Nyquist Bit Rate

$$  
C=2B\log_2 L  
$$

### 8.5 Shannon Capacity

$$  
C=B\log_2(1+SNR)  
$$

### 8.6 Nyquist Sampling Theorem

$$  
f_s\geq2f_{\max}  
$$

### 8.7 PCM Quantization Levels

$$  
L=2^n  
$$

### 8.8 PCM Bit Rate

$$  
R_b=f_s\times n  
$$

### 8.9 Bits per Symbol

$$  
\text{Bits per Symbol}=\log_2 M  
$$

Where M is the number of possible signal symbols.

---

## 9. Important Exam Questions

### Short Answer Questions

1. Differentiate between analog and digital signals.
    
2. Define periodic and non-periodic signals.
    
3. Explain amplitude, frequency, period, and phase.
    
4. What is a composite signal?
    
5. Define Fourier analysis.
    
6. What is signal bandwidth?
    
7. Differentiate between bit rate and bit length.
    
8. Differentiate between baseband and broadband transmission.
    
9. State the Nyquist bit rate formula.
    
10. What is line coding?
    
11. Differentiate between NRZ-L and NRZ-I.
    
12. What is Manchester encoding?
    
13. Explain Alternate Mark Inversion.
    
14. What is 2B1Q encoding?
    
15. What is the purpose of 4B/5B encoding?
    
16. Differentiate between B8ZS and HDB3.
    
17. State the Nyquist sampling theorem.
    
18. Define PCM and its three stages.
    
19. What is Delta Modulation?
    
20. Define slope overload distortion.
    
21. Differentiate between ASK, FSK, and PSK.
    
22. What is QAM?
    
23. Differentiate between AM, FM, and PM.
    
24. What is multiplexing?
    
25. Differentiate between synchronous and statistical TDM.
    
26. What is WDM?
    
27. Differentiate between FHSS and DSSS.
    

### Long Answer Questions

1. Explain analog and digital signals and their characteristics.
    
2. Explain the parameters of a sine wave with suitable diagrams.
    
3. Explain composite signals, Fourier analysis, and bandwidth.
    
4. Derive and solve problems using the Nyquist bit rate formula.
    
5. Explain unipolar, polar, and bipolar line coding techniques.
    
6. Explain multilevel and multitransition encoding techniques.
    
7. Describe 4B/5B, 8B/10B, B8ZS, and HDB3.
    
8. Explain PCM with its sampling, quantization, and encoding stages.
    
9. Explain Delta Modulation and its distortions.
    
10. Compare ASK, FSK, BPSK, QPSK, and QAM.
    
11. Explain AM, FM, and PM.
    
12. Explain synchronous and statistical TDM.
    
13. Describe WDM and its applications in optical fibre communication.
    
14. Explain FHSS and DSSS with diagrams.
    

---

## 10. Quick Revision Table

|Topic|Key Point|
|---|---|
|Analog Data|Continuous information|
|Digital Data|Discrete information|
|Analog Signal|Continuously varying|
|Digital Signal|Discrete signal levels|
|Periodic Signal|Repeats after a fixed interval|
|Non-Periodic Signal|Does not repeat regularly|
|Amplitude|Maximum signal magnitude|
|Frequency|Cycles per second|
|Period|Time for one cycle|
|Phase|Relative position of waveform|
|Composite Signal|Combination of multiple sine waves|
|Fourier Analysis|Represents signals using frequency components|
|Bandwidth|Frequency range|
|Bit Rate|Bits transmitted per second|
|Bit Length|Physical length occupied by one bit|
|Baseband|Direct transmission of encoded signals|
|Broadband|Uses modulated bandpass signals|
|Nyquist Bit Rate|Maximum rate for a noiseless channel|
|Unipolar NRZ|Uses zero and one voltage polarity|
|NRZ-L|Bit represented by signal level|
|NRZ-I|Bit represented by transition or no transition|
|RZ|Signal returns to zero within bit interval|
|Manchester|Mid-bit transition|
|Differential Manchester|Mid-bit transition plus differential encoding|
|AMI|Binary 1 alternates polarity|
|Pseudoternary|Binary 0 alternates polarity|
|2B1Q|2 bits mapped to 1 of 4 levels|
|8B6T|8 bits mapped to 6 ternary symbols|
|4D-PAM5|Five-level signalling over four dimensions|
|MLT-3|Three-level transition-based encoding|
|4B/5B|4 bits converted into 5|
|8B/10B|8 bits converted into 10|
|B8ZS|Replaces 8 consecutive zeros|
|HDB3|Replaces 4 consecutive zeros|
|PCM|Sampling, quantization, encoding|
|Delta Modulation|Transmits changes in signal|
|Slope Overload|Input changes faster than staircase|
|ASK|Changes amplitude|
|FSK|Changes frequency|
|PSK|Changes phase|
|QAM|Changes amplitude and phase|
|AM|Carrier amplitude changes|
|FM|Carrier frequency changes|
|PM|Carrier phase changes|
|TDM|Shares channel using time slots|
|WDM|Shares optical fibre using wavelengths|
|FHSS|Changes carrier frequency|
|DSSS|Uses spreading chip sequence|

---

## 11. Recommended Study Order

1. Understand [[Data and Signals]] and sine wave parameters.
    
2. Learn [[Bandwidth]], bit rate, and bit length.
    
3. Practise [[Nyquist Bit Rate]] numericals.
    
4. Study [[Line Coding]] schemes and their differences.
    
5. Learn [[Block Coding]] and [[Scrambling]].
    
6. Understand [[Pulse Code Modulation]] and [[Delta Modulation]].
    
7. Compare ASK, FSK, PSK, and QAM.
    
8. Study AM, FM, and PM.
    
9. Learn [[TDM]], [[WDM]], and [[Spread Spectrum]].
    
10. Revise the formula sheet and practise diagrams.
    

**High-priority examination topics:**

- Nyquist bit rate numericals.
    
- NRZ-L, NRZ-I, Manchester, and Differential Manchester.
    
- AMI, B8ZS, and HDB3.
    
- 4B/5B and 8B/10B.
    
- PCM and Delta Modulation.
    
- ASK, FSK, PSK, and QAM.
    
- Synchronous vs Statistical TDM.
    
- FHSS vs DSSS.