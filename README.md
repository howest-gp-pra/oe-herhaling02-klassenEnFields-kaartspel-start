# oe-herhaling02-klassenEnFields-kaartspel-start
## dit is een oefening op klassen met velden (nog geen eigenschappen) en constructors

### de bedoeling

Je maakt een applicatie die 2 spelkaarten zal genereren (simuleren) : 1 kaart voor jou, 1 kaart voor de computer.  Wie de hoogste kaart heeft wint.

### klasse

Je maakt een nieuw project aan in je solution.  Je kiest voor .Net **CORE** Class Library en je geeft het de naam **Pra.OefeningKlassenFields.CORE**.

Je verwijdert de automatisch aangemaakte klasse, en je voegt meteen een nieuwe klasse toe met de naam **Kaart**.  Maak deze klasse publiek.

In je klasse bestand : onder de regel "Pra.OefeningKlassenFields.CORE", maar boven de regel "public class Kaart" maak je 2 publieke enumeraties aan.  
Eerste publieke enumeratie krijgt de naam **KaartKleur** en stelt volgende waarden beschikbaar : rood en zwart.  
Tweede publieke enumeratie krijgt de naam **KaartSoort** en stelt volgende waarde beschikbaar : ruiten, harten, schoppen en klavers

Maak nu binnen je klasse (dus onder de regel "public class Kaart" en tussen de accolades) 4 publieke velden aan :  
* kleur van het (enumeratie) type KaartKleur
* soort van het (enumeratie) type KaartSoort
* waarde van het type int
* bonus van het type int

Maak nu 1 constructor aan die 2 argumenten ontvangt : 
* *soort* van het (enumeratie) type KaartSoort
* *waarde* van het type waarde

Binnen deze constructor zorg je er voor dat de 4 velden (zie hierboven) gevuld worden.
* soort en waarde zijn geen probleem, die worden als argement meegegeven (denk aan this. ...!)
* het veld kleur dien je automatisch op te vullen.  Wanneer het (enumeratie) type **soort** gelijk is aan harten of ruiten, dan wordt het veld **kleur** gevuld met de (enumeratie) waarde rood.  Is het (enumeratie) type **soort** gelijk aan schoppen of klavers, dan wordt het veld **kleur** gevuld met de (enumeratie) waarde zwart.
* het veld bonus krijgt volgende waarden
  * indien soort = harten => bonus = 0
  * indien soort = ruiten => bonus = 2
  * indien soort = klaver => bonus = 4
  * indien soort = schoppen => bonus = 6

Hiermee is je klasse afgewerkt.

### het WPF project

Voor je hier begint die je eerst via REFERENTIES in je solution explorer nog een referentie te maken naar je class library (dus naar **Pra.OefeningKlassenFields.CORE**)  

Maak bovenaan je code ook een verwijzing naar deze namespace m.b.v. een using statement.  Dus bovenaan voeg je toe :  
using Pra.OefeningKlassenFields.CORE;

Uiteraard ga je een randomgenerator nodig hebben.  Deze staat reeds in je code (Random rnd) die geïnstantieerd wordt tijdens het opstarten van je programma (rnd = new Random()).

Wanneer op de startknop geklikt wordt dien je volgende te doen : 
* maak een variabele aan met de naam mijnKaart van het type (onze klasse) Kaart
* maak een variabele aan met de naam computerKaart van het type (onze klasse) Kaart
* voor beide kaarten doe je volgende : 
  * genereer een random getal dat 1, 2, 3 of 4 oplevert.  
indien 1 => schoppen  
indien 2 => klavers  
indien 3 => harten  
indien 4 => ruiten  
  * genereer een random getal dat 1, 2, 3 ... 13 oplevert dat dient voor de waarde van betrokken kaart
  * instantieer de kaart en ken beide waarden toe aan elk van de 2 objecten
* toon de waarden van de 2 objecten (kaarten) in de respectieve labels op je venster
* de totale score per kaart = waarde + bonus
* geef in lblResultaat aan of je gewonnen of verloren bent, of om het een gelijk spel gaat

Werk dit eerst naar eigen goeddunken uit, maar maak dan even de bedenking dat je waarschijnlijk voor beide kaarten ongeveer dezelfde code geschreven hebt.  Misschien kan het aanmaken van de beide kaarten in een methode gebeuren zodat de code niet herhaald hoeft te worden.  Misschien willen we straks wel met 4 of meer spelers aan de slag ...
