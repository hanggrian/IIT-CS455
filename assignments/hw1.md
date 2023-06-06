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

**Using [digital signals](https://github.com/hendraanggrian/IIT-CS455/blob/main/signal.md#digital-signals)**:

$$
\begin{array}{rcl}
  L & = & B^2 \\\\
  & = & 4^2 \\\\
  & = & \bf 16 \sf \ levels
\end{array}
$$

Represented as:

| # | Binary | Decimal |
| ---: | --- | --- |
| 1 | `0000` | 0 |
| 2 | `0001` | 1 |
| 3 | `0010` | 2 |
| 4 | `0011` | 3 |
| 5 | `0100` | 4 |
| 6 | `0101` | 5 |
| 7 | `0110` | 6 |
| 8 | `0111` | 7 |
| 9 | `1000` | 8 |
| 10 | `1001` | 9 |
| 11 | `1010` | 10 |
| 12 | `1011` | 11 |
| 13 | `1100` | 12 |
| 14 | `1101` | 13 |
| 15 | `1110` | 14 |
| 16 | `1111` | 15 |

## Problem 3

> A computer monitor has the resolution of $1200 \times 1000$ pixels. If each
  pixel uses $1026$ colors, how many bits are needed to send the complete
  contents of a screen?

**Using [bit rate](https://github.com/hendraanggrian/IIT-CS455/blob/main/signal.md#bit-rate)**:

$$
\begin{array}{rcl}
  B & = & F . W . H . P \\\\
  & = & 1,200 \times 1,000 \times \log_{2}{1,026} \\\\
  & = & \bf 12,000,000,000 \sf \ bits
\end{array}
$$

## Problem 4

> Consider a sine wave $s(t)$ with the following parameters: period $T=0.1$
  sec., amplitude $A=10$ V and phase $\alpha=\pi/2$. Find an analytical formula
  for the superposition of two such sine waves $f(t) = s(t) + s(t)$ and draw its
  time and frequency domain plots ($t$ denotes time).



## Problem 5

> What are the disadvantages of the baseband transmission of a digital signal?



## Problem 6

> Explain why the original *Shannon* capacity formula can be simplified to
>
> $$
    C = B \frac{SNR_{dB}}{3}
  $$



## Problem 7

> A certain signal travels from source $A$ via points $B$ and $C$ to
  destination $D$. Between the points $A$ and $B$ the signal is amplified
  by $10$ dB. The points $B$ and $C$ are $10$ km apart. They are connected with
  a cable whose loss is $0.5$ dB/km. Between the points $C$ and $D$ the signal
  is amplified by $15$ dB. The power of the signal at the source $A$ is $1$ mW.
  What is the power of the signal at the destination $D$?



## Problem 8

> Define a DC component and its effect on digital transmission.



## Problem 9

> What is the role of a header added to a data unit in the OSI network model?



## Problem 10

> What is the difference between a logical address and a physical address?



## Problem 11

> What is the total delay for a file of $2.5$ million bytes that is being sent
  over a link with a router having queuing time of $2$ microseconds and
  processing time of $1$ microsecond. The length of the link is $1000$ km. The
  speed of the signal is $2 \times 108$ m/s. The link has a bandwidth of $5$
  Mbps. Which component of this delay is dominant? Which one is negligible?



## Problem 12

> The data input stream is `01001011`. Draw a figure presenting the output from:
>
> 1. AMI encoder
> 2. differential Manchester encoder


