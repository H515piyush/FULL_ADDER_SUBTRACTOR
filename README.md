# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![318405960-7116d2bf-8e90-4e96-bfd5-d62af11a317a](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/54e9554a-db39-46cb-815c-84c742936945)

![318405667-33d8ba16-9169-40b0-8696-3bb8e5c3a0b7](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/e5644d90-96cd-43bd-8e3c-2e46ec0ab260)

**Procedure**

```
**Full Adder:**
1.Open Quartus II and create a new project.
2.Use schematic design entry to draw the full adder circuit. 
3.The circuit consists of XOR, AND, and OR gates. 
4.Compile the design, verify its functionality through simulation. 
5.Implement the design on the target device and program it.

**Full Subtractor:** 
1.Follow the same steps as for the full adder. 
2.Draw the full subtractor circuit using schematic design. 
3.The circuit includes XOR, AND, OR gates to perform subtraction. 
4.Compile, simulate, implement, and program the design similarly to the full adder.
```


**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by:Piyush kumar 
RegisterNumber:212223220075
*/
```

## Full_adder
module ex5(a,b,cin,sum,carry);
input a,b,cin;
output sum,carry;
wire w1,w2,w3,w4;       
xor(w1,a,b);
xor(sum,w1,cin);        

and(w2,a,b);
and(w3,b,cin);
and(w4,cin,a);

or(carry,w2,w3,w4);
endmodule 

## Full_subtractor
module ex5(df,bo,a,b,bin);
output df,bo;
input a,b,bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule

```

**RTL Schematic**
![318405073-2e45d893-4f83-4a98-8bc2-d0d30b70e7e2](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/8e962897-cc6b-4cf5-83bb-b022ab4f2950)

![full sub rtl](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/28461f45-19a2-46dd-984e-17424abe2905)

**Output Timing Waveform**
FULL ADDER


FU![WhatsApp Image 2024-04-05 at 11 43 16_f941adc7](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/9a365a36-d985-43a9-8079-4faa42373cda)
LL SUBTRACTOR

![full sub waveform](https://github.com/H515piyush/FULL_ADDER_SUBTRACTOR/assets/147472999/8bb71c44-59e2-4c7d-82ea-7a7e6c4f1601)



**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



