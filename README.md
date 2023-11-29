## NAME:RAMYA P
## REF NO:23006111

# Experiment-04-Half-Subtractor and Full-subtractor
## Implementation of Half-subtractor and Full-subtractor circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1.Create a New Project:
*Open Quartus and create a new project by selecting "File" > "New Project Wizard."<br>
*Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).<br>
2.Create a New Design File:
*Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."<br>
*Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
3.Write the combinational Logic code:
*Open the newly created Verilog or VHDL file and write the code for your combinational logic.<br>
4.Compile the project:
*To compile the project, click on "Processing" > "Start Compilation" in the menu.<br>
*Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.<br>
5.Analyze and fix errors:
*If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.<br>
*Review and fix any issues in your code if necessary.<br>
*View the RTL diagram.<br>
6.Verification:
*Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".<br>
*Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.<br>
*Give the Input Combinations according to the Truth Table and then simulate the Output Waveform.<br>
## Program:
## HALF SUBTRACTOR
```
module halfsub(diff,carry,a,b);
input a,b;
output diff,carry;
xor(diff,a,b);
assign carry=(~a)&b;
endmodule
```
## FULL SUBTRACTOR
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
xor(diff,a,b,c);
assign carry= (~a)&c | (~a)&b | (b&c);
endmodule
```
## TRUTH TABLE
## HALF SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/541828f2-f4b3-40b3-8df3-63c2620e1d0d)

## FULL SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/d78e8955-9fec-408c-acf2-f37b2360701c)

## RTL REALIZATION
## HALF SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/31de25e9-b60a-41ed-96b7-8a94eac6d815)
## FULL SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/2e51d359-c6fb-435b-86a1-d23c4570039f)

## TIMING DIAGRAM

## HALF SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/03a62746-6e95-48a7-8a9f-a711dbc8b83f)
## FULL SUBTRACTOR
![image](https://github.com/23006111/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145981696/55216f7f-d95e-46c4-a75e-eb463c857339)




## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
