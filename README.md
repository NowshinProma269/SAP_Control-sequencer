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

Design Process:
 General Purpose Register:
<img width="1227" height="546" alt="vlsi1" src="https://github.com/user-attachments/assets/528dac01-a244-406a-a861-083a511f8f07" />

 Decoder:
<img width="775" height="521" alt="vlsi2" src="https://github.com/user-attachments/assets/f487f584-bdd7-4107-9a19-7ac359f891a0" />

 SRAM cell:
<img width="494" height="215" alt="vlsi3" src="https://github.com/user-attachments/assets/e6391207-74db-4d85-8fae-c1fe5bcd27bd" />

SRAM:
<img width="656" height="813" alt="vlsi4" src="https://github.com/user-attachments/assets/23e02093-e740-47ef-99ee-0893705ff025" />

 Instruction Register:
<img width="630" height="178" alt="vlsi5" src="https://github.com/user-attachments/assets/bd7b3e4d-ff6b-43e7-a845-d5c0e132bbd9" />

 Program Counter:
 <img width="499" height="160" alt="vlsi7" src="https://github.com/user-attachments/assets/bb4c801c-a5ec-437a-bcac-e560427b619f" />

 Control unit:
The control unit orchestrates CPU operations by generating timing and control signals for the fetch, decode, execute, and debug cycles. The state counter, built from cascaded flip-flops, produces sequential timing signals that coordinate each instruction phase. The opcode decoder interprets the 4-bit opcode from the instruction register, activating specific instruction signals like LDA, ADD, MUL, and HLT. Control logic combines these timing and opcode signals through logic gates to manage data flow, register loading, arithmetic operations including multiplication, memory writing, and debugging, ensuring precise execution sequencing.

 State Counter:
<img width="742" height="451" alt="vlsi6" src="https://github.com/user-attachments/assets/b04cf543-0df3-40c7-a2b2-bfb04295fe6c" />
 Opcode Decoder:
<img width="585" height="226" alt="vlsi8" src="https://github.com/user-attachments/assets/4b1b60b6-3d3c-416b-93c0-5c78b4bf617d" />
Control Logic:
<img width="920" height="617" alt="vlsi9" src="https://github.com/user-attachments/assets/e1a19dc6-e3ef-40f1-9558-167045f3e20d" />

Bootloader Control Logic:
The bootloader control logic uses a finite state machine (FSM) with JK flip-flops and combinational gates to automate the boot process—from system reset to loading programs from ROM to RAM and managing instruction cycles. It generates key control signals for enabling the memory address register, RAM writing, and execution control, supported by a Control ROM/Table Memory that issues microinstructions for timing and control sequencing. This setup enables autonomous and reliable program loading and execution without manual intervention.
<img width="539" height="437" alt="vlsi10" src="https://github.com/user-attachments/assets/e693a118-5cc1-45db-affe-d6e57cefd612" />

ALU:
The Arithmetic Logic Unit (ALU) performs addition and subtraction via an 8-bit ripple carry adder using cascaded full adders, with XOR gates for subtraction via 2’s complement. The ALU output is controlled through tri-state buffers. The multiplication circuit is a 4-bit by 4-bit array multiplier generating partial products using AND gates and summing diagonally with full adders, producing an 8-bit product enabled by a control signal.
ALU circuit:
<img width="1067" height="476" alt="vlsi11" src="https://github.com/user-attachments/assets/4f0098de-a7ae-4eb3-b407-28f1abbabb8a" />
 Multiplication Circuit:
![Uploading vlsi12.png…]()


All components integrate into a modular processor architecture connected by a central bus. The datapath manages address and data flow with registers, multiplexers, and pipeline registers to optimize operation. While a fully automated control sequencer is under development, manual operation supports system validation. The design combines arithmetic execution, bootloading, and systematic control signals via a unified control bus with debug interfaces, providing a scalable foundation for further processor automation and enhancement.
<img width="1041" height="762" alt="vlsi13" src="https://github.com/user-attachments/assets/eeda8f18-82a2-4368-bc15-aa1b3f8e5723" />





