# Rubber Ducky

## First, Understand HID

**HID stands for Human Interface Device.**

HID is a standard communication protocol commonly used by USB devices such as keyboards, mice, and other input devices.

When a USB device follows the HID standard, a compatible computer or smartphone can recognize it as an input device and receive input from it.

**But here's the interesting part!**

A device such as an Arduino Pro Micro (ATmega32U4) can be programmed to behave like a USB keyboard. This means it can send predefined keystrokes to a connected system, just like a physical keyboard.

This is the basic concept behind a *Rubber Ducky-style HID device*.

<center>
<img src="https://github.com/user-attachments/assets/68085843-0332-4832-8780-928a3cbf9bd0" width=557></img>
</center>
<blockquote>
**Important:** HID functionality does not automatically bypass antivirus software. Security software may still detect or block suspicious activity. HID devices can, however, be misused to execute unwanted keyboard actions, which is why they should only be tested on systems you own or have permission to use.
</blockquote>

---

## What Will You Need?

To build this project, you will need:

1. **Arduino Pro Micro (ATmega32U4)**

   Make sure you choose a compatible board with USB HID support.



<hr>
<BR>

# Arduino IDE Setup & Configuration

This guide explains how to install Arduino IDE, configure SparkFun Pro Micro board support, connect your Arduino device, and upload a program.

---

## Step 1: Install Arduino IDE

Download and install Arduino IDE on your Windows system using the official installer.

**Download Arduino IDE (Windows 64-bit):**

[Download Arduino IDE 2.3.10](https://downloads.arduino.cc/arduino-ide/arduino-ide_2.3.10_Windows_64bit.exe)

After downloading, run the installer and complete the installation process.

---

## Step 2: Install SparkFun Board Dependencies

Before using your Pro Micro board, make sure the required board support package is installed.

### 2.1 Configure Board Manager URL

1. Open Arduino IDE.
2. Navigate to **File → Preferences**.
3. Locate **Additional Boards Manager URLs**.
4. Paste the following URL:

https://raw.githubusercontent.com/sparkfun/Arduino_Boards/main/IDE_Board_Manager/package_sparkfun_index.json


5. Click **OK** to save the changes.

### 2.2 Install SparkFun AVR Boards

1. Navigate to **Tools → Board → Boards Manager**.
2. Search for **SparkFun AVR Boards**.
3. Find the SparkFun AVR Boards package.
4. Click **Install**.

After installation, SparkFun board support will be available in Arduino IDE.

<!-- Replace with your actual screenshot -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/69091a26-bc79-4912-9573-8913f6712fa7" width="700" alt="Arduino Board Manager">
</p>
<p align="center"><em>Figure 1: SparkFun AVR Boards installation</em></p>

---

## Step 3: Connect Arduino to Your System

Connect your Arduino Pro Micro to your computer using a compatible USB cable.

- Your system should detect the connected board.
- Arduino IDE should display the available COM port.
- Make sure the USB cable supports data transfer, not just charging.

<!-- Replace with your actual screenshot -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/539fe4f6-20a6-4c8e-be4e-2221cf1a253b" width="700" alt="Arduino connected to computer">
</p>
<p align="center"><em>Figure 2: Arduino device connection</em></p>

---

## Step 4: Configure Arduino Board Settings

After connecting your Arduino, select the appropriate board and processor settings.

### Board Selection

Navigate to:

**Tools → Board → SparkFun AVR Boards → SparkFun Pro Micro**

### Port Selection

Navigate to:

**Tools → Port → COM5**

*Note: COM5 is an example. Select the COM port assigned to your Arduino.*

### Processor Selection

Navigate to:

**Tools → Processor → ATmega32U4 (5V, 16 MHz)**

*Note: Select the processor configuration according to your actual Pro Micro hardware.*

---

## Step 5: Write and Upload Your Arduino Program

After configuring the board settings, you can write your Arduino program in the IDE editor.

### 5.1 Verify Your Code

- Write or paste your Arduino sketch into the editor.
- Click the **Verify (✓)** button.
- Arduino IDE will compile your code and check for errors.

<!-- Replace with your actual screenshot -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/759a961f-1122-46e8-b536-08266bec9b6a" width="700" alt="Arduino IDE Verify button">
</p>
<p align="center"><em>Figure 3: Verifying the Arduino sketch</em></p>

### 5.2 Upload Your Code

After successful verification:

1. Click the **Upload (→)** button.
2. Wait while Arduino IDE compiles and uploads the program.
3. Check the IDE status message for successful upload.

<!-- Replace with your actual screenshot -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/c13841e8-7158-4409-b03d-6148a00e2df1" width="700" alt="Arduino IDE Upload button">
</p>
<p align="center"><em>Figure 4: Uploading the Arduino sketch</em></p>

### 5.3 Execution

Once the upload is successful, the Arduino board executes the uploaded program according to its instructions.

---

## Setup Completed!

Your Arduino IDE is now configured and ready for programming with the SparkFun Pro Micro board.

---

## Requirements

| Component | Description |
|---|---|
| Software | Arduino IDE 2.3.10 |
| Board Package | SparkFun AVR Boards |
| Hardware | Arduino Pro Micro |
| Microcontroller | ATmega32U4 |
| USB Connection | Data-capable USB cable |
| Operating System | Windows 64-bit |

---

## Project Structure

```text
Arduino-USB-HID-Project/
│
├── README.md
│
├── Images/
│   ├── board_manager.png
│   ├── arduino_connection.png
│   ├── verify_code.png
│   └── upload_code.png
│
└── Code/
    └── hello_world.ino
```

---

**Disclaimer:** This repository is intended for educational purposes and authorized USB HID testing only. Use USB HID devices responsibly and only on systems where you have permission.










<hr>


## How to Identify the Correct Voltage and Clock Frequency of Your Arduino Pro Micro

Before selecting your board configuration in Arduino IDE, identify the correct voltage and clock frequency supported by your Pro Micro.

Common configurations:
- **5V / 16MHz**
- **3.3V / 8MHz**

### Solution 1: Check the Solder Jumper

Inspect the solder jumper on the back of your Arduino Pro Micro.

Look for the voltage selection markings:
- `5V`
- `3.3V`

Check which selection pad is connected through the solder bridge.

This helps identify the board's voltage configuration.

<img width="751" height="313" alt="image" src="https://github.com/user-attachments/assets/23041df9-2bd2-4b24-8a10-317275ab2894" />


### Solution 2: Check Your Board Specifications

If the solder jumper is not visible or you cannot identify the selected configuration, check your board's product specifications.

Collect the following details:

| Specification | Details |
|---|---|
| Model Number | Your board's model number |
| Processor | ATmega32U4 |
| Clock Speed | 8MHz / 16MHz |
| Connectivity | USB, I2C, SPI, UART, GPIO |

After collecting these details, ask an AI chatbot such as **Gemini or ChatGPT** to help identify your board's voltage and clock configuration.

**My Recommendation:** I personally prefer using Gemini for this identification process.

**Important:** Verify the voltage using the manufacturer's specifications or hardware documentation. Processor speed alone does not confirm the operating voltage.

















