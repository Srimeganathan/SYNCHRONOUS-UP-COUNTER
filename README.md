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

/* write all the steps invloved */

**PROGRAM**
```
module MULTIPLIER(a, b,y); input [3:0] a;
input [3:0] b; output [7:0] y;
wire t1,t2,t3,t4,t5,t6,t7,t8,t9,t10,t11,t12,t13,t14,t15,c0,c1,c2,c3,c4,x1,x2,x3,x4,x5,x6,x7,x8;
and(y[0],a[0],b[0]);
and(t1,a[1],b[0]);
and(t2,a[0],b[1]);
and(t3,a[2],b[0]);
and(t4,a[1],b[1]);
and(t5,a[0],b[2]);
and(t6,a[3],b[0]);
and(t7,a[2],b[1]);
and(t8,a[1],b[2]);
and(t9,a[0],b[3]);
and(t10,a[3],b[1]);
and(t11,a[2],b[2]);
and(t12,a[1],b[3]);
and(t13,a[3],b[2]);
and(t14,a[2],b[3]);
and(t15,a[3],b[3]);
fa a1(y[1],c0,t1,t2,1'b0); fa 
a2(x1,x2,t3,t4,c0);
fa a3(y[2],c1,x1,x2,t5); fa 
a4(x3,x4,t6,t7,c1); fa a5(x5,x6,x3,x4,t8); 
fa a6(y[3],c2,x5,x6,t9); fa 
a7(x7,x8,t10,t11,c2); fa 
s8(y[4],c3,x7,x8,t12);
fa a9(y[5],c4,t13,t14,c3);
fa a10(y[6],y[7],t15,c4,1'b0); endmodule
module fa(s,co,a,b,cin); input a,b,cin;
output s,co; xor(s,a,b,cin); wire 
l1,l2,l3; and(l1,a,b); 
and(l2,b,cin); and(l3,a,cin); 
or(co,l1,l2,l3; endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: RegisterNumber:
*/

**RTL LOGIC UP COUNTER**
![image](https://github.com/user-attachments/assets/327b02e0-16b4-44b1-9396-7db7e1b81a56)

**TIMING DIAGRAM FOR IP COUNTER**
![image](https://github.com/user-attachments/assets/d9b1f18c-63cb-4ae5-80d2-8a549f8265a4)

**RESULTS**
The multiplier are simulated and synthesized using Verilog HDL. And implement in fFPGA.
