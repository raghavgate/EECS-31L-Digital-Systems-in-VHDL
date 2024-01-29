In this assignment, you will design an accelerating object locator (Locator) which implements the equation below:

Location = ((at)^2)/2 + ut + x


Figure 1: Locator Equation.
In the physical implementation of the circuit, the values below are supplied by another circuit. For testing and validating our design, the values are pre-populated in our design. These constants for our LOCATION equation are as follows in our regArray as hexademical numbers:

The Zero Constant, if needed, is available in regArray(0)
Constant acceleration (a): 11 m/s2 (meters per second squared), stored in regArray(1)
Time (t): 35 seconds, stored in regArray(2)
An initial velocity (v0): 7 m/s (meters per second), stored in regArray(3)
Starting location (x0): 10 m (meters), stored in regArray(4)
regArray(5) through regArray(7) are free slots
The locator has three 1-bit inputs (Start, Rst, and Clk), as well as a 16-bit position output (Location) and a 1-bit output (Done). When Rst = ‘1’, the Locator is set to Start State. When Start = ‘1’, the Locator computes the following locating equation based on the values stored in the regArray and finds the new position of the object while ignoring any remainder from division. Once the result is calculated, the Locator enters into the End State and outputs the location through the Loc port for 1 clock cycle. The Loc port is set to 0 (or high impedance - all Z's - later for structural) at any other time. Similarly, the output signal Done (indicating the availability of the result on the Loc port) is set to ‘1’ for that clock cycle while it is set to ‘0’ at any other time.

You are not restricted to any specific design for the behavioral description, but you will be using a fixed datapath for the structural description.

Hint: note that multiplying 2 numbers in VHDL will result in an output that is the sum of the 2 numbers. For example, if you multiply two 8-bit numbers, the result will be 16-bits. You can store this output into a 16-bit entry/variable/signal. Alternatively, you can also store the lowest 8-bits into an 8-bit entry/variable/signal depending on needs and context.

Variable vs. Signal assignments: variable assignments happen sequentially (the value gets assigned once the line is processed). signal assignments happen in parallel with respect to timeline (all signal values get assigned when the process is over or after the delay has passed).
