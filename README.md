# STM32F411 Bare-Metal Timer-Based LED Blink

## Overview

This project demonstrates LED blinking using the TIM2 peripheral of the STM32F411CEU6 microcontroller through bare-metal register programming without using HAL delay functions.

The project was developed to understand:

- STM32 clock configuration
- GPIO register programming
- Timer (TIM2) configuration
- Prescaler and Auto Reload Register calculations
- Polling-based timer operation
- Memory-mapped peripheral registers
- Embedded debugging using OpenOCD and GDB

---

## Hardware Used

- STM32F411CEU6 Black Pill Board
- ST-Link V2 Programmer/Debugger
- LED connected to PA5
- USB Cable

---

## Software Used

- STM32CubeIDE
- OpenOCD
- GDB
- Git
- GitHub

---

## Project Objective

Generate a 1-second delay using TIM2 and toggle an LED connected to PA5 without using HAL_Delay().

---

## Timer Configuration

### System Clock

HSI = 16 MHz

### Prescaler Calculation

PSC = 15999

Timer Frequency:

Timer Clock = 16 MHz / (15999 + 1)

Timer Clock = 1000 Hz

Timer Tick = 1 ms

### Auto Reload Register

ARR = 999

Overflow Time:

(999 + 1) × 1 ms = 1000 ms = 1 second

---

## Working Principle

1. Enable GPIOA clock.
2. Configure PA5 as output.
3. Enable TIM2 clock.
4. Configure PSC and ARR.
5. Generate update event using EGR.
6. Start TIM2 counter.
7. Poll UIF flag in TIM2 status register.
8. Clear UIF flag after overflow.
9. Toggle LED on PA5.

---

## Features

- Bare-metal register programming
- No HAL_Delay()
- Timer-based delay generation
- Polling-based timer overflow detection
- Direct peripheral register access
- OpenOCD + GDB debugging

---

## Debugging Performed

The project was debugged using:

- OpenOCD
- GDB
- ST-Link V2

Debugging activities included:

- Setting breakpoints
- Viewing CPU registers
- Monitoring Program Counter (PC)
- Inspecting TIM2 registers
- Single-step execution
- Memory inspection

---

## Learning Outcomes

Through this project, I learned:

- STM32 timer fundamentals
- PSC and ARR calculations
- Peripheral clock configuration
- Memory-mapped I/O
- Bare-metal firmware development
- OpenOCD workflow
- GDB debugging basics
- Git and GitHub project management

---

## Future Improvements

- Timer Interrupt-Based LED Blink
- Multiple LEDs with different frequencies
- PWM LED Brightness Control
- Servo Motor Control using PWM
- FreeRTOS Integration

---

## Author

Harisudhan

Embedded Systems Learning Journey
