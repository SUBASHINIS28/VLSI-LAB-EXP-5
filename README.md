# VLSI-LAB-EXP-5


## SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM:

To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED: 

Xilinx 14.7 
Spartan6 FPGA

## PROCEDURE: 

STEP:1 Start the Xilinx navigator, Select and Name the New project.

STEP:2 Select the device family, device, package and speed. 

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 

STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

STEP:12 Load the Bit file into the SPARTAN 6 FPGA 

## Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


## VERILOG CODE:
```
module fsm( clk, rst, inp, outp);
input clk, rst, inp;
output outp;
reg [1:0] state;
reg outp;
always @(posedge clk, posedge rst)
begin
if(rst)
state<=2'b00;
else
begin
case(state)
2'b00:
begin
if(inp) state <=2'b01;
else state <=2'b10;
end
2'b01:
begin
if (inp) state <=2'b11;
else state<=2'b10;
end
2'b10:
begin
if (inp) state<=2'b01;
else state <=2'b11;
end
2'b11:
begin
if (inp) state <=2'b01;
else state <=2'b10;
end
endcase
end
end
always @(posedge clk, posedge rst)
begin
if(rst)
outp <= 0;
else if(state == 2'b11)
outp <= 1;
else outp<= 0;
end
endmodule
```

## OUTPUT:

![WhatsApp Image 2024-05-17 at 09 16 36_eb5b1f74](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-5/assets/153823077/fb30aa11-f6e9-4255-84a7-5c91a9a9d8e2)



## RESULT:

Hence the finite state machine has been simulated and synthesised using Vivado 2023.2

