---
titel: Managing Variable Scope
datum: 09-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - Scope
---
### Limiting Scope
*Lokale* variabelen kunnen ***nooit*** een grotere scope hebben dan degene waar ze in worden gedefinieerd:

```
public void voorbeeld(boolean waarde){
	if(waarde){
		int x = 20;
	}
	System.out.println(x); //DOES NOT COMPILE
}
```


| Scope              | When?                                                                           |
| ------------------ | ------------------------------------------------------------------------------- |
| Local variables    | In scope from *declaration to the end of the block*                             |
| Method parameters  | In scope *for the duration of the method*                                       |
| Instance variables | In scope *from declaration until the object is eligible for garbage collection* |
| Class variables    | In scope *from declaration till end of the program*                             |
