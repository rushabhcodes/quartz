---
created: 2025-05-14T21:51
updated: 2025-05-14T21:51
---
In an absolute loader the assembler generates the object file which can be stored on secondary storage instead of being directly loaded into the memory.

Along with each object file, the assembler also gives information about starting address and length of that object file.

Here the programmer does the allocation and linking functions explicitly for the loader

The loader simply does the task of loading the object file into the memory and initiating the execution.

![[Absolute Loader.excalidraw.svg]]

Advantages
- Since the assembler does not always reside in the main memory, it leaves more main memory space available to the user.

Disadvantages
- The programmer must do memory management since he explicitly does the allocation and linking for the loader.