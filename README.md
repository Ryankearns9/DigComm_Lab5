# Lab 5

## Introduction
Lab 5's objective is to physically build both QAM and QPSK waveforms. The lab uses the Emona Instruments pre-made lab setup and instructions to build these waveforms using the hardware listed below.

## Hardware
1. Emona TIMS (https://emona.com.au/products/engineering-teaching-equipment/electronics-telecoms-engineering/emona-tims-640.html)

## QPSK
Quadrature Phase Shift Keying is the act of modulating information through the act of altering the phase of a signal based on a 2-baud binary value. In this lab, there are two bauds per bit due to the 
Machester Encoding method used. When combined with QPSK, Manchester encoding effectively creates a BPSK waveform.

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
