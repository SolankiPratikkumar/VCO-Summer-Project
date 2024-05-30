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



* The higher the quality factor (Q) of the oscillator, the lower the VCO phase noise is. However, higher Q circuits have narrower frequency ranges. Increasing the power supply will also lower the phase noise
* One strategy for minimizing phase noise in such VCOs is to increase the voltage tuning range of the VTUNE to the VCO
