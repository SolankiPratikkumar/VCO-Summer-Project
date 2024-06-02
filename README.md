# VCO-Summer-Project

## What is Voltage Controlled Oscillator(VCO)?

* A voltage-controlled oscillator is an oscillator with an output signal whose output can be varied over a range, which is controlled by the input DC voltage. It is an oscillator whose output frequency is directly related to the voltage at its input. The oscillation frequency varies from few hertz to hundreds of GHz. By varying the input DC voltage, the output frequency of the signal produced is adjusted.


## Voltage Controlled Oscillator Applications

* Function generator by square and triangular wave generator
* Music Synthesizers generate audio signals that can be manipulated to create various sounds and effects
* Phase locked loop (PLL) main component in this system
* Frequency synthesizers or generators/analyzers, to generate stable output frequencies that are integer multiples of a reference frequency
* Frequency Modulation (FM) Radio Transmitters and Receivers use for carrier frequency
* Electronic jamming equipment by generating a continuous wave or modulated signal at the same frequency as the target system's operating frequency
* Clock Generation in microprocessor,FPGA, DSP application
* Radar Systems by generate the necessary frequencies for transmitting radar pulses and processing the returned echoes
* Motor Speed Control by controlling the frequency of a pulse-width modulation (PWM) signal to regulate motor speed precisely
* GPS Receivers helps in generating the high-precision frequencies required to lock onto satellite signals and determine position
* Television by generating the carrier signal for tuning into different channels

## VCO

* In RC and LC based VCO Circuts the frequency is given by f=1/2piRC and f= 1/2pirt(LC) respectively so as C value decreases the output f increase by inversely proportionate and as it follows Linear relation with voltage, hence also so as input voltage increase the output frequency increases,, same follows for other case   
* The control voltage and frequency of oscillations are directly proportional. That is, when one increases, the other will increase.
  
![1](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/808dc697-50b8-4666-b488-6ba9daacc3ef)

* We can see that at nominal control voltage represented by Vc(nom), the oscillator works at its free running or normal frequency, fC(nom). As the control voltage decreases from nominal voltage, the frequency also decreases and as the nominal control voltage increases, the frequency also gets higher.

## Working of IC566 --VCO:

![2](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/f5efbe30-9dbc-43bc-8360-66bde4fce058)

* The output waveform of this VCO will be square wave. As we know the output frequency is related to the control voltage.
* In this circuit the first Op-amp will function as an integrator.
* The voltage divider arrangement is implemented here. Because of this, the half of the control voltage that is given as input is given to the positive terminal of the Op-amp 1. The same level of voltage is maintained at the negative terminal. This is to sustain the voltage drop across the resistor, R1 as half of the control voltage.
* When the MOSFET is in ON condition, the current flowing from the R1 resistor passes through the MOSFET. The R2 have half the resistance, same voltage drop and twice the current as that of R1. So, the extra current charges the connected capacitor. The Op-amp 1 should provide a gradually increasing output voltage to supply this current.
* When the MOSFET is in OFF condition, the current flowing from the R1 resistor passes through the capacitor, get discharged. The output voltage obtained from the Op-amp 1 at this time will be falling. As a result, a triangular waveform is generated as the output of Op-amp 1.
* The Op-amp 2 will operate as Schmitt trigger. The input to this Op-amp is triangular wave which is the output of the Op-amp 1.
* If the input voltage is higher than the threshold level, the output from the Op-amp 2 will be VCC.
* If the input voltage is less than the threshold level, the output from the Op-amp 2 will be zero. Therefore, the output of the Op-amp 2 will be square wave.

## Performance Parameter

* Consider the unity-gain negative-feedback
             Vout/Vin(s) = H(s)/[1 + H(s)]
* if a negative-feedback circuit has a loop gain that satisfies two conditions:
* |H(jω0)| ≥ 1
*  H(jω0) = 180

* Center Frequency: The center frequency (i.e., the midrange value in Fig. 15.40) is determined by the environment in which the VCO is used. For example, in the clock generation network of a microprocessor,the VCO may be required to run at the clock rate or even twice that. Today’s CMOS VCOs achieve center frequencies as high as hundreds of gigahertz.
* Tuning Range:  The required tuning range is dictated by two parameters: (1) the variation of the VCO center frequency with process and temperature, and (2) the frequency range necessary for the application.The center frequency of some CMOS oscillators may vary by a factor of two at the extremes of process and temperature, thus mandating a sufficiently wide (≥ 2×) tuning range to guarantee that the VCO output frequency can be driven to the desired value. Also, some applications incorporate clock frequencies that must vary by one to two orders of magnitude depending on the mode of operation, demanding a proportionally wide tuning range. An important concern in the design of VCOs is the disturbance of the output phase and frequency as a result of noise on the control line. For a given noise amplitude, the noise in the output frequency is proportional to KVCO because ωout = ω0 + KVCO Vcont .
* Tuning Linearity: Actual oscillator characteristics typically exhibit a high-gain region in the middle of the range and a low gain at the two extremes. Compared to a linear characteristic (the gray line), the actual behavior displays a maximum gain greater than that predicted by implying that, for a given tuning range, nonlinearity inevitably leads to higher sensitivity for some region of the characteristic.
* Output Amplitude : It is desirable to achieve a large output oscillation amplitude, thus making the waveform less sensitive to noise. The amplitude trades with power dissipation, supply voltage, and even the tuning range. Also, the amplitude may vary across the tuning range,an undesirable effect.
* Power Dissipation: As with other analog circuits, oscillators suffer from trade-offs among speed, power dissipation, and noise. Typical oscillators drain 1 to 10 mW of power
* Output Signal Purity: Even with a constant control voltage, the output waveform of a VCO is not perfectly periodic. The electronic noise of the devices in the oscillator and supply noise lead to noise in the output phase and frequency. These effects are quantified by “jitter” and “phase noise” and determined by the requirements of each application

## Key Specification in VCO:

* Frequency Range:
(a) Tuning Range: The range of frequencies over which the VCO can oscillate, controlled by the input voltage.
(b)Center Frequency: The nominal frequency around which the VCO operates.

* Tuning Sensitivity (Kvco): The rate at which the output frequency changes with respect to the input control voltage, typically expressed in MHz/V or GHz/V.
* Phase Noise: A measure of the stability of the oscillator’s frequency, expressed in dBc/Hz at a specific offset from the carrier frequency. Lower phase noise is desirable for higher performance.
* Output Power: The power level of the VCO’s output signal, usually measured in dBm.
* Harmonic Distortion: Indicates the presence of harmonics in the output signal, typically expressed as Total Harmonic Distortion (THD) in percentage.
* Power Supply Voltage: The required voltage to power the VCO, important for integration into circuits with specific voltage levels.
* Power Consumption: The amount of power the VCO consumes during operation, usually measured in milliwatts (mW).
* Control Voltage Range:The range of input voltages over which the VCO can be tuned, usually specified in volts (V).
* Temperature Stability: The VCO’s ability to maintain consistent performance over a range of operating temperatures, often specified in ppm/°C.
* Linearity: The linearity of the frequency versus control voltage characteristic, which affects tuning accuracy and predictability.
* Startup Time: The time required for the VCO to stabilize and start oscillating at the desired frequency after power is applied.
* Load Impedance: The impedance that the VCO is designed to drive, usually expressed in ohms (Ω).
* Modulation Bandwidth: The maximum rate at which the VCO can be modulated by the input control voltage without significant distortion or loss of signal integrity.
* Phase Jitter: A measure of the short-term frequency stability of the VCO, often specified in seconds or as an integrated value over a specific frequency range.
* Supply Rejection Ratio: Indicates how well the VCO maintains its frequency despite variations in the supply voltage, usually expressed in dB.
* Package Type: The physical packaging of the VCO, important for integration into systems (e.g., surface-mount, through-hole, etc.).

## Types of VCO:

![13](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/2b4aae65-797a-456b-bdc6-b8fc2c551f6b)



## Three Stage Ring Oscillator

* As two and single stage doesn't satisfy Brarkhausen Criteria so we have shown three stage Ring Oscillator

  ![3](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/d43e5764-5e01-4039-ad90-04e45ac3a28a)

* The circuit oscillates only if the frequency-dependent phase shift equals 180◦, i.e., if each stage contributes 60◦. The frequency at which this occurs is given by

  ![4](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/c81ad6df-f5c6-40c2-bd75-912e91febbc1)

* The minimum voltage gain per stage must be such that the magnitude of the loop gain at ωosc is equal to unity
  
  ![5](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/cd0d8768-9b34-4f64-914f-4e36c4c3f93a)

* In summary, a three-stage ring oscillator requires a low-frequency gain of 2 per stage, and it oscillates at a frequency of √3 ω0, where ω0 is the 3-dB bandwidth of each stage
* Since each stage contributes a frequency-dependent phase shift of 60◦ as well as a low-frequency signal inversion, the waveform at each node is 240◦ (or 120◦) out of phase with respect to its neighboring nodes
* The ability to generate multiple phases is a very useful property of ring oscillators
* Suppose the circuit is released with an initial voltage at each node equal to the trip point of the inverters,Vtrip(The trip point of an inverter is the input voltage that results in an equal output voltage)
* With identical stages and no noise in the devices, the circuit would remain in this state indefinitely,but noise components disturb each node voltage, yielding a growing waveform. The signal eventually exhibits rail-to-rail swings.

![7](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/999f236c-742b-4a7f-9e28-81b0cdd62820)

* Lets begins with VX = VDD . Under this condition, VY = 0 and VZ = VDD. Thus, when the circuit is released, VX begins to fall to zero (because the first inverter senses a high input), forcing VY to rise to VDD after one inverter delay, TD, and VZ to fall to zero after another inverter delay.
* The circuit therefore oscillates with a delay of TD between consecutive node voltages, yielding a period of 6TD
* While the small-signal oscillation frequency is given by A0√3ω0/2
* when the circuit is released with all inverters at their trip point, the oscillation begins with a frequency of √3A0ω0/2, but, as the amplitude grows and
the circuit becomes nonlinear, the frequency shifts to 1/(6TD) (which is a lower value)

![6](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/a2a5dbe9-0178-494c-a99d-61d6aacfe60a)

## Differential Ring VCO

* Here, M5 operates in the deep triode region and amplifier A1 applies negative feedback to the gate of M5. If the loop gain is sufficiently large, the differential input voltage of A1 must be small, giving VP ≈ VREF and |VDS5| ≈ VDD − VREF .
* Thus, the feedback ensures a relatively constant drain-source voltage even if I1 varies. In fact, as I1, say, decreases, A1 raises the gate voltage of M5 such that Ron5 I1 ≈ VDD − VREF

  ![8](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/5407cb27-d1d5-4458-939a-264ac6ee308f)

* The idea is to “serve” the on-resistance of M3 and M4 to that of M5 and vary the frequency by adjusting I1 and ISS simultaneously. If M3 and M4 are identical to M5 and ISS to I1, then VX and VY vary from VDD to VDD − VREF as M1 and M2 steer the tail current to one side or the other.
* Thus, if process and temperature variations, say, decrease I1 and ISS, then A1 increases the on-resistance of M3–M5, forcing VP and hence VX and VY (when M1 or M2 is fully on) equal to VREF
* The bandwidth of the op amp A1 in Figure is of some concern. If a change in Vcont takes a long time to change ωout , then the settling speed of a PLL using this VCO degrades significantly.

## Current Folded Steerig VCO:

![11](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/6beedcc8-a650-4029-868d-78d77d5c46c9)

* In the circuit of Figure, the gain of each stage is varied by the tail current to achieve interpolation.But it is desirable to maintain constant voltage swings. We also recognize that the gain of the differential pair M5–M6 need not be varied because even if only the gain of M3–M4 drops to zero, the slow path is fully disabled.
* We then surmise that if the tail currents of M1–M2 and M3–M4 vary in opposite directions such that their sum remains constant, we achieve both interpolation between the two paths and constant output swings.
* The resulting circuit employs the differential pair M7–M8 to steer ISS between M1–M2 and M3–M4. If Vcont is very negative, M8 is off and only the fast path amplifies the input. Conversely, if Vcont is very positive, M7 is off and only the slow path is enabled.
* Since the slow path in this case employs one more stage than the fast path, the VCO achieves a tuning range of roughly two to one. For operation with low supply voltages, the control pair M7–M8 can be replaced by the current-folding topology

## Current Straved VCO

![12](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/23921ac9-5244-47fc-9774-070a203495fa)

* The current starved ring VCO illustrates a wide oscillation frequency range of 66–875 MHz at 1.8 V supply voltage using 180nm CMOS technology.
* The circuit formed by using ring oscillator consists of odd number of gain stages connected in series and bias stage consists of current sink and current source. The
oscillation is performed by ring oscillator and the frequency tuning is achieved by controlling the supply current.
* The variable bias currents are used to control the oscillation frequency of this ring VCO. The transistors M1 and M2 operate as inverters while M3 and M4 operate as current sink and current source, respectively. The current sources limit the current available to inverters.
* The drain currents of transistors M5 and M6 are same and are set by the input control voltage ðVctrlÞ. The current in transistors M4 and M5 is mirrored from bias stage to
each cascaded inverting stage.
* The bias circuit is used to provide correct polarization for transistors M3 and M4. The tuning of frequency of oscillation for a wide range can be done by changing the value of control voltage and this is the benefit of this configuration.
* The linearity and bandwidth of VCO are determined by variation of control voltage ðVctrlÞ. The main drawback of this circuit is that under low frequency, the current starved inverter suffers from slow rise and falls at its output.
* Frequency of oscillation is given by fosc = Id/2N*Ctotal*Vctrl
  
## LC VCO 

* The oscillation frequency of LC topologies is equal to fosc = 1/(2π√LC), suggesting that only the inductor and capacitor values can be varied to tune the frequency, and other parameters such as bias currents and transistor transconductances affect fosc negligibly. Since it is difficult to vary the value of monolithic inductors, we simply change the tank capacitance to tune the oscillator.
* Voltage-dependent capacitors are called “varactors.” A reverse-biased pn junction can serve as a varactor.

  ![9](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/5438fd78-1d58-4074-95a7-844c7efebbe1)

* . To avoid forward-biasing D1 and D2 significantly, Vcont must not exceed VX or VY by more than a few hundred millivolts. Thus,if the peak amplitude at each node is A, then 0 < Vcont < VDD − A + 300 mV, where it is assumed that a forward bias of 300 mV creates negligible current.
* Interestingly, the circuit suffers from a trade-off between the output swing and the tuning range. This effect appears in most LC oscillators.
* Note that, since the swings at X and Y are typically large (e.g., 1 Vpp at each node), the capacitanceof D1 and D2 varies with time. Nonetheless, the “average” value of the Capacitance is still a function of Vcont , providing the tuning range.

![10](https://github.com/SolankiPratikkumar/VCO-Summer-Project/assets/140999250/1a59cf0a-5eb4-470a-9a36-79c2cc6340b6)

* So, the varactor diode is represented by Simple diode with series resistance of diode and a capacitance Cn represents the (voltage-dependent) capacitance between the n-well and the substrate.
  
