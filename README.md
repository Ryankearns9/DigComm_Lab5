# Lab 5

## Introduction
Lab 5's objective is to physically build both QAM and QPSK waveforms. The lab uses the Emona Instruments pre-made lab setup and instructions to build these waveforms using the hardware listed below.

## Hardware
1. Emona TIMS (https://emona.com.au/products/engineering-teaching-equipment/electronics-telecoms-engineering/emona-tims-640.html)

## QPSK
Quadrature Phase Shift Keying is the act of modulating information through the act of altering the phase of a signal based on a 2-baud binary value. In this lab, there are two bauds per bit due to the 
Machester Encoding method used. When combined with QPSK, Manchester encoding forces bit transitions to cross the origin.

A typical QPSK constellation can be found below. The image was taken from ETSI EN 302 307-1.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/QPSK_Constellation.PNG)

### Manchester Encoding
Manchester Encoding is the act of encoding a bit by transitioning a bit from either high to low or low to high. It is assumed that the Emona Instruments follows IEEE standards and thus, encoded bits 
follow the below table for encoding. Note that this implies that a low to high voltage mid bit period transition implies a logical 1. Conversely a high to low voltage transition in the middle of a bit 
period implies a logcal 0.

| Bit        | Baud Voltage |
| ---------- |:------------:|
| 0 start    | high         |
| 0 end      | low          |
| 1 start    | low          |
| 1 end      | high         |

If we assume that Emona Labs follows both IEEE and ETSI standards, then we can conclude that a bit value of 0 will put us in the upper left quadrant while a 1 will put us in the lower right quadrant.
The implication of this is that a positive frequency at a bit period transition will imply a 0->1, a negative frequency will imply a 1->0, and no transition at all will imply a repeated bit value.

### Questions
The below questions are posed by the Emona Instruments labs. Answer correspond to the related question.

#### Question 1
The bit rate at the Oscilliscope, as seen in the below figure, is half that out of the Sequence Generator. This is because the Serial Output takes an input and will seperate even and odd bit indexes 
into the Channel 1 and Channel 2 outputs every other clock cycle. As seen in the below figure, Channel 1 and Channel 2 are half a sample period off from each other. 

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_1.png)

#### Question 2
The Multiplier output spectrum is shown in the below figure. The two blue peaks in the FFT output is distinctive of BPSK.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_2b.png)

In the below figure, we can further distinguish this as BPSK because the 180 degree phase shifts at bit boundaries.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_2a.png)

#### Question 3
This is the imaginary portion of the waveform. mentioned in Question 2. It is also a BPSK. As with the previous question, the two peaks of in the FFT suggest it is BPSK.
Further, the 180 degree change at bit boundaries further suggest that this is a BPSK waveform.


#### Question 4
According to theory, the signal present in the below images is QPSK. This can be seen by the more subtle phase transitions in the below time domain plot. Further, the FFT is a single lobe rather than 
the two distinct lobes seen in BPSK.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_3b.png)

#### Question 5
The waveform generated is a single sine wave because the sine and the cosine are added together. This creates the below trig.

$sin(\omega t + \phi b_0) + cos(\omega t + \phi b_1)$

$sin(\omega t + \phi b_0) + sin(\omega t + \phi b_1 - \pi /2)$

Using the Identity:

$sin(\alpha) + sin(\beta)=sin((\alpha + \beta)/2)cos((\alpha - \beta)/2)$

where $\alpha = \omega t + \phi b_0$ and $\beta=\omega t + \phi b_1 - \pi /2$. Therefore, $\alpha+\beta=2 \omega t + \phi b_0 + \phi b_1 + \pi/2$. Also, $\alpha - \beta=\pi/2 +\phi b_0 -\phi b_1$.

Our equation is thus, $sin(\omega t + (\phi b_0) /2 + (\phi b_1) /2 - \pi /4)cos(\pi/4 +\phi b_0/2 -\phi b_1/2)$ which is a single sine wave with a amplitude offset defined by the sine wave.


![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_3a.png)

#### Question 6
Two examples of multi-level amplitudes can be found below. As can be seen, there are 4 distict ampltidue levels when the phase is offset. Neither the sine or the cosine are fully canceled out when the 
phase is offset like this. Therfore, the the amplitudes for both are being added against eachother. The percent of each amplitude which is included is based on how offset the phase is.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_4b.png)
![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_4c.png)

#### Question 7
The output from the comparator is shown below. The explanation for what we are seeing can be explained by the following trigonometry:

Our original signal:

$f(s) = sin(\omega t + \phi b_0) + cos(\omega t + \phi b_1)$

When we multiply by our original sine signal offset by 180 degrees, we get:

$f(s) = sin(\omega t + \phi b_0)sin(\omega t + \pi) + cos(\omega t + \phi b_1)sin(\omega t + \pi)$

$f(s) = sin(\omega t + \phi b_0)sin(-\omega t) + cos(\omega t + \phi b_1)sin(-\omega t)$

We know the following identities
$sin(\Alpha ) sin(\Beta ) = (1/2) [ cos (\alpha - \beta) - cos (\alpha + \beta) ]$

$cos(\Alpha ) sin(\Beta ) = (1/2) [ sin (\alpha + \beta) - sin (\alpha - \beta) ]$





![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_5a.png)

