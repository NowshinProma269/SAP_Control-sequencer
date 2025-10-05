# SAP_Control_sequencer
Table of contents:
1.Project overview
2.Features
3.Key Components
4.Design Process
5.Final circuit
6.Compiler
7.Behavioral Analysis
8.Video Tutorials
9.Limitations
10.Future Improvements

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
<img width="1182" height="557" alt="vlsi12" src="https://github.com/user-attachments/assets/97c592fd-98fe-4b49-930b-fd0df60294c7" />

Final Circuit:
All components integrate into a modular processor architecture connected by a central bus. The datapath manages address and data flow with registers, multiplexers, and pipeline registers to optimize operation. While a fully automated control sequencer is under development, manual operation supports system validation. The design combines arithmetic execution, bootloading, and systematic control signals via a unified control bus with debug interfaces, providing a scalable foundation for further processor automation and enhancement.
<img width="1041" height="762" alt="vlsi13" src="https://github.com/user-attachments/assets/eeda8f18-82a2-4368-bc15-aa1b3f8e5723" />

Compiler Output:

<img width="880" height="388" alt="vlsi14" src="https://github.com/user-attachments/assets/f499b5d8-9338-4d5d-8a16-b4a892358564" />

Behavioral analysis consists of three main steps:


Instruction  |  Opcode (4-bit)  |  Description                      
-------------+------------------+-----------------------------------
LDA          |  0001            |  Load Accumulator from memory     
LDB          |  0010            |  Load B register from memory      
MUL          |  0011            |  Multiply Accumulator and B       
ADD          |  0100            |  Add memory content to Accumulator
STA          |  0101            |  Store Accumulator to memory      
HLT          |  1111            |  Halt execution                   


Input Compilation and ROM Code Generation: Assembly instructions are converted into 8-bit machine code by mapping each mnemonic to a 4-bit opcode and converting operands to 4-bit binary. These codes are concatenated and stored as hexadecimal values in ROM, ready for execution.

Bootloader Control and ROM-to-RAM Transfer: The bootloader FSM, implemented with JK flip-flops and combinational logic, automates system reset and program loading from ROM to RAM. It uses timing signals to control Memory Address Register loading, RAM writing, and execution enabling via precise control signals generated from a Control ROM/Table Memory.

Instruction Execution and Timing Control: After bootloading, the processor exits debug mode and starts fetching instructions sequentially through clock pulses. The fetch phase includes addressing memory, loading instructions into the instruction register, and incrementing the program counter. During decode, the control unit interprets opcodes and prepares relevant units. Execution performs arithmetic or memory operations, updates registers, and controls program flow. Behavioral outputs from multiplication and addition instructions confirm correct ALU operation and effective control signal coordination.

Together, these phases ensure accurate compilation, automatic program loading, and proper sequential execution of instructions.

Video Tutorials:
https://youtu.be/-2GEuG5JHSU?si=9D0z_mV9ZEGtKSAn


Limitations:
 Despite the successful design and implementation of the Modified SAP architecture with auto
matic control sequencing and enhanced arithmetic functionality, several limitations exist:
 1. Limited Instruction Set: The instruction set implemented is minimal and focused on
 basic arithmetic and data movement operations; advanced instructions such as branching,
 interrupts, or input/output handling are not supported.
 2. Restricted Memory Capacity: With only 16 memory locations (16×8 RAM), the archi
tecture supports only small programs, limiting its practical applications and scalability.
 3. Multiplication Unit Constraints: The multiplication circuit is limited to 4-bit by 4-bit
 integer multiplication, lacking support for wider word sizes or more complex arithmetic
 operations.
 4.Timing and Performance: The simple ripple-carry ALU design and sequential state
 counter limit processing speed and throughput relative to more advanced architectures.

 Future Improvements:
 The current design and implementation of the Modified SAP provide a solid foundation, yet
 there are several avenues for enhancement to increase functionality, performance, and usability:
 1. Expanded Instruction Set: Extend the instruction set architecture to include branches,
 jumps, interrupts, and I/O instructions to support more complex and practical programs.
 2. Memory Capacity Increase: Upgrade RAM size beyond 16 locations and implement
 expanded addressing schemes to run larger programs and data sets.
 3. Arithmetic Unit Enhancement: Improve the ALU by incorporating wider bit-width
 operations, faster adder architectures (such as carry-lookahead), and support for floating
point arithmetic.
 4. AdvancedMultiplication: Extend the multiplier to support wider operands and consider
 implementing division and other advanced arithmetic operations.
 5. Pipeline and Parallelism: Explore pipelining instruction execution and adding parallel
 data paths to improve throughput and system efficiency.
 6. Integration of AI/ML Techniques: In the long term, consider integrating machine
 learning assisted control or optimization for instruction scheduling and power manage
ment.
7. Robust Error Detection and Fault Tolerance: Implement error checking and correc
tion mechanisms to enhance reliability, especially for real-world deployment scenarios.
 
 Pursuing these improvements will substantially enhance the processor’s capabilities, usabil
ity, and performance, paving the way for more sophisticated applications and research devel
opment








