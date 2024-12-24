# Managementsamenvatting: Festo Packingstation Project
Voor dit project hebben we ons gericht op het analyseren en optimaliseren van het Festo Packingstation-systeem. Het doel was om de werking, communicatieprotocollen en interactie tussen verschillende componenten en stations te onderzoeken en te verbeteren.
Analyse van het Huidige Systeem
We hebben het huidige systeem grondig geanalyseerd, met specifieke aandacht voor:
1.	Communicatieprotocollen: Het gebruik van SCADA en IO-Link binnen onze opstelling.
2.	Opstelling en componenten: Begrijpen van de fysieke configuratie en de werking van de belangrijkste stations in het systeem.
3.	Gegevensuitwisseling: Analyseren van hoe productinformatie (zoals type, kleur, gewicht en verpakkingsstatus) tussen stations wordt uitgewisseld.


## Interactie via SCADA en IO-Link
Het systeem maakt gebruik van SCADA voor centrale monitoring en aansturing. Via IO-Link worden gegevens van sensoren en actuatoren binnen de stations verzameld en verwerkt. Deze combinatie zorgt ervoor dat:
•	Productinformatie zoals kleur, gewicht en verpakkingsstatus betrouwbaar wordt overgedragen.
•	Stations real-time kunnen communiceren om de verpakkingsprocessen te coördineren.


## Workflow van het Packaging Station
Het packaging station doorloopt de volgende stappen:
1.	Productinvoer: Gesorteerde producten worden vanuit het sorting station naar het packaging station getransporteerd. Sensoren via IO-Link detecteren de aanwezigheid en kenmerken van een product.
2.	Herkenning en Validatie: SCADA registreert en valideert de productinformatie zoals kleur, gewicht, en verpakkingsstatus.
3.	Verpakkingsvoorbereiding: Het station stelt de verpakkingslijn in op basis van de productkenmerken en voert verpakkingsmaterialen aan.
4.	Verpakken: Producten worden automatisch in verpakkingsmateriaal geplaatst. 
5.	Terug zetten op de band: De verpakte producten worden via de x-as teruggeplaatst op de conveyor voor verder transport.
6.	Rapportage: SCADA registreert alle procesgegevens en rapporteert eventuele afwijkingen voor aanpassingen.




## Verdeling van Taken
Om de verschillende aspecten van het project efficiënt aan te pakken, zijn de taken als volgt verdeeld:
•	Luuk: Implementatie en configuratie van het SCADA-systeem in combinatie met de besturing.
•	Milan: Ontwerpen van flowcharts, uitvoeren van tests, en afstellen van processen.
•	Thijs: Overzicht en documentatie van het systeemontwerp en ondersteuning bij tests.
•	Joost: Aanpassen van 3D-prints en accorderen en afstellen van de tests.
•	Jur: Schrijven van deze managementsamenvatting en ondersteuning bij tests en afstelling.


## Kenmerken van het Systeem
•	Invoer: Gesorteerde producten en verpakkingsmaterialen worden verwerkt in de verpakkingseenheid.
•	Uitvoer: Verpakte producten die gereed zijn voor opslag of verzending.
•	Communicatie: Het systeem is volledig afhankelijk van SCADA en IO-Link voor gegevensuitwisseling en procescontrole.

