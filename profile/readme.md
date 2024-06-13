
<a href="https://github.com/aethr-org"><img src="./logo.svg" alt="Logo" width="100"></a><br>

![License](https://img.shields.io/badge/license-NOT_DECIDED-red.svg?style=for-the-badge)
![Platform](https://img.shields.io/badge/license-NOT_DECIDED-red.svg?style=for-the-badge)


# AETHR
**The electric, radio-controlled, unmanned surveillance drone and it's control station project**


## Table of Contents
- [Overview](#overview)
- [Description](#description)
	- [Drone plane](#drone-plane)
		- [Flight control system](#flight-control-system)
		- [Surveillance system](#surveillance-system)
	- [Control station](#control-station)
- [Objectives](#objectives)
- [Problem Statement](#problem-statement)
- [Scope](#scope)
- [Requirements](#requirements)
	- [Communications](#communications)
	- [Flight Control System](#flight-control-system-1)
	- [Surveillance System](#surveillance-system-1)
	- [Control Station](#control-station-1)
- [Risks](#risks)
- [Deliverables](#deliverables)


## Overview
The AETHR is an advanced, electric, radio-controlled, unmanned surveillance drone plane and it's control system project. This drone is capable of flying a range of up to 200km with a single full battery charge, with a control radius of 100km from the control station. The drone features a fixed pilot camera at the very front of the plane and two dynamic, rotatable surveillance cameras for comprehensive aerial and ground monitoring from the top and the bottom of the plane. The main part of the drone, the flight control system, is responsible for the flying of the drone, the autopilot and GPS mechanisms, and incorporates monitoring functions that tracks both environmental conditions (air temperature, humidity, wind direction, and speed) and internal metrics (battery charge status, controllers' temperatures, flight data, speed, motor status, etc). Communication between the drone and the control station is secured through a custom encrypted radio protocol. This project encompasses the complete design, construction, and testing of both the drone and its control station.

[(to the top)](#aethr)


## Description
To dvelve deeper into the features of the project, it is split into 2 main parts:
- Drone plane.
- Control station.

### Drone plane
This drone will resemble the MQ-9 Reaper in form, optimized for aerodynamics and efficiency. It will be constructed from strong yet lightweight materials, including plastic, carbon fiber, and aluminum, ensuring durability and strength without compromising on weight. The drone will be powered by an internal battery pack capable of flying up to 200km on a single charge. A custom protocol will be used for all communications which will ensure that the communication between the drone and the control station is stable and secure and encrypted. The drone will have 2 main systems running in parallel which are:
- Flight control system.
- Surveillance system.

#### Flight control system
The flight control system is responsible for flying the drone. It includes communicating with the control station (at the 2.4GHz frequency), a front, static pilot camera, controlling the motors and wings, running the autopilot, and monitoring environmental and internal flight metrics:
- Air temperature and humidity.
- Wind direction and speed.
- Battery charge status and temperature.
- Controllers' temperatures.
- Flight data (speed, motor status, altitude, etc).

#### Surveillance system
The surveillance system allows to view and monitor everything above and below the drone using 2 dynamic, rotatable cameras (one on the top of the plane and the second on the bottom). Both cameras communicate to the control station at a separate frequency from the control station (5.8GHz) and can be controlled only by the control station. Each camera can be individually enabled or disabled via control commands using the control station to conserve the life of drone's battery.

[(to the top)](#aethr)

### Control station
The control station is a domain-specific controller deck that includes several parts to control the entirity of the drone:
- Flight controller.
	- Flight stick (for steering).
	- Thrust stick.
	- Monitoring keypad.
	- Pilot camera and drone's metrics monitor.
	- Autopilot keypad.
- Surveillance controller.
	- Bottom camera controller.
	- Top camera controller.
	- Split-view monitor for both cameras.

[(to the top)](#aethr)


## Objectives
- Design a robust and lightweight surveillance drone.
- Ensure that the drone can safely operate at temperatures from -30 up to 60 degrees Celsius.
- Ensure that the drone is sealed and protected from dust, small debree, and water particles.
- All inner electronics of the drone must be protected from water and inductive particles and elements.
- Design a control station for the drone.
- Integrate a secure communication system and protocol to protect against interference and interception.
- Develop the flight control system for the drone.
- Develop the surveillance system for the drone.
- Ensure the drone can cover a distance of up to 200km on a single full charge.
- Ensure the drone can operate and communicate with control station over a distance of up to 100km.
- Achieve successful test flights and system validation.

[(to the top)](#aethr)


## Problem Statement
Unmanned surveillance drones are increasingly essential for various applications, including environmental monitoring, security, and military operations. Current market solutions either lack the necessary range, durability, and advanced camera systems required for comprehensive surveillance or they are too expensive for most of the potential users. This project addresses these gaps by providing a durable, long-range drone equipped with versatile and energy-efficient systems for surveillance, control, monitoring, and payload management for an affordable price. For comparrison, here are a few drones that offer similar solutions to what this project features:
1. DJI Matrice 300 RTK
	- Range.
	The Matrice 300 RTK offers a maximum flight time of 55 minutes, which is significantly less than the 200km range of the AETHR.
	- Control Radius.
	The Matrice 300 RTK has a control range of up to 15km, whereas the AETHR aims to have a 100km control radius.
	- Cameras.
	While the Matrice 300 RTK can be equipped with various cameras, it typically does not include the dual dynamic, rotatable cameras for comprehensive monitoring above and below the drone like the AETHR.
	- Cost.
	The Matrice 300 RTK is priced at a premium, which can be prohibitive for many users.
2. AeroVironment RQ-20 Puma
	- Range.
	The Puma has a range of about 20km, far less than the 200km range of the AETHR.
	- Control Radius.
	The Puma's control radius is about 20km, significantly lower than the AETHR's 100km.
	- Cameras.
	The Puma is equipped with an electro-optical and infrared camera, but it lacks the dual dynamic, rotatable cameras of the AETHR.
	- Durability and Design.
	The Puma is designed for tactical use and is quite rugged, but it may not offer the same level of durability in diverse environmental conditions as the AETHR, which is engineered to operate from -30 to 60 degrees Celsius and is protected from dust and water particles.
	- Cost.
	The Puma is also priced for military and high-end commercial applications, making it less accessible to a broader range of users.

[(to the top)](#aethr)


## Scope
This project includes the following:
- Research.
- Design and development of the drone prototype and its control station.
- Testing of the drone prototype and its control station.
- Manuals.

This project excludes the following:
- Full-scale production
- Commercial deployment.

[(to the top)](#aethr)


## Requirements
### Communications
- Encrypted and secure communication between the drone and the control station.
- Integrates custom data-link protocol to communicate between the drone and the control station.
- Uses channel hopping to prevent interference and interception.

### Flight Control System
- Communicates at 2.4GHz radio frequency.
- Receives commands from the control station.
- Includes a pilot camera.
- Includes an autopilot with homing functionality and GPS.
- Monitors the following metrics:
	- Air temperature and humidity.
	- Wind direction and speed.
	- Battery charge status and temperature.
	- Controllers' temperatures.
	- Flight data (speed, motor status, altitude, etc).
- Implements battery preservation mechanisms.

### Surveillance System
- Communicates at 5.8GHz frequency.
- Integrates the top, arial surveillance camera.
- Integrates the bottom, ground surveillance camera.

### Control Station
- Incorporates a flight stick, thrust stick, and autopilot control keypad.
- Includes keypad for controlling monitoring of the drone.
- Includes a monitor for the pilot camera and drone's metrics.
- Incorporates Bottom camera controller.
- Incorporates Top camera controller.
- Includes split-view monitor for both surveillance cameras.

[(to the top)](#aethr)


## Risks
- Technical challenges in designing the plane:
	- Making the plane aerodynamic.
	- Modeling and aquiring parts and materials.
- Difficulties in developing the flying control system:
	- Basic sterring and controlling the motors and wings.
	- Autopilot, gyro, and GPS integration and development.
- Difficulties in developing the surveillance system:
	- Designing the probles for the cameras. 
	- Controlling the motors and movement of the cameras.
- Delays in research, development, and testing phases.

[(to the top)](#aethr)


## Deliverables
- A working prototype of the drone including the flight control system and the surveillance system.
- Fully functional control station with documentation.
- Comprehensive test report and user manual.

[(to the top)](#aethr)
