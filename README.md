# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
CMC
LDA 4200H
MOV B, A
LDA 4201H
ADD B
STA 4300H
JC STORE_CARRY: MVI A,01H
STA 4301H
HLT
```

### Output:
![add__ss1](https://github.com/user-attachments/assets/60f2eadd-bf48-4aa4-828d-2193848e7509)
![add_ss2](https://github.com/user-attachments/assets/3754001a-37d8-47d1-b62b-91d17a15039b)

### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
CMP C
JC SWAP
MOV B, A
MOV A, C
SWAP: SUB B
STA 4300H
HLT
```

### Output:
<img width="1892" height="859" alt="image" src="https://github.com/user-attachments/assets/e1119975-1a72-4dd1-bf1f-61a4b749039a" />
<img width="1891" height="848" alt="image" src="https://github.com/user-attachments/assets/475f10e3-e715-4db4-9a35-677889d5b0fd" />

### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
MOV B, A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:
<img width="1886" height="865" alt="image" src="https://github.com/user-attachments/assets/1e3d0695-cdd7-4d64-a421-7fa65660e90e" />
<img width="1890" height="852" alt="image" src="https://github.com/user-attachments/assets/4349e7b6-9ad0-40f5-a6e6-c4a24088b603" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:

### Output:

## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

