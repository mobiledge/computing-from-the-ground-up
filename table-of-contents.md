# Computing from the Ground Up
## Table of Contents

1. **The Wire: Electricity as Information**
   - A wire is either on or off — and that's enough
   - Electric charge, voltage, and the concept of a signal
   - Why two states are all a computer ever needs
   - Everything that follows rests on this single idea

2. **Making Decisions with Electricity**
   - The problem: how can a wire "react" to other wires?
   - Solving it with transistors: a switch controlled by electricity
   - Combining switches to make decisions: AND, OR, NOT
   - Building more powerful combinations: NAND, NOR, XOR
   - Only now, a name for what we've built: the logic gate

3. **Teaching a Wire to Remember**
   - The problem: our circuits forget the moment power changes
   - What if we fed a gate's output back into its own input?
   - A signal trapped in a loop: the birth of memory
   - Controlling what gets stored: the D latch
   - Only now, a name for what we've built: the flip-flop

4. **Scaling Memory Up**
   - The flip-flop as a trusted black box
   - Grouping 8 flip-flops to store a number: the byte
   - The problem: a byte that listens all the time
   - Adding an enabler to control when it stores: the register
   - Arranging registers into a grid with an address line: RAM

5. **Teaching Wires to Calculate**
   - The problem: how do we add two numbers in binary?
   - Building an adder from XOR and AND gates
   - Chaining adders to handle multi-bit numbers
   - Extending beyond addition: subtraction, AND, OR, NOT
   - Combining all operations behind a selector: the ALU

6. **Directing Traffic: The Control Unit**
   - The problem: we have an ALU and memory, but nothing coordinates them
   - A regular heartbeat to synchronize everything: the clock
   - Counting the clock's steps to track progress: the stepper
   - Translating an instruction into action: the decoder
   - Wiring them together into a control unit

7. **Putting It Together: A Simple CPU**
   - Connecting the ALU, memory, and control unit
   - The fetch-decode-execute cycle
   - A worked example: running a simple program
   - How this scales to real processors

*More chapters coming soon...*
