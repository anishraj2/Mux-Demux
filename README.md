### Ex. No. 7
### Date: 2.6.23
# Implementation of Multiplexer and Demultiplexer using Verilog HDL
## Aim:
To design and implement 4 X1 multiplexer and 1X4 demultiplexer circuit using Verilog HDL and verify its truth table.
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
## Multiplexer
Multiplexer is a combinational circuit that has maximum of 2n data inputs, ‘n’ selection lines and single output line. One of these data inputs will be connected to the output based on the values of selection lines.
Since there are ‘n’ selection lines, there will be 2n possible combinations of zeros and ones. So, each combination will select only one data input. Multiplexer is also called as Mux.
4x1 Multiplexer has four data inputs I3, I2, I1 & I0, two selection lines s1 & s0 and one output Y. One of these 4 inputs will be connected to the output based on the combination of inputs present at these two selection lines.
### Truth Table
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/f9577a7a-4124-4704-9091-3049d150e494)

### Logic Diagram
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/53ea88b0-5050-4e75-a51f-36c00e53a48d)


### Logic Expression
Y=S1′S0′I0+S1′S0I1+S1S0′I2+S1S0I3

### Block diagram
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/01ded8bd-64b4-406a-b6b2-488bdb0fa4d1)

## De-Multiplexer
De-Multiplexer is a combinational circuit that performs the reverse operation of Multiplexer. It has single input, ‘n’ selection lines and maximum of 2n outputs. The input will be connected to one of these outputs based on the values of selection lines.
Since there are ‘n’ selection lines, there will be 2n possible combinations of zeros and ones. So, each combination can select only one output. De-Multiplexer is also called as De-Mux.
1x4 De-Multiplexer has one input I, two selection lines, s1 & s0 and four outputs Y3, Y2, Y1 &Y0. The single input ‘I’ will be connected to one of the four outputs, Y3 to Y0 based on the values of selection lines s1 & s0.
### Truth Table
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/79275a3c-cd13-48e0-9a6e-e4c9567ca674)

### Logic Expression
Y3=s1s0I <br>
Y2=s1s0′I <br>
Y1=s1′s0I <br>
Y0=s1′s0′I <br>


### Logic Diagram
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/22aa1ffd-4981-4f40-81db-07914286c010)

### Block diagram
 ![image](https://github.com/rvinifa/Mux-Demux/assets/133735746/67d61732-4541-4162-948c-e11894957dec)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
### Multiplexer:
module mux(I0,I1,I2,I3,s1,s0,y);<br>
input I0,I1,I2,I3,s0,s1;<br>
output y;<br>
wire p,q,r,s,s1d,s0d;<br>
not(s1d,s1);<br>
not(s0d,s0);<br>
and(p,s1d,s0d,I0);<br>
and(q,s1d,s0,I1);<br>
and(r,s1,s0d,I2);<br>
and(s,s1,s0,I3);<br>
or(y,p,q,r,s);<br>
endmodule<br>
### De-Multiplexer:
module demux(I,s1,s0,y3,y2,y1,y0);<br>
input I,s1,s0;<br>
output y3,y2,y1,y0;<br>
wire s1d,s0d;<br>
not(s1d,s1);<br>
not(s0d,s0);<br>
and(y3,s1,s0,I);<br>
and(y2,s1,s0d,I);<br>
and(y1,s1d,s0,I);<br>
and(y0,s1d,s0d,I);<br>
endmodule<br>
## RTL Schematic:
### Multiplexer:<br>
![Multiplexer](1.png)<br>
### De-Multiplexer:<br>
![De-Multiplexer](2.png)
## Timing Diagram:
### Multiplexer:<br>
![Multiplexer](3.png)<br>
### De-Multiplexer:<br>
![De-Multiplexer](4.png)<br>
## Result:
Thus the multiplexer and demultiplexer circuits are designed and implemented and the truth tables are verified.

