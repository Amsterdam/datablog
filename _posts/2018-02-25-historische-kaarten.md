---
title: Historische Kaarten in het Dataportaal
lang: nl
ref: historical-maps
author: bert
---

Via het Dataportaal van de Gemeente Amsterdam kunnen historische kaarten van de Dienst der Publieke Werken worden bekeken. Het kaartmateriaal is ook beschikbaar voor eigen gebruik.

In 1909 was Amsterdam een stuk kleiner dan nu: ten westen van het Vondelpark, ten zuiden van de Pijp en ten oosten van de Dapperbuurt hield de stad op. Daarbuiten lagen polders met boerderijen. Ook het gebied aan de overkant van het IJ was grotendeels nog leeg, op een paar fabrieken en scheepswerven en de dijkdorpen Buiksloot en Nieuwendam na.

75 jaar later, in 1985, had de stad bijna dezelfde omvang als vandaag, alhoewel Amsterdam toen maar 100.000 inwoners meer had dan in 1909. Na jaren van groei daalde het inwonertal vanaf eind jaren zestig en bereikte in 1984 het laagste punt. Inwoners vertrokken naar plaatsen zoals Purmerend, Hoofddorp en Almere, en veel industrie en bedrijvigheid verliet de stad. De fabrieken, havens, pakhuizen en rangeerterreinen die achterbleven zouden pas jaren later worden gerenoveerd of gesloopt.

In dezelfde periode, tussen 1909 en 1985, produceerde de gemeentelijke Dienst der Publieke Werken (in 1980 hernoemd tot de Dienst Openbare Werken) een collectie gedetailleerde topografische kaarten van de stad, waarvan de kaartbladen bij elke stadsvernieuwing en -uitbreiding herzien werden. Het Amsterdamse Stadsarchief heeft een groot gedeelte van deze kaarten gedigitaliseerd, ze zijn te bekijken en downloaden via de [Beeldbank van het Stadsarchief](https://beeldbank.amsterdam.nl/beeldbank/indeling/grid?q_searchfield=publieke+werken&f_sk_documenttype%5B0%5D=kaart). (Vóór 1909 werden er door de gemeente ook kaarten gemaakt, maar pas vanaf 1909 gebeurde dit voor de hele stad en volgens een vast stramien. Na 1985 werden de kaarten alleen nog digitaal uitgegeven.)

{% include full-width-start.liquid %}
{% include figure.liquid
  caption="<a href=\"https://amsterdam.github.io/explore-historical-maps/publieke-werken-2500-1943.html#10/52.3539/4.8338\">De vaart naar Sloten</a> (en rechts het Vondelpark)."
  alt="Slotervaart"
  src="slotervaart.jpg" %}
{% include full-width-end.liquid %}

<!-- {% include float-start.liquid float="left" class="w-30" %}
{% include figure.liquid
  caption="Betondorp in de verder nog bijna lege Watergraafsmeer."
  alt="Betondorp"
  src="betondorp.jpg" %}
{% include float-end.liquid %} -->

De kaarten van de Dienst der Publieke Werken geven prachtig weer hoe Amsterdam in de twintigste eeuw groeide en veranderde, maar via het Stadsarchief zijn alleen de losse kaartbladen te raadplegen. Om van de losse kaartbladen een digitale historische atlas van Amsterdam te maken moeten de kaarten allereerst worden _gegeorefereerd_. Georefereren is het zó draaien, uitrekken en soms vervormen van scans van kaartmateriaal zodat ze precies passend op bijvoorbeeld Google Maps gelegd kunnen worden. Als daarna de kaarten worden uitgeknipt zodat de lege randen wegvallen kunnen de kaartbladen vervolgens met geografische software tot één kaart worden samengevoegd. Het georefereren en uitknippen van kaarten is tijdrovend precisiewerk, maar gelukkig heeft [Jan Hartmann](https://www.uva.nl/profiel/h/a/j.l.h.hartmann/j.l.h.hartmann.html) van de Universiteit van Amsterdam een aantal jaar geleden een groot gedeelte van dit werk al gedaan. Op de website van de [Amsterdam Time Machine](https://tiles.amsterdamtimemachine.nl) zijn enkele van door Jan Hartmann gegeorefereerde kaartlagen te bekijken.

Om de kaarten geschikt te maken voor het dataportaal heb ik scripts en databestanden van Jan Hartmann – met zijn hulp – verbeterd en aangevuld. Ook heb ik een aantal onnauwkeurigheden gerepareerd en ontbrekende kaartbladen toegevoegd.

__Een selectie van de kaarten van de Dienst der Publieke Werken zijn vanaf nu beschikbaar via [het Dataportaal van de Gemeente Amsterdam](https://data.amsterdam.nl/data/?modus=kaart&center=52.3812567%2C4.8965655&lagen=pw1943%3A1&legenda=true)!__

{% include figure.liquid
  caption="<a href=\"https://data.amsterdam.nl/data/monumenten/monumenten/id8ce679b8-86b4-4331-bb79-bdc6d340d01d/?modus=kaart&center=52.3681675%2C4.9373697&lagen=pw1909%3A1%7Ctcmnmt%3A1&legenda=true&zoom=13\">Gemeente- en rijksmonumenten op het voormalige veemarktterrein</a>."
  alt="Gemeente- en rijksmonumenten op het voormalige veemarktterrein"
  src="1909-in-city-data.jpg" %}

Binnenkort zal ik nog een aantal jaargangen van de Dienst der Publieke Werken-kaarten publiceren, en beginnen met oudere buurtkaarten uit de negentiende eeuw.

## Reis door de tijd!

Door kaarten uit verschillende jaren over elkaar heen te leggen en te vergelijken reis je via de historische kaartlagen door de tijd. Hoe was ’t om met de trein aan te komen op Station Weesperpoort? Hoe was de wandeling de stad uit, via Dorp Sloterdijk, over de Spaarndammerdijk? Op de kaart hieronder kun je de kaarten uit verschillende jaargangen vergelijken.

Maar de kaarten zijn van groter belang: bijvoorbeeld bij bouwwerkzaamheden en archeologische opgravingen zijn historische kaarten erg belangrijk, en ook worden de kaarten gebruikt om databases van historische straatnamen en huisnummers samen te stellen.

{% include full-width-start.liquid %}
{% include iframe.liquid src="https://amsterdam.github.io/explore-historical-maps/#13/52.3717/4.9344" class="vh-100" %}
{% include full-width-end.liquid %}

## Eigen gebruik van de kaartlagen

De gegeorefereerde kaarten zijn als _tiles_ beschikbaar volgens de [_Tile Map Service_-specificatie](https://en.wikipedia.org/wiki/Tile_Map_Service) (TMS). De meeste geografische software kan met deze standaard overweg. In bijvoorbeeld QGIS of Leaflet is het heel eenvoudig om de kaartlagen te gebruiken, ik leg hieronder uit hoe dat werkt.

De volgende kaartlagen zijn beschikbaar:

| Jaar | Schaal | Tile-URL                                                                  |
|:-----|:-------|:--------------------------------------------------------------------------|
| 1909 | 1:1000 | `https://{s}.data.amsterdam.nl/publieke-werken-1909/{z}/{x}/{y}.png`      |
| 1943 | 1:1000 | `https://{s}.data.amsterdam.nl/publieke-werken-1943/{z}/{x}/{y}.png`      |
| 1943 | 1:2500 | `https://{s}.data.amsterdam.nl/publieke-werken-1943-2500/{z}/{x}/{y}.png` |
| 1985 | 1:1000 | `https://{s}.data.amsterdam.nl/publieke-werken-1985/{z}/{x}/{y}.png`      |

### QGIS

In QGIS 3.0 en hoger kun je de kaartlagen gebruikeen voor in het _Browser_-paneel, rechts te klikken op _XYZ Tiles_ en voor _New Connection…_ te kiezen. Geef de kaart een naam, kies één van de URL's uit het lijstje hierboven, en klik op _OK_. Op het blog [Spatial Bias]((https://www.spatialbias.com/2018/02/qgis-3.0-xyz-tile-layers/)) worden alle stappen gedetailleerd beschreven.

{% include figure.liquid
  caption="<a href=\"https://www.spatialbias.com/2018/02/qgis-3.0-xyz-tile-layers/\">Een <em>XYZ Tile Layer</em> toevoegen met QGIS</a>."
  alt="Een XYZ Tile Layer toevoegen met QGIS"
  src="qgis-xyz.jpg" %}

### Leaflet

In [Leaflet](https://leafletjs.com/), een populaire viewer voor webkaarten, kan een TMS-laag worden toegevoegd met een paar regels JavaScript:

```js
var map = new L.Map('map')

var id = 'publieke-werken-1943'
var tileUrl = 'https://{s}.data.amsterdam.nl/' + id + '/{z}/{x}/{y}.png'

var tileLayer = L.tileLayer(tileUrl, {
  maxZoom: 16,
  minZoom: 8,
  tms: true, // Belangrijk!
  subdomains: ['t1', 't2', 't3', 't4']
}).addTo(map)

map.setView([52.4158, 4.9768], 10)
```

[Op GitHub](https://github.com/Amsterdam/explore-historical-maps) staan een aantal voorbeeldprojecten waarin de Publieke Werken-kaarten met Leaflet worden getoond.

<!--
## Schaal, kleur, jaargangen, projecties & bladnummers

- 1:1000-kaarten, elk adres en gebouw, huisnummers, stoepen
- 1:2500 bouwblokken, soms in kleur
- 1:5000

950 bij 750 meter

- Projectie: RD & Web Mercator

- link naar Observable
-->
