---
titel: Creating Objects
datum: 07-01-2025
hoofdstuk: 1
tags:
  - OCP
  - Java
  - Objects
---
Een object in een instantie van een klasse. Klassen zijn blauwdrukken voor objecten.

## Calling constructors
Om een nieuw object aan te maken kan het woord `new` gebruikt worden, als volgt:
`Dog dog = new Dog();`

In dit voorbeeld is `Dog` het *type* van de *instantie* `dog`.

Een constructor *heeft geen return type*.

De volgende code is dus wel valide, maar wordt niet aangeroepen met `new Dog()`:
```
package abc;

public class Dog{
	public void Dog(){
	
	}
}
```

Dog() is hier geen constructor, omdat deze methode een return type `void` heeft.

Als default geeft de compiler een "do nothing" constructor mee. Je kunt dus het object aanmaken en de methoden en velden gebruiken.

## Instance Initializer Blocks
Een *code block* is de code tussen twee brackets ( { } )

*Instance initializers* zij de code blocks die buiten methodes bestaan.

Het *balanced parentheses problem* is wanneer brackets niet aansluiten, bijvoorbeeld te weinig of te veel {  voor het aantal } dat er is,

Fields en Instance initializer blocks worden in volgorde uitgevoerd zoals in het bestand.

De constructor runt pas *nadat* alle initializer blocks zijn uitgevoerd.
