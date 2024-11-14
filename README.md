**Overview**
This project is a CAN Bus Display System designed to interface an Arduino Mega, a RA8875 Driver Board, a TFT LCD screen, and a CAN Bus network. The goal of the project is to display critical vehicle data, including RPM, gear, engine temperature, and more, on a real-time graphical display. The system uses a CAN Bus for communication between various components like the ECU, PDM, and sensors.

**Key Features:**
Arduino Mega: Acts as the central microcontroller.
RA8875 Driver Board: Interfaces with the TFT LCD for high-quality display rendering.
TFT LCD Screen: Displays vehicle data in real-time with a user-friendly layout.
CAN Bus: Facilitates communication between the ECU, PDM, sensors, and display system.
Modular design: Expandable to include additional data points or sensors as needed.

**Components**
This EagleCAD project includes the following major components:

Arduino Mega: A microcontroller used to process CAN messages and control the TFT display.
RA8875 Driver Board: Handles the graphical output to the TFT LCD screen.
TFT LCD Screen: A 5" display (800x480px) used to show data such as RPM, temperature, gear, and other vehicle metrics.
CAN Bus Transceivers: MCP2551 or SN65VD230 transceivers, used to interface the microcontroller with the CAN Bus network.
Power Distribution Module (PDM) and ECU: The source of vehicle data communicated over CAN, including engine parameters, sensor data, and operational status.
Sensors: Vehicle sensors (e.g., engine temperature, RPM, etc.) providing data over the CAN network.
Schematic Description
The schematic for this project outlines the connections between the Arduino Mega, RA8875 Driver Board, TFT LCD, and the CAN Bus network.

**Key Connections:**
Arduino Mega to RA8875 Driver Board:

The Arduino Mega communicates with the RA8875 Driver Board via SPI (Serial Peripheral Interface) to control the display.
Control signals (e.g., Reset, Chip Select) are used to interface with the RA8875.
The RA8875 is responsible for driving the TFT LCD screen and rendering the graphical interface.
Arduino Mega to CAN Bus:

The Arduino Mega uses a CAN Bus Shield or transceiver (like the MCP2551) to connect to the CAN Bus.
The CAN bus is used for communication between the Arduino, the ECU, PDM, and other sensors, sending and receiving critical vehicle data.
TFT LCD to RA8875:

The TFT LCD is controlled by the RA8875 driver board.
The RA8875 interprets commands from the Arduino and displays relevant data in real-time.
CAN Bus Communication:

The CAN Bus is used to receive data from the ECU and PDM and send it to the Arduino for processing.
The Arduino Mega listens for CAN messages containing sensor data and updates the display accordingly.
Software/Firmware
The project firmware is written using Arduino IDE. It handles the following functions:

CAN Bus Communication: Receiving and sending CAN messages between the Arduino Mega and CAN network.
Data Parsing: Extracting critical data from the CAN messages (e.g., RPM, temperature, gear).
Display Control: Drawing and updating the graphical data on the TFT LCD screen.
Indicator Logic: Managing visual cues such as shift lights, temperature warnings, and other alerts.

**Libraries Used:**
RA8875: Library to control the RA8875 driver board and display graphical content on the TFT LCD.
MCP_CAN: Library to interface with the MCP2551 CAN Bus transceiver.
CAN Bus Library: For setting up CAN communication, including message filtering and error handling.

**Pinout Overview:**
Arduino Mega to RA8875 Driver Board:
SCK (Clock) - Pin 52
MISO (Master In Slave Out) - Pin 50
MOSI (Master Out Slave In) - Pin 51
CS (Chip Select) - Pin 10
RESET - Pin 9
Arduino Mega to CAN Bus Transceiver (MCP2551):
CAN_H - CAN High
CAN_L - CAN Low
RX (CAN receive) - Pin 7
TX (CAN transmit) - Pin 8
Future Improvements and Expansion
User Customization: Allow the driver to choose which data to display (e.g., switch between RPM and fuel pressure).
Enhanced Display Features: Include more graphical elements, such as gauges, for a more intuitive user interface.
Data Logging: Add SD card support for logging vehicle data for analysis after the race.
Connectivity: Potentially expand to include wireless communication for remote monitoring or tuning.

**Hardware Setup:**
Connect the RA8875 Driver Board to the Arduino Mega using the SPI interface.
Connect the CAN Bus to the Arduino Mega using a CAN Bus Shield or transceiver.
Attach the TFT LCD to the RA8875 Driver Board.

**Software Setup:**
Download the necessary libraries from the Arduino Library Manager.
Compile and upload the firmware to the Arduino Mega.
Power on the system, and the TFT LCD should display the vehicle data in real-time.
