# SAP_Control-sequencer
Table of contents:
Project overview
Features
Key Components
Design Process
Final circuit
Compiler
Behavioral Analysis
Video Tutorials
Limitations
Future Improvements
Conclusion

Project overview:
This project modifies the SAP-1 microprocessor in Logisim-evolution by adding an automatic control sequencer for instruction cycles, a bootloader FSM for ROM-to-RAM loading, and an enhanced ALU supporting addition, subtraction, and 4x4-bit multiplication, improving automation and computational capability.

Features:
This project implements a modified version of the SAP-1 microprocessor architecture using Logisim-evolution. It features an automatic control sequencer that manages the instruction fetch, decode, execute, and debug cycles autonomously, removing manual intervention. The design incorporates a bootloader FSM that automates the transfer of programs from ROM to RAM during startup, enabling seamless system initialization.

The architecture includes essential components such as a program counter, memory address register, instruction register, general purpose registers, and a 16×8 RAM for storing data and instructions. The arithmetic logic unit (ALU) is enhanced to support addition, subtraction, and a 4-bit by 4-bit multiplication operation, broadening the processing capabilities of the processor.

Control logic combines timing signals from a state counter and decoded opcodes to precisely manage data flow and instruction execution. The overall design allows for structured, automated program execution verified through behavioral analysis using assembly instruction compilation and output validation.

Though limited by a minimal instruction set and small memory size, this project lays a strong foundation for further development in microprocessor design, offering opportunities for enhanced functionality, expanded memory, improved arithmetic units, and advanced control techniques. It serves as an educational platform for learning digital system fundamentals and processor automation.


Here are the key components of your Modified SAP Processor project:

1. Program Counter: Holds and increments the address of the next instruction to be fetched.  
2. Memory Address Register (MAR): Holds the memory address received from the program counter for RAM access.  
3. RAM (16×8): Temporary memory with 16 locations, each storing 8 bits, for instructions and data.  
4. Instruction Register (IR): Stores the fetched 8-bit instruction, splitting it into opcode (upper 4 bits) and operand (lower 4 bits).  
5. Automatic Control Sequencer: Generates control words to manage data flow and timing for fetch, decode, execute, and debug cycles autonomously.  
6. Bootloader Unit: Transfers programs from ROM to RAM at system startup automatically.  
7. Accumulator: An 8-bit register storing intermediate results from arithmetic operations.  
8. Adder-Subtractor with Multiplication: Performs addition, subtraction, and 4-bit by 4-bit multiplication operations.  
9. B Register: Temporarily holds the second operand for ALU operations.  
10. Output Register: Holds the final processed output for display.  
11. Binary Display: An array of 8 LEDs displaying the output register’s content in binary form.

These components work together to form a functional, automated microprocessor architecture.
