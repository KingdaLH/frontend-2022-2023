# Week 3 Uitwerking

In deze week kijken we naar layout en structuur in html met behulp van het `block` element en semantische tags. Ook kijken we naar slimme CSS selectors. We werken in Codepen.

<br>
<br>
<br>

## Document Flow

Omdat zowel de schermafmeting als de hoeveelheid content vaak verandert in een website, is het goed om zoveel mogelijk van `document flow` gebruik te maken. 
Dit betekent dat de browser de layout berekent door elementen onder of naast elkaar te zetten en de afmetingen te bepalen.

> *Voorbeeld: divs komen onder elkaar, en worden net zo hoog als nodig is voor de content in de div.*

Het leren gebruik maken van document flow is een essentiële skill in web development. Er is een groot verschil vergeleken met het opmaken van een document in Word of in een print programma, omdat je waarden nu niet vast staan. 

In deze les leren we twee basis principes van document flow: 

- [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
- Vaste en relatieve units

[Lees meer over document flow op MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)

<br>
<br>
<br>

## Block elements

De meeste HTML tags die je gebruikt zijn `block` of `inline`. Een `inline` element is bijvoorbeeld een `<a>` of `<span>`. 

Een **block** element gebruik je als container voor je content. Deze container heeft een **hoogte** en **breedte**, waardoor je met CSS een layout kan ontwerpen.

In de [default stylesheet](https://hell.meiert.org/core/css/css-2.2.css) kan je zien welke elementen standaard `inline` of `block` elements zijn, bijvoorbeeld:

```css
html, blockquote, body, div, form,
h1, h2, h3, h4, h5, h6, 
ol, p, ul { 
    display: block 
}
```
🔥 Je kan op [browser default styles](https://browserdefaultstyles.com/) snel zien wat de default style van een element is!

<br>
<br>
<br>

## DIV

De `<div>` is het standaard `block` element dat je vaak als container zal gebruiken voor andere elementen.

Een **block** element is standaard **net zo breed als je scherm**. De **hoogte** van een block element is gelijk aan de hoogte van de content IN het block element. 

Block elementen komen dus altijd **onder elkaar** te staan.

Met `margin` en `padding` kan je extra ruimte OM en IN het block element aanmaken. 

Je kan met `width` en `height` de hoogte via CSS bepalen. Meerdere block elementen zullen standaard onder elkaar staan, ook als je de `width` smaller hebt gemaakt dan het scherm.

Mocht je content buiten je container vallen (*omdat de `width` en `height` te klein zijn*), dan kan met `overflow` bepalen of die content wel of niet zichtbaar moet blijven.

HTML
```html
<div>
    <h1>Welkom</h1>
    <p>Dit is mijn portfolio website</p>
</div>
```
CSS
```css
body {
    background-color:grey;
    /*bij een waarde van 0 hoef je geen px units aan te geven*/
    margin:0;
    color:black;
}
div {
    background-color:white;
    margin:20px;
    padding:20px;
    height:120px;
    overflow:hidden;
}
```
Je kan `margin` per richting aanpassen. Dit werkt ook voor `padding` en `border`!
```css
div {
    margin-top:5px;
    margin-right:10px;
    margin-bottom:5px;
    margin-left:10px;
    /*shortcut*/
    margin:5px 10px 5px 10px;
    /*even shorter*/
    margin:5px 10px;
}
```

<br>
<br>
<br>

### Layout debug tip

Om beter te kunnen zien hoe de browser je `divs` plaatst en schaalt, kan je je elementen tijdelijk een `border` geven.

```css
div {
    border:1px solid red;
}
```

<br>
<br>
<br>

### Box-sizing

Omdat margin en padding standaard niet meegerekend worden bij het instellen van `width` en `height` kan je soms onverwachte effecten krijgen. Dit kan je oplossen met [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)

```css
* {
  box-sizing:border-box;
}
```
<br>
<br>
<br>

### Centreren 

Als je block element smaller is dan het scherm, dan kan het mooi zijn om deze te centreren. Een *magic trick* om dit te doen is de linker en rechter margin automatisch uit te rekenen via `auto`. 

```css
div {
    width:500px;
    margin: 0 auto;
}
```

Je kan tekst **in** een div centreren met `text-align`

```css
div {
    text-align:center;
}
```

<br>
<br>
<br>

## Semantische tags

Dit zijn `block elements` die al iets zeggen over de inhoud. Dit maakt je HTML leesbaarder, en het helpt zoekmachines om te begrijpen hoe je website in elkaar zit. 

```html
<nav>Hier de navigatie knoppen</nav>
<header>Hier een grote foto</header>
<main>
    <section>Hier de eerste sectie</section>
    <section>Hier de tweede sectie</section>
    <section>Hier de derde sectie</section>
</main>
<footer>Hier links naar socials</footer>
```
> *Als je `block` elementen nodig hebt *binnen* deze tags, dan gebruik je het `div` element.*

[Lees meer over Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)

<br>
<br>
<br>

## Relatieve units

Omdat je niet altijd weet wat de schermafmeting van je eindgebruiker is, is het riskant om met harde pixel waarden te werken. Een container van `1200px` kan er bij jou mooi uit zien, maar op een ander scherm te groot zijn.

Je kan je containers met het scherm mee laten schalen via de `vw, vh, %` units. 

- VW betekent : procent van de schermbreedte.
- VH betekent : procent van de schermhoogte.
- % betekent : procent van de breedte van de container waar dit element in zit.

> *Tip: gebruik altijd vw of vh, tenzij je zeker weet dat je element een percentage van een ander element moet zijn.*

Je kan via `min-width` en `max-width` een minimale en maximale waarde geven aan een container. In dit voorbeeld is de container altijd 60% van de schermbreedte, maar nooit kleiner dan 200 pixels en nooit groter dan 1000 pixels. Dit werkt ook voor `height`.

```css
section {
    width:60vw;
    min-width:200px;
    max-width:1000px;
}
```
<br>

### TIP wanneer `vw` en `%` ?

De top level containers (block elementen) van je website schaal je met `vw`. Je content blokken zijn dan bijvoorbeeld `80vw` van je scherm. Als je daar weer andere block elementen of afbeeldingen **IN** zet, dan maak je die `100%`. Die "child elements" zijn dan altijd net zo breed als de parent container.

<br>
<br>
<br>

## Classes en ids

We hebben tot nu toe telkens via CSS **alle** tags van een bepaald type aangepast. Soms wil je alleen sommige tags aanpassen, of zelfs maar 1 enkele tag:

- Een groep van tags aanpassen doe je via het `class` keyword.
- Een enkele unieke tag aanpassen doe je via het `id` keyword.

HTML
```html
<section class="explanation">Dit is een explanation section</section>
<section class="explanation">Dit is een explanation section</section>
<section id="notes">Dit is een notes section</section>
```
CSS

In CSS gebruik je `.` om classes te stylen en `#` om ids te stylen.

```css
.explanation {
    background-color:lightblue;
}

#notes {
    background-color:lightyellow;
}
```

<br>
<br>
<br>

### Nested selectors

Je kan met CSS *nested selections* maken. Hieronder zie je een aantal voorbeelden. Let goed op het gebruik van spatie, komma en het weglaten van spatie.

```css
/* alle section tags met de class explanation*/
section.explanation { ... }

/* alle elementen met class explanation binnen een div*/
div .explanation { ... }

/* alle div tags binnen een section tag */
section div { ... }

/* alle p tags als direct child van een element met id notes */
#notes > p { ... }

/* ALLE elementen binnen een element met id notes */
#notes * { ... }

/* alle divs EN alle elementen met class explanation */
div, .explanation { ... }
```
Door slim met nested selectors te werken heb je minder classes en ids nodig!<br>
Speel de [CSS game](https://flukeout.github.io) om hier verder mee te oefenen.

<br>
<br>
<br>

## Voorbereiding week 4

- Maak alvast een [account aan op github.com](https://github.com/)
- Download alvast [Visual Studio Code](https://code.visualstudio.com/download)


<br>
<br>
<br>

## Links

- [CSS Layout: document flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)
- [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
- [W3Schools Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
- [Box Sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
- [Oefen met nested selectors!](https://flukeout.github.io)
- [HTML](https://www.w3schools.com/html/) en [CSS](https://www.w3schools.com/css/) op W3Schools
