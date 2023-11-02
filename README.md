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
The bit rate at the Oscilliscope, as seen in the below figure, is half that out of the Sequence Generator. This is because the Serial Output takes an input an will seperate even an odd bit indexes into the 
Channel 1 and Channel 2 outputs every other clock cycle.

![Image](https://github.com/Ryankearns9/DigComm_Lab5/blob/main/imgs/Lab_5_QPSK/picture_1.png)
