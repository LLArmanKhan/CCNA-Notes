# Hardware vs Firmware vs Software

## 1. Hardware

**Hardware** refers to the physical components of a computer or electronic device that can be physically touched and felt.

Hardware forms the physical structure of a device and provides the components required to perform computing operations.

**Examples:**
- CPU (Processor)
- RAM
- Motherboard
- Hard Disk / SSD
- Keyboard
- Monitor
- Network Interface Card (NIC)

**Important Characteristics:**

- Hardware consists of physical components.
- Once manufactured, the physical structure and design of a hardware component generally cannot be changed through normal software operations.
- However, hardware components can be replaced, upgraded, repaired or modified.

**Example:**

Consider a laptop with 4 GB RAM. We can replace the existing RAM module with an 8 GB RAM module, provided the laptop supports it.

Similarly, we can replace an HDD with an SSD to improve storage performance.

**Important:** Upgrading or replacing a hardware component is different from changing the physical design of the existing component.

---

## 2. Firmware

**Firmware** is a type of low-level software that provides instructions to hardware components on how to operate and perform their designated functions.

It acts as an interface between hardware and higher-level software, helping initialize, manage and control hardware operations.

Firmware is generally installed during the manufacturing process of an electronic device. However, in some cases, it can also be installed or programmed after manufacturing.

### 2.1 Why Do We Need Firmware?

When a hardware device is manufactured, it contains several electronic components, such as:

- Transistors
- MOSFETs (Metal-Oxide-Semiconductor Field-Effect Transistors)
- JFETs (Junction Field-Effect Transistors)
- Integrated Circuits (ICs)
- Controllers and other electronic components.

For example, a processor or an electronic chip contains millions or billions of transistors working together to perform different operations.

The hardware's circuit design and internal logic allow these components to work together electrically. However, programmable hardware also needs instructions to initialize, configure and control its operations.

This is where **Firmware** comes into the picture.

Firmware provides the necessary instructions to programmable hardware components and controllers so that they can perform their designated functions.

In simple words, firmware helps programmable hardware operate as intended by providing the instructions required to manage its operations.

### 2.2 Where is Firmware Stored?

Firmware is generally stored in non-volatile memory associated with the hardware device.

This memory may be integrated into the hardware chip or provided as a separate memory component.

Common types of memory used to store firmware include:

- ROM (Read-Only Memory)
- EEPROM (Electrically Erasable Programmable Read-Only Memory)
- Flash Memory

Non-volatile memory retains its stored information even when the power is turned off.

**Important Points:**

- Firmware is generally stored in the hardware's associated memory.
- This memory is generally not directly accessible to ordinary users.
- In some devices, users or administrators can access firmware settings or update firmware through dedicated interfaces.
- Firmware can often be updated or reprogrammed without replacing the physical hardware.

### 2.3 Important Characteristics of Firmware

- Firmware is a type of low-level software.
- It is closely associated with hardware.
- It provides instructions for initializing and controlling hardware operations.
- It is generally stored in non-volatile memory.
- It is generally installed during the manufacturing process, although it can also be programmed afterwards.
- Firmware is generally not directly accessible to ordinary users.
- Firmware can often be updated without replacing the physical hardware.
- Incorrect firmware updates or improper firmware erasure can cause a device to malfunction or become unable to boot.

**Important:** Many programmable digital electronic devices rely on firmware for their proper functioning. However, not every electronic component requires firmware. Simple components such as resistors, capacitors and basic electrical switches can operate without firmware.

### 2.4 Real-World Example: Smartphone

A smartphone contains multiple hardware components and controllers. Different firmware components help these hardware subsystems perform their designated operations.

Some examples include:

1. **Battery Management System:** The firmware of the Battery Management System helps monitor battery conditions, manage charging and control battery-related operations.

2. **Wi-Fi Controller:** The Wi-Fi controller firmware helps manage wireless communication and the operation of the Wi-Fi hardware.

3. **Camera Subsystem:** The camera subsystem firmware helps control camera hardware operations, sensor communication and image capture.

4. **Touch Controller:** The touch controller firmware helps process touch inputs and communicate them to the device's operating system.

5. **Power Management:** The firmware associated with power management helps manage power-related operations and hardware initialization.

A smartphone therefore uses multiple firmware components across different hardware subsystems to perform its operations.

**Note:** These firmware components may be part of integrated controllers or larger firmware packages. Every hardware component does not necessarily have independent firmware.

### 2.5 Understanding Firmware Through the Smartphone Boot Process

Consider purchasing a brand-new smartphone.

When we press the power button, several operations take place before the operating system becomes ready.

**Boot Process:**

1. **Power Button Pressed:** The power management circuitry detects the power-on request.

2. **Power Management:** The Power Management IC (PMIC) helps provide and sequence power to different hardware components.

3. **Boot ROM Execution:** The processor executes its initial boot code, generally stored in an internal Boot ROM.

4. **Hardware Initialization:** The boot process initializes the necessary hardware components, such as the CPU, RAM and other system components.

5. **Bootloader Execution:** The bootloader prepares the system and loads the operating system.

6. **Operating System Starts:** The operating system initializes its services and drivers, making the smartphone ready for use.

**Important:** The boot process involves firmware, bootloader code and operating system software working together.

Firmware plays an important role in initializing the hardware and preparing the device for the operating system.

### 2.6 Firmware in Daily Smartphone Usage

Firmware does not work only during the boot process. It also helps manage hardware operations while the device is being used.

Consider a smartphone that has been configured and is being used regularly.

Different firmware components help manage different hardware operations.

**Examples:**

1. **Battery Charging:** When we connect the smartphone to a charger, the firmware of the Battery Management System helps monitor battery conditions, regulate charging and manage battery-related operations.

2. **Camera:** When we open the camera and capture a photograph, the camera subsystem firmware helps manage communication with the camera sensor and control camera-related hardware operations.

3. **Wi-Fi:** When we turn on Wi-Fi, the Wi-Fi controller firmware helps manage wireless communication and the operation of the Wi-Fi hardware.

4. **Touchscreen:** When we touch or scroll on the smartphone screen, the touch controller firmware helps process the touch inputs and communicates the detected input to the operating system.

These examples demonstrate how different firmware components help different hardware subsystems perform their intended functions.

### 2.7 Can We Update Firmware?

Yes. Modern electronic devices support firmware updates.

Generally, firmware is installed during the manufacturing process. However, manufacturers can release firmware updates after the device has been manufactured.

Firmware updates modify the instructions stored in the device's non-volatile memory without necessarily changing the physical hardware.

**Why Do Manufacturers Release Firmware Updates?**

- To fix hardware-related bugs.
- To improve device stability.
- To improve hardware compatibility.
- To fix security vulnerabilities.
- To improve device performance.

**Examples:**

- BIOS/UEFI updates on computers.
- Router firmware updates.
- Smartphone firmware updates.
- SSD firmware updates.

**Important Points:**

- Firmware can often be updated without replacing the hardware.
- Firmware generally cannot be modified like ordinary application software.
- Some firmware updates require special tools or manufacturer-provided utilities.
- Incorrect firmware updates or improper erasure can cause a device to malfunction or become unable to boot.
- Generally all Digital Electronic Devices need a Firmware

---

## 3. Software

**Software** refers to a collection of programs and instructions that tell a computer what tasks to perform.

Software runs on hardware and uses the underlying hardware resources to perform different operations.

Unlike hardware, software does not have a physical form that can be touched.

**Examples:**
- Operating Systems (Windows, Linux, Android)
- Web Browsers (Chrome, Firefox)
- Applications (MS Word, WhatsApp)
- Programming Software (VS Code)

### 3.1 Where is Software Stored?

Software is generally stored in the device's secondary storage, such as:

- HDD (Hard Disk Drive)
- SSD (Solid State Drive)

When software needs to execute, the required instructions and data are loaded into RAM.

**Example:**

When we install Windows on a computer, its system files are stored on the SSD or HDD. When the computer starts, the necessary operating system components are loaded into RAM.

### 3.2 Types of Software Updates

Consider a smartphone. It can receive different types of updates:

1. **Application Update:** When an application such as WhatsApp receives an update through the Google Play Store, it is an application software update.

2. **Operating System Update:** When a smartphone receives a new Android version, it is an operating system update.

3. **Firmware Update:** When the manufacturer releases an update for the device's firmware, it updates the low-level instructions used to operate the relevant hardware components.

---

## 4. Hardware vs Firmware vs Software

| Feature | Hardware | Firmware | Software |
|---|---|---|---|
| Definition | Physical components | Low-level instructions for hardware | Programs and instructions for performing tasks |
| Physical Form | Physical | Non-physical | Non-physical |
| Storage | Physical components | Generally non-volatile memory | Generally HDD/SSD |
| Modification | Replace, repair or upgrade | Can often be updated or reprogrammed | Can be installed, updated or removed |
| Purpose | Provides physical resources | Initializes and controls hardware operations | Performs user and system tasks |
| Examples | CPU, RAM, SSD | BIOS/UEFI, router firmware | Windows, Chrome, WhatsApp |

---

## 5. Quick Revision

- **Hardware:** The physical components of a computer or electronic device that can be physically touched.
- **Firmware:** Low-level software that provides instructions to initialize and control hardware operations.
- **Software:** Programs and instructions that perform different tasks using hardware resources.

**Remember:**

Hardware = Physical components

Firmware = Hardware-level instructions

Software = Programs and applications

**Important Concept:**

Firmware is technically a type of software, but all software is not firmware.

---

## 6. References

**Video:** Hardware vs Firmware vs Software

**Channel:** Technical Guftugu

**Link:** https://youtu.be/a3w5a3rys80?si=vG7_qdSxbOGdGddC 