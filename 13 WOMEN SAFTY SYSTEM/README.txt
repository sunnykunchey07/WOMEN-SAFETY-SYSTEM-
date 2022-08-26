Technical Specifications: 

Supply voltage: 3.4V – 4.5V
Power saving mode: Sleep Mode power consumption=.5mA
Frequency bands: SIM900A Dual-band: EGSM900, DCS1800.
Operating Temperature: -30ºC to +80ºC
Supports MIC and Audio Input
Speaker Input
UART interface support
Firmware upgrade by debug port
Communication: AT Commands
We have previously interfaced GSM with Arduino and build many projects using the GSM module including the accident alert system.

Connection Diagram
Women Safety system with GPS Tracking & Alerts can be subdivided into two sections such as Transmitter and Receiver section. The circuit diagrams for each section is described as follows:

Transmitter Section:  

In the RF Transmitter part, there will be an SOS button along with a 433 MHz RF transmitter, which will transmit the data to the receiver part wirelessly. The purpose of making two individual parts here is, to minimize the size of the transmitting module so that it can be worn as a wrist band.

Receiver Section: 

In the RF Receiver section, the data transmitted from the wrist band (Transmitter part) is received by the device having a 433 MHz RF receiver. The RF receiver sends this information to Arduino through the digital pin. Arduino Nano then receives the signal and processes it using the program which is flashed into it. When the victim presses the SOS button in the transmitter part, a HIGH signal is generated and passes to the Arduino side, and then Arduino sends a signal to SIM900 modem, to send an SMS to Registered user along with the GPS coordinate which has already been stored in the Microcontroller by the help of NEO6M GPS module. The circuit diagram of the Receiver side is shown as below:

Programming of Arduino
After successful completion of the Hardware connections, now it’s time for programming the Arduino Nano. The stepwise explanation of the code is given below.

Start the code by including all the required library files in the code like TinyGPS++.h for NEO6M GPS board, SoftwareSerial.h for defining the Software serial pins.