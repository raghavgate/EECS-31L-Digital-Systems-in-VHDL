In this assignment you will design a controller for parking permit dispensing machines. These automated pay machines provide daily permits. You need to specify it by an FSM and implement the controller with state register and combinational circuit (Figure 1). A sample simulation waveform is shown below (Figure 2). To keep things simple and consistent for this lab, the state register should only be sensitive to the rising edge of the clock (as shown in the lecture slides). The daily parking permit cost $20. Each pay station has a single slot, which accepts various bills. A subcontractor provides a bill sensor, which outputs a 3-bit vector named Input, representing $5, $10, $20, or cancelling the transaction. We dispense the permit (Permit = ‘1’ for one clock cycle) when $20 or more is collected and produce change if needed (ReturnChange = ‘1’ for one clock cycle). We do not have to worry about the exact amount of change, since that is taken care of by another module we communicate with outside of our circuit. If the user cancels the transaction before submitting the required amount, no permit is dispensed (Permit = ‘0’) and change is returned (ReturnChange = ‘1’ for one clock cycle). After we dispense a permit and/or return change, we return to our initial state and await another transaction.


Bill Sensor Data:
The data coming from the Bill Sensor module will operate as follows:

The Input vector is “001” if $5 is inserted, “010” if $10 bill is inserted, “100” if $20 bill is inserted, “000” if no bill is inserted, and “111” if the user canceled the transaction.
When no bill is inserted: “000” is supplied for 20ns*.
When a bill is inserted (or a transaction is cancelled): “001”, “010”, “100”, “111”  is supplied for 20ns*.
After a bill is inserted (or a transaction is cancelled): “000” is supplied for at least 20ns*.
A sample simulation waveform will be shown in class.

*For behavioral, we set our clock cycle to 10 ns; setup time will be 1 ns. For structural, we will use our actual calculated clock cycle; setup time will be 1 ns.


