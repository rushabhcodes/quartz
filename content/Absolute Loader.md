In an absolute loader the assembler generates the object file which can be stored on secondary storage instead of being directly loaded into the memory.

Along with each object file, the assembler also gives information about starting address and length of that object file.

Here the programmer does the allocation and linking functions explicitly for the loader

The loader simply does the task of loading the object file into the memory and initiating the execution.

![[Absolute Loader.excalidraw.svg]]

### Advantages
- Since the assembler does not always reside in the main memory, it leaves more main memory space available to the user.
- Requires no relocation as addresses are fixed in the code.
- Loads programs quickly due to direct memory placement.
- Has a simple design because it performs no address modification.
- Consumes minimal system resources during loading.
- Ensures predictable execution by using absolute memory locations.
- Works well in systems without operating system support.
- Avoids the need for external symbol resolution or linking.

### Disadvantages
- The programmer must do memory management since he explicitly does the allocation and linking for the loader.