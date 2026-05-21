---
title: Maven dependencies
date: 06-01-2025
tags:
  - Maven
  - Dependencies
  - "#PackageManagement"
  - "#Java"
---
Soms kan het zo zijn dat Maven lokale dependencies niet herkent, terwijl deze wel correct zijn geimporteerd. 

Mogelijke oplossingen:

| 1   | Reload All Maven Projects Incrementally volgens de reload knop in de Maven Tab. |
| --- | ------------------------------------------------------------------------------- |
| 2   | Generate Sources and Update Folders For All Projects                            |
| 3   | Herstart de IDE                                                                 |
Werkt het nog niet?

Dan kan via het volgende commando de lokale dependencies worden verwijderd en geforceerd opnieuw worden gedownload:

```
mvn dependency:purge-local-repository
```

Met het commando:
```
mvn clean install -U
```
Kan het ook werken, maar dat wordt als het goed is automatisch gedaan bij de purge.