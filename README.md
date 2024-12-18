### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:
![Screenshot 2024-12-18 213943](https://github.com/user-attachments/assets/17318fa2-a97d-45d1-92a9-c22ab9278107)


![Screenshot 2024-12-18 214031](https://github.com/user-attachments/assets/e2e47dbd-f803-45de-9abf-494f30488e29)


Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:Sarankumar.V RegisterNumber:24010668
```
**PROGRAM**
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```


**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-18 214048](https://github.com/user-attachments/assets/1934b071-a471-4a5c-960f-c3f244bb457b)

**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-18 214057](https://github.com/user-attachments/assets/9c8d2803-7927-4ed4-81c8-a62352e7b5e1)


**TRUTH TABLE**


![Screenshot 2024-12-18 214108](https://github.com/user-attachments/assets/aeac8bfe-acc4-48de-bdab-d1f1bc877207)

**RESULTS**
The 4-bit synchronous up-counter was successfully implemented using Verilog in Quartus Prime. The functionality was validated by simulating the counter, which correctly counted up from 0000 to 1111 in binary, incrementing by 1 on each clock pulse. The synchronous nature of the counter ensured that all flip-flops were clocked simultaneously, with each flip-flop toggling based on the state of the preceding flip-flops. The output sequence followed the expected counting pattern, confirming the correct operation of the 4-bit synchronous up-counter.


