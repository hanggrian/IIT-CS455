<!-- hotfix: KaTeX -->
<!-- https://github.com/yzane/vscode-markdown-pdf/issues/21/ -->
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<script type="text/x-mathjax-config">MathJax.Hub.Config({ tex2jax: { inlineMath: [['$', '$']] }, messageStyle: 'none' });</script>

# [Homework 2](https://github.com/hanggrian/IIT-CS455/blob/assets/assignments/hw2.pdf)

## Problem 1

> What is the carrier signal? Explain its role in the analog transmission.

A carrier signal is a high-frequency signal produced by the sending device. The
signal would then go through modulation, that is, modifying amplitude,
frequency, or phase.

## Problem 2

> Consider a low-pass channel with the carrier frequency of $15$ kHz. What is
  the BASK bit rate if $d=0.5$?

**Using [Bandwidth for ASK](https://github.com/hanggrian/IIT-CS455/blob/main/analog_transmission.md#bandwidth-for-ask)**:

$$
\begin{array}{rcl}
  B & = & (1+d).S \\\\
  & = & (1+0.5).15 \sf \ KHz \\\\
  & = & \bf 22.5 \sf \ KHz
\end{array}
$$

## Problem 3

> Calculate the baud rate for the given bit rate and type of modulation:
>
> - $3000$ bps, BFSK
> - $50$ kbps, BASK
> - $60$ kbps, 16-QAM
> - $9000$ bps, QPSK

Bit rate | Baud rate
--- | ---:
$3000$ bps, BFSK | $3,000 \textsf{ bps}\ /\ 1 = \bf 3,000 \sf \ bps$
$50$ kbps, BASK | $50 \textsf{ kbps}\ /\ 1 = \bf 50 \sf \ kbps$
$60$ kbps, 16-QAM | $60 \textsf{ kbps}\ /\ 4 = \bf 15 \sf \ kbps$
$9000$ bps, QPSK | $9,000 \textsf{ bps}\ /\ 2 = \bf 4,500 \sf \ bps$

## Problem 4

> The constellation diagram has two points whose coordinates are $(2,0)$
  and $(8,0)$. What modulation does this diagram present? What is the
  interpretation of these coordinates?

In constellation diagram, $X$-axis is related to in-phase career while $Y$-axis
is quadrature career. Because $X$ axis is moving $(2 \to 8)$ and $Y$ stays the
same $(0)$, it suggests that **BFSK modulation** is in use.

## Problem 5

> How is a channel related to a link?

In the context of multiplexing, many channels share one link. Channel refers to
the portion of a link that carries a transmission between a given
sender-receiver pair.

## Problem 6

> Why is a filter needed in the FDM demultiplexing process?

Filters are needed in demultiplexing FDM to decompose the multiplexed signals
into their constituent component signals, separating the input signals from
their carriers and passing them to the output lines.

## Problem 7

> We would like to digitize a certain analog signal using $5$ bits per sample.
  The lowest frequency of this signal is $100$ kHz and its bandwidth is $200$
  kHz. What is the bit rate?

**Using [Nyquist theorem](https://github.com/hanggrian/IIT-CS455/blob/main/digital_transmission.md#nyquist-theorem)**:

$$
\begin{array}{rcl}
  C & = & 2B . S \\\\
  & = & 2.(100+200) \textsf{ KHz} . 5 \\\\
  & = & 600 \textsf{ KHz} . 5 \\\\
  & = & \bf 3,000 \sf \ kbps
\end{array}
$$

## Problem 8

> Can packets in a datagram network arrive at their destination out of order? If
  so, why?

A packet in a datagram network is created independently even if a packet is part
of multipacket transmission. Therefore yes, they are unordered.

## Problem 9

> What are the basic differences between circuit switching and datagram
  switching?

| | Circuit switching | Datagram switching
--- | --- | ---
Type | Connection-oriented | Connection-less
Flow | Connection setup &rarr; Data transfer &rarr; Connection teardown | Carry header &rarr; Routing table &rarr; Forward packet
Efficiency | **Bad** &mdash; Resources are allocated for the entire duration of the connection. | **Better** &mdash; Resources are allocated only when there are packets to be transferred.
Delay | **Minimal** &mdash; Due to the time needed to create the connection, transfer data and disconnect the circuit. | **Significant** &mdash; Each packet may wait at a switch before it is forwarded.

## Problem 10

> Explain the function of a dial-up modem.

The function of a dial-up modem is to modulate and demodulate.

Function | Conversion
--- | ---
Modulate | Binary data &rarr; Bandpass analog signal
Demodulate | Modulated signal &rarr; Recovered binary data

## Problem 11

> The FHSS technique with $16$ different carrier frequencies is used to create a
  communication channel for a certain sender-receiver pair. The resulting
  expanded bandwidth is $B1$. We have to increase the number of the
  sender-receiver pairs from $1$ to $8$. What is the resulting expanded
  bandwidth $B2$?

**Using [FHSS](https://github.com/hanggrian/IIT-CS455/blob/main/bandwidth_utilization.md#fhss)**:

$$
\begin{array}{rcl}
  B_2 & = & B_1 . N \\\\
  & = & 16 \textsf{ carriers} . 8 \\\\
  & = & \bf 128 \sf \ carriers
\end{array}
$$

## Problem 12

> Explain why ADSL is asymmetric.

- Faster and inexpensive &mdash; Compared to a dial-up modem.
- Focus on what's important &mdash; Most users require download instead of
  upload speed.
