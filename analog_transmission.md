# Analog transmission

## Digital-to-analog conversion

Digital-to-analog conversion is the process of changing one of the
characteristics of an analog signal based on the information in digital data.

A sine wave is defined by:

- Amplitude
- Frequency
- Phase

Any of them can be changed based on the information in digital data giving us
three mechanisms for connecting digital data into an analog signal.

### Data rate vs signal rate

$$
\begin{array}{rcl}
  S & = & \displaystyle \frac{N}{T} \\\\
  \sf signal \ rate & = & \sf \frac{data \ rate}{num \ of \ data \ elements \ carried \ in \ one \ signal}
\end{array}
$$

The sending device produces a high-frequency signal called the **carrier
signal**. Digital information changes the carrier signal by modifying one or
more of its characteristics (amplitude, frequency, or phase). This kind of
modification is called **modulation**.

### Amplitude shift keying

In *amplitude shift keying (ASK)*, the **amplitude** of the carrier signal **is
varied**. Both frequency and the phase remain constant.

#### Binary ASK

In *Binary ASK (BASK)*, the amplitude of one signal level is $0$, the other is
the same as the amplitude of the carrier.

$$
  1 - A \qquad 1 - A_1 \\\\
  0 - 0 \qquad 0 - A_2
$$

#### Bandwidth for ASK

$$
\begin{array}{rcl}
  B & = & (1+d).S \\\\
  & = & \sf (1 + depends \ on \ modulation \ and \ filtering \ process) . signal \ rate
\end{array}
$$

The middle of the bandwidth is where $f_c$ the carrier frequency is located.

If digital data are presented as a unipolar NRZ, digital signal with a high
voltage of $1$ V and a low voltage of $0$ V. The implementation can be achieved
by multiplying the NRZ digital signal by the carrier signal coming from an
oscillator.

We can have multilevel ask in whcih there are more than two levels.

$$
\begin{array}{llll}
  00 & A_1 & 1 & A_1 \\\\
  01 & A_2 && \\\\
  10 & A_3 & 0 & A_2 = 0 \\\\
  11 & A_4 &&
\end{array}
$$

### Frequency shift keying

#### Binary FSK

In *Binary FSK (BFSK)*, we have selected two carrier frequencies $f_1$
and $f_2$.

| Carrier | Data element | Representation |
| --- | --- | --- |
| First | `0` | $f_1$ |
| Second | `1` | $f_2$ |

$$
\begin{array}{rcl}
  B & = & (1+d).S + 2\Delta f \\\\
  & = & \sf (1 + depends \ on \ modulation \ and \ filtering \ process) . signal \ rate + 2 . deviation \ from \ the \ carrier \ frequency
\end{array}
$$

$$
\begin{array}{rcl}
  f_1 & = & f_c - \Delta f \\\\
  f_2 & = & f_c + \Delta f
\end{array}
$$

BFSK can be implemented by using a voltage-controlled oscillator that changes
its frequency according to the input voltage.

#### Multilevel FSK

We can use 4 different frequencies $f_1$, $f_2$, $f_3$, and $f_4$ to send 2 bits
at a time. To send 3 bits at a time, we can use 8 frequencies.

$$
2^2 = 4 \begin{cases}
   0 & 0 & \qquad f_1 \\\\
   0 & 1 & \qquad f_2 \\\\
   1 & 0 & \qquad f_3 \\\\
   1 & 1 & \qquad f_4
\end{cases}\\\\
2^4 = 16 \begin{cases}
   0 & 0 & 0 & 0 & \qquad f_1 \\\\
   \vdots & \vdots & \vdots & \vdots & \\\\
   1 & 1 & 1 & 1 & \qquad f_{16}
\end{cases}
$$

$$
\begin{array}{rcl}
  B & = & (1+d).S + (L-1).2\Delta f
\end{array}
$$

Minimum value of $2\Delta f$ needs to be $S$.

The bandwidth with $d=0$:

$$
\begin{array}{rcll}
  B & = & S+(L-1).S = L.S \\\\
  & = & \sf S+(num \ of \ frequencies-1).S = num \ of \ frequencies . S
\end{array}
$$

$$
\textsf{3 bits/signal}\\\\
2^3 = 8 \begin{cases}
   0 & 0 & 0 \\\\
   \vdots & \vdots & \vdots \\\\
   1 & 1 & 1
\end{cases}
$$

$$
\textsf{4 bits/signal}\\\\
2^4 = 16 \begin{cases}
   0 & 0 & 0 & 0\\\\
   \vdots & \vdots & \vdots & \vdots \\\\
   1 & 1 & 1 & 1
\end{cases}
$$

### Phase shift keying

In phase shift keying, the phase of the carrier is varied. Both amplitude and
frequency remain constant.

#### Binary PSK

In *Binary PSK (BPSK)*, We have only two signal elements: One with the phase
of $0 \degree$ and the other with the phase of $180 \degree$.

**Implementation**: The signal element with phase $180 \degree$ can be seen as
the compliment of the signal element with phase $0 \degree$. The polar NRZ
signal is multiplied by the carrier signal.

| Bit | Representation |
| --- | --- |
| `0` | $180 \degree$ |
| `1` | $0 \degree$ |

#### Quadrature PSK

*Quadrature PSK (QPSK)* uses two separate BPSK modulations, one is in phase, the
other quadrature (out-of-phase) the incoming bits are first passed through
serial-to-parallel conversion that sends one bit to one modulator and the next
bit to the other modulator.

The two composite signals created by each multiplier are sine waves with the
same frequency but with different phases when they are added. The result is
another sine wave with one of four positive phases: $45 \degree$, $-45 \degree$,
$135 \degree$, $-135 \degree$.

#### Constellation diagram

A **constellation diagram** can help us define the amplitude and phase of a
signal element when we are using two carriers. The length of the vector that
connect the point to the origin is the amplitude of the signal element, the
angle, the vector makes with the $X$ axis is the phase of the signal element.

| | $X$-axis | $Y$-axis |
| --- | --- | --- |
| Related to | In-phase career. | Quadrature career. |
| Projection of the point | Defines the amplitude of the in-phase component. | Defines the amplitude of the quadrature component. |

## Analog-to-analog conversion

### Analog modulation

Analog modulation is the representation of **analog information** by an **analog
signal**. Modulation is needed if only a bandpass channel is available.

### Amplitude modulation

In *amplitude modulation (AM)* transmission, the carrier signal is modulated so
that its amplitude varies with the changing modulating signal. The frequency and
phase of the carrier remain the same.

The AM modulation creates a bandwidth that is twice the bandwidth of the
modulating signal and covers a range centered around the carrier frequency.

The *Federal Communication Commision (FCC)* allows $10$ KHz for each AM station.
AM stations are allowed carrier frequencies between $530$ and $1700$ KHz, but
each station carrier frequency must be separated from those on either side of it
by at least $10$ KHz.
