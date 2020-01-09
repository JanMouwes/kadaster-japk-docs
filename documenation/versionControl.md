# Versiebeheer tool
### Beschrijving
Voor ontwikkelaars een open deur, voor anderen is het minder vanzelfsprekend

Staat de volledige applicatie in één versiebeheer systeem? Is dat inclusief de documentatie (architectuur, functioneel en technisch), configuratieparameters en omringende scripts? Geldt dat ook voor testscripts en testdata?

### Waarom
Als documentatie verspreid staat, weet je zeker dat op termijn een deel kwijt raakt, veroudert of op een andere manier out-of-sync raakt. Het is waarschijnlijk dat de code wel bewaard blijft. Als de overige deliverables in de buurt van de code blijven, is de kans het grootst dat ze niet verdwijnen door de tand des tijds.

### Grenswaarden
De wiki pagina van een applicatie staat vaak op een andere plek dan de code. Soms is het mogelijk om een wiki pagina te genereren vanuit het versiebeheer systeem, maar dat betekent wel dat de wiki pagina aangepast moet worden in het versiebeheer systeem, in plaats van rechtstreeks op de wiki pagina. Met Git (README.md files) vervaagt de grens tussen wiki en code