# Data Transmission

## 1. What is a Transmission Mode?

A **Transmission Mode** defines the direction in which data can flow between two devices over a communication link.

A communication link is the physical or wireless medium that connects two devices. The transmission mode determines how data is exchanged through that link.

There are three types of transmission modes:

1. Simplex Mode
2. Half-Duplex Mode
3. Full-Duplex Mode

## 2. Types of Transmission Modes

### 2.1 Simplex Mode

In Simplex Mode, data can travel in only one direction. One device acts as the sender, while the other acts as the receiver.

- Data transmission is unidirectional.
- The receiving device cannot send data back through the same communication link.
- The direction of data transmission is fixed.

**Real-World Examples:**

1. **Television Broadcasting:** A broadcasting station transmits audio and video signals to televisions, but televisions do not send signals back through the same communication channel.
2. **Public Address (PA) System:** A microphone sends audio signals to loudspeakers. The loudspeakers receive and reproduce the audio but do not transmit audio back to the microphone.

**Direction:**

`Computer A ──────────> Computer B`

### 2.2 Half-Duplex Mode

In Half-Duplex Mode, data can travel in both directions, but not simultaneously.

Both devices can send and receive data. However, only one device can transmit data at a particular time. Devices must take turns communicating.

- Data transmission is bidirectional.
- Both devices can send and receive data.
- Simultaneous transmission in both directions is not possible.

**Real-World Examples:**

1. **Walkie-Talkies:** Both users can communicate with each other, but only one person can speak at a time. The other person must wait until the first person finishes transmitting.
2. **CB (Citizens Band) Radio:** Used for communication between people, particularly in vehicles and field operations. Users take turns transmitting messages over a shared radio channel.

**Direction:**

`Computer A ──────────> Computer B`

`Computer A <────────── Computer B`

*Note: Both directions are supported, but only one direction can be active at a time.*

### 2.3 Full-Duplex Mode

In Full-Duplex Mode, data can travel in both directions simultaneously.

Both devices can transmit and receive data at the same time without waiting for the other device to finish transmitting.

- Data transmission is bidirectional.
- Both devices can send and receive data.
- Simultaneous transmission in both directions is possible.

**Real-World Examples:**

1. **Telephone Communication:** During a telephone conversation, both participants can speak and listen simultaneously without waiting for the other person to finish speaking.
2. **Modern Switched Ethernet:** In a typical full-duplex Ethernet connection between a computer and a network switch, both devices can transmit and receive data simultaneously.

**Direction:**

`Computer A <══════════> Computer B`

## 3. Quick Revision

- **Simplex:** Communication happens in only one direction.
- **Half-Duplex:** Communication happens in both directions, but one direction at a time.
- **Full-Duplex:** Communication happens in both directions simultaneously.

**Remember:**

- Simplex = One-way communication
- Half-Duplex = Two-way communication, one at a time
- Full-Duplex = Two-way communication, simultaneously

## 4. References

**Video:** Data Transmission Mode - Simplex, Half Duplex and Full Duplex - Hindi/Urdu | CCNA Lectures

**Channel:** Technical Guftugu

**Link:** https://youtu.be/KPiKMobVcO0?si=qOEbIjYW3Vet2hkn