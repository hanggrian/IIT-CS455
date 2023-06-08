# Transmission

## Digital-to-digital conversion

### Line coding

Line coding is the process of converting digital data to digital signals.

| Source | Description |
| --- | --- |
| Sender | Digital data are encoded into a digital signal. |
| Receiver | Digital data are recreated by decoding the digital signal. |

| Data element | Signal element |
| --- | --- |
| The smallest entity that can represent a piece of information; this is the **bit**. | The shortest unit of a digital signal. |
| What we need to send. | What we can send. |
| Are being carried. | Are the carriers. |

### Data rate vs signal rate

The data rate defines the number of data elements sent in 1s (bit rate). The
**signal rate** is called the **baud rate**.

A **baud** is a signaling event or the change in the amplitude or the frequency
or phase of the carrier wave.

**Baud rate** refers to the number of signaling events that can be generated in
a 1s interval.

The relationship between data rate and signal rate:

$$
\begin{array}{rcl}
  S & = & \frac{CN}{T} \\\\
  \sf baud \ rate & = & \sf \frac{factor \times data \ rate (bps)}{data \ elements \ each \ signal}
\end{array}
$$

Most digital signals we encounter in real life have a bandwidth with finite
values. The bandwidth is theoretically infinite but many components have such a
small aplitude that they canb be ignored. The effective bandwidth is finite.

The baud rate are not bit rate determines the required bandwidth for a signal.

The receiver calculates a running average of the received signal power. This
average is called the baseline. The incoming signal power is evaluated against
this baseline to determine the value of the data element.

### DC component

The voltage level of a signal is constant.

A *Direct Current (DC)* component presents a problem for a system that can
**not** low frequencies or a system that uses electrical coupling via a
transformer.

To correctly interpret the signal received from the server, the receiver's bit
intervals must correspond exactly to the sender's bit intervals. If the
receiver's clock is faster or slower, the bit intervals are not matched and the
receiver might misinterpret the signals.

### Self-synchronization

Self-synchronization can be achieved if there are transitions in the signal that
alert the receiver to the beginning, middle, or the end of the pulse.

### Unipolar scheme

In a unipolar scheme, all the signal levels are on one side of the time axis,
either above or below.

A unipolar scheme was designed as a *Non-Return-to-Zero (NRZ)* scheme in which
the positive voltage defines bit $1$ and the zero voltage defines bit $0$. It is
called NRZ because the signal does not return to zero at the middle of the bit.

### Polar scheme

In a **polar scheme**, the voltages are on **both sides of the same axis**. For
example, the voltage level for $0$ can be positive and the voltage level for $1$
can be negative.

### Two versions of NRZ

| Variant | Description |
| --- | --- |
| NRZ-Level | The level of voltage determines the value of the bit. |
| NRZ-Invert | The change or lack of change in the level of the voltage determines the value of the bit. **If there is no change the bit is $\bf 0$, if there is a change the bit is $\bf 1$**. |

The *Return-to-Zero (RZ)* scheme uses three values: positive, negative, and
zero. In RZ, the signal changes not between but during the bit.

### Manchester

In **Manchester** encoding the duration of the bit is divided into two values.
The voltage remains at one level during the first half and moves to the other
level in the second half.

In **Differential Manchester**, there is always a transition at the middle of
the bit but the bit values are determined at the beginning of the bit. **If the
next bit is $\bf 0$ there is inversion, if the next bit is $\bf 1$ there is
none.**

| | `0` | `1` |
| --- | --- | --- |
| Manchester | ![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/encoding_m_0.png) | ![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/encoding_m_1.png) |
| Differential Manchester | ![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/encoding_dm_0.png) | ![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/encoding_dm_1.png) |

### Multilevel binary

There are three voltage levels: positive, negative, and zero. The voltage level
for one data element is zero, while the voltage level for the other element
alternates between positive and negative.

### AMI

*Alternate Mark Inversion (AMI)* a zero voltage represents binary $0$.
Binary $1$ s are represented by alternating positive and negative voltages.

### Pseudoternary

$1$ is encoded as zero voltage and the $0$ bit is encoded as alternating
positive and negative voltages.

### Multilevel schemes

Let's increase the number of bits per baud by encoding a pattern of $m$ bits
into a pattern of $n$ signal elements. We have two types of data elements
($0$ s and $1$ s) which means that a group of $m$ data elements can produce a
combination of $2^m$ data patterns.

If we have $L$ different levels, then we can produce $L^n$ combination of
signal patterns.

Data encoding is not possible if $2^m > L^n$ because some data patterns can
**not** be encoded.

#### 2B1Q

*Two Binary, One Quarterary (2B1Q)* uses data patterns of size $2$ and encodes
the $2$-bit patterns as one signal element belonging to a four-level signal. In
this type of encoding $m=2, n=1, L=4$.

#### 8B6T

*Eight Binary, Six Ternary (8B6T)*, the idea is to encode a pattern of $8$ bits
as a pattern of $6$ signal elements, where the signal has $3$ levels (ternary).

### DC balance

Each signal pattern has a weight of $0$ or $+1$. There is no pattern with the
weight $-1$. If two groups of weight $1$ are encountered one after another, the
first one is sent as is, while the next one is totally inverted to give a weight
of $-1$.

## Analog-to-digital conversion

## Transmission modes
