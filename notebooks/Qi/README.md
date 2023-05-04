# ECE445_ChipDispenser
Note keeping for team 65 Chip Dispenser

# Lab Notebook

## Group meeting - 01/31

### Today's Objective
To delve deeper into the functionality of our chip storage system and to brainstorm other potential projects that could leverage similar technologies.

### Work Completed
We first focused on our chip storage system, discussing its two primary functions:
1. **Take out:** The system should be able to read component requests from the user terminal and dispense the requested chips.
2. **Store:** The system should be able to accept incoming chips, recognize them, and store them in their designated slots.

We identified text recognition as a potential challenge in this process, considering the cost implications of implementing a camera for this purpose.

In the spirit of innovation, we also brainstormed a few other potential projects that could make use of similar technologies. These include:
- **Dumpling Dispenser:** A machine that prepares and cooks dumplings upon the press of a button. Once cooked, a plate of ready-to-eat dumplings would be dispensed.
- **Vegetable Multi-shape Auto Chopper:** A machine capable of chopping vegetables into various desired shapes (slice, dice, shred, mince).
- **Curl Wire Straightening & Separating Machine:** A machine designed to straighten used wires and separate them based on length.

The visual aid and block diagram for this session was prepared by me to facilitate our discussion and illustrate our ideas better. I led the meeting, ensuring that we stayed on topic and reached our objectives for the day.

![Block Diagram](Block_Diagram_V1_(02_21).png)

### Reflections & Next Steps
In today's session, we not only refined our understanding of the chip storage system but also explored the potential for similar technologies in different applications. Our next step will be to explore solutions to the text recognition problem in our chip storage system and to further develop the other project ideas.

---

## Group meeting - 02/03

### Today's Objective
To formulate a comprehensive design plan for our "Chip Dispenser" project, aimed at streamlining the process of chip distribution in large ECE classes.

### Work Completed
As a team, we identified the need for an automated system that could handle the identification, storage, and dispensation of various types of chips based on user input. We proposed a system consisting of seven subsystems:
1. Chip delivery system
2. Chip identification system, which employs a barcode scanner
3. Chip storage system
4. Chip dispensing system, operated by an electric motor
5. Power supply system
6. User terminal for chip requests
7. Control system for managing the input and output processes

The proposed system, in essence, aims to alleviate the labor-intensive and time-consuming process of chip distribution in large classes, while also enhancing accuracy.

I took charge of the meeting to ensure that we stayed on track and worked effectively towards our goal of formulating a comprehensive design plan.

### Reflections & Next Steps
Today's work resulted in a solid framework for our design project. The next steps will involve further development of each subsystem, starting with detailed design and part selection. It's important to remember that our success criterion involves the system's ability to correctly identify, store, and dispense chips, as well as form a regular bar shape in the storage system. We will also need to ensure that the system can handle a user-input mixture of chips and output specified chips in the correct numbers.

---

## Project Proposal Record - 02/05/2023

## Problem
In ECE classes such as ECE210 and ECE385, distributing specific chips among a large number of students is a time-consuming and labor-intensive task. This is because the chips look similar, making them difficult to sort and distribute manually.

## Proposed Solution
Our team proposes a system that can automatically dispense the desired chips. Users can input their chip requirements, and the system will dispense the necessary chips, reducing manual labor and time.

## High-Level Requirements
- The system should accurately dispense the specified chips in response to user input, achieving at least 90% accuracy during 10 consecutive dispensing processes.
- The system should accurately display the number of remaining chips for all types, as well as the system's current state (input mode, output mode, or halt) with 98% accuracy.
- The battery capacity should be sufficient to sustain at least 20 full dispensing processes.

## Subsystem 1: Storage Subsystem
Holds specific chip types in tubes. Requirement: Securely accommodate tubes and enable easy placement.

## Subsystem 2: Dispensing Subsystem
Dispenses intended chips using a Chip Dispensing Module (CDM) and keeps track of remaining chips. Requirements: Accurate and smooth chip dispensing, accurate chip count.

## Subsystem 3: Power Subsystem
Responsible for supplying power to the entire system using 12V and 5V batteries. Requirements: Stable power supply during dispensing processes, sufficient battery capacity.

## Subsystem 4: User Terminal
A number pad connected to the control system for user input. Requirements: Accurate handling of user input, display of system's current state.

## Subsystem 5: Control Subsystem
Receives, processes, and sends signals to all other subsystems using a development board (Arduino). Requirement: Accurate calculation of remaining chips.

## Additional Subsystem 1: Chip Delivery System
Accepts a sequence of different chips and outputs them one by one for scanning. Requirements: Consistent chip delivery to the identification area, placement at a convenient angle, and maintaining a constant distance between chips.

## Additional Subsystem 2: Chip Identification Subsystem
Uses a barcode scanner to identify chip ID and communicates it to the controller. Requirements: Proper angle and scanning area for chip identification, 80% accuracy in chip identification, and correct placement in the storage subsystem.

## Tolerance Analysis
Challenges in ensuring chips remain in the correct position within tubes due to their non-flat contact surface. The chip-tube lifting height, platform surface texture, and solenoid pushing speed are key features to test for optimal results. Goals: have chips fall out of the tube upright, have the solenoid knock exactly one chip onto the holding wall, and prevent the second-to-last chip from bouncing after the last chip is gone.

## Power Consumption
The majority of power consumption comes from the solenoid and number pad, with other components operating at mW levels. A typical 12V alkaline battery should be sufficient to sustain 20 iterations of the dispensing process.

## Ethics and Safety
Original design intended to aid in dispensing electronic components in ECE faculties, aiming to reduce repetitive work. Not designed for illegal use. Safe 12V power supply but caution needed to prevent objects from entering tubes, avoid injuries from the narrowly spaced mechanical parts, and prevent harm to eyes from the laser.

---

# Design Document Update Record

## Original Submission Date: 02/20

### Introduction

#### Problem Statement
Initially, we identified a problem in the process of sorting and distributing electronic chips for ECE classes. It was noted that this process is currently done manually by staff, which is both tedious and time-consuming. 

#### Proposed Solution
The proposed solution was to develop an automated system that could dispense chips as per the user's request. The user would simply input the desired list of chips on a number pad, and the system would dispense the corresponding chips from storage. An additional chip input function was proposed to be added if time allowed, which would involve the system identifying different chips and sorting them into separate slots.

#### High-level Requirements
1. After the user selects the desired chips, the system should dispense the correct number of specified chips with at least 90% accuracy during 10 consecutive dispensing processes, provided the storage tubes are not empty. It was noted that the system should be able to dispense single chips.
2. The system should accurately inform the user about the remaining number of each type of chip with 98% accuracy. It should also update the user on the current state of the system (input mode, output mode, or halt) with 98% accuracy.
3. The battery capacity should be sufficient to sustain at least 20 dispensing processes with all system components functioning correctly.

This first part of the design document provided a clear problem statement and a detailed proposal for a solution, as well as specifying high-level requirements for the system. This was accompanied by relevant visual aids and tables for clarity.

### Subsystem Descriptions and Changes

#### Subsystem 1: Storage subsystem
The storage subsystem was designed to hold specific types of chips in individual slots. The storage system was also equipped with a chip counter that displays the number of remaining chips in each tube on a Liquid Crystal Display (LCD). A laser transmitter and receiver were proposed to detect when a chip was dispensed, with the count decreasing by one for each dispensed chip. A manual reset functionality was proposed for when a new tube of chips is placed. 

#### Subsystem 2: Dispensing subsystem
The dispensing subsystem was designed to dispense chips from storage, with a maximum of three types of chips managed by one Chip Dispensing Module (CDM). Each CDM was proposed to have a solenoid at the bottom that could push the bottom chip into a collection area.

#### Subsystem 3: Power subsystem
This subsystem was responsible for the power supply of the whole system. A 12V battery was proposed for the solenoid and a 5V battery for the rest of the system. A voltage regulator was proposed for the 5V battery to step down from 5V to 3.3V.

#### Subsystem 4: User terminal
The user terminal was proposed as a number pad that could input the number of chips required. The user would be able to use a switch to select from input mode and output mode.

#### Subsystem 5: Control subsystem
The control subsystem was proposed to receive, process, and send signals to all other subsystems. A development board (Arduino) was proposed as the microprocessor. This subsystem would handle data from each CDM to monitor remaining chips and send control signals to each solenoid to dispense chips and handle input from the number pad.

#### [Additional] Subsystem 1: Chip delivery system
This subsystem was proposed to accept a sequence (in-line) of different chips and output them one by one for the scanner to use by using a solenoid. This was an additional system that would only be built after the previous four subsystems had been implemented and tested thoroughly.

#### [Additional] Subsystem 2: Chip identification subsystem
This subsystem was proposed to have a barcode scanner to identify the chip and inform the controller of the chip ID. The scanning area would have at most one chip at a time, and the chip would need to be placed at a proper angle to the scanner. Like the Chip delivery system, this was an additional system that would only be built after the previous four subsystems had been implemented and tested thoroughly.

#### Cost Analysis and Schedule 

---

## Group meeting - 02/27 - 03/03
- Initiated order for parts required for prototyping.
- Conducted testing of laser parts in hand.
- Started the design process for the PCB.

---

## PCB Design Record - 03/08

Completed the design and schematics of a working Printed Circuit Board (PCB). The PCB has been designed to effectively connect and manage all the required components for the project. I was responsible for this critical task, using my knowledge of electrical circuits and design software to create a functional and efficient PCB layout.


---

## Group meeting - 03/06 - 03/10
- Placed the first round of orders with PCBway.
- Conducted the first teamwork evaluation.
- Finalized revisions for the machine shop.
- Commenced board assembly.
- Conducted testing of received parts (solenoids etc).

---

## Group meeting - 03/13 - 03/17
- Team took a break for Spring.

---

## Group meeting - 03/20 - 03/24
- Continued testing of received parts.
- Started work on the Dispensing, User terminal, Actuation, and Power systems.
- Conducted refinement of design as needed.

I began assembling the Power subsystem and User terminal, carefully following the designs and making sure all components were correctly connected. I also started working on the Chip Dispensing Module, ensuring its mechanical parts were assembled correctly for efficient operation.

---

## Group meeting - 03/27 - 03/31
- Placed the second round of orders with PCBway.
- Each team member submitted an individual progress report.
- Implemented and tested Dispensing, User Terminal, Storage, and Power subsystems.
- Continued refinement of design as needed.

---

## Group meeting - 04/03 - 04/07
- Completed the Dispensing subsystem and performed necessary tests.
- Conducted tests on the User Terminal.
- Finished Storage subsystem and conducted tests.
- Monitored the Power subsystem during operation.

This week, I conducted comprehensive tests on the solenoids and lasers, using a total of 360 chips for each test to ensure their reliability and performance. The results will inform our next steps in refining these components.

---

## Group meeting - 04/10 - 04/14
- Completed Team Contract Fulfillment.
- Integrated User Terminal with Storage and Dispensing subsystems.
- Conducted final assembly and tests of subsystems 1-5.
- Prepared for Mock Demo.

---

## Group meeting - 04/17 - 04/21
- Conducted Mock Demo.
- Prepared for Final Demo.