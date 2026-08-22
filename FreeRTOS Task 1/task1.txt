STM32 FreeRTOS Multi-Tasking Project

Overview

This repository contains an STM32 embedded systems project developed
using STM32CubeIDE and FreeRTOS through the CMSIS-RTOS interface.

The project demonstrates the creation and execution of multiple
concurrent FreeRTOS tasks with different priorities. Each task controls
a GPIO output and periodically toggles an LED/output pin. The project
also monitors the FreeRTOS stack usage of each task using
uxTaskGetStackHighWaterMark().

The uploaded main.c is generated/configured using STM32 HAL and
CMSIS-RTOS interfaces.

Key Features

-   FreeRTOS-based multitasking
-   CMSIS-RTOS2 thread creation using osThreadNew()
-   Four independent tasks
-   Different task priorities
-   GPIO control using STM32 HAL
-   Periodic task execution using vTaskDelay()
-   Stack high-water-mark monitoring
-   System clock initialization using HSI48
-   STM32 GPIO initialization
-   FreeRTOS scheduler initialization and startup

Task Configuration

The project contains four FreeRTOS tasks:

1.  myTask01
    -   Priority: osPriorityHigh2
    -   Stack size: 128 * 4
    -   GPIO: PA5
    -   Toggle interval: 5 seconds
2.  myTask02
    -   Priority: osPriorityHigh1
    -   Stack size: 128 * 4
    -   GPIO: PA6
    -   Uses a 2-second HAL_GetTick()-based busy wait before toggling
    -   vTaskDelay(): 4 seconds
3.  myTask03
    -   Priority: osPriorityNormal
    -   Stack size: 128 * 4
    -   GPIO: PA7
    -   Toggle interval: 3 seconds
4.  myTask04
    -   Priority: osPriorityLow
    -   Stack size: 128 * 4
    -   GPIO: PB6
    -   Toggle interval: 2 seconds

Stack Monitoring

The project uses uxTaskGetStackHighWaterMark(NULL) inside every task to
record the remaining stack margin.

The measured values are stored in:

-   Task1_Stack
-   Task2_Stack
-   Task3_Stack
-   Task4_Stack

This provides a practical demonstration of monitoring FreeRTOS task
stack usage and helps in evaluating task memory requirements.

GPIO Configuration

The following GPIO pins are configured as push-pull outputs:

-   PA5
-   PA6
-   PA7
-   PB6

All four pins are initially reset and are toggled by the corresponding
FreeRTOS tasks.

Software and Tools

-   STM32CubeIDE
-   STM32 HAL
-   FreeRTOS
-   CMSIS-RTOS interface
-   C programming language

Program Flow

1.  HAL_Init() initializes the STM32 HAL.
2.  SystemClock_Config() configures the system clock.
3.  MX_GPIO_Init() configures the GPIO pins.
4.  osKernelInitialize() initializes the RTOS kernel.
5.  Four FreeRTOS tasks are created using osThreadNew().
6.  osKernelStart() starts the scheduler.
7.  The RTOS scheduler manages the four tasks according to their
    priorities.
8.  Each task toggles its assigned GPIO and records its stack high-water
    mark.

Learning Outcomes

This project provides hands-on experience with:

-   Real-Time Operating Systems
-   FreeRTOS task creation and scheduling
-   Task priorities
-   Preemptive multitasking concepts
-   CMSIS-RTOS2 APIs
-   GPIO programming using STM32 HAL
-   Task delays and timing
-   FreeRTOS stack monitoring
-   STM32CubeIDE project development
-   Embedded C programming

Repository Contents

Typical project files may include:

-   main.c
-   FreeRTOS/CMSIS-RTOS configuration files
-   STM32CubeIDE project configuration files
-   STM32 HAL configuration files
-   Generated build files

Author

Prasad R Patil

Electronics and Communication Engineering (ECE)

Keywords / GitHub Topics

stm32 freertos cmsis-rtos stm32cubeide embedded-systems embedded-c rtos
multitasking task-scheduling stm32-hal gpio microcontroller
real-time-systems task-priority stack-monitoring electronics
