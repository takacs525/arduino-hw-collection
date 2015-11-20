# HC-07 / RS232 TTL CSR Bluetooth wireless slave Module Board

## Images
![Image1](images/hc-07.jpg?raw=true)

## Features
* Core Modules using HC-07 slave modules, leads from the module interface including VCC, GND, TXD, RXD. 
* Reserve LED output pin status,Single Chip Microcomputer can be judged connected or not by the foot state,KEY pin is invalid for slave. 
* LED indicate show connection status, when it is flashing means non-connection, normally on mean it connect successfully 
* Backplane set anti-reverse diode with 3.3V LDO, input voltage: 3.6V - 6V 
* Unpaired current: about 30 MA, Paired: about 10 MA, input voltage can't exceed 7V, Interface level 3.3V 
* can be directly connected the various SCM (51, AVR, PIC, ARM, MSP430, etc.), the microcontroller can also be directly connected without MAX232
* Effective distance: 10M 
* After repaired,can used as full-duplex serial, supports 8 data bits, 1 stop bit, no parity communication format (8N1)
* Easy to connect this module with any standard Bluetooth device, just search and key "1234" passcode 
* Running in slave role: Pair with BT dongle and master module, Simply establish connection between device with Bluetooth function GPS, PC, PDA, PSP phone, Industrial control, etc.
* PCB SIZE: 35mm * 15mm * 2mm
* PRODUCT WEIGHT: 3.6 g

## Configuration

### A factory default parameters
Slave Baud Rate: 9600, N, 8,1. Pair: 1234; to require host mode, specify when the next single.

### Configuration steps

#### test communications

    Send: AT (return OK, around one second, issued annually)
    Return: OK

#### change the Bluetooth serial communication baud rate

    Send: AT + BAUD1
    Returns: OK1200
    Send: AT + BAUD2
    Returns: OK2400

Available settings:

    1 --------- 1200
    2 --------- 2400
    3 --------- 4800
    4 --------- 9600
    5 --------- 19200
    6 --------- 38400
    7 --------- 57 600
    8 --------- 115 200
    9 --------- 230 400
    A --------- 460 800
    B --------- 921 600
    C --------- 1 382 400

* Not recommended for more than 115200 baud rate, signal interference make the system unstable.
* Set with more than 115,200 machine is unavailable, use microcontroller programming at higher than 115 200 in order to use this baud rate and re-issued AT command set low baud rate
* AT command to set the baud rate, the next power to use without re-set, you can power down to save baud rate.

#### change the Bluetooth name
To set the current name, the Bluetooth name to be searched. 20 characters or less.

    Send: AT + NAMEname
    Returns: the OKname

Example: change the Bluetooth name to bill_gates

    Sending AT + NAMEbill_gates
    Return OKname

#### change the Bluetooth passkey
To set a passcode, 4 bytes, this command can be used from the machine or the host.

    Send: AT + PINxxxx
    Returns: the OKsetpin

The slave adapter or mobile phone pops up to enter the passkey window, then manually enter this parameter can be connected to the slave. Host with the master Bluetooth module with digital cameras, digital cameras from the machine, find the password of the camera pair, and then set up the White Bluetooth module, the master Bluetooth module can automatically connect the camera.

Example: change the Bluetooth PIN to 8888
 
    Sending AT + PIN8888
	Return OKsetpin
