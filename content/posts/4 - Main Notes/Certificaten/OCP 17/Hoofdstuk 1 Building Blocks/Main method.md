---
titel: Main method
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
---
De meest simpele vorm van de main methode ziet er als volgt uit:

```
public class Program{
	public static void main(String[] args){
		System.out.println("Hello World!");
	}
}
```

*args* staat hier voor de argumenten die bij het draaien van het programma aan de JVM worden meegegeven.

`System.out.println(args[0]);` is hier dus valide als er minimaal één argument wordt meegestuurd.

```
public final static void main(final String[] args){

}
```

Meegeven van de *final* annotatie is ook valide in deze context.


