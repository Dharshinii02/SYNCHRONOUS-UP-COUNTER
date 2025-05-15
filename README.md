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

1.Create a new project in Quartus Prime and select the target FPGA device.

2.Write the Verilog code for the 4-bit synchronous up counter.

3.Add the code to the project and save it with a .v extension.

4.Compile the design to check for syntax or logic errors.

5.Simulate the circuit using the waveform editor or ModelSim to verify correct counting.

**PROGRAM**
```
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
Developed by:Dharshini J
RegisterNumber:212224240036


**RTL LOGIC UP COUNTER**
![Screenshot 2025-05-15 204215](https://github.com/user-attachments/assets/78a0a050-eed8-4dc7-bbbd-6983b2f622cf)


**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2025-05-15 204233](https://github.com/user-attachments/assets/fef0447b-0da7-406e-8caa-28469c21dee1)

**TRUTH TABLE**

![Screenshot 2025-05-15 204246](https://github.com/user-attachments/assets/838e139a-dbbb-4fcd-82bd-1bc464c820d0)

**RESULTS**.
Hence a 4 bit synchronous up counter is implemented correctly.
