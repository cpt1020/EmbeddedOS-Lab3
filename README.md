# Analysis and Implementation of Embedded Operating Systems Lab 3

嵌入式作業系統分析與實作 Analysis and Implementation of Embedded Operating Systems [CSIE7618] @ NCKU 2022 Spring

## Development Environment

- Development Board
    - STM32F407G-DISC1
- Real-Time Operating System (RTOS)
    - [FreeRTOS v10.2.1](https://github.com/FreeRTOS/FreeRTOS/tree/V10.2.1)
- IDE
    - STM32CubeIDE

## Report

https://hackmd.io/@cpt/embeddedOS_lab3

## Introduction

- Students have to use serial peripheral interface (SPI) to read/write registers of LIS3DSH motion sensor
- Deferred interrupt handling is required in this lab
  - The ISR will give a semaphore to wake up the handling task
- If no interrupt is triggered, only the green LED blinks
- Once the development board is shaked, an interrupt will be triggered
  - The ISR should toggle the red LED
  - Just as aforementioned, the ISR will give a semaphore to wake up the handling task
- What the handling task does is to make the orange LED blink 5 times