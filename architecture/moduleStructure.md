# Module structuur: opdeling, naamgeving, aantal, niet overbodig
### Beschrijving
Als er conventies zijn voor de indeling en naamgeving van modules: kijk of deze gevolgd worden. Als er geen conventies zijn: kijk of de modules op hoog nivo de architectuur-blokken en/of functionaliteit weerspiegelen. Kijk of de naamgeving logisch is, of er geen functionaliteit onnodig verdeeld is over de verschillende modules en of de afhankelijkheden tussen modules zijn zoals je zou verwachten. Kijk ten slotte of alle modules meegenomen worden in het bouwproces

### Waarom
Vaak zijn modules het abstractie-nivo waarop je met niet-technische mensen over de code kunt communiceren. In die module zitten de web pagina’s die je te zien krijgt, daar zit de beheer-applicatie, of daar zit alle logica, die vanuit de andere modules wordt aangeroepen.

### Tips en hulpmiddelen
Gebruik een dependency tree vanuit je ontwikkelomgeving of build tool.