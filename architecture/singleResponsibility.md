# Opsplitsing van verantwoordelijkheden
**Stelregel:** Logica alleen in de applicatie, data alleen in de database

'TODO:' Er zijn andere systeem architecturen mogelijk, waarvoor deze verdeling niet geldt

### Beschrijving

In een ‘ideale’ systeemarchitectuur worden verschillende verantwoordelijkheden aan verschillende componenten toegekend. Een logische verdeling zou alle logica in de applicatie plaatsen en alle data in de database opslaan. Dit ideaalbeeld is lang niet altijd realistisch. Afwijkingen maken het systeem complexer. Deze afwijkingen kunnen verschillende kanten op zijn: logica in de database (bv. stored procedures) en data bij de applicatie (persistentie op het file systeem).

### Waarom
* Zodra applicatielogica over verschillende componenten wordt verdeeld, worden vooral foutpaden in de code een tricky aangelegenheid. Juist die foutpaden zijn nogal eens een ondergeschoven kindje in het testproces.

* Uitzoeken van problemen over verschillende log files heen, als deze al te vinden en te correleren zijn, is lastiger dan wanneer de flow in 1 bestand te volgen is.

* Applicatie code en database code worden nogal eens in verschillende code bases opgeslagen en volgen soms een net-niet afgestemd release proces. Logica in verschillende code bases vergroot het risico op incompatibiliteit, data in verschillende bronnen vergroot het risico op inconsistenties.

* Unit testen werken makkelijker tegen een initieel lege of gedefinieerde dataset. Testen tegen een in-memory database zorgt er voor dat de unit testen niet afhankelijk zijn van de vulling van een database. Logica in de database is vaak database-afhankelijk, waardoor de unit testen niet meer tegen een in-memory database kunnen worden gedraaid

### Tips en hulpmiddelen
Probeer de applicatie te draaien op een vers geïnstalleerd systeem, kijk of er environment variabelen of data files nodig zijn om de applicatie werkend te krijgen. Kijk of het database schema stored procedures of views met complexe logica bevat. Vooral database triggers die bij een commit worden uitgevoerd zijn lastig, omdat de applicatie-code dan al veel verder is dan de plek waar de fout gemaakt werd. Draai de unit testen met een in-memory database.

### Grenswaarden
Deze richtlijn is niet zwart-wit, er zijn diverse grensgevallen en redenen om er van af te wijken. Een paar voorbeelden:

* Logica die nodig is om de integriteit van de database te bewaken

    Vrijwel altijd heeft het database-component de verantwoordelijkheid om zijn eigen integriteit te garanderen. Daar is een stuk logica voor nodig, al is het maar een primary key constraint op een tabel. Een bijzondere eigenschap van deze logica is dat hij niets aan de data verandert.

* Systeem configuratie: In JNDI of (applicatie-externe) configuratie files

* Strict gesproken kun je de database connectie settings ook zien als data. Zonder deze ‘data’ zou je de database nooit kunnen benaderen. Deze data kan logischerwijs niet in de database worden opgeslagen.

* Indexes

* Deze database logica zorgt wel voor veranderingen in de database, maar alleen van gegevens die niet zichtbaar zijn voor de applicatie.

* Views

* Data die niet in een database staat

* Property files

* Vanwege performance is het soms nodig om logica in een database uit te voeren