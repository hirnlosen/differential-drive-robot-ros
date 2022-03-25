# Differential Drive Robot

## Introduction

This project is based on the [project](https://github.com/AZhed/differential-drive-robot) made by [Andrei Jedancov](https://github.com/AZhed).   
The goal of the project is to transfer all software to ROS format.  

---

## Robot design

The differential drive robot includes the following devices and sensors:

- Single board computer **Raspberry Pi 4 8GB**
- Hardware platform **Arduino Mega 2560**
- Motor driver **TB6612FNG**
- 2 Hall-Effect Magnetic Encoders **AS5600**
- I2C Multiplexer **CJMCU-9548** for encoders

---

## Installation

Clone the repository into desired directory:

```bash
git clone https://github.com/hirnlosen/differential-drive-robot-ros.git
```

---

## Setup

Go to the project folder:

```bash
cd differential-drive-robot-ros
```

For remote control, it is necessary that the robot (Raspberry Pi) and the PC have a connection to the same Wi-Fi network. You need to find out the IP address of the Raspberry Pi, this can be done with the following command:

```bash
ifconfig
```

(section wlan0: inet \<IP-adress\>)

This IP address must be specified in the scripts **SocketServer.py** and **SocketClient.py** (variable HOST).

---

## Usage

Go to the project folder:

```bash
cd differential-drive-robot
```

Start the server on Raspberry Pi:

```bash
python3 scripts/SocketServer.py
```

Run the client on PC:

```bash
python3 scripts/SocketClient.py
```

---

## Robot control

After running server and client scripts you can control robot motion using the following keyboard keys on your PC:  
`w` - forward  
`x` - back  
`a` - left turn  
`d` - right turn  
`s` - stop moving  
`e` - increase the speed of rotation of the wheels  
`q` - reduce the speed of rotation of the wheels  
`Ctrl+c` - shutdown client and server

---

## Repository structure

> lib  
>> AS5600  
>> Encoder  
>> InitData  
>> Motor  
>> PID  
>> Position  
>> TwoWheeledRobot  
>> Velocity

>src
>> main.cp

> scripts
>> SocketServer.py  
>> SocketClient.py

All robot parameters and pin numbers are in the file lib/InitData/constants.h

Below is the connection of all elements

---

## Dependencies

### AS5600

This code uses a third party library AS5600 licensed under the [GPL-3.0 License](https://choosealicense.com/licenses/gpl-3.0/)

---

## Classes

<!-- ![](https://github.com/AZhed/2WRobot/img/classes.png) -->
<img src="img/classes.png" width="400">

---

## License

[MIT](https://choosealicense.com/licenses/mit/)
