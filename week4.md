# Week 4

## Maandag 19 juni 2023

Vandaag ben ik even aan de slag geweest met het verder stijlen van het formulier. Zo ben ik aan de slag gegaan met de thema's, deze heb ik zo gestijlt dat ze nu onder elkaar staan inplaats van naast elkaar en dat je dan moet scrollen.

**Before:** <br>
Scrollen door de thema's is niet voor iedereen handig.

<img src="images/week4/themes-before.png" width="1024px" alt="Scrollen door de thema's is niet voor iedereen handig">

<br>

**After:** <br>
Daarom zie je nu de thema's meteen allemaal.

<img src="images/week4/themes-after.png" width="1024px" alt="Daarom zie je nu de thema's meteen allemaal">

Daarna ben ik bezig geweest met het stijlen van de afbeelding die je te zien krijgt als je een link toevoegd.

**Before:** <br>
De afbeelding wordt nu erg groot weergegeven.

<img src="images/week4/imagelink-before.png" width="1024px" alt="De afbeelding die je upload word erg groot weergegeven,">

<br>

**After:** <br>
Daarom heb ik deze kleiner gemaakt, zodat je sneller de rest van het formulier ziet.

<img src="images/week4/imagelink-after.png" width="1024px" alt="Daarom heb ik deze kleiner gemaakt, zodat je sneller de rest van het formulier ziet">

<br>

Als laatste ben ik bezig geweest met het verder schrijven van de readme. Voor de readme heb ik een stukje geschreven over hoe je het project kan installeren en dat we gebruik maken van een API en dat je die zelf kan maken met Supabase.

## Dinsdag 20 juni 2023

Vandaag ben ik eerst bezig geweest met het goed toegankelijk maken van het formulier. Ik kwam er namelijk achter dat de thema's niet met tab bereikbaar waren. Daarom heb ik ze omgebouwd en opnieuw gestijlt, zodat ze nu wel met tab bereikbaar zijn. Ook heb ik de :focus state voor de andere velden mooi gemaakt.

```handlebars
<ul>
  {{#each themes}}
    <li>
      <label for="{{this}}">{{this}}</label>
      <input
        type="checkbox"
        name="theme"
        id="{{this}}"
        value="{{incrementIndex @index}}"
      />
    </li>
  {{/each}}
</ul>
```

```css
main.wish-form section form input:focus-visible,
main.wish-form section form textarea:focus-visible {
  outline-offset: 0.15rem;
  outline: 0.125rem solid var(--color-button-primary);
  border-radius: 0.1875rem;
}

main.wish-form section form > ul li input:focus-visible {
  outline-offset: 0.25rem;
}
```

Rond kwart over 9 heb ik met Pip besproken wat zij de dagen dat ik er niet was heeft gedaan en wat er allemaal nog moet gebeuren. Zo had Pip een aantal pull requests en issues aangemaakt, waar ik op moest reageren of even naar moest kijken of ik wist hoe ze dit kon oplossen. De eerste pull request waar ik naar heb gekeken ging over het splitten van de CSS, zodat het overzichtelijker werd. Hier had ik een kleine aanpassing voor aangegeven om de namen van de bestanden aan te passen, zodat er geen hoofdletters in zitten. Dit kan namelijk soms voor problemen zorgen.

Daarna heb ik naar de pull request over het refactoren van de overview page en het maken van de partial voor de wishcard. Deze zagen er goed uit en heb ik na het checken goedgekeurd.

Dan waren er nog twee issues waar ik naar moest kijken. De eerste issue ging over wat ik ervan zou vinden als het masonry grid er net anders uit zou komen te zien. Hierop heb ik gereageerd dat ik het goed vond omdat het andere te moeilijk is om in deze tijd voor elkaar te krijgen. Bij de tweede issue had Pip hulp nodig bij het het switchen tussen het masonry grid en het normale grid. Hier probeerde ze de goede selector te vinden, om dit met CSS te doen. Hier heb ik naar gekeken en heb ik een oplossing voor gevonden. Maar uiteindelijk kwamen we erachter dat deze oplossing niet helemaal goed is. Omdat masonry alleen in Firefox werkt en :has daarin niet werkt. Dus hier ga ik morgen nog even naar kijken.

Dit was de oplossing die ik had bedacht:

```css
.filterBar:has(form:nth-of-type(2) .gridBtn > input:checked)
  + .themeFilters
  + .grid {
  grid-template-rows: auto;
  background-color: red;
}
```

Als laatste ben ik weer gaan kijken naar het verzenden van het formulier naar Supabase. Hier waren wat dingen weer in veranderd die ik nog niet goed had begrepen en wist hoe ik voor elkaar moest krijgen. Met wat hulp van Maijla heb ik voor elkaar gekregen om de wens naar Supabase te sturen. Dit heb ik gedaan met de volgende code:

```js
router.post("/wens", async (req, res) => {
  try {
    const { data, error } = await supabase
      .from("suggestion")
      .insert([
        {
          title: req.body.title,
          description: req.body.description,
          image: req.body.imageLink,
        },
      ])
      .select(); // De wens wordt toegevoegd aan de suggestion tabel

    const insertId = data[0].id ?? null; // Er wordt een array teruggegeven, maar we willen alleen het id van de eerste entry hebben (die we net hebben toegevoegd) met dank aan de hulp van Maijla

    if (error || !insertId) {
      throw error; // Als er een error is, of als er geen insertId is wordt er een error gegooid
    }

    const { error: themeError } = await supabase
      .from("suggestion_theme")
      .insert([
        {
          suggestionId: insertId,
          themaId: req.body.theme,
        },
      ]); // De thema's worden toegevoegd aan de suggestion_theme tabel

    if (themeError) {
      throw themeError; // Als er een error is wordt er een error gegooid
    }

    res.render("main", {
      layout: "index",
      message: "Wens succesvol toegevoegd",
    });
  } catch (error) {
    res.status(500).json({
      error: "Er is een fout opgetreden bij het toevoegen van de wens",
    });
    console.log(error);
    return;
  }
});
```

In de avond ben ik nog even verder gegaan om al een deel van de popup te maken, die in het formulier moet komen. Dit heb ik gedaan met een dialog. De code kun je hieronder zien.

```html
<button id="dialog-btn">Show the dialog</button>
<dialog id="dialog">
  <h2>Kijk of je wens al bestaat</h2>
  <button value="cancel" formmethod="dialog" id="dialog-close">Sluiten</button>
  <form>
    <input
      type="search"
      id="search"
      name="search"
      placeholder="Zoek een wens..."
    />
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
      <path
        d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"
      />
    </svg>
  </form>
  <ul>
    {{#each whises}}
    <li>
      <a href="/wens/{{this.id}}"> {{this.title}} </a>
    </li>
    {{/each}}
  </ul>
</dialog>
```

```js
const dialogBtn = document.querySelector("#dialog-btn");
const dialog = document.querySelector("#dialog");
const dialogCloseBtn = document.querySelector("#dialog-close");

dialogBtn.addEventListener("click", () => {
  dialog.showModal();
});

dialogCloseBtn.addEventListener("click", () => {
  dialog.close();
});
```

```css
/* Dialog button */
main.wish-form article button#dialog-btn {
  padding: 0.375rem 1rem;
  border: 2px solid var(--color-button-primary);
  border-radius: 0.375rem;
  margin-top: 0;
  display: inline-block;
  text-decoration: none;
  color: var(--color-button-primary);
  background-color: transparent;
}

/* Dialog */
main.wish-form article dialog {
  max-width: 70%;
  max-height: 85vh;
  width: 100%;
  padding: 1.5rem 2rem;
  border: none;
  border-radius: 12px;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

main.wish-form article dialog::backdrop {
  background: rgba(0, 0, 0, 0.25);
}
```

## Woensdag 21 juni 2023

Vandaag ben ik de dag begonnen met het verder gaan met het stylen van de dialog in het formulier. Daarna had Pip een probleem met de Masonry library en had ze even hulp nodig om dit op te lossen. Hiervoor had ik een codepen aangemaakt om zelf te kunnen kijken of ik het werkent kon krijgen. Dit is uiteindelijk deels gelukt en heb ik de code aan Pip gegeven, zodat zij dit in het project kon zetten. De CodePen is: https://codepen.io/inevdh/pen/VwVKvQr.

Nadat ik Pip had geholpen ben ik weer verder gegaan met het goed krijgen van de dialog. Ik kwam erachter dat het slim is om de partial die Pip heeft gemaakt voor de wishcards te gebruiken. Hier moest ik alleen eerst een pull request voor aan maken. Deze had verschillende merge confilcts die ik nog moest oplossen, voordat Pip hem kon goedkeuren. Nadat ik deze had opgelost kon Pip de pull request goedkeuren en kon ik verder met de dialog.

Vandaag heb ik ook de design review van afgelopen donderdag ingehaald bij Vasilis. De feedback die ik heb gekregen is:

- Kijken of ik bij de titels een stukje tekst kan plaatsen wat er precies van de persoon verwacht wordt.
- Het formulier uit twee stappen laten bestaan, zodat de gebruiker echt eerst gaat checken of de wens die de gebruiker in de gedachte heeft al bestaat. Wanneer dit niet het geval kan de gebruiker het formulier invullen.
- Nog verder kijken naar validatie.
- Scroll margin toevoegen aan input velden, zodat deze niet onder de header komt wanneer deze niet is ingevuld.

Na de lunch heb ik Laiba geholpen met het posten van de data naar Supabase. Dit was even ingewikkeld maar uiteindelijk was de oplossing best simpel. Er ging iets niet helemaal goed in de HTML er werd iets niet goed afgesloten. Toen we dit hadden opgelost ging het posten van de data naar Supabase goed.

In de middag heb ik ook nog een code review gehad met Justus. Hij gaf aan dat we goed moeten gaan kijken naar wat er echt een musthave moet zijn en wat we op should en couldhave moeten zetten. Zodat we optijd alles af krijgen. Verder gaf hij aan dat ik eventueel Multer kan gaan gebruiken voor het uploaden van een image in het formulier en deze naar Supabase kan sturen. Maar dit is wel een couldhave, dus ik moet dit alleen gaan doen als ik tijd over heb.

In de avond ben ik nog verder gegaan met het voorelkaar krijgen van het versturen van meerdere thema's naar Supabase. Eerst had ik de volgende code:

```js
const { error: themeError } = await supabase.from("suggestion_theme").insert([
  {
    suggestionId: insertId,
    themaId: req.body.theme,
  },
]);

if (themeError) {
  throw themeError;
}
```

Maar hiermee werd er maar 1 thema toegevoegd en als je er meerdere selecteerde kreeg ik een error, omdat je geen array kan sturen naar de database, maar alleen losse nummers. Daarom had ik het idee om er een `.map()` om te zetten zodat er voor elk geselecteerde thema een insert query wordt gemaakt. Dit heb ik gedaan met de volgende code:

```js
const themes = req.body.theme;
const themeInsertPromises = themes.map(async (theme) => {
  // Voor elk thema wordt er een insert query gemaakt
  const { error: themeError } = await supabase.from("suggestion_theme").insert([
    {
      suggestionId: insertId,
      themaId: theme,
    },
  ]);
  if (themeError) {
    throw themeError;
  }
});

await Promise.all(themeInsertPromises); // De thema's worden toegevoegd aan de suggestion_theme tabel
```

Eerst had ik alleen de `.map()`, maar alleen daarmee alleen werkte het niet. Daarom heb ik het aan ChatGPT gevraagd en die gaf aan dat ik er een `Promise.all()` bij moest zetten en dat daarmee dan alle thema's los worden toegevoegd aan de suggestion_thems tabel in Supabase.

## Donderdag 22 juni 2023
