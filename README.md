# ALU implemented in verilog
## Problem statement(refer to the attached pdf) ->
  It performs arithmetic operations and logical operations on binary data.

  ## Let's break the code ->

  ### Module Inputs and Outputs:
  clk: Clock signal
  rst: Reset signal
  X, Y: 8-bit inputs
  control: 6-bit control signal
  out: 8-bit output
  zr: Zero flag output
  ng: Negative flag output

  ### Internal Registers:
  x, y: 8-bit registers to store input values
  o: 8-bit register to store the output value
  con_zr, con_ng: Single-bit registers for zero and negative flags
  v: 6-bit register to hold the control signal value
  state, nstate: 4-bit registers to represent the current and next state of the processor

  ### State Definitions:
  parameter statement defines symbolic names for different states.
 States are defined for various stages of processing: idle, start, s0 to s5 for different operations, and stop.

 ### State Machine:
 The always @(posedge clk) block updates the current state (state) based on the clock signal and reset (rst) condition.
 The always @(*) block determines the next state (nstate) based on the current state.
 State transitions occur according to the defined sequence.

 ### Operation Execution:
 Inside the second always @(*) block, operations corresponding to different states are executed based on the control signal (v).
 Each state performs specific operations on the inputs x and y and updates the output o.
 Operations include conditional assignments based on the control signals for different arithmetic and logical operations.

 ### Output Assignment:
 assign statements assign values to out, zr, and ng based on internal registers.
