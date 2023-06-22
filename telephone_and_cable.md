# Telephone and cable

## Telephone network

A **local loop** is a twisted-pair cable that connects a subscriber to the
nearest local central office.

**Trunks** are transmission media that handle the communication between central
offices.

Switches are located in a switching office. A switch connects several local
loops or trunks and allows establishing a connection between different subscribers.

Traditional telephone lines carry frequencies between $300$ Hz and $3,300$ Hz.
The effective bandwidth of a telephone line being used for data transmission
is $2,400$ Hz, covering the range from $600$ Hz to $3,000$ Hz.

## Dial-up modems

The term **modem** is a word that refers to the two entities that make up the
devices: a signal modulator and a signal de-modulator.

| Entity | Role |
| --- | --- |
| Modulator | Creates a bandpass analog signal from binary data. |
| Demodulator | Recovers the binary data from the modulated signal. |

### V.32

32-QAM with a baud rate of $2,400$. Because only $4$ bits of each $5$-bit
pattern represent data, the resulting data rate is $4.2,400 = 9,600 \sf \ Kbps$.

### V.32BIS

128-QAM ($7$ bits).

$$2,400.6 = 14,400 \sf \ bps$$

## Digital subscriber line

The modulation technique that has become standard for *Asymmetric Digital
Subscriber Line (ADSL)* is called the **discrete multitone technique (DMT)**. It
combines QAM with FDM. An available bandwidth of $1,1$ MHz is divided into $256$
channels.

| Type | Channel |
| --- | --- |
| Voice | $0$ |
| Idle | $1 \to 5$ |
| Upstream data | $\underbrace{6 \to 30}_{25 \sf \ channels}$ |
| Downstream data | $\underbrace{31 \to 255}_{225 \sf \ channels}$ |
