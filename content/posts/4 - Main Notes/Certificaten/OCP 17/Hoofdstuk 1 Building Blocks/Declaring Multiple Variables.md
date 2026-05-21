---
titel: Declaring Multiple Variables
datum: 09-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
---
Je kunt meerdere variabelen declareren in dezelfde statement:

```
String s1, s2;
String s1 = "String2", s1;
String s1 = "String1", s2 = "String2";
```

Je kunt meerdere variabelen *declareren* zolang ze van hetzelfde *type* zijn.
*Initializeren* van deze variabelen moet apart voor iedere:

```
int num, String value; // Compileert niet! Niet hetzelfde type!
String s1, s2 = "String"; // s1 heeft geen waarde!
```

