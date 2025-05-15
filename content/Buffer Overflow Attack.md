---
created: 2025-05-14T23:18
updated: 2025-05-15T00:04
---
A **buffer overflow** is a venerability that arises when a program writes more data to a memory buffer than it can hold. This causes the excess data to overflow into adjacent memory locations, potentially corrupting data or altering the programs control flow. Attackers can exploit this behavior to execute arbitrary code, crash the program or access sensitive information.

There are two main types of buffer overflows:
1. **Stack based buffer overflow** - Occurs in the stack memory used for function calls and local variables. It is often easier to exploit due to the predictable nature of stack memory.
2. **Heap-based buffer overflow** - Occurs in the heap memory, which is used for dynamic memory allocation. It can be more complex to exploit because the heap memory layout is less predictable.

### **Example in C**
```c
#include <stdio.h>
#include <string.h>

int main() {
	char buffer[5];
	gets(buffer);
	printf("Buffer: %s\n", buffer);
	return 0;
}
```

- The buffer is allocated with 5 bytes.
- The function `gets()` reads user input without checking the length.
- If the input exceeds 5 characters, it overflows and may overwrite adjacent memory.

```terminal
Input: 123456
Output: Segmentation fault (core dummped)
```

### **Security Risks** 
- **System crashes** or unexpected behavior.
- **Arbitrary code execution** by injecting malicious code into the program's memory space.
- **Data breaches** and unauthorized access to sensitive information.

### **Prevention Techniques**
- **Input validation** to ensure that the input data does not exceed the buffer's capacity.
- **Use of safe functions** like `fgets()` instead of `gets()`.
- Use modern compiler protection:  **Stack canaries**, **ASLR**, **DEP**.
- Prefer memory safe languages such as Rust or Go.