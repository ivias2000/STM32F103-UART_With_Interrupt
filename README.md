# STM32F103-UART_With_Interrupt
This C code is a main program file targeting a microcontroller, likely an STM32 microcontroller, using USART communication to receive and process commands. It appears to be a basic state machine that reacts to specific characters received via USART1. 
focus on the interrupt-driven USART reception:
![Interrupt-example-ARM-cortex-M-microcontroller](https://github.com/ivias2000/STM32F103-UART_With_Interrupt/assets/125237611/21b817dd-dbfd-41d4-9c6f-2eb3bbedc997)

Includes:
The code includes various header files representing different libraries used in the project, including "main.h," "usart.h," and "gpio.h." These headers provide access to functions and constants required for the peripherals and libraries used in the application.

Global Variables:

state: An integer variable that represents the current state of the state machine.
rec: A character variable used to store the received character from USART1.
a, b, c: Integer variables used to store specific values based on the received commands.
Callback Function:
The code includes a callback function HAL_UART_RxCpltCallback, which is called whenever a character is received through USART1. Inside this function, the state machine is implemented using a switch statement. The state machine has three states (state = 0, state = 1, and state = 2) to handle different sequences of received characters.

Main Function:
The main function is the entry point of the program. It initializes the microcontroller's peripherals, specifically USART1 and GPIO pins, and then enters an infinite loop.

System Clock Configuration:
The SystemClock_Config function configures the system clock for the microcontroller.

USART Reception with Interrupt:
The most important part is the use of HAL_UART_Receive_IT in the main function. This function configures USART1 to receive data using interrupts. When a character is received, the interrupt is triggered, and the HAL_UART_RxCpltCallback function is called to handle the received data.

Infinite Loop:
The main loop in the main function remains empty and doesn't perform any additional tasks. The state machine logic and USART receive are handled in the interrupt callback function.

The interrupt-driven approach allows the microcontroller to continue its main loop without waiting for USART data. When data is received, the interrupt is triggered, and the callback function processes the data accordingly.
![Screenshot 2023-07-18 114246](https://github.com/ivias2000/STM32F103-UART_With_Interrupt/assets/125237611/efef6255-e90c-4195-9c90-fac0b6e0e8fc)

To use this code on GitHub, follow the steps mentioned earlier to create a new repository and upload this C code as the main program file. Additionally, you can include a README.md file in your repository to provide more information about the project and how to use the code.




