A **macro** is a **named sequence of instructions** that can be inserted into code multiple times using a single macro call. It helps eliminate repetitive coding and increases code reusability.

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

## Macro Expansion
Macro expansion is the process of **replacing a macro call** with the actual sequence of instructions defined in the macro body.

## Types of Parameters in Macros

| **Type**       | **Description**                              | **Example**                |
| -------------- | -------------------------------------------- | -------------------------- |
| **Positional** | Substituted by order                         | `M1 A, B` → `&P1=A, &P2=B` |
| **Keyword**    | Substituted by name                          | `M1 &P1=A, &P2=B`          |
| **Default**    | Uses default values if not passed            | `&P1=10` (if not provided) |
| **Mixed**      | Combination of positional and keyword params | `M1 A, &P2=B`              |
## 