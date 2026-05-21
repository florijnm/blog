---
titel: Statements and Blocks
datum: 11-02-2025
hoofdstuk: 3
tags:
  - OCP
  - Java
  - Statements
  - Blocks
---
### Statements and Blocks

Een statement in een code block ziet er als volgt uit:
```
{
	patrons++;
}
```

#### If-statement
A statement or block often serves as the target of a decision-making statement. For example, we can prepend the decision-making *if* statement to this example:

```
if(true){
	patrons++;
}
```

Voor de if-statements zijn voor *single* statements de codeblocks optioneel:


```
if(true)
	patrons++;
```

Voor *multiline* statements zijn ze verplicht:
```
if(true)
	System.out.println("Ik word geprint als true!");
	System.out.println("Ik word ook geprint bij false!");
```

#### Else statement
Een else statement ziet er als volgt uit. Een else is optioneel, net als de codeblocks bij single-statements.
```
if(true){

} else{

}
```

In Java zijn `0` en `1` geen boolean waarden. Dit compileert dus niet:
```
int hourOfDay = 1;
if(hourOfDay){

}
```

### Shortening Code with Pattern Matching
```
void compareIntegers(Number number){
	if(number instanceof Integer data){ //Hier wordt data een Integer
		System.out.println(data.compareTo(5));
	}
}
```

