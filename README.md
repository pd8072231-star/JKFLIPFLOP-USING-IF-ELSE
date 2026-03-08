# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
1.Create a new project in Quartus II and open a Block Diagram/Schematic file. 
2.Place logic symbols and connect inputs A, B, Cin and outputs Sum, Cout. 
3.Implement logic: Sum = A ⊕ B ⊕ Cin, Cout = AB + Cin(A ⊕ B).
4.Compile and simulate to verify the output waveform.

**PROGRAM**
```
module exp_4(
input clk,
input j,
input k,
output reg q,
output reg qbar
);

always @(posedge clk) begin
if (j == 0 && k == 0) begin
    q <= q;
    qbar <= qbar;
end 
else if (j == 0 && k == 1) begin
    q <= 0;
    qbar <= 1;
end 
else if (j == 1 && k == 0) begin
    q <= 1;
    qbar <= 0;
end 
else if (j == 1 && k == 1) begin
    q <= ~q;
    qbar <= ~qbar;
end
end

endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
<img width="1920" height="1080" alt="Screenshot (585)" src="https://github.com/user-attachments/assets/fcf59e21-27f3-4eea-8cc6-3a55f08b8bcc" />


**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1920" height="1080" alt="Screenshot (586)" src="https://github.com/user-attachments/assets/0e45b397-4c7c-432d-9dca-3948261f6fc1" />


**RESULTS**
Thus,the JK flipflop executed successfully.
