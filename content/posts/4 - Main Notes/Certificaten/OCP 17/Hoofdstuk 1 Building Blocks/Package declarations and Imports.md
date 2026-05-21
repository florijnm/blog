---
titel: Declarations and Imports
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - PackageManagement
---
Java stopt klassen in *packages*. Dit houdt in dat als je code gebruikt vanuit libraries je de compiler moet vertellen *waar* de klassen zich bevinden.

Als je dit niet doet kun je `error: cannot find symbol` krijgen.

```
public class NumberPicker{
	public static void main(String[] args){
		Random r = new Random();
		System.out.println(r.nextInt(10));
	}
}
```

Het bovenstaande voorbeeld compileert dus niet, omdat nergens een import van Random wordt gedaan.

Het volgende voorbeeld compileert wel:

```
import java.util.Random;
public class NumberPicker{
	public static void main(String[] args){
		Random r = new Random;
		System.out.println(r.nextInt(10));
	}
}
```

## Wildcards
Een wildcard (`*`) zorgt ervoor dat *alle klassen in een package* tegelijk worden geimporteerd.

Wat belangrijk is om te weten is dat een wildcard *niet* de *child-packages* importeerd. 

Met een wildcard zoals het volgende is de klasse `Random` beschikbaar:
`import java.util.*`

Maar niet de subpackage `java.util.concurrent`.

Het gebruiken van een wildcard resulteert *niet* in een trager programma. De compiler zorgt ervoor dat er alleen wordt geimport wat wordt gebruikt. Het zorgt er dus voor dat de import-lijst korter wordt, ten kostte van leesbaarheid van geimporteerde klassen.

## Redundant Imports
Er is één package die Java automatisch importeert, dat is `java.lang`. 
Hierin zitten klassen zoals *System*. 

Als je dus handmatig deze package importeert is die *redundant*, overbodig.

## Naming conflicts
Klasnamen hoeven in Java niet uniek te zijn, zolang ze maar in verschillende packages zitten. 

Handmatig een klasse benoemen voor import:
`import java.util.Date;`

Neemt voorrang op alle wildcards. Hierdoor compileert het volgende voorbeeld:
```
import java.util.Date;
import java.sql.*;
```

Ondanks dat in de java.sql package ook een Date klasse zit.

Stel er zijn wel twee dezelfde hetende imports, zoals:

```
import java.util.Date;
import java.sql.Date;
```

Dan vertelt de compiler je dat de imports *ambiguous* zijn.