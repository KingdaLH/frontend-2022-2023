# Week 2 Uitwerking

## HTML 

```html
<h1>Welkom</h1>
<p>Dit is de eerste les van front-end web development</p>

<h2>HTML Tags</h2>
<p>Het gebruik van HTML tags zorgt dat de browser een opmaak geeft aan de tekst. Zonder tags wordt al je tekst achter elkaar geplaatst.<br>
De P tag is een paragraaf. Line breaks gebruik je als je binnen een paragraaf naar de volgende regel wil springen.<br>
Je gebruikt <em>emphasis</em> en <strong>strong</strong> om een woord extra nadruk te geven.</p>

<h3>Afsluiten van tags</h3>
<p>De meeste tags bestaan uit een opening en afsluiting.<br>
Er zijn een aantal uitzonderingen waarbij de tag los kan staan: <br> en <img>.
</p>

<h3>Links en afbeeldingen</h3>
<p>Je kan een link maken met de A tag: <a href="https://cmgt.hr.nl">ga naar de CMGT showcase</a><br>
Je kan afbeeldingen plaatsen met de IMG <img src="./images/myimage.png"> tag. Afbeeldingen zijn vaak niet in de juiste afmeting. Dit moet je schalen met CSS.<br>
Afbeeldingen vereisen een `alt` tag om aan te geven wat er op de afbeelding staat <img src="./images/myimage.png" alt="cat"></p>

<h3>Nested tags</h3>
<p>Tags kunnen binnen andere tags staan, bijvoorbeeld een afbeelding als link: <a href="https://..."><img src="..."></a>.<br>
De <span>SPAN</span> tag is de enige tag die helemaal geen effect heeft op je opmaak, tenzij je dat zelf aangeeft in je CSS.
</p>

<h3>Opmaak in je code</h3>
<p>Je kan je HTML leesbaarder maken door elk level van nesting in te springen met een tab of vier spaties. </p>

<h3>Lijst</h3>

<p>Een lijst maak je met OL, UL en LI items.</p>

<ol>
    <li>Gieter pakken</li>
    <li>Water vullen</li>
    <li>Planten water geven</li>
</ol>

<ul>
    <li>Sporten</li>
    <li>Kat eten geven</li>
    <li>Afwas doen</li>
</ul>

```

### Afbeeldingen op Codepen

Met behulp van *Cat as a Service* of *Unsplash* kan je makkelijk oefenen met afbeeldingen in Codepen.

```html
<img src="https://source.unsplash.com/1600x900/?pizza">
<img src="https://cataas.com/cat/cute">
```

<br>
<br>
<br>


## Links

Links kunnen naar een externe pagina gaan of binnen dezelfde pagina blijven. Met `target` kan je bepalen waar een link opent.

### 🔗 EXTERNE LINK
```html
<a href="https://cmgt.hr.nl" target="_blank">Link naar externe pagina, de CMGT Student Showcase</a>
```

### 🔗 LINK BINNEN DEZELFDE PAGINA
```html
<a href="#overcmgt">Lees meer over CMGT</a>

<!-- de link springt naar de target -->
<a name="overcmgt"></a>
```

### Link targets

Een link opent standaard in hetzelfde venster. Dit kan je aanpassen met het [target](https://www.w3schools.com/tags/att_a_target.asp).

```html
<a href="https://cmgt.hr.nl" target="_blank">CMGT</a>
```

<br>
<br>
<br>

## Table

Een table is een manier om data *(bv. een cijferlijst uit excel)* in rijen en kolommen te tonen.  

```html
<table>
    <thead>
        <tr>
            <th>Student</th>
            <th>Cijfer</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Omar</td>
            <td>7</td>
        </tr>
        <tr>
            <td>Elise</td>
            <td>8</td>
        </tr>
        <tr>
            <td>Antwan</td>
            <td>6</td>
        </tr>
    </tbody>
</table>
```

<br>
<br>
<br>

# CSS

Je hebt gezien dat de browser automatisch opmaak aan je tags geeft, afhankelijk van de tag die je gebruikt. Dit gebeurt via het [default user agent stylesheet](https://hell.meiert.org/core/css/css-2.2.css)

Je kan je eigen opmaak toevoegen via een CSS bestand. Doe dit door eerst de `tag` in te voeren die je wil aanpassen. 

Je kan bijvoorbeeld tekst binnen een `<p>` element centreren met `text-align`. Je kan ook de pagina als geheel aanpassen via de `body` tag. 

Je kan ALLES selecteren met `*`. Je kan comments plaatsen in CSS met `/* mijn comment */`. 

<br>
<br>
<br>

## Cascading Style Sheets?

Het woord `cascading` betekent dat je styles *op elkaar kan stapelen*. Dit gebeurt van top-level naar detail-level. In dit voorbeeld wordt het woord *Capibara* geel. Als je de `span` weg laat wordt het woord groen. Als je de `p` tag weg laat wordt het woord blauw. 

HTML

```html
<body>
    <h1>Knaagdieren in het wild</h1>
    <p>
        Het woord <span>Capibara</span> betekent "Heer van het gras"
    </p>
</body>
```
CSS
```css
body {
    color:blue; 
}
p {
    color:green;
}
span {
    color:yellow;
}
```

<br>
<br>
<br>

## Colors

Je kan kleuren op meerdere manieren aangeven:

- `lightblue` - [zie deze lijst van standaard kleurnamen die je kan gebruiken](https://www.w3schools.com/cssref/css_colors.asp).
- `rgb(233,29,49)` - geef de ***red, green blue*** values als een getal van 0 tot 255
- `rgba(233,44,22,0.4)` - hetzelfde met een transparantie van 0 tot 1. 
- `#FF0000` - oldschool hexadecimale manier om een kleurwaarde door te geven. Dit voorbeeld is rood FF, groen 00, blauw 00.
- `#F00` - een afkorting van `#FF0000`
- `hsl(0,100%,50%)` - dit staat voor ***hue (kleur), saturation (verzadiging), lightness (helderheid)***

<br>
<br>
<br>

## Voorbeeld

Bekijk het voorbeeld om aan de slag te gaan met `color, backgroundcolor, px, border` en het stylen van `a` links. 

```css
body {
    margin:30px;
    background-color:rgb(230,230,230);
    color:green;
    scroll-behavior: smooth;
}

p {
    text-align:center;
    border:2px solid darkblue;
    border-radius:10px;
    background-color:lightblue;
    color:rgba(0,0,0,0.4);
    margin:20px;
    padding:20px;
}

span {
    color:#FF0000;
}

li {
    color:green;
}

/* Links styling */
a {
    color:black;
    text-decoration:none;
}

a:visited { 
    color:grey;
}

a:hover { 
    text-decoration: underline;
}

a:active { 
    color:yellow; 
}
```

<br>
<br>
<br>

## Fonts

Je kan fonts stylen met `font-family, font-size, font-weight, text-decoration, font-style`. 

In de `<body>` tag plaats je de default `font-size` voor je document in pixels *(bv. 16px).*. Vervolgens kan je in specifieke elementen je font size aanpassen met `em`.

- `1em` betekent 100% van de default font size
- `2em` betekent 200% van de default font size
- `1.2em` betekent 120% van de default font size

De default font-families zijn:

- `serif` (times new roman)
- `sans-serif` (arial, helvetica)
- `monospace` (voor code)
- `cursive` (handschrift)

```css
body {
    font-size:16px;
    font-family:sans-serif;
}
h2 {
    font-size:1.4em;
    font-weight:bold;
    font-style:italic;
    text-decoration:underline;
}
```

<br>
<br>
<br>

## Margin en padding

Het werken met margins en paddings is de belangrijkste manier om "ademruimte" in je pagina te maken. 

- `margin`: ruimte buiten de container. Dit zorgt dat je content blokken niet te dicht tegen elkaar aan staan. 
- `padding`: ruimte binnen de container. Dit zorgt dat tekst niet meteen tegen de rand van de container aan staat.

<br>

```css
body {
  margin:0;
  background-color:grey;
}

p {
  margin:8px;
  padding:8px;
  background-color:white;
}
```



<br>
<br>
<br>

### HSL

Het werken met `rgba` of `hsl` maakt het makkelijker om je kleuren harmonieus te houden. Dit zorgt voor eenheid in je pagina.

[HSL color picker](https://www.w3schools.com/colors/colors_hsl.asp)

*Donkerblauwe tekst op lichtblauwe achtergrond met behulp van rgba of hsl*

```css
p {
    background-color:lightblue;
    color:rgba(0,0,0,0.4);
}

h2 {
    background-color:hsl(197, 100%, 50%);
    color:hsl(197, 100%, 25%)
}
```
> *TIP Om je pagina een prettig kleurpalet te geven kan je met deze [color picker](https://coolors.co/image-picker) een aantal kleuren uit je header afbeelding halen.*

<br>
<br>
<br>

## CLE Opdracht : portfolio website

- [Voorbeeld Amber Voskamp](http://voskamp.tv/Amfox/)


<br>
<br>
<br>

## Links

- [Codepen](https://codepen.io)
- [MDN margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) en [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
- [Styling Tables](https://www.w3schools.com/css/tryit.asp?filename=trycss_table_fancy)
- [Default Stylesheet](https://hell.meiert.org/core/css/css-2.2.css)
- [HTML](https://www.w3schools.com/html/) en [CSS](https://www.w3schools.com/css/) op W3Schools
