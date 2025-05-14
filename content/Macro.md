A **macro** is a **named sequence of instructions** that can be inserted into code multiple times using a single macro call. It helps eliminate repetitive coding and increases code re-usability.

## **Macro Definition Syntax**
A macro is defined using `MACRO` and ends with `MEND`:
```MACRO
ADDVAL &X, &Y
    LOAD AREG, &X
    ADD AREG, &Y
MEND
```
## **Macro Call**
To invoke the macro:
```
ADDVAL NUM1, NUM2
```
During **macro expansion**, the macro call is replaced with:
```
LOAD AREG, NUM1
ADD AREG, NUM2
```

## Types of Parameters in Macros
### By Place of Use

- Formal Parameters
	which appear in macro definition. Also called as place holder.
- Actual Parameters
	which appear in macro call.

### By Way of Use

| **Type**       | **Description**                              | **Example**                |
| -------------- | -------------------------------------------- | -------------------------- |
| **Positional** | Substituted by order                         | `M1 A, B` → `&P1=A, &P2=B` |
| **Keyword**    | Substituted by name                          | `M1 &P1=A, &P2=B`          |
| **Default**    | Uses default values if not passed            | `&P1=10` (if not provided) |
| **Mixed**      | Combination of positional and keyword params | `M1 A, &P2=B`              |
## Macro Expansion
Macro expansion is the process of **replacing a macro call** with the actual sequence of instructions defined in the macro body.
## Conditional Macro Expansion
Conditional expansion means that a model statement is expanded only under specific conditions.
It is achieved by altering the flow of control during the macro expansion by using AIF and AGO statements.

► AIF – like if statement
```
AIF (exp.) <sequence symbol>
```
► AGO – like GOTO statement.
```
AGO < sequence symbol >
```
### Example :
A macro named EVAL is to be defined such that the call `EVAL A, B, C` would generate efficient code to evaluate the expression A-B+C by using AREG. When the first two parameters of a call are identical , EVAL should generate a single MOVER instruction to load the 3 rd parameter into AREG.
```
MACRO
	EVAL    &X, &Y, &Z
		AIF     (&X EQ &Y)   .LABEL
		MOVER   AREG, &X
		SUB     AREG, &Y
		ADD     AREG, &Z
		AGO     .OVER
LABEL   MOVER   AREG, &Z
OVER    MEND
```
## [[Macro Data Structure]]
- Macro Definition Table (MDT)
- Macro Name Table (MNT)
- Macro Definition Table Counter (MDTC)- indicate next entry in MDT
- Macro Name Table Counter (MNTC) - indicate next entry in MNT
- Argument List Array (ALA)