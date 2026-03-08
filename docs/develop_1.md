## Development 1
### Doelstellingen
Het hoofddoel van de eerste develop-fase was het verkennen van de mogelijkheden voor het product, met de volgende deeldoelen: inzicht krijgen in de ontwikkeling van kinderen, onderzoeken hoe zij interageren met de interface van de beer, mogelijke ontwerpen van de bijbehorende app verkennen, en bepalen hoe het product gerealiseerd kan worden.

### Materiaal & methoden
Voordat de interviews en literatuuronderzoek konden starten, werd eerst een functionele analyse uitgevoerd. In dit proces werd een verbeterde en meer gedetailleerde versie van het storyboard gemaakt om te onderzoeken wat de verschillende stappen zijn die met het product doorlopen worden. Daarnaast werd de productarchitectuur vastgesteld en de minimal viable productfuncties (MVP) gedefinieerd om de kernfunctionaliteiten te prioriteren. Tot slot werd een morfologische matrix opgesteld om mogelijke ontwerpvarianten systematisch te onderzoeken en evalueren.

Daarna werd er een literatuuronderzoek uitgevoerd om de ontwikkeling van een kind beter te begrijpen. Hierbij werd onderzoek gedaan naar de verschillende domeinen : motorische, cognitieve, sociaal-emotionele en taalontwikkeling. Informatie kwam uit openbare bronnen, zoals websites, blogs en academisch onderzoek. Vervolgens werd de informatie vergeleken, zodanig dat er een tijdlijn van kon gemaakt worden. 

interviews

### Resultaten
#### Literatuuronderzoek 
Uit het literatuuronderzoek zijn volgende tijdlijnen ontstaan waarbij telkens één domein wordt bekeken.
![Motorische](<../img/motorische ontwikkeling.png>)
![Cognitieve](<../img/cognitieve ontwikkeling.png>)
![Taal](<../img/taal- en spraakontwikkeling.png>)
![Sociaal - emotionele](<../img/sociaal - emotionele ontwikkeling.png>)

#### Testinterviews
**Analyse van gebruikerstesten met de interactieve beer**

Tijdens de testen van de interactieve beer werd een Wizard of Oz-opstelling gebruikt. Hierbij fungeerde een fysieke knuffelbeer als tastbare interface, terwijl een smartphone op de buik het Figma-prototype toonde. Via een Bluetooth-muis werden de schermen op afstand bestuurd, zodat de volledige interactiestroom getest kon worden zonder dat de echte hardware en software al ontwikkeld waren. De focus van de test lag vooral op het gedrag, begrip en de motivatie van kinderen tijdens dagelijkse zelfzorgtaken zoals handen wassen.

Uit de testen kwamen verschillende belangrijke inzichten naar voren. Zo bleek dat kinderen verschillende niveaus van begeleiding nodig hebben. Beginners hebben nood aan een gedetailleerd stappenplan met kleine, duidelijke stappen, terwijl kinderen met meer ervaring sneller willen werken. Het systeem moet daarom adaptief zijn en begeleiding kunnen aanpassen aan het niveau van het kind. Daarnaast werd duidelijk dat de interactie soms plaatsvindt in een natte omgeving, waardoor het moeilijk kan zijn om knoppen te bedienen. Daarom is het belangrijk dat de interface waterbestendig en makkelijk schoon te maken is.

Verder bleek dat duidelijke en concrete instructies belangrijk zijn. Te complexe pictogrammen of te veel visuele elementen kunnen verwarrend zijn voor jonge kinderen. Tot slot toonde de test aan dat audiofeedback een grote meerwaarde heeft. Wanneer instructies werden voorgelezen, reageerden kinderen sneller en met meer zekerheid. Audio is daarom essentieel, zeker omdat kinderen in deze leeftijdsgroep vaak nog niet kunnen lezen. Positieve geluidjes en bevestigingen kunnen daarnaast helpen om kinderen gemotiveerd en betrokken te houden. 

**Analyse van de app-interface**

Uit de evaluatie blijkt dat ouders vooral belang hechten aan een eenvoudige, duidelijke en overzichtelijke app. De app moet snel en intuïtief werken, zodat ouders gemakkelijk taken kunnen instellen of aanpassen zonder door complexe menu’s te moeten navigeren. Daarnaast vinden ouders het belangrijk dat routines flexibel aangepast kunnen worden. Vooraf ingestelde taken zoals kleren aandoen, handen wassen of naar het toilet gaan zijn handig, maar ouders willen ook zelf taken kunnen toevoegen en de volgorde ervan aanpassen. Het is bovendien nuttig dat routines opgeslagen kunnen worden, zodat ze later snel opnieuw gebruikt kunnen worden.

Voor gezinnen met meerdere kinderen is het belangrijk dat meerdere accounts mogelijk zijn, zodat de gegevens en voortgang per kind overzichtelijk blijven. Ook moet de app toegankelijk zijn op meerdere smartphones, zodat beide ouders de verbinding met de knuffelbeer kunnen maken en de vooruitgang kunnen opvolgen. Ouders willen daarnaast de voortgang van hun kind kunnen volgen, bijvoorbeeld via visuele feedback zoals sterretjes, badges of een voortgangsbalk, en via een overzicht op langere termijn.

Verder kan het motiverend zijn wanneer kinderen zelf betrokken worden, bijvoorbeeld door de volgorde van taken te kiezen of hun voortgang op de beer te zien. Ook meldingen en tips worden als nuttig beschouwd, omdat ze ouders helpen om oefenmomenten niet te vergeten en ondersteuning bieden bij het oefenen. Tot slot moet de app duidelijk tonen of de knuffelbeer correct verbonden is en of de ingestelde routine goed is doorgestuurd, zodat ouders zeker zijn dat het systeem correct werkt. 

### Hardware en opstelling
Onderstaand schema toont de opstelling die later gebruikt zal worden om het project te realiseren. Op basis daarvan werden de benodigde componenten aangekocht. In de volgende fase (Develop 2) wordt de opstelling opgebouwd en wordt de code geschreven om het systeem te testen.

![Opstelling Planda](<../img/Opstelling Planda.jpg>)

##### Gebruikte componenten

- Arduino Mega
- 3.5" TFT-display
- DFPlayer Mini
- Speaker
- Weerstanden: 1000 Ω, 330 Ω, 220 Ω
- LED
- Drukknop
- POGO-pin connector
- Scherm en visuele feedback

Uit eerdere testen bleek dat visuele ondersteuning belangrijk is voor kinderen. Daarom wordt een relatief groot scherm gebruikt waarop duidelijke pictogrammen of afbeeldingen worden weergegeven. Er werd gekozen voor een TFT-display, omdat dit eenvoudig te implementeren is en in een latere fase ook touchscreenfunctionaliteit kan ondersteunen.

##### Audiofeedback

Naast visuele feedback krijgt het kind ook audio-impulsen:

- Voor de taak: een gesproken uitleg van de opdracht
- Tijdens de taak: muziek of geluiden om motivatie te stimuleren
- Na de taak: een belonend geluid

Deze audio wordt afgespeeld via een DFPlayer Mini met een SD-kaart en speaker. Tussen de RX-pin van de DFPlayer en de Arduino wordt een 1000 Ω weerstand geplaatst, omdat de DFPlayer op 3.3 V logica werkt en de Arduino Mega 5 V gebruikt.

##### Arduino keuze

Er werd gekozen voor een Arduino Mega in plaats van een Arduino Uno omdat:

- De SRAM van een Uno (2 kB) te klein is voor dit project.
- De Mega meer poorten heeft, wat nodig is omdat het display-shield veel pinnen gebruikt.

##### Connectie met de beer

Tussen het scherm en de teddybeer wordt een magnetische POGO-pin connector gebruikt. Hierdoor kunnen de drukknoppen en LED’s in de beer blijven, terwijl het scherm eenvoudig kan worden losgekoppeld. In een latere fase wordt nog een oplossing uitgewerkt om deze poort beter te verbergen zodat kinderen er niet gemakkelijk aan kunnen komen.

### Conclusies & implicaties
Uit de testen blijkt dat het concept goed werkt, maar dat enkele onderdelen nog verder verbeterd moeten worden. Zo is adaptieve begeleiding nodig afhankelijk van het niveau van het kind, zijn waterbestendige knoppen belangrijk in natte situaties en speelt audio een grote rol omdat jonge kinderen vaak nog niet kunnen lezen. Speelse geluidjes en positieve feedback helpen bovendien om kinderen gemotiveerd te houden.

Daarnaast blijkt dat ouders een eenvoudige en overzichtelijke app willen. Ze willen routines makkelijk kunnen instellen en aanpassen en de voortgang van hun kind kunnen volgen via visuele feedback. 