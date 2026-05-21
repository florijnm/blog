[[Aquamarijn]] [[Services]] [[Keten]]

Team Aquamarijn werkt vooral in de Persoonsgerichte beoordeling van de keten. De keten is als volgt

**--Intake--**
De keten begint bij de intake. Hier komen berichten binnen vanuit externe applicaties of ketenpartners, zoals het Openbaar Ministerie.

Een paar van deze applicaties zijn:
	- VHIS (Voorlopige Hechtenis Service)
	- TRIS (Transactie Intake Service)
	- DNAVIS(DNA-Veroordeelden Intake Service)
	- GIS (Generieke Intake Service) 
	- ODR (Opdrachtenregister) ***(Aquamarine)***

**VHIS**
[Algemene beschrijving - Voorlopige Hechtenis Service (VHIS) - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/VHIS3)
	Voorlopige Hechtenis betekent dat, als een persoon wordt verdacht van het plegen van een strafbaar feit, een rechter kan besluiten om de persoon alvast in *voorlopige* hechtenis te plaatsen in afwachting van de veroordeling.

**TRIS**
[Home - Transactie Intake Service (TRIS) - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/TRIS/.Home+v7.1.1)
	Deze service verzorgt te intake voor transacties. De aangeboden berichten worden syntactisch en semantisch gevalideerd en daarna als generieke gebeurtenis naar GIS gezet.

**DNAVIS**
[Algemene beschrijving - DNAV Intake Service - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/DNAVIS/.Algemene+beschrijving+v1.0_Eerste_implementatie)
	-- Kon geen generieke informatie vinden.

**GIS**
[Algemene beschrijving - Generieke Intake Service (GIS) - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/GIS/.Algemene+beschrijving+v1.4.0)
	De generieke intake service. Iedere intake service applicatie die stuurt, het bericht dat zij ontvangen door naar GIS om vervolgens naar Persoonsgericht beoordeling te sturen.

**ODR**
[Algemene beschrijving - Opdrachtenregister - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/ODR0100)
	Het opdrachtenregister is een centraal register waar verzoeken tot uitvoering van strafrechtelijke beslissingen worden geregistreerd als routeringsopdrachten en opdrachtcomponenten. 

--**Persoonsgericht beoordeling**--
Persoonsgericht beoordeling krijgt vanuit GIS een bericht. Bij dit onderdeel van de keten wordt informatie zoals de context toegevoegd door het ODR te benaderen. 

De applicaties die in deze fase van de keten zitten zijn:
	- DSB (Dirigent Strafrechtelijke Beslissingen) (***Aquamarine*)
	- IDA (Informatiedienst Aice) (*Aquamarine*)

**DSB**
[Algemene beschrijving - Dirigent Strafrechtelijke Beslissing - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/DSB001/.Algemene+beschrijving+v2.37_pre)
	De Dirigent Strafrechtelijke Beslissingen is het systeem voor routeren van de strafrechtelijke beslissingen. Alle strafrechtelijke beslissingen moeten via deze applicatie lopen. De DSB gaat een persoonsgerichte beoordeling doen en bepalen in welke volgorde sancties moeten worden uitgevoerd. Daarnaast zorgt de DSB ervoor dat bij interventies en negatieve aflopen de juiste vervolgstappen worden ondernomen.

**IDA**
[Communicatie Informatiedienst AICE (IDA) met bronnen - Domeinarchitectuur Executie - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/DAEX/Communicatie+Informatiedienst+AICE+%28IDA%29+met+bronnen)
	De IDA is verantwoordelijk voor het ontsluiten van zaakinhoudelijke gegevens vanuit diverse bronnen naar afnemers binnen AICE. In ODR zijn deze gegevens (behalve Levita en OM-Afdoening) als referentie gekoppeld aan een opdracht of opdrachtcomponent. In ODR zijn dus niet de fysieke gegevens vastgelegd, maar een referentie naar deze gegevens. IDA zal op basis van een verzoek ODR raadplegen voor de referenties en zal per referentie de daadwerkelijke bron benaderen.
**ROP**
[Algemene beschrijving - Raadplegen Opdrachten - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/ROP)
	ROP staat voor Raadplegen Opdrachten.


**--Coördinerend--**
Deze fase is de uitvoerende fase. Nadat besloten is wat gedaan moet worden wordt hierin de daadwerkelijke actie ondernomen en uitgezet naar de relevante diensten. Deze services zijn als volgt:
	- COMO (Coördineren Geldelijke Sanctie)
	- COVI
	- COSI (***Aquamarine***)
	- SYTSE (***Aquamarine****)

**COSI**
[Communicatie Informatiedienst AICE (IDA) met bronnen - Domeinarchitectuur Executie - CJIB Confluence (minjus.nl)](https://confluence.shs.cjib.minjus.nl/display/DAEX/Communicatie+Informatiedienst+AICE+%28IDA%29+met+bronnen)
	Krijgt een bericht van DSB over het uitvoeren of verwerken van een interventie. Vanuit AFDA kan een bericht worden ontvangen over de afloop. Vervolgens levert COSI richting IRS een aanlevering van de strafrechtelijke beslissing of de aanlevering van de gebeurtenis van de strafrechtelijke beslissing.

**SYTSE**
	Systeem JeugdTaakstraffen. 

**--Afdoen--**

AFDA (Aquamarijn)



