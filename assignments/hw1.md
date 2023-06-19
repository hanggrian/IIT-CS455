<!-- hotfix: KaTeX -->
<!-- https://github.com/yzane/vscode-markdown-pdf/issues/21/ -->
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<script type="text/x-mathjax-config">MathJax.Hub.Config({ tex2jax: { inlineMath: [['$', '$']] }, messageStyle: 'none' });</script>

# [Homework 1](https://github.com/hendraanggrian/IIT-CS455/blob/assets/assignments/hw1.pdf)

## Problem 1

> What are advantages and disadvantages of a fully connected mesh topology of a
  network?

| Advantages | Disadvantages |
| --- | --- |
| High redundancy because each connection is handled individually | Expensive and difficult to install and maintain |
| Network expansion doesn't require setup or disruption | Network requires a high traffic capability |
| No need for a centralized system | Consumes more power than other topologies |

## Problem 2

> We would like to send 4 bits per level of a digital signal. How many signal
  level are needed?

**Using [digital signals](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#digital-signals)**:

$$
\begin{array}{rcl}
  L & = & B^2 \\\\
  & = & 4^2 \\\\
  & = & \bf 16 \sf\ levels
\end{array}
$$

Illustrated as:

| Binary | Decimal | Binary | Decimal | Binary | Decimal | Binary | Decimal |
| ---: | :--- | ---: | :--- | ---: | :--- | ---: | :--- |
| `0000` | 0 | `0100` | 4 | `1000` | 8 | `1100` | 12 |
| `0001` | 1 | `0101` | 5 | `1001` | 9 | `1101` | 13 |
| `0010` | 2 | `0110` | 6 | `1010` | 10 | `1110` | 14 |
| `0011` | 3 | `0111` | 7 | `1011` | 11 | `1111` | 15 |

## Problem 3

> A computer monitor has the resolution of $1200 \times 1000$ pixels. If each
  pixel uses $1026$ colors, how many bits are needed to send the complete
  contents of a screen?

**Using [bit rate](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#bit-rate)**:

$$
\begin{array}{rcl}
  B & = & F . R . P \\\\
  & = & 1 \times 1,200 \times 1,000 \times \log_{2}{1,026} \\\\
  & = & \bf 12,000,000,000 \sf\ bits
\end{array}
$$

## Problem 4

> Consider a sine wave $s(t)$ with the following parameters: period $T=0.1$
  sec., amplitude $A=10$ V and phase $\alpha=\pi/2$. Find an analytical formula
  for the superposition of two such sine waves $f(t) = s(t) + s(t)$ and draw its
  time and frequency domain plots ($t$ denotes time).

**Using [sine waves](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#sine-waves)**:

$$
\begin{array}{rcl}
  S & = & \displaystyle A . \sin(\frac{2 \pi}P + \alpha) \\\\
  & = & 10 \times \sin(\frac{2 \pi}{0.1} + \pi/2)
\end{array}
$$

$$
\begin{array}{rcl}
  F & = & 2S \\\\
  & = & 10 \times \sin(\frac{2 \pi}{0.1} + \pi/2) + 10 \times \sin(\frac{2 \pi}{0.1} + \pi/2) \\\\
  & = & \bf 20 \times \sin(\frac{2 \pi}{0.1} + \pi/2)
\end{array}
$$

Illustrated as:

![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/hw1_analog.png)

## Problem 5

> What are the disadvantages of the baseband transmission of a digital signal?

- Limited bandwidth &mdash; Digital signals need to be approximated with analog
  signals in case of limited bandwidth.
- High interference &mdash; More susceptible to noises compared to modulation.
- Short distance &mdash; Requires extra equipments to amplify.

## Problem 6

> Explain why the original *Shannon* capacity formula can be simplified to
>
> $$
    C = B \frac{SNR_{dB}}{3}
  $$

**Using [noise](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#noise)**:

$$
\begin{array}{rcl}
  SNR_{dB} & = & 10 . \log_{10}{SNR} \\\\
  \frac{SNR_{dB}}{10} & = & \log_{10}{SNR}
\end{array}
$$

**Using [Shannon capacity](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#noisy-channel-shannon-capacity)**:

$$
C = B . \log_2{(1 + SNR)}
$$

When $SNR$ is very high, we can simplify $1+SNR$.

$$
\begin{array}{rcl}
  \log_2{SNR} & = & \log_{10}{SNR} / \log_{10}2 \\\\
  & = & \frac{SNR_{dB}}{10} / \log_{10}2 \\\\
  & = & SNR_{dB} / 10 . \log_{10}2 \\\\
  & = & \bf \displaystyle \frac{SNR_{dB}}3
\end{array}
$$


## Problem 7

> A certain signal travels from source $A$ via points $B$ and $C$ to
  destination $D$. Between the points $A$ and $B$ the signal is amplified
  by $10$ dB. The points $B$ and $C$ are $10$ km apart. They are connected with
  a cable whose loss is $0.5$ dB/km. Between the points $C$ and $D$ the signal
  is amplified by $15$ dB. The power of the signal at the source $A$ is $1$ mW.
  What is the power of the signal at the destination $D$?

**Using [amplification](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#amplification)** A &rarr; B:

$$
\begin{array}{rcl}
  P_2 & = & P_1 . 10^{G / 10} \\\\
  & = & 1 \times 10^{10 / 10} \\\\
  & = & \bf 10 \sf\ mW
\end{array}
$$

**Using [attenuation](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#attenuation)** B &rarr; C:

$$
\begin{array}{rcl}
  P_3 & = & P_2 . 10^{G / 10} \\\\
  & = & 10 \times 10^{-(0.5 \times 10) / 10} \\\\
  & = & 10 \times 10^{-5 / 10} \\\\
  & = & \bf 3.16 \sf\ mW
\end{array}
$$

**Using amplification** C &rarr; D:

$$
\begin{array}{rcl}
  P_4 & = & P_3 . 10^{G / 10} \\\\
  & = & 3.16 \times 10^{15 / 10} \\\\
  & = & \bf 99.92 \sf\ mW
\end{array}
$$

## Problem 8

> Define a DC component and its effect on digital transmission.

DC component is constant voltage in a signal that presents a problem in some
scenarios:

- A system that can **not** transmit low frequencies.
- A system that uses electrical coupling via a transformer.

## Problem 9

> What is the role of a header added to a data unit in the OSI network model?

The roles of **network layer** in OSI model are:

- Logical addressing
- Routing
- Internetworking
- Packetizing
- Fragmentation
- Address resolution

## Problem 10

> What is the difference between a logical address and a physical address?

Logical addressing in **network layer** refers to assigned address like IP
address. While physical addressing in **data link layer** are attached to
hardware like MAC address.

## Problem 11

> What is the total delay for a file of $2.5$ million bytes that is being sent
  over a link with a router having queuing time of $2$ microseconds and
  processing time of $1$ microsecond. The length of the link is $1,000$ km. The
  speed of the signal is $2 \times 10^8$ m/s. The link has a bandwidth of $5$
  Mbps. Which component of this delay is dominant? Which one is negligible?

**Using [propagation time](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#propagation-time)**:

$$
\begin{array}{rcl}
  PT & = & \displaystyle \frac{D}{PS} \\\\
  & = & \frac{1,000 \textsf{ km}}{(2*10^8) \textsf{ m/s}} \\\\
  & = & \frac{1,000,000,000 \textsf{ cm}}{200,000,000 \textsf{ m/s}} \\\\
  & = & \bf 5 \sf\ ms
\end{array}
$$

**Using [transmission time](https://github.com/hendraanggrian/IIT-CS455/blob/main/signals.md#transmission-time)**:

$$
\begin{array}{rcl}
  TT & = & \displaystyle \frac{MS}{B} \\\\
  & = & \frac{2.5 \textsf{ Mb} \times 8}{5 \textsf{ Mbps}} \\\\
  & = & \frac{20 \textsf{ Mb}}{5 \textsf{ Mbps}} \\\\
  & = & \bf 4 \sf\ s
\end{array}
$$

Therefore, **propagation time is negligible**.

## Problem 12

> The data input stream is `01001011`. Draw a figure presenting the output from:
>
> 1. AMI encoder
> 2. Differential Manchester encoder

![](https://github.com/hendraanggrian/IIT-CS455/raw/assets/lines/hw1_digital.png)

[View full graph](https://github.com/hendraanggrian/IIT-CS455/blob/main/lines/hw1.drawio)
