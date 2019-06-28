# OctaveDifferentiation

There are multiple factors affecting the sound produced by an instrument, some of them being the pitch or timbre, frequency, the make of the instrument and so on. We have restricted our scope to frequency band distinction for recognition. Our project differentiates between 2 octaves of the D note of a piano.

The system has been designed TMS320C6713 DSP based DSK6713 kit (hardware implementation).

## System Description

The system consists of:
• DIP switches
• LEDs
• High pass Filter
• Low Pass Filter
The project is implemented on a TMS320C6455 DSP based DSK6455 kit.

## Specifications:

1. The final output is notified using the LEDs available on the DSK6713 board. Of thefour LEDs in total, glowing of the left two LEDs implies that the ocatave identified is of the lower frequency and the right two LEDs imply that the octave is of the higher
frequency.

2. The DIP switches are used to assign a null value to the essential variable in the code On account of this, we can switch input signals without having to terminate the program and rerun it.

3. The filters used are FIR filters of order 50 and with a sampling rate of 16kHz.
