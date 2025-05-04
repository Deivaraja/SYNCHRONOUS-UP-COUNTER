### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).
    2.Input a bit serially into the shift register.
    3.Shift the contents of the register one position to the right (or left).
    4.Output the shifted bit from the last stage of the register.
    5.Repeat steps 2-4 for each bit you want to input and shift

**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.

    module Verilog1(clk, sin, q);
    input clk;
    input sin;
    output [3:0] q;
    reg [3:0] q;
    always @(posedge clk)
    begin
    q[0] <= sin;
    q[1] <= q[0];
    q[2] <= q[1];
    q[3] <= q[2];
    end
    endmodule

```
Developed by: DEIVARAJA R

RegisterNumber:212224240031
```



**RTL LOGIC FOR SISO Shift Register**

![exp10 rtl](https://github.com/user-attachments/assets/35a6590e-342e-4bc9-94c3-38e87c311d65)


**TIMING DIGRAMS FOR SISO Shift Register**

![WhatsApp Image 2024-12-14 at 21 43 22_940555cd](https://github.com/user-attachments/assets/06ec21aa-304b-431c-8cf3-a51bb75cd44d)


**RESULTS**

Thus the SISO Shift Register is implemented using verilog and validated their functionality using their functional tables


