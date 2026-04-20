# Structuur van een Submission Information Package (SIP)
In de afbeelding is een voorbeeld van de structuur weergegeven van de informatieobjecten en bestanden in een SIP.  Elk informatieobject kan een aggregatie zijn. 

![Structuur van de informatieobjecten en bestanden in een SIP](images/sip2.png)


## Sidecar-structuur
De export uit het bronsysteem moet een sidecar-structuur hebben.
In deze structuur zit de inhoud in een directory-structuur: elk aggregatieniveau van de informatieobjecten is een map. Een bestand kan op elk aggregatieniveau in de map zitten. Ook als daar ook nog een aggregatie van informatieobject beschikbaar is. Denk aan een e-mail met bijlagen of een website met de webpagina’s. 
Elk informatieobject en elk bestand heeft zijn eigen MDTO metagegevensbestand. In de sidecar moet het versienummer van de betreffende MDTO-versie zijn opgenomen (zie [MDTO.xml](https://github.com/NationaalArchief/MDTO-XSD)).

De plaats van het metagegevensbestand dat bij een aggregatie (map in de SIP) hoort, is in deze aggregatie. De plaats van het metagegevensbestand dat bij een bestand hoort, is naast het bestand.

Een informatieobject is uniek en kan maar één keer in de SIP voorkomen. Er is altijd maar één hiërarchische relatie. De hiërarchische relatie met de bovenliggende aggregatie moet ook  meegeleverd worden in de MDTO-metagegevens. 

De aggregaties zijn de informatieobjecten die een hiërarchische relatie kennen. Dit is niet de 1 op 1 ordening zoals die in het bronsysteem bestaat. Als een dossier in de ordening in het bronsysteem onder meerdere informatieobjecten valt dan wordt deze maar 1 keer als record in de structuur opgenomen. De originele ordening is te vinden in de relaties.

## Aggregatieniveau
Elke aanlevering kent in ieder geval één aggregatieniveau.  Er is altijd sprake van een informatieobject, met meestal nog een bestand. Er kunnen meer aggregaties geleverd worden, met boven en onderliggende aggregaties.
Elke aanlevering kent een bovenliggende aggregatieniveau  in het doelsysteem.  Naar dit informatieobject moet in de informatieobjecten die hier direct onder geplaatst worden in de MDTO-metadata een verwijzing zijn opgenomen.
Neem in de pakbon op in welke collectie, bijv. archief, deze aanlevering moet worden geplaatst.

## Naamgeving
De sidecar met MDTO-metadata bestaat uit een voorgeschreven formaat (XML) en een bestandsnaam. Dit ziet er zo uit: <naam>.MDTO.xml of bij een bestand: <bestandsnaam>.bestand.MDTO.xml. 

Elk informatieobject of bestand moet een naam hebben. Deze naam moet in de aanlevering uniek zijn en hoeft **niet** met de titel overeen te komen. Voor de <informatieobjectnaam>. MDTO.xml of <bestandnaam.extensie>. MDTO.xml geldt in de aanlevering een limiet op het aantal karakters van 255.  
De namen van het informatieobject, bestand en de sidecars mogen niet de volgende karakters bevatten: **< > : “ / \ | ? * # &.of spatie**. Schoon, indien nodig, de informatieobject- en bestandsnamen in de SIP van deze karakters voor aanlevering.

Let op: De titel van een informatieobject staat altijd in de metagegevens. Deze kan wel leestekens bevatten of langer zijn dan 255 karakters. Verwar dit niet met de naam van het informatieobject zoals meegegeven voor de aanlevering. 

## Metagegevens MDTO aanleveren
MDTO metagegevens moeten in een MDTO metagegevensbestand worden aangeleverd. De aanleverende organisatie zorgt ervoor dat waar mogelijk na redelijke inspanning  metagegevensvelden een waarde hebben. Dit kan in voorkomende gevallen extra inspanning vragen van de aanleverende organisatie, bijvoorbeeld door het combineren van metagegevens. Verplichte metagegevens moeten altijd worden aangeleverd. 

Voor het vullen kan gebruik worden gemaakt van het [XML-schema](https://github.com/NationaalArchief/MDTO-XSD) of van de [RDF-ontologie](https://github.com/NationaalArchief/MDTO-RDF).          

Met behulp van de .xsd controleert een doelsysteem de aangeleverde MDTO.xml bestanden.  

## Additionele metagegevens aanleveren
Als naast MDTO ook een set met andere metagegevens meegeleverd wordt  bij een informatieobject doet u dat door het toevoegen van een eigen bestand voor elke set van metadata. Zoals voor elk bestand kent dit bestand een sidecar met de MDTO-metadata voor bestand.

Voor elk metadatabestand gelden de volgende eisen:

* Elk bestand maakt gebruik van een gedefinieerde standaard en wordt conform deze standaard opgeleverd. (De standaard mag ook een eigen schema zijn.)
* Elk bestand maakt gebruik van een standaardformaat uit de lijst van voorkeursformaten. Denk hierbij aan: XML, JSON, CSV, RDF.
* Metagegevens die in meerdere sets voorkomen worden in elke metagegevens set meegeleverd. Dus als het veld naam in MDTO en in RGBZ of OWMS voorkomt wordt dit veld in beide standaarden gevuld met de metagegevens. 
* Additionele metagegevens voor bestanden zijn enkel technisch van aard (bijv. PREMIS).
* De naamgeving is overeenkomstig de naamgeving van de MDTO.xml bestanden.

De documentatie, zoals een definitiebestand, van een niet-erkende (eigen) standaard of metagegevensschema, levert u als informatieobject mee.