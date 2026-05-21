---
titel: Garbage collection and destroying objects
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - GarbageCollection
  - Memory
---

### Destorying Objects
De *Java Virtual Machine* zoekt voor objecten die niet meer gebruikt worden en ruimt ze dan op uit het geheugen.

Alle java objecten worden opgeslagen op de *memory heap* van het programma. De heap, ookwel de *free store* is een grote pool van ongebruikt geheugen die voor je java applicatie is gereserveerd. 

Wanneer een object niet meer wordt gebruikt en *niet meer toegankelijk is* is deze *eligible* voor garbage collection. Wanneer de garbage collection draait is niet door de ontwikkelaar te regelen. Wel kunnen we de JVM aanraden om het uit te voeren, maar Java kan dit gewoon negeren dus er is geen zekerheid: `System.gc()`.

### Tracing Eligibility
Hoe weet de JVM wanneer een object eligible is? Het monitort constant de objecten en wacht tot het object niet langer dat geheugen nodig heeft. Het object blijft op de heap tot het niet meer *reachable* is, dat gebeurt wanneer:
1. Het object heeft geen referenties meer die ernaar verwijzen
of:
2. Alle referenties naar het object zijn out-of-scope

