# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
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



Write the detailed procedure here 


## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: 212222230092
RegisterNumber:  NAVEEN KUMAR P
*/
```
```
### half sub:
module halfsubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

### full sub:

module fullsubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule

```

## Output:

## Truthtable:
### half:
![image](https://user-images.githubusercontent.com/119401470/231669261-19be9063-b068-4a91-916f-fcde62001dda.png)

### full:

![image](https://user-images.githubusercontent.com/119401470/231669321-3c65e3ad-04f3-4edc-b96d-a84e25509b81.png)



##  RTL realization:
### half
![halfsub](https://user-images.githubusercontent.com/119401470/231669717-430d20b8-f07a-4f93-98a3-cbc301210c50.png)

### full
![WhatsApp Image 2023-04-13 at 11 50 33](https://user-images.githubusercontent.com/119401470/231670872-7fe05f69-e27a-4dfc-8f3f-84053b982665.jpg)

## Timing diagram :
### half:
![WhatsApp Image 2023-04-13 at 11 50 20](https://user-images.githubusercontent.com/119401470/231672206-9516a4ba-c38a-47c1-bd0d-21d7f322a246.jpg)

###full:

![WhatsApp Image 2023-04-13 at 11 50 07](https://user-images.githubusercontent.com/119401470/231672303-462c7592-0b39-4be1-9895-914081d77a71.jpg)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
