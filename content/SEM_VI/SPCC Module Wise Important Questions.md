---
created: 2025-05-20T12:04
updated: 2025-05-20T12:04
---
8# Module 1
## Difference between Application Software and System Software

![[Difference between Application Software and System Software#^e77dfc]]

## Difference between Compiler and Interpreter
![[Difference between Compiler and Interpreter]]
# Module 2 - Assembler
## Explain forward reference problem and how it is handled in assembler design

![[Forward Reference]]

## Explain with flowchart the design of Two Pass Assembler

![[Pass 1 of 2 Pass Assembler.excalidraw.svg]]
## Numerical Based on [[Two Pass Assembler]]
Consider the following assemble program
```asm
START 501
	A DS 1
	B DS 1
	C DS 1
READ A
READ B
MOVER AREG, A
ADD   AREG, B
MOVER AREG, C
PRINT C
END
```
Generate Pass-1 and Pass-2 and also show contents of Database table
## With reference to assembler explain the following table with suitable example. POT, MOT, ST, LT, BT

![[Assembler#Data Structures Used in Assembler]]

> [!info] Extra
> 
> Explain different assembler directives with examples
> [[Assembler Directives#📘 **Common Assembler Directives (with Examples) **]]
> 
> Enlist different types of errors that are handled by Pass 1 and Pass 2 asssembler 

# Module 3 - Macro and Macro Processor
## Draw a neat flowchart of Two Pass Macro Processor, Explain with the help of an example

Pass 1
![[Pass 1 Two Pass Macro.excalidraw.svg]]

Pass 2
![[Pass 2 Two Pass Macro.excalidraw.svg]]

## With reference to macro, explain the following tables with examples:
- MNT
- MDT
- ALA
![[Macro Data Structure]]
## Explain macro and different features of macro with examples
![[Macro]]
## Explain with example Conditional Macro Expansion
![[Macro#Conditional Macro Expansion]]

> [!info] Extra
> 
> Parameterized Macro
> 
> Explain advance macro facilities with suitable examples
> 
> Explain the working of Single Pass Macro Processor with a neat flowchart

# Module 4 - Loaders and Linkers
## What is a loader and explain the functions of a loader with example
![[Loader]]

## Explain design and flowchart of absolute loader
![[Absolute Loader]]
## Explain the working of Direct Linking Loader with an example and also show entry in different built by DLL
## Explain Dynamic Linking Loader in Detail

>[!info] Extra
>
>Difference between Dynamic Linking and Dynamic Loading with example
>
>What is relocation and linking concept in Loader
>
>Explain different types of loaders in detail

# Module 5 - Compiler Analysis Phase
## What are the different phases of the compiler with example
## Illustrate compilers internal  presentation of source program for the following statements after each phase
```C
position = initial + rate * 60
```
```C
a = a * b - 5 * 3 / c
```
## Predictive parser LL1 (Sum based on this)
##  Define Left Recursion and Eliminate Left Recursion
## Find FIRST and FOLLOW
## Write short note on Lex and Role of Lexical Analysis
## Compare Pattern, Lexemes and Token with example
## Error recovery techniques used in compilert
## Short note on Synthesized and inherited attributes

>[!info] Extra]
>
>Difference between LL parser and LR parser
>
>Explain Syntax Directed Translation
>
>Compare the performance of compilers and interpreters
>
>Difference between Top-down and Bottom-up parsing techniques
>
>Explain Recursive Decent parser
>
>Short note or Sum on
>	- LR0
>	- SLR1
>	- CLR1
>	- LALR1
# Module 6 - Compiler Synthesis phase
## What is code optimization? Explain various Code Optimization Techniques in detail with example
## Explain different issues in code generation
## Write a Short Note on Three Address Code
## Construct the Three Address Code for the following program
```C
i = 1;
x = 0;
while(i <= n) {
	x = x + 1;
	i = i + 1;
}

min = a[0];
for(i = 0; i < n; i++) {
	if(a[i] > max) {
		max = a[i];
	}
}
```

> [!info] Extra
> 
> YACC
> 
> Explain DAG with suitable example
> 
> Explain different ways of representing Intermediate Code with example

