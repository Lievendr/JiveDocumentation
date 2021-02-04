# Hoe omgaan met te verwijderen data

Omdat de data in provincies.incijfers.be op vele plaatsen hergebruikt wordt, kunnen we onderwerpen **en kubusdimensies** niet zomaar deleten (of codes wijzigen). Want:

- ze verdwijnt dan uit de Themaboom
- Dashboard geeft foutmeldingen
- opgeslagen links en werkruimtebestanden van klanten werken niet meer
- rapporten werken niet meer
- presentaties werken niet meer
- de Swing Connector kan het niet deleten bij connector-klanten (en ze zouden zelf alle bovenstaande issues hebben)

Als je een thema herorganiseert proberen we daarom toch de bestaande onderwerpen te hergebruiken. Dit is deels een inhoudelijke keuze. Bijvoorbeeld is het wellicht geen goed idee als een onderwerp dat vroeger "mannen" bevatte nu "vrouwen" te laten bevatten. Maar wellicht is het wel OK om dit oude onderwerp "mannen" te behouden wanneer we vanaf nu de transseksuelen hieruit kunnen halen. Het gaat hier steeds om de Onderwerpcode, uiteraard moeten de omschrijvingen en andere metadata wel aangepast worden!

## Verwachtingen van  Swing Connector klanten

Als je data ontvangt via de Swing Connector, doe dan regelmatig onderstaande checks.

Uitdovende data wordt niet meer gecontroleerd en wordt doorgaans vervangen door nieuwe cijfers. Deze cijfers mogen dus niet verdeeld worden onder het label "provincies.incijfers.be". Connector-klanten moeten er zelf voor zorgen dat de UITDOVENDE onderwerpen en zeker UITGEDOOFDE onderwerpen zo snel mogelijk uit hun externe themaboom en dashboard verdwijnen.


 

1)	Uitdovende onderwerpen in Jive

Optie 1: 
Ga naar Studio > Viewer > Category tree en klik op de map van je publieke themaboom. Klik op “Export” > select all indicators in this category. Na een paar minuten krijg je een excel. Je krijgt een volledig overzicht, maar de onderwerpnamen ontbreken. Die info moet je nog toevoegen. Bijvoorbeeld door een export van de Indicators tabel te maken en de themaboom export te verrijken met de namen met behulp van "vertikaal zoeken". Zoek vervolgens op het woord “uitdovend” of "uitgedoofd".

Optie 2:
Ga naar je live Jive versie, en type in de zoekfunctie het woord “uitdovend” of "uitgedoofd"

2)	Uitdovende onderwerpen in Dashboard

Zoals optie 1 hierboven, maar exporteer de map die je gebruikt om je Dashboard te voeden. Je gaat nog moeten dubbelchecken in je dashboard zelf, aangezien niet elk onderwerp in die themaboom per se ook echt in je Dashboard gebruikt wordt!

3)	Uitdovende onderwerpen in Rapporten

Ga naar Studio>Data>"Consistency checks" en maak het rapport “Indicators used in reports”. Filter in de “varname” op “uitdovend” of "uitgedoofd". Opgelet: je krijgt hier een overzicht van alle indicatoren die je rapport nodig heeft, zelfs als deze enkel als aggregatieonderwerp, drempelonderwerp of in een formule gebruikt worden.

4)  Uitdovende onderwerpen die door andere onderwerpen gebruikt worden
- zorg dat er geen formules gebruik maken van deze onderwerpen (zoek in veld Formula)
- de onderwerpen kunnen eventueel ook als AggregateVar en TresholdVar gebruikt zijn 



## Databeheer PinC

Onderwerpen en kubusdimensies/kubusdimensie-itmes moeten uiteindelijk wel kunnen verdwijnen. Hiervoor volgen we dit stappenplan:

### 1. De verantwoordelijke voor het onderwerp kijkt zoveel mogelijk na waar de onderwerpen gebruikt worden en past aan of geeft door aan anderen wat aangepast moet worden
1. Aanpassen EXTERNE themaboom
2. Impact checken op INTERN, en dus ook Swing Connector en Dashboard (dit kan via Data>Controleren>Overzicht Onderwerpen in Thema's).
    * Voor Dashboard moet je de uitdovende verwijderen en eventueel vervangen + nieuwe presentaties aanmaken.
    * Voor Connector: het onderwerp moet in de themaboom van de Connector blijven staan, anders stroomt de info dat dit uitdovend is niet automatisch door. Geef het ook door aan Joost, zodat dit expliciet gecommuniceerd kan worden naar de Centrumsteden
3. Impact op rapporten checken. (dit kan via Data>Controleren>Overzicht Onderwerpen in Rapporten)
4. Impact checken op afgeleide onderwerpen. Dit kan door bij Data>Onderwerpen te filteren in de kolom Formules op basis van de getroffen onderwerpen
 
### 2. De verantwoordelijke laat de onderwerpnaam beginnen met "UITDOVEND (sinds XX/XX/20XX) - oude onderwerpnaam"

Pas de data verder nog niet aan. Op die manier blijft alles werken, maar krijgen "koppige" eindgebruikers toch een duidelijke waarschuwing. We voegen ook deze voetnoot toe aan het onderwerp: "Je zou deze data niet meer mogen zien. Is dat toch het geval, laat dit dan weten aan info@provincies.incijfers.be . We wijzen je dan de weg naar de correcte opvolger van deze reeks. Bezorg ons de link en/of een screenshot van waar je deze reeks precies zag."
Je kan hiervoor [deze excel](https://share.vlaamsbrabant.be/share/page/site/socialeplanning/document-details?nodeRef=workspace://SpacesStore/838b2172-5b54-4ee6-afa2-c2c7ce99303a) (tabblad "uitdovend") gebruiken.

### 3. Na zes maand wissen we alle data.

Dat kan heel eenvoudig aan de hand van [deze excel](https://share.vlaamsbrabant.be/share/page/site/socialeplanning/document-details?nodeRef=workspace://SpacesStore/838b2172-5b54-4ee6-afa2-c2c7ce99303a) (tabblad "uitgedoofd"). Vul daar in kolom A en B enkel de INDICATOR CODE en de NAME in; de rest wordt voor jou ingevuld.

Wat doet die:
* We vervangen elk eerder bestaand cijfer door -99999 in 1970 door in de formule naar onderwerp v9999_uitdovend te verwijzen
* We verwijderen de link naar de metadata
* We koppelen aan bron "uitgedoofd" met hulp voor de gebruiker
* We zetten deze zelfde info ook als Footnote
* We wissen het aggregatieonderwerp
* We wissen begin- en eindperiode (en dus wordt dit 1970)
* We wissen de drempel-info

Pas ook de namen aan naar "UITGEDOOFD (sinds NIEUWE DATUM) - oude onderwerpnaam"
   
### 4. Uiteindelijk verwijderen van onderwerpen / kubusdimensies

Eventueel kan er op lange termijn overgegaan worden tot het volledig wissen van de onderwerpen uit Swing. Pas nadat een onderwerp uitgedoofd is, kan het gedelete worden. Dit vereist dat wij het deleten en aan de beheerder van de Swing Connector laten weten dat een onderwerp gewist moet worden bij de Connector-klanten.
Als je een object uiteindelijk wil deleten, dan moet het eerst UITGEDOOFD zijn. Als de vorige stappen goed gebeurt zijn, kan dit geen problemen geven. De Swing Connector verwijdert nooit automatisch records. We moeten dit dus aan de ABF-Connectorbeheerder laten weten, zodat die deze stap manueel kan doorvoeren.


## FAQ

* Indien data niet meer geactualiseerd kan worden, maar toch nog bewaard moet worden, dan is dit niet noodzakelijk UITDOVEND. Uitdovend is specifiek voor data die eigenlijk niet meer gebruikt mag worden omdat we ze niet meer onderhouden. Oude data die nog valide blijft is gewoon oud. Vul in dit geval gewoon de metadata aan met waarom dit onderwerp voorlopig toch nog behouden blijft.
* deze uitleg is eerst geschreven op maat van Onderwerpen, maar is net zo goed van toepassing op kubusdimensies én ook kubusdimensie-items!
* Voor kubusdimensies geldt aanvullend: laat elke wijziging weten aan Joost, want hier is extra beheer nodig in functie van de Swing Connector. De wijziging moet manueel goedgekeurd worden door ABF tijdens de update.
* Een onderwerp dat nooit gepubliceerd is geweest mag je uiteraard wél gewoon deleten!
* Het is technisch niet mogelijk om data te deleten aan de kant van de Connector-klant, we kunnen enkel overschrijven. Dit is logisch, omdat we anders de issues die we bovenaan beschreven aan hun kant zouden veroorzaken. De techniek van uitdovende onderwerpen laat toe dit op een goede manier te organiseren.


 


 