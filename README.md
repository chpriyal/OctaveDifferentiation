# OctaveDifferentiation
By Priyal Chhatrapati

For a detailed explation, read my [blogpost](https://chpriyal.github.io/)

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

## FIR Filters

Finite impulse response (FIR) filter is a filter whose impulse response (or response to any finite length input) is of finite duration, because it settles to zero in finite time. The impulse response of an Nth-order discrete-time FIR filter lasts for N + 1 samples, and then settles to zero. The output y of a linear time invariant system is determined by convolving its input signal
x with its impulse response b.

For a discrete-time FIR filter, the output is a weighted sum of the current and a finite number of previous values of the input. The operation is described by the following equation, which defines the output sequence y[n] in terms of its input sequence x[n]:

y[n] = b0x[n] + b1x[n-1] + --------- + bNx[n-N] where:

• x[n]is the input signal,

• y[n] is the output signal,

• bi are the filter coefficients, also known as tap weights, that make up the impulse response,

• N is the filter order; an Nth-order filter has (N+1) terms on the right-hand side.


An FIR filter has a number of useful properties:

• Require no feedback. This means that any rounding errors are not compounded by summed iterations. The same relative error occurs in each calculation. This also makes implementation simpler.

• Are inherently stable. This is due to the fact that, because there is no required feedback, all the poles are located at the origin and thus are located within the unit circle (the required condition for stability in a Z transformed system).

• They can easily be designed to be linear phase by making the coefficient sequence symmetric; linear phase, or phase change proportional to frequency, corresponds to equal delay at all frequencies.

## Implementation

The implementation was done by first observing the two octaves in Time and Frequency domain.
Both the D1 and D6 octave samples are passed through the High-pass and Low- pass filters; the FFT plots indicate that the D1 octave frequencies get attenuated in the desired manner when passed through the correctly tuned High-pass filter and the D6 and Low pass filter have a synonymous relationship.

LPF and HPF of required specifications are generated using the filterDesigner tool on Matlab. The cut-off frequencies for the filters are obtained on the basis of the harmonics present in the respective D1 and D7 Octave samples.
