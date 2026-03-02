LC-5200 Datapath Visualizer
An interactive, cycle-by-cycle datapath visualizer for the LC-5200a processor — built to help students understand how instructions move through the datapath and what control signals are active at each microcode cycle.
https://tobi-obitayo.github.io/lc5200-datapath-visualizer/lc5200-datapath-visualizer.html

What It Does
Select an LC-5200 instruction and step through its execution one microcode cycle at a time. At each cycle, the visualizer highlights:

Active control signals — Load, Drive, and Write signals (LdPC, DrALU, WrMEM, etc.)
Datapath flow — how data moves across the bus between components
ALU operation — which function is being performed (ADD, SUB, NAND, PASS, etc.)
Register and memory activity — reads, writes, and addressing
Cycle description — a plain-English explanation of what's happening

The fetch phase can be toggled on or off, and an animation mode visualizes bus flow in real time.

Datapath Components
ComponentDescriptionPCProgram CounterMARMemory Address RegisterIRInstruction Register (32-bit, with field breakdowns)A / BTemporary registers feeding the ALUALUArithmetic Logic Unit (6 operations)Registers16 × 32-bit general-purpose register fileMemory2¹⁶ × 32-bit addressable memorySign ExtendOffset sign extension unitComparison LogicDrives CmpTrue signal to the microcontroller

Controls
InputAction→ / Next buttonAdvance one microcode cycle← / Prev buttonGo back one cycleShow Fetch toggleInclude/exclude the FETCH0 cycleAnimate Flow toggleAnimate data movement on the bus

Why I Built This
Stepping through microcode on paper during CS 2200 made it hard to build a mental model of the full datapath. This visualizer makes the signal-level behavior concrete and was particularly helpful for understanding how FETCH, ALU operations, memory reads/writes, and branching each play out cycle by cycle.

Tech Stack

Vanilla HTML, CSS, JavaScript
No dependencies — runs entirely in the browser


Contributing
The repo is public — feel free to open issues or PRs for additional instructions, bug fixes, or UI improvements.
