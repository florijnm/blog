---
titel: Understanding Java Operators
datum: 16-01-2025
hoofdstuk: 2
tags:
  - OCP
  - Java
  - Operators
  - Tertary
---
In Java heb je drie verschillende soorten operators:
1. Unary
2. Binary
3. Ternary

### Operator Precedence
In principe worden dezelfde regels als in de wiskunde gehandhaaft:

```
var per = 2 * height + 2 * length;

^
| 

var per = ((2 height) + (2 * length));
```

In de volgende tabel is de 'order' van operator precedence opgenomen, van hoog naar laag


| Operator                        | Symbols and examples                                                       | Evaluation    |
| ------------------------------- | -------------------------------------------------------------------------- | ------------- |
| Post-unary operators            | expression**++**, expression**--**                                         | Left-to-right |
| Pre-unary operators             | **++**expression, **--**expression                                         | Left-to-right |
| Other unary operators           | *-*, *!*, *~*, *+*, *(type)*                                               | Right-to-left |
| Cast                            | **(Type)**reference                                                        | Right-to-left |
| Multiplication/division/modulus | * ,  /, %                                                                  | Left-to-right |
| Addition/subtraction            | *+*, *-*                                                                   | Left-to-right |
| Shift operators                 | *<<*, *>>*, *>>>*                                                          | Left-to-right |
| Relational operators            | *<*, *>*, *<=*, *>=*, *instanceof*                                         | Left-to-right |
| Equal to/not equal to           | *==*, *!=*                                                                 | Left-to-right |
| Logical AND                     | *&*                                                                        | Left-to-right |
| Logical exclusive OR            | *^*                                                                        | Left-to-right |
| Logical inclusive OR            | *\|*                                                                       | Left-to-right |
| Conditional AND                 | *&&*                                                                       | Left-to-right |
| Conditional OR                  | *\|\|*                                                                     | Left-to-right |
| Ternary operators               | boolean expression *?* expression1 : expression2                           | Right-to-left |
| Assignment operators            | *=*, *+=*, *-=*, **=*, */=*, *%=*, *&=*, *^=*, *\|=*, *<<=*, *>>=*, *>>>=* | Right-to-left |
| Arrow operator                  | *->*                                                                       | Right-to-left |
### Applying Unary Operators
Een *unary* operator is eentje die precies één variabel, of operand, nodig heeft om te kunnen functioneren.

| Operator           | Examples   | Description                                                                                                                          |
| ------------------ | ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Logical complement | !a         | Inverts a boolean's logical value                                                                                                    |
| Bitwise complement | ~b         | Inverts all 0s and 1s in a number                                                                                                    |
| Plus               | +a         | Indicates a number is positive, although numbers are assumed to be positive in Java unless accompanied by a negative unary operator. |
| Negation or minus  | -d         | Indicates a literal number is negative or negates an expression                                                                      |
| Increment          | e++<br>++f | Increments a value by 1                                                                                                              |
| Decrement          | g--<br>--h | Decrements a value by 1                                                                                                              |
| Cast               | (String) i | Casts a value to a specific *type*                                                                                                   |
Je kunt, logisch gezien, geen operators gebruiken op verkeerde types: je kunt geen logical complement gebruiken op een integere waarde, en geen numerieke operators op booleans.

Wat belangerijk is om te weten is hoe de *pre* en *post* increments werken:

| Operator       | Example | Description                                               |
| -------------- | ------- | --------------------------------------------------------- |
| Pre-increment  | ++w     | Increases the value by 1 and returns the *new* value      |
| Pre-decrement  | --w     | Decreases the value by 1 and returns the *new* value      |
| Post-increment | w++     | Increases the value by 1 and returns the *original* value |
| Post-decrement | w--     | Decreases the value by 1 and returns the *original* value |

```
int parkAttendance = 0;
System.out.println(parkAttendence); //0
System.out.println(++parkAttendence); //1
System.out.println(parkAttendence--); //1
System.out.println(parkAttendence); //0
```

#### Binary Arithmetic Operators

| Operator       | Example | Description                                                          |
| -------------- | ------- | -------------------------------------------------------------------- |
| Addition       | a + b   | Adds two numeric values                                              |
| Subtraction    | c - d   | Subtracts two numeric values                                         |
| Multiplication | e * f   | Multiplies two numeric values                                        |
| Division       | g / h   | Divides one numeric value by another                                 |
| Modulus        | i % j   | Returns the remainder after division of one numeric value by another |
De multiplicative operators hebben zoals gewoonlijk een hogere prioriteit.

`int price = 2 * 5 + 3 * 4 - 8;` = `int price = (2 * 5) + (3 * 4) - 8;`
#### Floor value
Een *floor value* is het getal *voor* de komma bij een numerieke waarde.
Bij `4.9999999` is dit dus 4, maar ook bij `4.1`.

### Numeric Promotion
Er zijn een paar regels die je moet volgen als het gaat om numerieke promotie, wanneer je operators gebruikt.

1. If two values have different data types, Java will automatically promote one of the values to the larger of the two data types.
2. If one of the values is integral and the other is floating-point, Java will automatically promote the integral value to the floating-point value's data type.
3. Smaller data types, namely, byte, short, and char, are first promoted to int any time they're used with a Java binary arithmetic operator with a variable (as opposed to a  value), even if neither of the operands is int.
4. After all promotion has occurred and the operands have the same data type, the resulting value will have the same data type as its promoted operands.

### Assigning Values
Voor het assignen van waardes kunnen verschillende operators worden gebruikt:

| Operator                  | Example       | Description                                                                                                                                             |
| ------------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Assignment                | `int a = 50;` | Assings the value on the right to the variable on the left.                                                                                             |
| Addition assignment       | `a += 5;`     | Adds the value on the right to the variable on the left and assigns the sum to the variable                                                             |
| Subtraction assignment    | `b -= 0.2`    | Subtracts the value on the right from the value on the left and assigns the difference to the variable                                                  |
| Multiplication assignment | `c *= 100`    | Multiplies the value on the right with the variable on the left and assigns the product to the variable                                                 |
| Division assignment       | `d /= 4`      | Divides the variable on the left by the value on the right and assigns the quotient to the variable                                                     |
| Equality                  | `a == 10`     | Primitieven: Returns true if the two values represent the same value<br><br>Objecten: Returns true if the two values *reference* the same object        |
| Inequality                | `a != 10`     | Primitieven: Returns true if the two values represent different values<br><br>Objecten: Returns true if the two values do not reference the same object |
#### Casting
Casting is een *unary* operator waar een data type expliciet wordt geinterpreteerd als een andere data type. Het is optioneel. Het is verplicht bij wanneer je een groter object in en kleinere type wilt stoppen, zoals een *float* naar een *int*.
### Relational Operators
Een relational operator vergelijkt twee expressions en returnt een *boolean*.

| Operator                 | Example               | Description                                                                                                                                                              |
| ------------------------ | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Less than                | `a < 5`               | Returns true if the value on the left is strictly *less than* the value on the right                                                                                     |
| Less than or equal to    | `a <= 5`              | Returns true if the value on the left is *less than or equal to* the value on the right                                                                                  |
| Greater than             | `3 > 5`               | Returns true if the value on the left is *strictly greater than* the value on the right                                                                                  |
| Greater than or equal to | `4 >= 3`              | Returns true if the value on the left is *greater than or equal* to the value on the right                                                                               |
| Type comparison          | `e instanceof String` | Returns true if the *reference* on the left size is an *instance* of the type on the right side (class, interface, record, enum, annotation). Null will result in false. |

### Logical Operators
Je hebt *logical operators*, dit verwijst naar booleans.
Je hebt *bitwise operators*, dit verwijst naar numerieke data types.

| Operator             | Example  | Description                                                    |
| -------------------- | -------- | -------------------------------------------------------------- |
| Logical AND          | `a & b`  | Value is *true* if both values are true                        |
| Logical inclusive OR | `c \| d` | Value is true if at least on of the values is true.            |
| Logical exclusive OR | `e ^ f`  | Value is true only if one value is true and the other is false |

### Conditional Operators

| Operator        | Example    | Description                                                                                                               |
| --------------- | ---------- | ------------------------------------------------------------------------------------------------------------------------- |
| Conditional AND | `a && b`   | Value is true only if both values are true. If the left side is false, then the right side will not be evaluated.         |
| Conditional OR  | `c \|\| d` | Value is true if at least one of the values is true. If the left side is true, then the right side will not be evaluated. |

### Ternary Operator
De ternary operator is een conditionele operator en ziet er als volgt uit:
`? : `
`booleanExpression ? expression1 : expression2;`


