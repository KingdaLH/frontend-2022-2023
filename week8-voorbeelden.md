# Code Voorbeelden zelfstudie week 8

- Google fonts
- Fontawesome icons
- CSS `calc()`
- CSS transform
- CSS transition
- CSS animation
- CSS filter
- Images voor hi-density displays
- CSS grid
- CSS variables
- Position absolute / relative / fixed



<br>
<br>
<br>

## Google fonts

Kies een font en een stijl uit, bv. [roboto light](https://fonts.google.com/specimen/Roboto). Klik in de rechter balk onder "use on the web" op "@import". Plaats de getoonde code in je CSS file:

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

body {
    font-family: 'Roboto', sans-serif;
}
```
> *TIP: kies twee fonts. Een fancy font voor headers, en een prettig leesbaar font voor bodytekst.*

[Google Fonts](https://fonts.google.com/)

<br>
<br>
<br>

## Fontawesome icons

Download fontawesome via de script tag
```html
<script defer src="https://use.fontawesome.com/releases/v5.3.1/js/all.js"></script>
```
Vervolgens kan je de icons gebruiken:
```html
<i class="fab fa-linkedin fa-2x"></i>
<i class="fab fa-youtube fa-2x"></i>
<i class="fab fa-github fa-2x"></i>
<i class="fab fa-instagram fa-2x"></i>
```
[Bekijk alle icons hier](https://fontawesome.com/icons)

<br>
<br>
<br>

## CSS calc

Met `calc()` kan je berekeningen maken tussen verschillende soorten units. In dit voorbeeld centreren we een element door de `margin` de helft van het scherm (`50vw`) te maken, **minus de helft van de breedte van het element (`50px`)**

```html
<div id="logo">Uw logo hier</div>
```
```css
#logo {
    width : 100px;
    margin-left : calc(50vw - 50px);
}
```

<br>
<br>
<br>

## CSS Transform

Transform is een manier om je elementen te vervormen of te verplaatsen, zonder dat de `document flow` (*de layout van je pagina*) breekt. Het element staat stiekem nog op de standaard plaats, maar wordt door de GPU anders gerenderd. Transform werkt goed samen met animaties.

*Voorbeeld: schaal het element x2, verplaats het 100px naar rechts en beneden.*
```css
.logo {
    transform:scale(2) translate(100px, 100px);
}
```
[MDN documentatie transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

<br>
<br>
<br>

## CSS Transitions

Een transitie is een animatie die automatisch afspeelt als een element een andere stijl krijgt. Dit werkt erg goed voor `hover` effecten:

```css
div {
  background-color: lightblue;
  color:darkblue;
  width:200px;
  height:200px;
  transform:scale(1);
  transform-origin:center;
  transition: all 0.4s ease-in-out;
}

div:hover {
  color: lightblue;
  background-color:darkblue;
  transform:scale(1.2);
}
```
[Bekijk meer voorbeelden op MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)

<br>
<br>
<br>

## CSS Animations

Met keyframe animations kan je een animatie afspelen zonder dat er een interactie met de gebruiker is. In dit voorbeeld laten we een afbeelding infaden.

```html
<img src="https://cataas.com/cat">
```

```css
img {
  width:200px;
  animation: movedown 3s ease-out;
}

@keyframes movedown {
  from {
    opacity:0;
    transform: scale(1.2) translateY(-100px);
  }

  to {
    opacity:1;
    transform: scale(1) translateY(0);
  }
}
```
[Lees meer over animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) en [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)

<br>
<br>
<br>

## CSS Filter

Met filter kan je kleuren aanpassen, de achtergrond blurren, en een dropshadow geven aan transparante afbeeldingen.

```css
.logo {
    filter: blur(5px);
    filter: brightness(0.4);
    filter: drop-shadow(16px 16px 20px blue);
    filter: hue-rotate(90deg);
}
```
Je kan filters ook animeren. In dit voorbeeld verandert een plaatje van zwartwit naar kleur als je eroverheen hovert.

```css
img {
    width:200px;
    filter: grayscale(100%);
    transition:all 1s ease-out;
}

img:hover {
    filter: grayscale(0%);
}
```


[Bekijk alle opties op MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)

<br>
<br>
<br>

## Images voor hi-density displays

Telefoons en nieuwe laptops hebben vaak een hoge-resolutie display. Dat zorgt ervoor dat afbeeldingen in een lage resolutie *(72 pixels per inch)* blurry kunnen worden. 

Met [`srcset`](https://css-tricks.com/responsive-images-css/) kan je hoge resolutie afbeeldingen toevoegen voor hi-density displays.

```html
<img srcset="
  examples/images/image-384.jpg 1x, 
  examples/images/image-768.jpg 2x
" alt="…">
```

<br>
<br>
<br>

## CSS Grid

Als je content bestaat uit rijen én kolommen *(bv. een overzicht van pokémon cards)*, dan heb je CSS Grid nodig. In onderstaand voorbeeld wordt een grid gemaakt van 3 kolommen, en 2 rijen. 

```css
.container {
    display: grid;
    
    /* 3 columns and 2 rows */
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows:1fr 1fr; 
    
    /* space between rows and columns */
    grid-column-gap: 15px;
    grid-row-gap: 15px;
}
```
Met media queries kan je die layout veranderen voor kleine schermen.
```css
@media (max-width: 480px) {
  .container {
    /* 1 columns and 6 rows */
    grid-template-columns: 1fr;
    grid-template-rows:1fr 1fr 1fr 1fr 1fr 1fr; 
  }
}
```

[Oefenen met CSS Grid](https://cssgridgarden.com)

<br>
<br>
<br>

## CSS Variables

Stel je variabelen (*custom properties*) in via `:root`. Plaats `--` voor je variabelenaam. Gebruik variabelen via `var()`.

```css
:root {
  --bg-color: rgb(120,100,20);
}
#cat-gallery {
  background-color: var(--bg-color);
}
```
[MDN Documentatie](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)

<br>
<br>
<br>

## Position : absolute / relative / fixed / sticky

Met de CSS stijl `position:absolute / fixed / sticky` haal je een element **uit de document flow**. Het element heeft dan geen effect meer op de positionering van andere elementen. Het element *zweeft* als het ware boven je normale document. Je kan het element nu positioneren met `left, top, bottom, right`. Een voorbeeld:

```html
<div id="logo"></div>
```
```css
#logo {
    position:absolute;
    left:20px;
    top:20px;
}
```
Een veelgemaakte fout is om deze manier van positioneren te gebruiken voor elementen die eigenlijk wél in je document flow moeten blijven.

### Wanneer gebruik je position?

- Voor *floating buttons*, die altijd op dezelfde plek moeten blijven staan en boven je document zweven.
- Voor een *fixed navigation bar* die altijd bovenin je pagina moet blijven staan.
- Voor **modal boxes** (*"Klik OK om door te gaan"*) die boven je webpagina zweven.
- `position:relative` kan je gebruiken om elementen "hard" te positioneren, *binnen* een parent element die wél in je document flow staat.
- `position:relative` kan je bijvoorbeeld gebruiken om een tekst bovenop een `<img>` element te plaatsen. 



<br>
<br>
<br>

# Online code voorbeelden

- [HTML en CSS voorbeeldproject: de Cybertruck](https://codepen.io/eerk/pen/YzWKXPG)
- [HTML en CSS tutorial: bouw een capibara website](https://glitch.com/@KokoDoko/html-basics)
- [Horizontal Scroller](https://codepen.io/eerk/pen/PoEVXOv)
- [Kolommen met flex box en schalende afbeeldingen](https://codepen.io/eerk/pen/rNdWjKR)
- [Filters op images](https://divisoup.com/how-to-use-css3-filters-to-create-captivating-images)
