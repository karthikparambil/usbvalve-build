# **USBValve (Personal Build)**

This repository serves as a detailed documentation of my personal build of **USBValve**, an incredible open-source hardware project originally designed and created by [Cesare Pizzi (cecio)](https://github.com/cecio). Building this device has been a fantastic way to learn more about hardware security, the inner workings of USB protocols, and the practical application of microcontrollers in defensive tooling.

## **What is USBValve?**

USBValve is a defensive hardware tool designed to inspect and analyze untrusted USB devices in a safe, isolated environment. It essentially acts as a "hardware firewall," an air-gapped bridge, between a potentially dangerous USB device and your valuable computer system.

When you plug an unknown or untrusted USB device into the USBValve, it does not passively pass the data through to the connected host computer. Instead, the microcontroller aggressively interrogates the connected device. It analyzes its fundamental descriptors, interfaces, vendor information, and behavior. This rigorous inspection process allows you to determine if a device is malicious before you expose your actual machine to potential harm.

For example, USBValve is highly effective at detecting a "BadUSB" or a "Rubber Ducky." These malicious tools are physically designed to look exactly like standard, harmless USB flash drives. However, once connected, they secretly register as human interface devices (HIDs), such as a keyboard. They then rapidly type pre-programmed, malicious payloads, executing commands faster than a human could react, potentially compromising the system, installing malware, or stealing credentials. USBValve catches this deception instantly.

It displays all this critical information—identifying the exact device class and capabilities—on the OLED screen, giving you a clear, immediate look at what the device *really* is, ensuring you don't inadvertently deploy an attack against yourself.

**Original Repository & Source Code:** [https://github.com/cecio/USBvalve](https://github.com/cecio/USBvalve)

## **🔧 Hardware Bill of Materials**

I built this device following the exact specifications and schematic provided in the original project. Here is a detailed breakdown of the components I sourced for the assembly:

| Component | Details & Notes |
| :---- | :---- |
| **Microcontroller** | **Raspberry Pi Pico**  |
| **Display** | **0.96" OLED I2C Display**  |
| **USB Type-A Female** | **serves output** |

## **📸 Build Gallery**

*Note: This section will be updated with photos of my soldering process, internal wiring, and the final assembled unit.*

\<\!--

INSTRUCTIONS FOR USER:

Upload your high-quality images to your GitHub repository (e.g., inside a folder named 'img').

Then, uncomment the lines below and change the filenames to match your specific image paths.

\--\>

\<\!--

### **Internal Wiring**

*A look at the connections between the Pico, the USB port, and the OLED screen. Pay close attention to the D+ and D- lines.*

### **Final Assembly**

*The fully assembled device running a scan, showing a clear pass or fail reading.*

\--\>

## **⚡ Firmware & Installation**

I utilized the official pre-compiled firmware provided by the original creator, which makes the setup process incredibly straightforward. To replicate this build and flash your own Raspberry Pi Pico, follow these steps:

1. **Download Firmware:** Go to the [original USBValve releases page](https://www.google.com/search?q=https://github.com/cecio/USBvalve/releases) and download the latest .uf2 file. Ensure you are downloading the correct version for your specific Pico model.  
2. **Enter Bootloader Mode:** Hold down the BOOTSEL button on your Raspberry Pi Pico. While keeping the button held down, plug the Pico into your computer via a high-quality micro-USB cable.  
3. **Flash the Device:** The Pico will mount on your computer as a standard mass storage device named RPI-RP2. Simply drag and drop the downloaded .uf2 file onto this drive. The device will automatically reboot, flash the code, and the OLED screen should light up with the USBValve logo, indicating a successful installation.

## **⚠️ Disclaimer**

This project is constructed strictly for **educational and defensive purposes**. The device is a diagnostic tool designed to help users inspect USB devices to ensure they are safe to use in controlled environments.

I am not the original author of the code or the hardware design; this repository serves only as a documentation of my personal assembly of the tool to demonstrate my soldering, hardware assembly skills, and understanding of USB security concepts. Please use this tool responsibly and only on devices you own or have permission to test.

## **📜 Credits**

All credit for the original concept, schematic, and software engineering goes to **Cesare Pizzi**.

* **Original Project:** [cecio/USBvalve](https://github.com/cecio/USBvalve)  
