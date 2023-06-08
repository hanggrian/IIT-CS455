# Signals

## Analog signals

### Sine waves

Superposition of two sine waves:

$$
\begin{array}{rcl}
  S & = & \displaystyle A . \sin(\frac{2 \pi}P + \alpha) \\\\
  \sf position & = & \sf amplitude \times \sin(\frac{2 \pi}{period} + phase)
\end{array}
$$

$$
\begin{array}{rcl}
  F & = & 2S \\\\
  \sf superposition & = & \sf 2 \times position
\end{array}
$$

### Wavelength

The wavelength is a distance a signal can travel in one period.

$$
\begin{array}{rcl}
  \lambda & = & \displaystyle \frac{v}{f} \\\\
  \sf wavelength & = & \sf \frac{propagation \ speed}{frequency}
\end{array}
$$

> #### Example
>
> Wavelength of red light where $f=4.10^{14}$ Hz.
>
> $$
  \begin{array}{rcl}
    \lambda & = & \frac{v}{f} \\\\
    & = & \frac{3.10^8}{4.10^{14}} \\\\
    & = & \bf 0,75 \sf \ mm
  \end{array}
  $$

### Fourier analysis

*Jean-Baptiste Fourier* showed that any composite signal is actually a
combination of simple sine waves with different frequencies, amplitudes, and
phases.

The frequency $f$ of the sine wave which is the same as the frequency of the
composite signal is called the fundamental frequency or **first harmonic**.

## Digital signals

A digital signal is a composite signal with frequencies between $0$
and $\infty$.
We can transmit a digital signal by using **baseband** or **modulation**.

If a signal has $L$ levels, each level needs $\log_2{L}$ bits.

$$
\begin{array}{rcl}
  L & = & B^2 \\\\
  \sf signal \ length & = & \sf bits^2
\end{array}
$$

### Bit rate

The bit rate is the number of bits sent in 1 s expressed in bits per second
(bps).

$$
\begin{array}{rcl}
  B & = & F . R . P \\\\
  \sf bits & = & \sf frames \times resolution \times bits \ per \ pixel
\end{array}
$$

> #### Example
>
> We need to download text documents at the rate of **100 pages per minute**.
  What is the required bit rate of the channel?
>
> - 24 lines with 80 characters
> - one character requires 8 bits
>
> $$
  \begin{array}{rcl}
    100 . 24 . 80 . 8 & = & \frac{1,536,000}{60} \\\\
    & = & \bf 25,600 \sf \ bps
  \end{array}
  $$

### Fourier analysis (digital)

The Fourier analysis can be used to decompose a digital signal.

| Type | Description |
| --- | --- |
| Periodic | The decomposed signal has a frequency domain representation with an **infinite bandwidth and discrete frequencies**. |
| Non-periodic | The decomposed signal still has an infinite bandwidth but the frequencies are continuous. |

### Baseband transmission

Baseband requires a low-pass channel, a channel with bandwidth that starts
from $0$.

If we want to preserve the exact form of a non-periodic digital signal, we need
to send the continuous range of frequencies beetween $0$ and $\infty$.

In a low-pass channel with limited bandwidth, we approximate the digital signal
with an analog signal.

### Modulation tranmission

Modulation allows us to use a **bandpass channel** &mdash; A channel with a
bandwidth that does not start from $0$.

## Amplification

$$
\begin{array}{rcl}
  P_2 & = & P_1 . 10^{G / 10} \\\\
  P_2 & = & P_1 . \sf 10^{gain / 10}
\end{array}
$$

## Transmission impairment

Signal travels through transmission media which are not perfect. The
imperfection causes signal impairment. What is sent is **not** what is received.
Three causes of impairment:

### Attenuation

Attenuation means loss of energy. When a signal travels through a medium, it
loses some of its energy to overcome the resistance of the medium.

To show that a signal has lost or gained strength we use the UMT of the decibel.
The decibel (dB) measures the **relative** strengths of the two signals or one
signal at two different points.

$$
\begin{array}{rcl}
  dB & = & L . D \\\\
  \sf total \ loss & = & \sf loss \ per \ kilometer \times distance
\end{array}
$$

$$
dB = 10 . \log_{10}\frac{P_2}{P_1}
$$

Where $P_1$ and $P_2$ are the powers of a signal at points $1$ and $2$
respectively.

> #### Example
>
> $$
  \begin{array}{rcl}
    \log{a}.b & = & \log{a} + \log{b} \\\\
    10 \log_{10}\frac{P_3}{P_1} & = & 10 \log_{10}\frac{P_3}{P_2} . \frac{P_2}{P_1} \\\\
    & = & 10 (\log\frac{P_3}{P_2} + \log\frac{P_2}{P_1}) \\\\
    & = & 10 \log\frac{P_3}{P_2} + 10 \log\frac{P_2}{P_1} \\\\
    & = & 10 - 3 \\\\
    & = & \bf 7 \sf \ dB
  \end{array}
  $$

### Distortion

Distortion means that the signal changes its form or shape because signal
components at the receiver have phases different from what they had at the
sender.

### Noise

| Type | Description |
| --- | --- |
| Thermal noise | Random motion of electrons in a wire which creates an extra signal not originally sent by the transmitter. |
| Induced noise | Comes from sources such as motors & appliances. |
| Crosstalk | An effect of one wire on the other. |
| Impulse noise | A signal with high energy in a very short time that comes from power lines or lightning. |

The *Signal-to-Noise Ratio (SNR)* is actually the ratio of what is wanted
(signal) to what is not wanted ().

$$
\begin{array}{rcl}
  SNR & = & \displaystyle \frac{ASP}{ANP} \\\\
  \sf signal-to-noise \ ratio & = & \sf \frac{average \ signal \ power}{average \ noise \ power}
\end{array}
$$

$SNR_{dB}$ is defined:

$$
\begin{array}{rcl}
  SNR_{dB} & = & 10 \log_{10} SNR \\\\
  \sf (signal-to-noise \ ratio)_{dB} & = & 10 \log_{10} signal-to-noise \ ratio
\end{array}
$$

## Data rate limits

### Noiseless channel: Nyquist bit rate

For a noiseless channel, the nyquist bit rate formula defines the
**theoretical** maximum bit rate.

$$
\begin{array}{rcl}
  R & = & 2 . B . \log_2 L \\\\
  \sf bit \ rate (in \ bps) & = & \sf 2 \times bandwidth \times \log_2 signal \ levels \ used
\end{array}
$$

### Noisy channel: Shannon capacity

In 1944, Claude Shannon introduced a formula called the **Shannon Capacity** to
determine the **theoretical** highest data rate for a **noisy** channel:

$$
\begin{array}{rcl}
  C & = & B . \log_2{(1 + SNR)} \\\\
  \sf capacity (in \ bps) & = & \sf bandwidth \times \log_2{(1 + signal-to-noise \ ratio)}
\end{array}
$$

For practical purposes when the SNR is very high, we can assume that $SNR+1$
is almost the same as SNR.

## Performance

Performance of network &mdash; How good is it?

An increase in bandwidth in Hz means an increase in bandwidth in bps.

| Measurement | Description |
| --- | --- |
| Bandwidth | Potential measure of a link data rate. |
| Throughput | Actual measure of how fast we can send data. |

### Latency

The **latency or delay** defines how long it takes for an entire message to
completely arrive at the destination from the time the first bit is sent from
the source.

$$
\begin{array}{rcl}
  L & = & PT + TT + QT + PD \\\\
  \sf latency & = & \sf propagation \ time + transmission \ time + queueing \ time + processing \ delay
\end{array}
$$

#### Propagation time

Propagation time measures time required to travel from the source to the
destination.

$$
\begin{array}{rcl}
  PT & = & \displaystyle \frac{D}{PS} \\\\
  \sf propagation \ time & = & \sf \frac{distance}{propagation \ speed}
\end{array}
$$

The propagation speed of electromagnetic signals depends on the medium and
frequency of the signal.

#### Transmission time

The time required for transmission of a message depends on the size of the
message and the bandwidth of the channel.

$$
\begin{array}{rcl}
  TT & = & \displaystyle \frac{MS}{B} \\\\
  \sf transmission \ time & = & \sf \frac{message \ size}{bandwidth}
\end{array}
$$

#### Queueing time

The time needed for each intermediate or end device to hold the message before
it can be processed.
