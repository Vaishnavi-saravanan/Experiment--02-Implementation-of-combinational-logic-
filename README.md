# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram
Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Procedure
Step 1: Create a project with required entities. 
Step 2: Create a module along with respective file name. 
Step 3: Run the respective programs for the given boolean equations. 
Step 4: Run the module and get the respective RTL outputs. 
Step 5: Create university program(VWF) for getting timing diagram. 
Step 6: Give the respective inputs for timing diagram and obtain the results.

# Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: VAISHNAVI S
RegisterNumber: 212222230165 
```
 # COMBINATION 1 USING NAND OPERATION
```
module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R;  
assign P = C&(~B)&(~A);  
assign Q = D&(~C)&(~A);  
assign R = (~C)&B&(~A);  
assign F = (~P&~Q&~R);  
endmodule 
```

# COMBINATION 2 USING NOR OPERATION
``` 
module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R,S;  
assign P = C&(~B)&A;  
assign Q = D&(~C)&A;  
assign R = C&(~B)&A;  
assign S = ~(P|Q|R);  
assign F = ~S;  
endmodule 
```
#  Output:
# COMBINATION 1:
# RTL
![Screenshot 2023-05-14 172927](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/b030bf33-24f2-432a-ae52-333aac418b35)
# Timing Diagram
![Screenshot 2023-05-14 172933](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/11fcfc92-98dc-42e9-bb1a-41697a42dfa0)
# Truth Table
![Screenshot 2023-05-14 172944](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/e408fa31-858b-4801-84aa-d7f0c4f98dc7)
## COMBINATION 2:
# RTL realization:
![Screenshot 2023-05-14 172834](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/6e943938-433d-4eec-86a6-cb472b49e144)
# Timing Diagram:
![Screenshot 2023-05-14 172841](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/a9d8b239-8d55-4ba3-bfa7-1029615f819a)
# Truth Table:
![Screenshot 2023-05-14 172853](https://github.com/Vaishnavi-saravanan/Experiment--02-Implementation-of-combinational-logic-/assets/118541897/5c56f01e-58b4-4246-8c09-2baa42a0d2d0)
# Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
