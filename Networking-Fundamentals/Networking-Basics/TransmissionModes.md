
# Data Transmission

## 1. What is a Transmission Mode?

A **Transmission Mode** defines the direction in which data can flow between two devices over a communication link.

A communication link is the physical or wireless medium that connects two devices. The transmission mode determines how data is exchanged through that link.

There are three types of transmission modes:

a. Simplex Mode
b. Half-Duplex Mode
c. Full-Duplex Mode

## 2. Types of Transmission Modes

### 2.1 Simplex Mode

In Simplex Mode, data can travel in only one direction. One device acts as the sender, while the other acts as the receiver.

- Data transmission is unidirectional.
- The receiving device cannot send data back through the same communication link.
- The direction of data transmission is fixed.

**Example:** Traditional television broadcasting, where a TV station transmits signals to televisions, but televisions do not send signals back to the broadcasting station.

**Direction:**

`Computer A ──────────> Computer B`

### 2.2 Half-Duplex Mode

In Half-Duplex Mode, data can travel in both directions, but not simultaneously.

Both devices can send and receive data. However, only one device can transmit data at a particular time. Devices must take turns communicating.

- Data transmission is bidirectional.
- Both devices can send and receive data.
- Simultaneous transmission in both directions is not possible.

**Example:** Walkie-Talkies, where one person speaks while the other listens. They must take turns communicating.

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

**Example:** Telephone communication, where both participants can speak and listen simultaneously.

**Direction:**

`Computer A <══════════> Computer B`

## 3. Quick Revision

- **Simplex:** Communication happens in only one direction.
- **Half-Duplex:** Communication happens in both directions, but one direction at a time.
- **Full-Duplex:** Communication happens in both directions simultaneously.

**Remember:**

Simplex = One-way communication

Half-Duplex = Two-way communication, one at a time

Full-Duplex = Two-way communication, simultaneously