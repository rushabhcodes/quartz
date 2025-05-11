A loader is a program that loads executable files (programs) from secondary storage into primary memory (RAM) for execution by the CPU. Its primary function is to take an executable file produced by a compiler or an assembler and place it into memory so that it can be run. 

The loader is an essential component of the operating system responsible for managing the execution of
	programs.

![[Linker and Loader.excalidraw.svg]]

## Basic function of a loader
#### 🔹 **1. Allocation**
- Reserves or allocates memory space in main memory for the program.
- Coordinates with the operating system to assign space for code, data, and stack segments.
#### 🔹 **2. Linking**
- Resolves symbolic references (e.g., function calls, variable addresses) between program modules or libraries.    
- Combines multiple object files and resolves inter-dependencies.
#### 🔹 **3. Relocation**
- Adjusts address-sensitive instructions so that the program can be executed from a memory location **different** from the one originally specified.    
- Uses **relocation bits** to identify which instructions need modification.
#### 🔹 **4. Loading**
- Transfers the executable machine code into the allocated memory.    
- Initializes registers and control and then **passes control** to the starting point of the program for execution.

## Types of Loader / Loader Schemas 

| **Loader Type**                    | **Description**                                                                              |
| ---------------------------------- | -------------------------------------------------------------------------------------------- |
| **1. Compile and Go Loader**       | The assembler loads the machine code directly into memory; no object file is created.        |
| **2. Absolute Loader**             | Loads programs at specified memory addresses. Allocation and linking are manual.             |
| **3. Relocating Loader**           | Supports relocation, enabling flexible memory assignment.                                    |
| **4. Direct Linking Loader (DLL)** | Uses two passes to resolve external references and relocation. Builds a load module.         |
| **5. Dynamic Loading Loader**      | Loads only required segments at runtime, using an overlay structure for memory optimization. |
![[Macro]]
![[Macro Data Structure]]