# Week 8 - Becoming a MASTER

Deze week gaan we de puntjes op de i zetten om jouw website een professionele uistraling te geven.

⚠️ Met de stof uit deze les kan je ***MASTER*** punten scoren voor je eindbeoordeling!

- <a href="#tips">Een professionele website</a>
- <a href="#fouten">Veelgemaakte fouten</a>
- <a href="#zelfstudie">Zelfstudie</a>

<br>
<br>
<br>


<a name="tips"></a>
# Een professionele website

> *Het hoeft er niet mooi uit te zien, als het maar werkt...*

Het ontwerpen van een webpagina gaat niet alleen over "mooi" of "lelijk". Het gaat over het bruikbaar en overzichtelijk maken van je informatie en je navigatie. 

Bij het ontwerp van je webpagina moet je met veel zaken rekening houden. Je wil graag dat gebruikers *engaged* zijn, nieuwsgierig worden, en jouw brand onthouden. Tegelijkertijd moet je site bruikbaar zijn voor een zo breed mogelijk publiek op verschillende platformen en met verschillende achtergronden. 

Het onderwerp van je site is hierbij cruciaal. Verkoop je een product, bied je informatie, of is je website een applicatie? Gebaseerd op al deze punten ga je *design keuzes* maken. 

<br>

## Toegankelijkheid en performance

- Hou rekening met de toegankelijkheid van je website. Lees de [overheidsrichtlijnen](https://www.digitaleoverheid.nl/digitale-inclusie/digitaal-toegankelijk/), en doe de [accessibility](https://validator.w3.org) test.
- Om de perfomance van je pagina te verbeteren gebruik je [Google Lighthouse](https://www.youtube.com/watch?v=VyaHwvPWuZU).

## Layout

- Ontwerp een rustige symmetrische indeling om je pagina overzichtelijker te maken, maar kijk ook of je iets origineels of unieks met je indeling kan doen. Kijk hoe andere websites dit doen. Lees over [grid theorie](https://960.gs) en [grids in web design](https://webdesign.tutsplus.com/articles/a-comprehensive-introduction-to-grids-in-web-design--cms-26521)
- Zorg dat je layout en vormgeving past bij het onderwerp van je website. 
- Kies een uniek [font](https://fonts.google.com) voor je header tekst, en een prettig leesbaar font voor je bodytekst. Wees je bewust van het verschil tussen "sans-serif" en "serif".
- Kijk of icons (bv. [fontawesome](https://fontawesome.com)) jouw indeling kunnen verhelderen.
- Kies een professionele hero foto of hero video. Zorg dat deze mooi meeschaalt met alle schermformaten.
- Kies een prettig [kleurpalet](https://coolors.co). Gebruik bijvoorbeeld je [hero foto om kleuren te kiezen](https://coolors.co/image-picker).
- Maak slim gebruik van *witruimte* in je layout. Dit kan rust en overzicht geven aan je pagina. Vermijd de gevreesde *"wall of text"*. Je gebruikers gaan dit niet lezen. Maak je content engaging.
- Gebruik transities en animaties om je interface gebruiksvriendelijker te maken. 
- Denk na over het verschil tussen mobiele en desktop weergave. Is dit alleen een kwestie van items onder elkaar zetten, of kan je de mobiele weergave nog wat meer gebruiksvriendelijk maken? Denk bv. aan een horizontal scroller.

> *Door de "professionele website" tips in je eindproduct te verwerken kan je een MASTER punt scoren - zie de cursushandleiding.*

<br>
<br>
<br>


<a name="fouten"></a>
# Veelgemaakte fouten

- Inline styles gebruiken in je HTML bestand (`<div style="width:100px"></div>`)
- `position:absolute/relative` gebruiken voor elementen die in de `document flow` moeten blijven
- `display:float` gebruiken in plaats van `flex`
- Afbeeldingen worden ingedrukt of uitgerekt omdat je geen `cover` of `object-fit` gebruikt.
- Afbeeldingen hebben allemaal verschillende verhoudingen waardoor je pagina onrustig oogt. 
- Er is placeholder tekst of dummy afbeeldingen gebruikt die niets met het onderwerp van de site te maken hebben.
- Tutorial code uit 1996 copy-pasten 
- `<br><br><br>` of lege `<p></p>` tags gebruiken om witruimte te maken
- De `meta viewport` tag vergeten waardoor site te klein wordt op mobiele schermen
- De layout breekt op mobiele schermen *(navigatie past niet, tekst onleesbaar, foto's veel te groot of veel te klein, etc.)*
- Afbeeldingen van 20MB
- `<div>` gebruikt waar je een semantisch element kan gebruiken *(bv.`<div class="section">` in plaats van `<section>`)*
- `width` en `height` proberen te geven aan een `inline` element
- `%` gebruikt in plaats van `vw` om een waarde  een percentage van de breedte van het scherm te maken.
- Niet begrepen dat `<head>` en `<header>` een  verschillende functie hebben.
- `<table>` gebruiken voor layout doeleinden.
- Je opent `.html` files lokaal met `file://` in plaats van `http://localhost`.

> *Door deze fouten te vermijden in je eindproduct kan je een MASTER punt scoren - zie de cursushandleiding.*

<br>
<br>
<br>


<a name="zelfstudie"></a>
# Zelfstudie

In deze cursus hebben we de basis gelegd van het werken met HTML en CSS. Er is echter nog een hele wereld aan technieken waar je je in kan verdiepen! In deze lijst lichten we een aantal toe. [🔥 Er zijn ook code voorbeelden](./week8-voorbeelden.md)

- [Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
- SVG
- [Video](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) 
- [Audio](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- Position absolute/relative/fixed, wanneer gebruik je dit?
- CSS `calc()`
- CSS transform
- CSS transition en animation
- CSS filter
- [CSS voor Dark Mode](https://css-tricks.com/dark-modes-with-css/)
- CSS variables 🤯
- [CSS grid](https://developer.mozilla.org/en-US/docs/Web/CSS/grid)

[🔥 Bekijk hier de code voorbeelden](./week8-voorbeelden.md)

> *Door punten uit de zelfstudie lijst te verwerken in je eindproduct kan je een MASTER punt scoren - zie de cursushandleiding.*

<br>
<br>
<br>

# Code voorbeelden

- [Voorbeelden week 8](./week8-voorbeelden.md)
- [Voorbeeldproject: de Cybertruck](https://codepen.io/eerk/pen/YzWKXPG)
- [Voorbeeldproject: Alan Kay](https://hr-cmgt.github.io/alankay-dynabook/) en [code](https://github.com/HR-CMGT/alankay-dynabook)
- [HTML en CSS tutorial: bouw een capibara website](https://glitch.com/@KokoDoko/html-basics)
- [Horizontal Scroller](https://codepen.io/eerk/pen/PoEVXOv)
- [Kolommen met flex box en schalende afbeeldingen](https://codepen.io/eerk/pen/rNdWjKR)


<br>
<br>
<br>

# Online bronnen

Online bronnen voor verdere zelfstudie:

- 🔥 [W3Schools HTML](https://www.w3schools.com/html/) en [CSS tutorials!](https://www.w3schools.com/css/)
- [MDN](https://developer.mozilla.org/en-US/)
- [CSS-Tricks](https://css-tricks.com/guides/)
- [Codepen Spark](https://codepen.io/spark)
- [Dev.to](https://dev.to)
- [Stackoverflow](https://stackoverflow.com), en [zelf een goede vraag stellen](https://stackoverflow.com/help/how-to-ask).
- [NetNinja](https://www.youtube.com/c/TheNetNinja), [LevelUpTuts](https://www.youtube.com/c/LevelUpTuts), [Traversy Media](https://www.youtube.com/c/TraversyMedia)




<br>
<br>
<br>

# Links

- [HTML](https://www.w3schools.com/html/) en [CSS](https://www.w3schools.com/css/) op W3Schools
- [Google Fonts](https://fonts.google.com)
- [Fontawesome Icons](https://fontawesome.com/icons)
- [Kleurpalet genereren](https://coolors.co) en [uit een afbeelding halen](https://coolors.co/image-picker)
- [Online SVG editor](https://editor.method.ac)
- [🔥 PenPot free webdesign tool](https://penpot.app) en [Youtube  tutorials](https://www.youtube.com/channel/UCAqS8G72uv9P5HG1IfgnQ9g)
- [Figma](https://www.figma.com) webdesign tool
- [UI-First Design](https://medium.com/sigma-software/benefits-of-using-ui-first-real-life-experience-ed81814b028e)
- [Website Carbon Emission Calculator 💨](https://www.websitecarbon.com)

