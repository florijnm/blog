---
titel: Switch Statements
datum: 11-02-2025
hoofdstuk: 3
tags:
  - OCP
  - Java
  - Switch
---
Een switch statement is een *complexere* keuze structuur. In de "switch" wordt een variabele gecontroleerd tegen waardes aan, en als er een *case* is die overeenkomt wordt dit pad bewandeld. Als er geen match is, wordt de *default* case gekozen.

Als er geen default is, en ook geen overeenkomst, wordt de switch overgeslagen. 

```
switch(variableToTest){ //REQUIRED
	case constantExpression1: //OPTIONAL
		break; //OPTIONAL
	case constantExpression2, constantExpression3: //OPTIONAL
		break; //OPTIONAL
	default: //OPTIONAL
		break; //OPTIONAL
} //REQUIRED
```

Breaks zijn niet verplicht, maar zonder breaks loopt hij standaard langs alle paden, ook de default.

### Determining Acceptable Case Values
De waardes in elke *case* statement moet *compile-time* constant values van dezelfde data type zijn als de switch value.
De value moet ook zijn van een literal, *enum constant*, of *final*.

### Switch Expression
```
int result = switch(variableToTest){
	case constantExpression1 -> 5;
	case constantExpression2, constantExpression3 -> {
		yield 10;
	}
	default -> 20;
};
```

