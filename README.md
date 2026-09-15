# ECE-230L---Lab-3
NAND Only Logic Lab 3

# Lab 03 \- NAND Only Logic

In this lab, you’ve learned how to convert arbitrary logical equations into NAND only circuits, and why that might be a good thing.

# Rubric

| Item | Description | Value |
| :---- | :---- | :---- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

# Lab Summary

In this lab we learned how to implement NAND gates as universal gates for AND/OR gates and converted them into a circuit only using NAND gates. We built a NAND only implementation with a 7400 chip that had four different 2 input NAND gates. We learned how physical NAND gates on a breadboard related to digital logic on an FPGA.

# 

# 

# Lab Questions

## 1 \- Write down DeMorgan’s Law and the truth tables proving it out.

DeMorgan’s Laws are: 	**1\.  \!(A \+ B) \= \!A \* \!B**    		(NOT A) AND (NOT B)  
**2\.  \!(A \* B) \= \!A \+ \!B**		(NOT A) OR (NOT B)

**F \= (A.\~B) \+ (C.D) Truth Table**

| A | B | C | D | \~B | A\~B | CD | F |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | **0** |
| 0 | 0 | 0 | 1 | 1 | 0 | 0 | **0** |
| 0 | 0 | 1 | 0 | 1 | 0 | 0 | **0** |
| 0 | 0 | 1 | 1 | 1 | 0 | 1 | **1** |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | **0** |
| 0 | 1 | 0 | 1 | 0 | 0 | 0 | **0** |
| 0 | 1 | 1 | 0 | 0 | 0 | 0 | **0** |
| 0 | 1 | 1 | 1 | 0 | 0 | 1 | **1** |
| 1 | 0 | 0 | 0 | 1 | 1 | 0 | **1** |
| 1 | 0 | 0 | 1 | 1 | 1 | 0 | **1** |
| 1 | 0 | 1 | 0 | 1 | 1 | 0 | **1** |
| 1 | 0 | 1 | 1 | 1 | 1 | 1 | **1** |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | **0** |
| 1 | 1 | 0 | 1 | 0 | 0 | 0 | **0** |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | **0** |
| 1 | 1 | 1 | 1 | 0 | 0 | 1 | **1** |

**F \= \~\[ \~(A · \~(B · B)) · \~(C · D) \] NAND Only Truth Table**

| A | B | C | D | N1 \~BB | N2 \~AN1 | N3 \~CD | N4 F=N2N3 |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 0 | 0 | 0 | 0 | 1 | 1 | 1 | **0** |
| 0 | 0 | 0 | 1 | 1 | 1 | 1 | **0** |
| 0 | 0 | 1 | 0 | 1 | 1 | 1 | **0** |
| 0 | 0 | 1 | 1 | 1 | 1 | 0 | **1** |
| 0 | 1 | 0 | 0 | 0 | 1 | 1 | **0** |
| 0 | 1 | 0 | 1 | 0 | 1 | 1 | **0** |
| 0 | 1 | 1 | 0 | 0 | 1 | 1 | **0** |
| 0 | 1 | 1 | 1 | 0 | 1 | 0 | **1** |
| 1 | 0 | 0 | 0 | 1 | 0 | 1 | **1** |
| 1 | 0 | 0 | 1 | 1 | 0 | 1 | **1** |
| 1 | 0 | 1 | 0 | 1 | 0 | 1 | **1** |
| 1 | 0 | 1 | 1 | 1 | 0 | 0 | **1** |
| 1 | 1 | 0 | 0 | 0 | 1 | 1 | **0** |
| 1 | 1 | 0 | 1 | 0 | 1 | 1 | **0** |
| 1 | 1 | 1 | 0 | 0 | 1 | 1 | **0** |
| 1 | 1 | 1 | 1 | 0 | 1 | 0 | **1** |

| Original | NAND only |
| :---- | :---- |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 1 | 1 |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 1 | 1 |

## 2 \- What is the value in converting circuits to NAND only?

- The value is that converting to NAND only is useful because it is universal and any boolean function can be made entirely from NAND gates. This allows for simplified designs and more efficient hardware while also being a cheaper manufactured cost.

## 3 \- How does what you did in lab with the breadboard relate to the FPGA?

\-The breadboard demonstrated the same digital logic that could be found in an FPGA, we connected individual NAND gates together using wires and gates in the 7400 chip. In an FPGA the same boolean function is used by programming internal logic instead of physically wired NAND gates. The breadboard shows a physical representation of digital logic that we have been learning.

# Code Submission

Upload a .zip of all your code or a public repository on GitHub.
