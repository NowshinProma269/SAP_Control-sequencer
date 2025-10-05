# SAP_Control-sequencer
#Table of contents
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

#Project overview
This project modifies the SAP-1 microprocessor in Logisim-evolution by adding an automatic control sequencer for instruction cycles, a bootloader FSM for ROM-to-RAM loading, and an enhanced ALU supporting addition, subtraction, and 4x4-bit multiplication, improving automation and computational capability.

Features:
This project implements a modified version of the SAP-1 microprocessor architecture using Logisim-evolution. It features an automatic control sequencer that manages the instruction fetch, decode, execute, and debug cycles autonomously, removing manual intervention. The design incorporates a bootloader FSM that automates the transfer of programs from ROM to RAM during startup, enabling seamless system initialization.

The architecture includes essential components such as a program counter, memory address register, instruction register, general purpose registers, and a 16×8 RAM for storing data and instructions. The arithmetic logic unit (ALU) is enhanced to support addition, subtraction, and a 4-bit by 4-bit multiplication operation, broadening the processing capabilities of the processor.

Control logic combines timing signals from a state counter and decoded opcodes to precisely manage data flow and instruction execution. The overall design allows for structured, automated program execution verified through behavioral analysis using assembly instruction compilation and output validation.

Though limited by a minimal instruction set and small memory size, this project lays a strong foundation for further development in microprocessor design, offering opportunities for enhanced functionality, expanded memory, improved arithmetic units, and advanced control techniques. It serves as an educational platform for learning digital system fundamentals and processor automation.
