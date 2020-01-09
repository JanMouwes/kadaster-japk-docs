## Complexe (organisatie-interne) interfaces

**Beschrijving**

Vaak vanuit enterprise architectuur gedreven, universeel toepasbare interfaces waarvan de specifieke invulling van applicatie tot applicatie verschilt.

**Waarom**

Op een hoog abstractienivo lijkt het handig als alle systemen binnen een organisatie één taal spreken. In de praktijk leidt dit vaak tot zulke abstracte interfaces, dat alle applicaties hun eigen interpretatie van die taal hanteren. Door de interpretatieverschillen verergert een organisatie-breed interface protocol vaak het communicatieprobleem tussen applicaties, in plaats van dat het dat oplost. Bovendien remt zo'n interface de innovatie: Om een nieuwe versie van 'de interface' te introduceren, moeten álle applicaties over naar een nieuwe versie.

**Tips en hulpmiddelen**

Dit soort interfaces zijn meestal herkenbaar aan veel of grote XSD's, vaak gegenereerd vanuit een modelleertool. Indicatoren van wanneer deze interfaces meer op een ivoren toren gericht zijn dan op de realiteit: 
* Veelvuldig terugkomen van termen als 'generiek' en 'universeel'
* Meerdere versies van deze XSDs tegelijk in één applicatie
* Generieke key-value paren in de interface, voor data die niet in de interface zit.
