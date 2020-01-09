# Buildstraat
Kijk of het bouw-, integratie- en deployment proces van deze applicatie past binnen de buildstraat

> **Note:** 'Omdat de precieze invulling van de buildstraat verschilt van organisatie tot organisatie, kunnen we hier slechts een voorbeeld geven. Pas eventeel de Waardering-kolom aan aan de maturity van je buildstraat'


| Tool                      | Waardering                                                                 | 
| --------------------------|:--------------------------------------------------------------------------:| 
| Versiebeheer              | Subversion = groen; overig versiebeheer = oranje; geen versiebeheer = rood | 
| Build tool                | Maven 3 = groen; Maven 2 = oranje; overig = rood                           |  
| Build server              | Jobs in Jenkins = groen; geen jobs = rood                                  | 
| Automatische deployment   | Nightly deployments = groen; incidenteel te triggeren vanuit Jenkins = oranje; overig = rood      | 
| Metrics analyse           | Sonar ingeregeld = groen; Geen Sonar ingeregeld = rood                      | 