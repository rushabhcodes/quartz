---
created: 2025-06-23T02:42
updated: 2025-06-23T03:12
---
> TypeScript is a strongly typed programming language that builds on JavaScript.

~ [Typescrpt Docs](https://www.typescriptlang.org/)

Documentation on [JavaScript at the Mozilla Web Docs](https://developer.mozilla.org/docs/Web/JavaScript/Guide).

---
## Strongly typed vs Loosely typed
The terms `strongly typed` and `loosely typed` refer to how programming languages handle types, particularly how strict they are about type conversions and type safety.

| Strongly typed languages<br><br>                                                                                                                        | Loosely typed languages                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Examples - Java, C++, C, Rust<br><br>2. Benefits -<br>	1. Lesser runtime errors<br>	2. Stricter codebase<br>	3. Easy to catch errors at compile time | 1. Examples - Python, Javascript, Perl, php<br><br>2. Benefits<br>	1. Easy to write code<br>	2. Fast to bootstrap<br>	3. Low learning curve |

> [!fail] Does not work

```C++
#include <iostream>
int main() {
int number = 10;
number = "ten";
return 0;
}
```




> [!success] Does work

```Js
function main() {
  let number = 10;
  number = "text";
  return number;
}
```

