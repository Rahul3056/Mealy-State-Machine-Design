### **Mealy State Machine Design**

#### **Concept Overview**  
A **Mealy State Machine** is a type of Finite State Machine (FSM) in which the **output depends on both the current state and the input**. This typically makes Mealy machines **faster in response** since the output can change immediately with the input, without waiting for the clock edge.

#### **Detailed Explanation**  
- **States** are defined as unique conditions of the system.  
- **Transitions** occur based on inputs and current states.  
- **Output logic** is associated with the transitions, not just the states.  

**Key Differences from Moore FSM**:  
- **Output is a function of current state and input**  
- Usually requires fewer states than Moore FSM for the same operation  
- Can respond faster, but may produce glitches if not handled carefully

#### **Applications**  
- Sequence detectors  
- Communication controllers  
- Control units in CPUs  
- Input validation circuits

#### **Execution Steps**  
1. Define the states using `parameter` or `typedef enum`  
2. Write the next state logic using `always @(*)`  
3. Use an `always @(posedge clk)` block to update the current state  
4. Output logic is written inside the next-state logic block  
5. Simulate with a testbench

#### **Real-World Example for Practice**  
**Design a sequence detector for “101” using a Mealy FSM**

#### **Expected Output**  
The output `y` becomes `1` as soon as the pattern "101" is detected — since it's a Mealy machine, the output responds during the same clock cycle when the last `1` is received.
