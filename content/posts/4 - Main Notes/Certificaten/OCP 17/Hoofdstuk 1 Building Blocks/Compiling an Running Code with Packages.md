---
titel: Compiling an Running Code with Packages
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - Compiling
---
## Compiling
Met het commando `javac` kunnen *.java* bestanden gecompileerd worden.

Ook ik verschillende packages. Stel er zijn twee packages onder de map ~/OCP, namelijk packagea en packageb.

Dan kan het commando `javac *.java` wel worden uitgevoerd, maar worden de klassen onder de packages niet gecompiled. Wildcards pakken *niet* de subdirectories op.

Wat wel werkt is:
`javac ~/OCP/packagea/*.java` en `javac ~/OCP/packageb/*.java`.

Met de optie `-d` kan de *target* directory worden opgegeven. Dan worden alle gebouwde bestanden daar heen verplaatst. De *structuur* van de bestanden wordt behouden, dus bij het volgende commando:

`javac -d target ~/OCP/packagea/*.java && javac ~/OCP/packageb/*.java`

Bevinden de klassen zich onder *target/packagea/* en */target/packageb*
## Running
Met het commando:
`java -cp target target/Program`
Wordt java uitgevoerd. 
De optie `-cp` vertelt aan de compiler waar de benodigde gecompileerde klassen kunnen worden gevonden.

## Jar files
Een *JAR* (Java Archive) is een soort zip bestand die Java class bestanden bevat.

Je kunt een JAR maken door het commando:
`jar -cvf myNewJar.jar .`

Hier kunnen de volgende opties worden meegegeven

| Optie | Beschrijving                                                            |
| ----- | ----------------------------------------------------------------------- |
| -c    | Maakt een nieuwe Jar file                                               |
| -v    | Print details van het bouwen                                            |
| -f    | JAR filename                                                            |
| -C    | Directory waar de files staan die nodig zijn voor het bouwen van de JAR |

