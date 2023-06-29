# Reflectie

In deze reflectie ga ik per gevolgd vak gedurende de Minor Web Design & Development kijken wat ik wel en niet heb gedaan gedurende de Meesterproef. Daarnaast ga ik ook vertellen wat ik allemaal heb geleerd.

## CSS to the Rescue

### Doelen

- Je kunt experimenteren met (voor jou) nieuwe css-technieken - om de mogelijkheden op waarde te schatten en te gebruiken waar gepast.

  Gedurende het project heb ik gebruik gemaakt van een aantal voor mij nieuwe CSS, zo heb ik gebruik gemaakt van de `:focus-visible` selector. Deze heb ik gebruikt voor de velden in het formulier en op andere elementen die gefocust moeten worden wanneer je met tab door de website gaat. Daarnaast heb ik ook gebruik gemaakt van de :has() selector dit was erg handig voor het stylen van verschillende onderdelen. Has heb ik bijvoorbeeld gebruikt voor het stylen van het inputveld waar een link naar een afbeelding moet worden ingevuld. Hier kijk ik of het formulier een span heeft met de class error. Als dit het geval is dan moet het inputveld waar de link in zit geen `margin-bottom` hebben.

  Deze selectores kun je beide terug vinden in het volgende bestand [new-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/new-wish.css).

- Je hebt begrip van de volle kracht en mogelijkheden van CSS. Je laat zien dat CSS meer kan dan alleen web pages 'stylen'.

  Ja, ik heb begrip van wat er allemaal mogelijk is met CSS, maar ik heb nog lang niet alles uitgeprobeert. Ik weet bijvoorbeeld wanneer ik iets met display flex kan doen of met grid. Wanneer ik de :has() selecotor kan gebruiken of hoe je ervoor kan zorgen dat wanneer iets juist is ingevult er een vinkje komt. Maar er zijn natuurlijk nog veel meer dingen die ik had kunnen doen, zoals het toevoegen van animaties of het gebruiken van container queries. Hier heb ik alleen niet genoeg tijd voor gehad om er echt aandacht aan te besteden.

- Je hebt begrip van de interactie-technieken van CSS (en HTML). De UX is aangenaam bruikbaar binnen de gekozen context(en).

  Ja, ik heb begrip van de interactie-technieken van CSS en HTML. Ik heb bijvoorbeeld gebruik gemaakt van de `:focus-visible` en de `:valid` selector. Hiermee heb ik ervoor gezorgd dat de gebruiker bijvoorbeeld weet hij/zij is in de website en weet de gebruiker bijvoorbeeld ook wanneer het fomulier juist is ingevult. Hier had ik misschien nog meer mee kunnen doen, door bijvoorbeeld bij de knoppen een animatie te laten afspelen wanneer je er met je muis overheen hovert. Maar ook hier heb ik helaas geen tijd voor gehad.

  Dit kun je ook terug vinden op de [new-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/new-wish.css) pagina.

- Je hebt begrip hoe progressive enhancement elegant toe te passen. Je laat zien dat je cascade, inheritance en specificity kunt toepassen.

  Ik heb zo min mogelijk gebruik gebruik gemaakt van classes en id's alleen voor de onderdelen waar het echt nodig was, zoals op de main van iedere pagina, zodat je precies kan zien welke code precies bij welke pagina krijgt en ook niet krijgt dat je code steeds wordt overschreven, wat eigenlijk voor een andere pagina bedoeld is. Daarnaast heb ik geen gebruik gemaakt van !important maar heb ik alles zo specifiek als nog mogelijk geschreven. Dit kun je terug vinden in de volgende bestanden:

  - [new-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/new-wish.css)
  - [detail-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/detail-wish.css)
  - [detail-person.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/detail-person.css)

## Web App From Scratch

### Doelen

- User Interface - you design, build and test the user interface by applying interface design principles

  Gedurende het project ben ik veel bezig geweest met het maken van de designs voor de user interface. Pip en ik hebben hiervoor veel overlegt hoe we bepaalde onderdelen het beste konden aanpakken en hoe we het beste de data konden laten zien. Voor de verschillende pagina's en onderdelen van de pagina's hebben we veel designs gemaakt in Figma. De afbeeldingen hiervan kun je gedurende de verschillende weken in mijn productbiografie zien.

- Code structure - you write modular, consistent and efficient HTML, CSS and JavaScript code by applying structure and best practices. You manage state for the application and the UI

  Ik heb zoveel mogelijk geprobeerd om de code die ik heb geschreven zo gestructureerd mogelijk te schrijven. Hiervoor hebben Pip en ik ook regels opgesteld om ervoor te zorgen dat alles goed bij elkaar past. Zo heb ik om overzicht te houden boven alles neer gezet waar het precies over gaat in [script.js](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/scripts/script.js) en ook comments in veel bestanden geplaatst, zodat iedereen kan lezen wat er precies gebeurd. Ook heb ik zo veel mogelijk geprobeerd om geen code te herhalen. Dit is alleen niet helemaal goed gelukt in de [routes.js](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/router/routes.js), maar hier heb ik en Pip helaas ook niet genoeg tijd voor gehad om daar rustig voor te gaan zitten en functies te schrijven voor het ophalen van de data. Daarnaast was het ophalen van de data vanuit Supabase voor mij nieuw en was het veel uitzoek werk, waardoor ik het juist wel fijn vind dat alles overal waar het nodig is staat. Hierdoor kan ik het zelf makkelijker terug vinden en aanpassen. Maar het is natuurlijk wel netter om dit in een functie te zetten.

  De CSS bestanden waar ik aan heb gewerkt heb ik geprobeerd zo netjes mogelijk op te bouwen. Het eerste element wat op de pagina voorkomt staat dan ook boven aan in het CSS bestand. Op deze manier kan ik het zelf goed terug vinden en is het ook overzichtelijk met de HTML ernaast. Daarnaast heb ik ook een eigen structuur voor het schrijven van de CSS, zo begin ik in de selector met de width en height en ga ik dan naar de padding, border en margin. Daarna komt alles wat met positionering te maken heeft en daarna de alles met fonts en kleuren. Dit is niet de standaard manier, maar voor mij werkt dit het beste en zo kan ik zelf alles makkelijk terug vinden.

  Het managen van de states van de UI is niet echt van toepassing, als het werkt werkt het en als het niet werkt komt er een error in de console en op het scherm. Dit stond wel op de planning maar hebben we geen tijd voor gehad.

  De code netjes en consistent is geschreven, kun je terug vinden in de volgende bestanden:

  - [form.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/form.hbs)
  - [wish.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/wish.hbs)
  - [person.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/person.hbs)
  - [new-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/new-wish.css)
  - [detail-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/detail-wish.css)
  - [detail-person.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/detail-person.css)

- Data management - you understand how you can work with an external API using asynchronous code. You can retrieve data, manipulate and dynamically convert it to structured html

  In dit project ben ik veel bezig geweest met het versturen en ophalen van data uit Supabase. Dit was voor mij helemaal nieuw en ik heb er ook even mee lopen struggelen om dit goed voor elkaar te krijgen. Maar het is me gelukt en daar ben ik dan ook trots op. Daarnaast lijkt het mij ook erg leuk om dit in de toekomst nog een keer te doen, om het zo beter onder de knie te krijgen. Het ophalen en versturen van de data naar Supabase kun je terug vinden in het volgende bestand vanaf regel 98 tot en met 220 in [routes.js](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/router/routes.js).

## Browser Technologies

### Doelen

- Je leert wat Progressive enhancement is en hoe je dit kan toepassen.

  Ik heb veel geleerd over hoe ik op een formulier goed progressive enhancement kan toevoegen. Dit heb ik ook gebruikt in het project. Eerst heb ik het formulier in HTML gemaakt, daarna toen hier alles goed werkte heb ik het formulier gestyled met CSS en `:valid` gebruikt om aan te geven wanneer het formulier goed is ingevuld. Wanneer dit goed was heb ik ervoor gezorgd dat er met JavaScript error meldingen worden weergegeven, zodat het nog duidelijker voor de gebruiker wordt wat er niet goed is.

  Dit kun je terug vinden in de volgende bestanden:

  - [form.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/form.hbs)
  - [new-wish.css](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/css/new-wish.css)
  - [script.js](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/public/scripts/script.js) vanaf regel 121

- Je leert Browser Technologies te onderzoeken, testen en implementeren als enhancement.

  Ik weet redelijk wat wel en niet in welke browser gesupport wordt, doordat ik dit vaak heb opgezocht op caniuse.com, maar helaas hebben we dit project niet in alle browsers kunnen testen, door tijdgebrek. Daarnaast was het ook niet heel erg nodig dat dit project in elke browser werkt, omdat het project geheel op nieuw wordt gemaakt in het eigen systeem van CrossmarX.

- Je leert hoe je Feature Detection doet en wat je kan doen als een 'feature' niet werkt of wordt ondersteund.

  Ik weet hoe ik dit moet doen, maar heb dit helaas niet toegepast in dit project. Zo heb ik bijvoorbeeld gebruik gemaakt van `:has()`, alleen heb ik hier nog geen `@support` voor toegevoegd om ervoor te zorgen dat het ook werkt in de browsers waar `:has` nog niet in wordt ondersteund.

## Progressive Web Apps

### Doelen

- Deal with server side rendering;

  Alle pagina's in de website worden server side gerenderd. Dit doen we doordat we data moeten ophalen en versturen van en naar Supabase. De data die we in de res.render mee sturen halen we op met handlebars. De res.render kun je terug vinden in [routes.js]() en het laten zien van de data in de handlebars kun je terug vinden in de volgende bestanden:

  - [form.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/form.hbs)
  - [detail-wish.hbs](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/wish.hbs)

- Implement a Service Worker;

  Dit was niet nodig voor het project, waardoor we dit niet hebben toegepast.

- Enhance the critical render path for a better runtime or percieved performance.

  Ik heb ervoor gezorgd dat het font een erg kleine block periode heeft, zodat dit snel wordt ingeladen. Dan maak ik in mijn code ook gebruik van async await, waardoor eerst de een stuk code wordt uitgevoert tot dat dat is voltooid en gaat dan verder, maar verder heb ik geen tijd gehad om hier meer aan te doen.

## Real Time Web

### Doelen

- Deal with real-time complexity;

  Dit was niet nodig voor het project, waardoor ik het niet hebben toegevoegd.

- Handle real-time client-server interaction;

  Dit was niet nodig voor het project, waardoor ik het niet hebben toegevoegd.

- Handle real-time data management;

  Dit was niet nodig voor het project, waardoor ik het niet hebben toegevoegd.

- Handle multi-user support.

  Dit was niet nodig voor het project, waardoor ik het niet hebben toegevoegd.

## Human Centered Design

### Doelen

- Leren hoe je (design) principles in een ontwerp kan toepassen.

  Dit was voor mij niet echt van toepassing, omdat de functionaliteit niet echt voor specifiek iemand gemaakt moest worden. We hebben wel rekening gehouden met de toekomstige gebruikers van de website. Daarom hebben we de website bijvoorbeeld ook op verschillende manieren getest. Zo heb ik de website door een contrast check gehaald en gekeken of alles met tab bereikbaar is.

- User needs begrijpen en gebruiken in je ontwerp.

  Onder de feedback gesprekken met de opdrachtgever gaf hij verschillende dingen aan die belangrijk waren voor de gebruikers. Zo gaf hij aan dat het bijvoorbeeld belangrijk is dat ze echt mee kunnen denken om van Strandeiland een zo duurzame en sociale wijk te maken. Daarom is het belangrijk dat de gebruikers op een niet al te ingewikkelde manier een wens aan kunnen maken. Het formulier moet daarom niet uit te veel verschillende stappen bestaan. Daarom heb ik ervoor gekozen, dat er maar 1 pagina is waar je je hele wens in een keer kan invullen.

  De code van het formulier kun je op [deze pagina bekijken](https://github.com/PipHarsveld/Hallo-Strandeiland/blob/main/views/form.hbs) en [hier](https://hallo-strandeiland.adaptable.app/wens-toevoegen) op de website.

- Leren hoe je moet testen en de resultaten gebruiken voor het verbeteren van je ontwerp.

  We hebben geen tijd gehad om de website echt te gaan testen met eventuele gebruikers. Dus is dit voor mij niet van toepassing.

## Wat heb ik geleerd?

Gedurende deze vijf weken werken aan een project heb ik erg veel geleerd. Zo heb ik veel geleerd over het samen werken in een repository en dat je goed moet opletten dat je in de goede branche werkt. Dit deed ik regelmatig fout. Dan was ik een branche voor iets anders bezig met iets wat niet in die branche hoorde. Dit moet nog meer in mijn systeem komen en daar moet ik dan ook met volgende projecten goed op gaan letten. Verder heb ik veel geleerd op het gebied van data ophalen en toevoegen aan Supabase. Dit was een hele klus maar het is gelukt. Daarnaast heb ik ook veel geleerd van de merge conflicten die Pip en ik zijn tegen gekomen en hoe je dit moet oplossen. Het werken met git vind ik zo nu en dan nog wel lastig maar het hoe meer ik het doe hoe beter ik er in word.

## Waar ben ik trots op?

Ik ben erg trots op het formulier dat ik heb gemaakt, met validatie en dat, wanneer hij goed is ingevuld, ook data naar Supabase stuurt. Dit vond ik ook echt leuk om te maken en uit te zoeken hoe ik dit precies moest doen. Daarnaast ben ik ook trots op de detail pagina, hier haal ik de data, die ik naar Supabase heb gestuurd, weer op en laat ik het op de juiste plek zien. Het was ook erg lastig om de thema's voor op de detail pagina op te halen. Dit kwam doordat je eerst de nummers moet ophalen waar de thema's bij horen en daarna moet je het bij behorende thema uit een andere tabel ophalen. Maar ook dit is na wat uitzoek werk gelukt.

Als laatste ben ik ook erg trots op de samenwerking en wat Pip en ik hebben opgeleverd aan de opdrachtgever. We hebben hard gewerkt en ik vind dat we met zijn tweeën veel hebben bereikt in deze vijf weken. Daarnaast ging de samenwerking met het andere team van Hallo Strandeiland ook erg goed en hebben we op een goede manier samen kunnen werken met een database. Ook was de opdrachtgever blij met wat we hebben gemaakt en gaat hij wat we hebben gemaakt meenemen in het verder uitwerken van Hallo Strandeiland.
