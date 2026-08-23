STM32 FreeRTOS Multi-Tasking Project

Overview
--------
This repository contains an STM32 embedded systems project developed using
STM32CubeIDE, STM32 HAL, and FreeRTOS through the CMSIS-RTOS interface.

The project demonstrates four concurrent FreeRTOS tasks with different
priorities. Each task controls a GPIO output and periodically toggles its
assigned pin. The project also monitors the stack high-water mark of each
task using uxTaskGetStackHighWaterMark().

Features
--------
- FreeRTOS multitasking
- CMSIS-RTOS2 thread creation using osThreadNew()
- Four independent RTOS tasks
- Different task priorities
- STM32 HAL GPIO control
- Task delays using vTaskDelay()
- Task stack monitoring
- STM32 system clock configuration
- GPIO initialization
- FreeRTOS scheduler initialization

Task Configuration
------------------

Task 1 - myTask01
- Priority: osPriorityHigh2
- Stack size: 128 * 4
- GPIO: PA5
- Toggle delay: 5000 ms

Task 2 - myTask02
- Priority: osPriorityHigh1
- Stack size: 128 * 4
- GPIO: PA6
- 2000 ms HAL_GetTick()-based busy wait
- vTaskDelay(): 4000 ms

Task 3 - myTask03
- Priority: osPriorityNormal
- Stack size: 128 * 4
- GPIO: PA7
- Toggle delay: 3000 ms

Task 4 - myTask04
- Priority: osPriorityLow
- Stack size: 128 * 4
- GPIO: PB6
- Toggle delay: 2000 ms

Stack Monitoring
----------------
The project enables FreeRTOS stack monitoring using:
- configCHECK_FOR_STACK_OVERFLOW = 2
- INCLUDE_uxTaskGetStackHighWaterMark = 1

Stack high-water-mark values are stored in:
- Task1_Stack
- Task2_Stack
- Task3_Stack
- Task4_Stack

GPIO Configuration
------------------
The following GPIO pins are configured as push-pull outputs:
- PA5
- PA6
- PA7
- PB6

Program Flow
------------
1. HAL_Init() initializes the STM32 HAL.
2. SystemClock_Config() configures the HSI48 system clock.
3. MX_GPIO_Init() configures the GPIO pins.
4. osKernelInitialize() initializes the RTOS kernel.
5. Four tasks are created using osThreadNew().
6. osKernelStart() starts the FreeRTOS scheduler.
7. The scheduler manages tasks according to their priorities.
8. Each task toggles its GPIO and records its stack high-water mark.

Software and Tools
------------------
- STM32CubeIDE
- FreeRTOS
- CMSIS-RTOS2
- STM32 HAL
- Embedded C

Learning Outcomes
-----------------
- Real-Time Operating Systems
- FreeRTOS task creation and scheduling
- Task priorities and multitasking
- GPIO programming
- Task delays and timing
- Stack monitoring
- STM32 HAL
- CMSIS-RTOS APIs
- Embedded C programming
- STM32CubeIDE development

Repository Contents
-------------------
- main.c
- FreeRTOS/CMSIS-RTOS configuration files
- STM32CubeIDE project files
- STM32 HAL configuration files

Author
------
Prasad R Patil
Electronics and Communication Engineering (ECE)

GitHub Topics / Tags
--------------------
stm32
freertos
cmsis-rtos
stm32cubeide
embedded-systems
embedded-c
rtos
multitasking
task-scheduling
task-priority
stack-monitoring
stm32-hal
gpio
microcontroller
real-time-systems
electronics
