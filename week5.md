# Week 5

## Maandag 26 juni 2023

De ochtend ben ik begonnen met het maken van designs van onderdelen waar Pip en ik geen tijd meer voor hebben om uit te werken of helemaal te veranderen. Ik heb designs gemaakt van hoe het er eventueel uit zou kunnen komen te zien als gebruikers meerdere afbeeldingen zouden uploaden bij hun wens. Dit heb ik verwerkt in de wishcards en op de detail page van de wens. dan heb ik ook een design gemaakt van hoe het formulier eruit zou kunnen komen te zien als het in twee stappen was verdeeld, zodat de gebruiker sneller eerst gaat kijken of zijn wens al bestaat dan dat de gebruiker meteen een nieuwe wens aanmaakt. Als laatste heb ik nog een ontwerp gemaakt van het filteren op thema. In dit ontwerp kun je precies zien hoeveel wensen er bij een thema horen en staat het ook meteen in volgorde van thema met de meeste wensen naar de minste wensen. Hieronder zal ik de ontwerpen plaatsen.

Ontwerp van wishcard met twee afbeeldingen. Afbeelding veranderd op hover:

![Ontwerp van de wishcard met meerdere afbeeldingen - hover](/images/week5/hover_wishcard.gif)

Ontwerp van wishcard met meerdere afbeeldingen, als slideshow:

![Ontwerp van de wishcard met meerdere afbeeldingen - slideshow](/images/week5/slideshow_wishcard.gif)

Ontwerp van detail page met meerdere afbeeldingen, als slideshow:

![Ontwerp van de detail page met meerdere afbeeldingen - slideshow](/images/week5/slideshow_wish.gif)

Ontwerp van het formulier in twee stappen:

![Ontwerp van het formulier in twee stappen](/images/week5/two_step_form.gif)

Ontwerp van het filteren op thema, met daarbij het aantal wensen per thema:

![Ontwerp van het filteren op thema](/images/week5/filter_amout_of_wishes.jpg)

In de middag zijn het andere groepje en Pip en ik bezig geweest met hoe we de stand op willen gaan zetten. We hebben bedacht om er een soort strand van de maken en onze laptops op eilandjes te plaatsen. Veer de zee dachten we eerst blauw papier te gebruiken, maar omdat dit niet heel duurzaam is gaan we gebruik maken van een blauw tafelkleed. Voor de stand zijn Pip en ik naar de SoLow gegaan om een paar decoraties te kopen.

In de avond ben ik nog verder gegaan met de detailpagina om ervoor te zorgen dat wanneer je ook de buttons van ambassadeur worden en wens steunen klikt er ook iemand word toegevoegd aan de lijst in de sidebar. Dit heb ik gedaan door een persoon per lijst op hidden te zetten en deze met JavaScript te voorschijn te halen. Dit heb ik gedaan met de volgende code:

```handlebars
<li class="hidden">
  <div>
    <h4>Sanne van de Graaf</h4>
  </div>
  <img
    src="https://hallostrandeiland.nl/blobs/gebiedsplatform/w272h272-cropped/72130/2020/4/WhatsApp_Image_2019-06-02_at_11_46_16_AM.jpeg"
    alt="Profielfoto van: Sanne van de Graaf"
  />
</li>
```

```js
const ambassadorButton = document.querySelector(
  ".wish section article button:first-of-type"
);
const ambassador = document.querySelector(
  ".wish aside section:first-of-type ul li:first-of-type"
);

console.log(ambassadorButton);

if (ambassadorButton) {
  ambassadorButton.addEventListener("click", () => {
    ambassador.setAttribute("class", "show");
  });
}
```

Dit heb ik ook gedaan voor het plaatsen van een reactie. Wanneer je dan bij het formulier op de button verstuur klikt komt er een reactie bij de reacties te staan.

## Dinsdag 27 juni 2023

In de ochtend kwam ik erachter dat de code voor het ophalen van de thema's op de detail pagina niet meer werkten. En dat daardoor soms de gehele pagina niet meer werkte. Ik ben hiermee aan de slag gegaan om dit te proberen te fixen. Na veel code aan en uitzetten ben ik er uiteindelijk achter gekomen dat het niet aan de code maar aan Supabase lag. In Supabase zat een wens waarvan heel veel lege thema's werden opgehaald. Deze hebben we verwijderd en toen werkte alles weer.

Daarna ben ik aan de slag gegaan met het updaten van de persoon pagina. Deze heb ik weer helemaal netjes gemaakt, responsive getest en tekst aangepast, zodat deze goed past bij de rest van de pagina's. Nu is het ook mogelijk om op een persoon van in de sidebar bij een wens te klikken en dan kun je die persoon bekijken. Nadat dit er goed uitzag heb ik hiervoor een pull request gemaakt. Deze is goedgekeurd en gemerged.

In de middag ben ik aan de slag gegaan met het verwijderen van alle code die in comments stonden en heb ik ook in de JavaScript alle console.logs verwijderd. Op deze manier ziet de code er toch een stuk netter uit.

Als laatste kreeg ik nog een issue van Pip dat er achter de header geen box-shadow zit, waardoor als je door bijvoorbeeld de overzicht pagina scrollt de header overloopt in de wishcards. Dit ziet er een beetje raar uit waardoor ik dit heb aangepast.

Verder ben ik even aan de slag gegaan met het testen van de toegankelijkheid en het checken van het contrast, maar hier ga ik morgen mee verder.

## Woensdag 28 juni 2023

Ik ben de dag begonnen met het verder werken aan de contrast check. Ik kwam erachter dat ik een extentie in Chrome heb waarmee ik het contrast van de website kan checken. Hieruit kwamen verschillende punten:

- De huisstijlkleur blauw kan niet samen met wit gebruikt worden.
- De donker grijze kleur die we gebruiken is te licht deze moet donkerder worden. Bijvoorbeeld #595959.

Daarna ben ik opnieuw door de website heen gegaan met tab. Hieruit kwamen ook een aantal punten:

- De wishcards hebben geen focus
- Je gaat uit de dialog wanneer je door tabt
- Zoek icoon in de header wordt overgeslagen

De zoek icoon heb ik meteen aangepast. Dit moest een button worden inplaats van een label en nu krijgt hij wel een focus. Ik heb helaas geen tijd meer om het tabben uit de dialog op te lossen. Nu moet de website alleen nog getest worden met een screenreader en de kleuren aanpassen, zodat het contrast beter wordt.

De rest van de putnen zoals het contrast heb ik zoveel mogelijk opgelost. Alleen de blauwe kleur uit de huisstijl heb ik niet aangepast, omdat dit een kleur uit de huisstijl is. In de presentatei gaan we een stukje plaatsen over het contrast daarvan.

Daarna ben ik bezig geweest met het schrijven van comments met uitleg over de code die ik heb geschreven. Deze comments kun je vooral terug vinden in server.js, routes.js en in script.js.

In de middag ben ik aan de slag gegaan met het verder schrijven van de Design Rationale. Hier heeft Pip mij geholpen met het goed toevoegen van de probleem definitie en de oplossing. Daarna ben ik aan de slag gegaan om screenshots te maken van de uiteindelijke pagina's. Toen ik dit aan het doen was kwam ik een bug tegen. Wanneer je nieuwe wens in stuurde werden de thema's niet op de detail pagina laten zien. Ik ben gaan proberen om dit op te lossen, maar dit lukte niet helemaal. Toen heb ik Maijla om hulp gevraagt en zij heeft het probleem opgelost. Het probleem was dat de thema's niet goed werden meegegeven, door inplaats van een render een redirect te doen, ging het wel goed. Hiermee kon ik ook de message met een if else statement laten zien, wanneer het een net aangemaakte wens was. Ik zal de code hieronder plaatsen:

In de router.post:

```js
return res.redirect(`/wens/${insertId}/${req.body.title}?message=1`); // Redirect to the detail page of the wish - Thanks to Maijla
```

In de router.get(/wens/:id/:title):

```js
const wishAdded = req.query.message; // Get the message query parameter - Thanks to Maijla
```

en in de res.render:

```js
message: wishAdded ? "Je wens is succesvol toegevoegd" : null;
```

Nadat dat was opgelost kon ik weer verder met het maken van screenshots en kon ik weer verder met de design rationale.

In de avond ben ik ook nog verder gegaan met het schrijven van de design rationalen. Ik heb alle code waar ik wil dat de docenten sowieso naar kijken erin gezet. Met daarbij de uitleg. Ook staan er comments bij de code voor meer duidelijkheid.

## Donderdag 29 juni 2023

Vandaag ben ik begonnen met het maken van een opzetje van mijn reflectie. Daarna ben ik de aan de slag gegaan met het maken van de presentatie, zodat deze voor vanmiddag af is. Ook heb ik de laatste stukjes tekst en afbeeldingen toegevoegd aan de design rationale. Hier hoeft Pip nu alleen nog haar deel aan toe te voegen en dan is ie klaar!!

In de middag ben ik aan de slag gegaan met alles in de Wiki plaatsen wat er nog niet in staat, zodat deze ook compleet is. Dit had ik redelijk snel gedaan waardoor ik daarna aan de slag kon met de poster. Deze ben ik uiteindelijk gaan maken, omdat de poster waar Pip mee bezig was opeens verwijdert is en Pip nog meer te doen had dan ik. De poster had ik gelukkig redelijk snel af. Toen de poster af was moesten we meteen richting het Stadsloket om daar ons product te presenteren voor de opdrachtgever, iemand van de Gemeente Amsterdam en degene die heeft geholpen met het ontwerp van het huidige ontwerp van hallo Strandeiland.

De presentatie ging erg goed en ze waren erg enthausiast. Ze hadden ook nog wel wat punten waar we misschien beter over na hadden kunnen denken als we meer tijd hadden gehad. Maar wat we hebben gemaakt vonden ze goed, dus daar ben ik erg blij mee.

In de avond ben ik aan de slag gegaan met het schrijven van mijn reflectie.
