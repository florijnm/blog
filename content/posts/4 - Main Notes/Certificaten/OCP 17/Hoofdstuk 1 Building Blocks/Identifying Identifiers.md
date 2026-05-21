---
titel: Identifying Identifiers
datum: 09-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - NamingConventions
---
Een *identifier* is de naam van een *variabele*. Een variabel is een naam voor een stukje geheugen waar data wordt opgeslagen.

Er zijn vier regels die gelden bij de benaming van zulke identifiers:

| Rule                                                                                                                            | Example                                                               |
| ------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Identifiers must begin with *a letter*, *a currency symbol*, or a *_*                                                           | `String _test = "COMPILEERT"` <br>`String $test = "COMPILEERT"`       |
| Identifiers can include numbers *but not start with them*                                                                       | `String 3test = "COMPILEERT NIET!"`<br>`String test3 = "COMPILEERT!"` |
| A single underscore *_* is not allowed as an identifier                                                                         | `String _ = "COMPILEERT NIET!"`                                       |
| You cannot use the same name as a Java reserved word, but you *can* use versions of the keyword because Java is case-sensitive. |                                                                       |


| Reserved words |           |              |            |
| -------------- | --------- | ------------ | ---------- |
| Abstract       | assert    | public       | if         |
| boolean        | break     | return       | implements |
| byte           | continue  | short        | import     |
| case           | default   | static       | instanceof |
| catch          | do        | strictfp     | int        |
| char           | double    | super        | interface  |
| class          | else      | switch       | long       |
| const          | enum      | synchronized | native     |
| final          | extends   | this         | new        |
| finally        | private   | throw        | package    |
| float          | protected | throws       | volatile   |
| for            | try       | transient    | while      |
| goto           | void      |              |            |

## Legale voorbeelden
```
long okidentifier;
float $OK2Identifier;
boolean _alsokbutKnowsonice$;
char __SStillOkbutKnowsonice$;
```

## Illegale voorbeelden
```
int 3DPointClass; //Identifiers cannot begin with a number.
byte hollywood@vine; //@ is not a letter, digit, $ or _
String *$coffe; // * is not a letter, digit, $ or _
double public; // public is a reserved word
short _; // a single underscore is not allowed
```
