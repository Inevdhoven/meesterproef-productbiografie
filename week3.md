# Week 3

## Maandag 12 juni 2023

Vandaag ben ik begonnen met het opzetten van de HTML en CSS voor de persoon pagina. Daarna ben ik even aan de slag gegaan met de popup waar je een overzicht van de wensen kunt bekijken om te kijken of je wens niet al bestaat. Deze kun je hieronder bekijken. Na dat ik die ontwerpen af had ben ik verder gegaan met het bouwen van de HTML en CSS voor de persoon pagina. Deze heb ik aan het einde van de dag afgekregen en kun je vinden op de branch `page-person`. Tussendoor hebben Pip en ik ook verschillende dingen besproken waaronder de nieuwe designs die ik heb gemaakt en daar heb ik dan ook wat dingen aan verbeterd.

<img src="images/week3/formulier-popup.jpg" width="1024px" alt="Formulier popup overzicht wensen">

<img src="images/week3/person-page-new.jpg" width="1024px" alt="Detail pagina van persoon">

[Link naar branch page-person](https://github.com/PipHarsveld/Hallo-Strandeiland/tree/page-person)

```html
<main class="person">
  <button class="button-back">Terug</button>
  <section>
    <div>
      <div>
        <h1>Esther Grandiek</h1>
        <p>
          Ondernemer, Professional, Toekomstige bewoner, Poppenkast activities.
        </p>
      </div>
      <img
        src="https://hallostrandeiland.nl/blobs/gebiedsplatform/w272h272-cropped/72130/2021/28/Esther_Grandiek.png"
        alt="Afbeelding van Esther Grandiek"
      />
    </div>
    <article>
      <h2>Over Esther Grandiek</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime mollitia
        molestiae quas vel sint commodi repudiandae consequuntur voluptatum
        laborum numquam blanditiis harum quisquam eius sed odit fugiat iusto
        fuga praesentium optio, eaque rerum!
      </p>
      <p>
        Provident similique accusantium nemo autem. Veritatis obcaecati tenetur
        iure eius earum ut molestias architecto voluptate aliquam nihil, eveniet
        aliquid culpa officia aut! Impedit sit sunt quaerat, odit, tenetur
        error, harum nesciunt ipsum debitis quas aliquid. Reprehenderit, quia.
        Quo neque error repudiandae fuga?
      </p>
    </article>
  </section>
  <aside>
    <h2>Organisatie waar Esther bij hoort:</h2>
    <ul>
      <li>
        <h3>Gemeente Amsterdam, gebiedsontwikkeling Amsterdam Oost</h3>
        <img
          src="https://www.kuuk.nl/wp-content/uploads/2019/05/logo-gemeente-amsterdam.png"
          alt="Logo Gemeente Amsterdam"
        />
      </li>
      <li>
        <h3>Gemeente Amsterdam</h3>
        <img
          src="https://www.kuuk.nl/wp-content/uploads/2019/05/logo-gemeente-amsterdam.png"
          alt="Logo Gemeente Amsterdam"
        />
      </li>
    </ul>
    <h2>Wensen van Esther:</h2>
    <ul>
      <li>
        <h3>Zwerfafval laten opruimen door kinderen...</h3>
        <p>
          Zorgen dat er elke maand een dag is dat er zwerfafval word opgeruimd
          door...
        </p>
        <img
          src="https://plus.unsplash.com/premium_photo-1681152783638-5857e676a916?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8dHJhc2h8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=800&q=60"
          alt="Zwerfafval"
        />
      </li>
      <li>
        <h3>Zwerfafval laten opruimen door kinderen...</h3>
        <p>
          Zorgen dat er elke maand een dag is dat er zwerfafval word opgeruimd
          door...
        </p>
        <img
          src="https://plus.unsplash.com/premium_photo-1681152783638-5857e676a916?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8dHJhc2h8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=800&q=60"
          alt="Zwerfafval"
        />
      </li>
    </ul>
  </aside>
</main>
```

Nu zie je dat alles nog hard coded is, maar dit gaan we binnenkort aanpassen zodat het vanuit de API wordt opgehaald.

## Dinsdag 13 juni 2023

Vandaag ben ik aan de slag gegaan met de detail pagina van de wens. Deze pagina zou Pip eerst uitwerken in HTML en CSS, maar omdat de pagina met het overzicht meer werk kost, ga ik deze maken. Hier ben ik de hele ochtend mee bezig geweest en daarna ben ik aan de slag gegaan met een paar bugs in de header. Deze zijn nu ook opgelost.

De rest van de dag ga ik verder met het formulier.
