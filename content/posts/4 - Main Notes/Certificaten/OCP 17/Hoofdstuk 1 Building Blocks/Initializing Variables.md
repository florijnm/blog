---
titel: 
datum: 09-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - Variables
---
Een *lokale* viariabele is een variabel die gedefinieerd is in een constructor, methode of initializer block.

### Final Local Variables
Met het keyword *final* kunnen we constante variabelen declareren.
```
final int y = 10;
int x = 20;
y = x + 10; // DOES NOT COMPILE
```

```
final int[] favoriteNumbers = new int[10];
favoriteNumbers[0] = 10;
favoriteNumbers[1] = 20;
favoriteNumbers = null; //DOES NOT COMPILE
```

### Uninitialized Local Variables
Lokale variabelen hebben *geen default value*. Als je dit probeert te lezen gooit de compiler een *uninitialized* error.

```
public int notValid(){
	int y = 10;
	int x;
	int reply = x + y; //DOES NOT COMPILE
	return reply;
}

public int valid(){
	int y = 10;
	int x;
	x = 3;
	int z;
	int reply = x + y;
	return reply;
}
```


### Defining Instance and Class Variables
Een *instance* variabel zit op een *instantie* van een klasse.
Een *class* variabel zit op de klasse zelf. Dit houdt vaak in dat het *static* is.
Een *class* variabel is *shared* over alle *instances* van een klasse.

### Inferring the Type with *var*
Het keyword *var* kan worden gebruikt om *bij lokale variabelen* automatisch het type te bepalen. Dit heet *local variable type inference*. var is ook een *reserved type name*, dat betekent dat een type, zoals class, interface of enum, niet var mag heten.

```
public class Zoo{
	var name = "Artis"; //DOES NOT COMPILE

	public void whatTypeAmI(){
		var name = "Hello";
		var size = 7;
	}
}
```




