---
titel: Ordering Elements in a Class
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
---

| Element                    | Example               | Required | Where does it go?                    |
| -------------------------- | --------------------- | -------- | ------------------------------------ |
| Package declaration        | `package abc;`        | false    | First line in the file               |
| import statements          | `import java.util.*;` | false    | Immediately after the package        |
| Top-level type declaration | `public class C`      | true     | Immediately after the imports        |
| Field declarations         | `int value;`          | false    | Any top-level element within a class |
| Method declarations        | `public int method()` | false    | Any top-level element within a class |
Compileert:
```
package abc;

import java.util.Random;

public class Program{
	String name = "Program";
	public static void main(String[] args){
		System.out.println(name);
	}
}
```

Compileert niet:
```
import java.util.Random;

package abc;

String name = "Program";

public class Program{
	public static void main(String[] args){
		System.out.println(name);	
	}
}
```

