---
titel: Understanding Data Types
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - DataTypes
  - String
  - boolean
  - int
  - byte
  - long
  - float
  - double
  - char
---
Java heeft twee soorten data typen: *primitieve* typen en *referentie* typen.

## Primitives

Primitieve data types houden de waarde in memory vast waar ze gealloceerd zijn.

Er zijn acht ingebouwde data types die primitief zijn. Een primitief is *geen* object in Java. Het is één waarde die in het geheugen wordt opgeslagen, zoals een nummer.

| Keyword | Type                         | Min value      | Max value     | Default value | Example |
| ------- | ---------------------------- | -------------- | ------------- | ------------- | ------- |
| boolean | `true` of `false`            | n/a            | n/a           | false         | true    |
| byte    | 8-bit integrale waarde       | -128           | 127           | 0             | 123     |
| short   | 16-bit integral value        | -32768         | 32767         | 0             | 123     |
| int     | 32-bit integral value        | -2.147.483.648 | 2.147.483.647 | 0             | 123     |
| long    | 64-bit integral value        | -2^63          | 2^63 - 1      | 0L            | 123L    |
| float   | 32-bit floating-point value  | n/a            | n/a           | 0.0f          | 123.45f |
| double  | 64-bit floating-poiont value | n/a            | n/a           | 0.0           | 123.456 |
| char    | 16-bit Unicode value         | 0              | 65535         | \u000         | 'a'     |
Een *String* is geen primitief, maar een object!!

De waarde van de numerieke primitieven is niet van -128 tot 128, omdat elke van deze typen een byte reserveerd voor de negatieve. Dit betekent dat het *signed* is.

*Unsinged* betekent dat het strikte positieve waardes zijn, dus 0 tot 255.

Een *Long* dient een `L` achter de waarde te hebben, anders ziet de compiler de waarde als een int.

Een float dient een `F` achter de waarde te hebben, anders ziet de compiler het als een double.

`long max = 3123456789` --> dit compileert niet
`long max = 3123456789L` --> dit compileert wel

Je mag underscores (`_`) in getallen stoppen om ze leesbaarder te maken:
`long max = 3_123_456_789L` --> compileert wel
Ze mogen alleen *niet* beginnen of eindigen.
`long max _3_123_456_789L` --> compileert niet


## References
Referenties houden *niet* zelf de waarde vast, maar verwijzen door naar een object in het geheugen door het geheugenadres te bewaren, zoals een *pointer* in C++.

Alle referenties zijn dezelfde grootte in geheugen, het object waar het naar verwijst kan verschillen.

Een voorbeeld van zo'n reference is het type *String*. 
`String greeting;`
`greeting` is een referentie.
Een referentie kan via twee manieren waardes krijgen: door het van een onder object te krijgen en door een nieuw object te maken met `new`.

`String greeting = new String("Hoe gaat het?");`
`greeting` bevat het geheugenadres van het object `String("Hoe gaat het?")

Als vuistregel kan worden aangenemen dat primitieven altijd *lage letters* hebben, en een referentie altijd begint met *hoofdletter*. Op primitieven kunnen geen methode worden aangeroepen, maar op referenties wel:
```
String hoi = "Hoi";
int length = hoi.length(); //COMPILEERT
int bad = length.length(); //COMPILEERT NIET
```

## Wrapper klas
Elke primitieve heeft zijn eigen 'wrapper' klasse die ervoor zorgt dat er een referentie van kan worden gemaakt.

| Primitive | Wrapper     | Example                     |
| --------- | ----------- | --------------------------- |
| boolean   | `Boolean`   | `Boolean.valueOf(true)`     |
| byte      | `Byte`      | `Byte.valueOf((byte)1)`     |
| short     | `Short`     | `Short.valueOf((short)1)`   |
| int       | `Integer`   | `Integer.valueOf(1)`        |
| long      | `Long`      | `Long.valueOf(123)`         |
| float     | `Float`     | `Float.valueOf((float)1.0)` |
| double    | `Double`    | `Double.valueOf(1.0)`       |
| char      | `Character` | `Character.valueOf('c')`    |

## Defining text blocks
```
"Java Study Guide"
	By Scott & Jeanne

String value = """
   "Java Study Guide"
	   By Scott & Jeanne
"""
```

`String code = "\"Java Study Guide\"\n   By Scott & Jeanne"`

| Syntax | Value                     |
| ------ | ------------------------- |
| \n     | New line in String        |
| \      | " i.p.v. een einde String |
