---
title: Historische Kaarten op data.amsterdam.nl
lang: nl
ref: historical-maps
author: bert
---

Nieuw op data.amsterdam.nl: historische kaarten van de Dienst der Publieke Werken. Bekijk hoe Amsterdam eruit zag in 1909, 1943. Of ga zelf aan de slag met dit unieke historische kaartmateriaal.

In 1909 was Amsterdam een stuk kleiner dan nu: ten westen van het Vondelpark, ten zuiden van de Pijp en ten oosten van de Dapperbuurt hield de gewoon stad op. Daarbuiten lagen polders met boerderijen. Ook het gebied aan de overkant van het IJ was grotendeels nog leeg, op een paar fabrieken, scheepswerven en de dijkdorpen Buiksloot en Nieuwendam na.

75 jaar later, in 1985, had de stad bijna dezelfde omvang als vandaag, hoewel Amsterdam toen maar 100.000 inwoners meer telde dan in 1909. Na jaren van groei daalde het inwonertal vanaf eind jaren zestig en bereikte het in 1984 het laagste punt. Amsterdammers vertrokken naar plaatsen zoals Purmerend, Hoofddorp en Almere, en veel industrie en bedrijvigheid verliet de stad. De fabrieken, havens, pakhuizen en rangeerterreinen die achterbleven zouden pas jaren later worden gerenoveerd of gesloopt.

In dezelfde periode, tussen 1909 en 1985, produceerde de gemeentelijke Dienst der Publieke Werken (in 1980 hernoemd tot de Dienst Openbare Werken) een collectie gedetailleerde topografische kaarten van de stad, waarvan de kaartbladen bij elke stadsvernieuwing en -uitbreiding herzien werden. Het Amsterdamse Stadsarchief heeft een groot deel van deze kaarten gedigitaliseerd. Ze zijn te bekijken en downloaden via de [Beeldbank van het Stadsarchief](https://beeldbank.amsterdam.nl/beeldbank/indeling/grid?q_searchfield=publieke+werken&f_sk_documenttype%5B0%5D=kaart). Vóór 1909 werden er door de gemeente ook kaarten gemaakt, maar pas vanaf 1909 gebeurde dit voor de hele stad volgens een vast stramien. Na 1985 werden de kaarten alleen nog digitaal uitgegeven.

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

Hoewel in de Beeldbank de losse kaartbladen in hoge resolutie te bekijken en downloaden zijn, is het in niet mogelijk om de kaarten geografisch te doorzoeken en om alle kaartbladen uit één periode samen te voegen tot enkel kaartbeeld. Om van de losse kaartbladen een digitale historische atlas van Amsterdam te maken moeten de kaarten allereerst worden _gegeorefereerd_.

Georefereren is het zó draaien, uitrekken en soms vervormen van scans van kaartmateriaal dat ze precies passend op bijvoorbeeld Google Maps gelegd kunnen worden. Als daarna de kaarten worden uitgeknipt zodat de lege randen wegvallen kunnen de kaartbladen vervolgens met geografische software tot één kaart worden samengevoegd. Het georefereren en uitknippen van kaarten is tijdrovend precisiewerk. Gelukkig heeft [Jan Hartmann](https://www.uva.nl/profiel/h/a/j.l.h.hartmann/j.l.h.hartmann.html) van de Universiteit van Amsterdam een aantal jaar geleden een groot gedeelte van dit werk al gedaan. Op de website van [Amsterdam Time Machine](https://tiles.amsterdamtimemachine.nl) zijn enkele van de door Jan Hartmann gegeorefereerde kaartlagen te bekijken.

Om de kaarten geschikt te maken voor publicatie op data.amsterdam.nl hebben we scripts en databestanden van Jan Hartmann – met zijn hulp – verbeterd en aangevuld. Ook hebben we een aantal onnauwkeurigheden gerepareerd en ontbrekende kaartbladen toegevoegd.

__Een selectie van de kaarten van de Dienst der Publieke Werken is vanaf nu beschikbaar via [data.amsterdam.nl](https://data.amsterdam.nl/data/?modus=kaart&center=52.3812567%2C4.8965655&lagen=pw1943%3A1&legenda=true)!__

{% include figure.liquid
  caption="<a href=\"https://data.amsterdam.nl/data/monumenten/monumenten/id8ce679b8-86b4-4331-bb79-bdc6d340d01d/?modus=kaart&center=52.3681675%2C4.9373697&lagen=pw1909%3A1%7Ctcmnmt%3A1&legenda=true&zoom=13\">Gemeente- en rijksmonumenten op het voormalige veemarktterrein</a>."
  alt="Gemeente- en rijksmonumenten op het voormalige veemarktterrein"
  src="1909-in-city-data.jpg" %}

We zijn van plan binnenkort meer historische kaartlagen te publiceren, te beginnen met [oudere buurtkaarten uit de negentiende eeuw](https://beeldbank.amsterdam.nl/beeldbank/weergave/record/?id=010043000002_061).

## Reis door de tijd!

Door kaarten uit verschillende jaren over elkaar heen te leggen en te vergelijken kun je door de tijd reizen. Hoe was ’t om met de trein aan te komen op Station Weesperpoort? Wat zag je, als je via Dorp Sloterdijk over de Spaarndammerdijk de stad uit liep? Maar de kaarten zijn van groter belang: bij bouwwerkzaamheden en archeologische opgravingen worden historische kaarten gebruikt om vooraf een beeld te krijgen van wat er bij het graven aangetroffen zal worden. De kaarten laten bijvoorbeeld zien waar fabrieken stonden en wat in deze fabrieken gemaakt werd. Ook worden historische kaarten gebruikt om databases van verdwenen straatnamen en huisnummers samen te stellen.

Op de kaart hieronder kun je kaarten uit verschillende jaargangen vergelijken en zien hoe Amsterdam veranderde tussen 1909 en 1985:

{% include full-width-start.liquid %}
{% include iframe.liquid src="https://amsterdam.github.io/explore-historical-maps/#13/52.3717/4.9344" class="vh-100" %}
{% include full-width-end.liquid %}

## Schaal, kleur, jaargangen, projecties & bladnummers

De Dienst der Publieke Werken gaf kaarten uit voor verschillende doeleinden en in verschillende schalen. De 1:1000-kaarten zijn het meest gedetailleerd; elk individueel adres, gebouw, huisnummer, putdeksel en lantaarnpaal is zichtbaar. Deze kaartbladen, die steeds een stuk stad van 950 bij 750 meter laten zien, vertegenwoordigen het grootste gedeelte van de gedigitaliseerde kaarten van het Stadsarchief.

Jan Hartmann heeft vier selecties gemaakt uit de beschikbare kaarten, deze zijn als kaartlagen beschikbaar via het dataportaal:

- __1909 (1:1000)__: In 1909 maakte de Dienst der Publieke Werken de eerste serie 1:1000-kaarten. Deze gebruiken nog een eigen Amsterdamse projectie, waardoor de kaartbladen niet precies het noorden boven hebben (dit is goed te zien op het indexblad hieronder). Alleen wanneer de stad veranderde en er nieuwe wijken werden gebouwd gaf de Dienst nieuwe kaartbladen uit, en sommige van de allereerste kaartbladen ontbreken in de collectie van het Stadsarchief. Niet alle kaarten Jan Hartmanns selectie zijn daardoor precies uit 1909. Sommige zijn een paar jaar jonger (en er zitten zelfs kaartbladen uit 1923 tussen).
- __1943 (1:1000 en 1:2500)__: Rond 1940 werd de hele kaartenserie opnieuw getekend, ditmaal wél met het noorden precies naar boven. Bovendien werd er ook een prachtige 1:2500-kaart gemaakt, in kleur. Deze is helemaal onderaan deze pagina te bekijken. Voor deze twee series geldt ook dat niet alle kaartbladen precies in 1943 zijn uitgegeven; sommige zijn iets nieuwer.
- __1985 (1:1000)__: De laatste serie papieren kaarten werd rond 1985 uitgegeven. Inmiddels waren er meer dan 600 kaartbladen op deze schaal nodig om heel Amsterdam te beslaan. In 1909 waren dit er nog maar 150. Sommige kaartbladen in deze serie zijn een paar jaar ouder.

{% include figure.liquid
  caption="Bladwijzer van 1:1000-kaarten uit 1909, waarop duidelijk te zien is dat de oriëntatie van de kaartbladen een beetje gedraaid is ten opzichte van het noorden."
  alt="Bladwijzer"
  src="bladwijzer-1909.jpg" %}

Ook de kaarten met kleinere schaal zijn de moeite waard, zie bijvoorbeeld de volgende voorbeelden in de Beeldbank. Echter, deze kaarten moeten nog uitgeknipt en aan elkaar geplakt worden voor we ze toe kunnen voegen aan data.amsterdam.nl.

- [1945, blad 5 (1:5000)](https://beeldbank.amsterdam.nl/afbeelding/ANWP00248000001)
- [1991, blad 1 (1:10.000)](https://beeldbank.amsterdam.nl/beeldbank/weergave/record/?id=ANWQ00083000001)

## Zelf aan de slag!

De gegeorefereerde kaarten zijn als _tiles_ beschikbaar volgens de [_Tile Map Service_-specificatie](https://en.wikipedia.org/wiki/Tile_Map_Service) (TMS). De meeste geografische software kan met deze standaard overweg. Momenteel zijn de volgende kaartlagen beschikbaar:

| Jaar | Schaal | Projectie  | ID                             |
|:-----|:-------|:-----------|:-------------------------------|
| 1909 | 1:1000 | EPSG:28992 | `publieke-werken-1909-rd`      |
| 1943 | 1:1000 | EPSG:28992 | `publieke-werken-1943-rd`      |
| 1943 | 1:2500 | EPSG:28992 | `publieke-werken-1943-2500-rd` |
| 1985 | 1:1000 | EPSG:28992 | `publieke-werken-1985-rd`      |

__Belangrijk: op data.amsterdam.nl gebruiken we [Rijksdriehoekscoördinaten](https://nl.wikipedia.org/wiki/Rijksdriehoeksco%C3%B6rdinaten), terwijl de meeste software kaart-tiles in de Web Mercator-projectie verwacht. Binnenkort voegen we ook Web Mercator-tiles toe (en breiden we de voorbeelden hieronder uit)!__

Van een kaartlaag-ID kun je op de volgende manier een tile-URL maken:

`https://{s}.data.amsterdam.nl/publieke-werken-1909-rd/{z}/{x}/{y}.png`.

Deze URL’s zijn niet direct in de browser te openen (ze bevatten _template strings_ zoals bijvoorbeeld `{x}`), maar geografische software kan ermee overweg! Op [GitHub](http://github.com/Amsterdam/historical-maps) staan alle tile-URL’s handig op een rijtje.

### Leaflet

In [Leaflet](https://leafletjs.com/), een populaire viewer voor webkaarten, kan een TMS-laag worden toegevoegd met een paar regels JavaScript. Standaard verwacht Leaflet tiles in de Web Mercator-projectie, maar met behulp van [Proj4Leaflet](http://kartena.github.io/Proj4Leaflet/) worden ook andere projecties ondersteund.

Om in een HTML-pagina de historische kaarten met Leaflet te gebruiken moet je allereest Leaflet toevoegen:

```html
<link rel="stylesheet"
  href="https://unpkg.com/leaflet@1.4.0/dist/leaflet.css"/>
<script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js"></script>
```

Daarna Proj4Leaflet en [Proj4js](http://proj4js.org/):

```html
<script
  src="https://unpkg.com/proj4js@1.3.4/proj4js/dist/proj4.js"></script>
<script
  src="https://unpkg.com/proj4leaflet@1.0.2/src/proj4leaflet.js"></script>
```

Nu kan met JavaScript de historische kaartlaag worden toegevoegd:

```html
<script>
var RD = new L.Proj.CRS(
  'EPSG:28992',
  '+proj=sterea +lat_0=52.15616055555555 +lon_0=5.38763888888889 ' +
    '+k=0.9999079 +x_0=155000 +y_0=463000 +ellps=bessel +units=m ' +
    '+towgs84=565.2369,50.0087,465.658,-0.406857330322398,' +
    '0.350732676542563,-1.8703473836068,4.0812 +no_defs', {
      origin: [-285401.92, 22598.08],
      resolutions: [
        3440.640, 1720.320, 860.160, 430.080,
        215.040, 107.520, 53.760, 26.880,
        13.440, 6.720, 3.360, 1.680,
        0.840, 0.420, 0.210, 0.105
      ],
      bounds: L.bounds([-285401.92, 22598.08], [595401.920, 903401.920])
    }
)

var map = new L.Map('map', {
  crs: RD
})

var id = 'publieke-werken-1943-rd'
var tileUrl = 'https://{s}.data.amsterdam.nl/' + id + '/{z}/{x}/{y}.png'

var tileLayer = L.tileLayer(tileUrl, {
  maxZoom: 16,
  minZoom: 8,
  tms: true, // Belangrijk!
  subdomains: ['t1', 't2', 't3', 't4']
}).addTo(map)

map.setView([52.4158, 4.9768], 10)
</script>
```

[Op GitHub](https://github.com/Amsterdam/explore-historical-maps) staan een aantal voorbeeldprojecten die laten zien hoe je de Publieke Werken-kaarten met Leaflet kunt gebruiken. Wanneer we meer historische kaartlagen toevoegen aan het dataportaal wijden we er een nieuwe post aan op het Datablog!

<!-- ### OpenLayers -->

<!-- ### QGIS

In QGIS 3.0 en hoger kun je de kaartlagen gebruiken door in het _Browser_-paneel rechts te klikken op _XYZ Tiles_ en te kiezen voor _New Connection…_. Geef de kaart een naam, kies één van de URL’s uit het lijstje hierboven, en klik op _OK_. Op het blog [Spatial Bias]((https://www.spatialbias.com/2018/02/qgis-3.0-xyz-tile-layers/)) worden alle stappen gedetailleerd beschreven.

{% include figure.liquid
  caption="<a href=\"https://www.spatialbias.com/2018/02/qgis-3.0-xyz-tile-layers/\">Een <em>XYZ Tile Layer</em> toevoegen met QGIS</a>."
  alt="Een XYZ Tile Layer toevoegen met QGIS"
  src="qgis-xyz.jpg" %} -->

{% include full-width-start.liquid %}
{% include iframe.liquid
  src="https://amsterdam.github.io/explore-historical-maps/2500.html#13/52.3628/4.8832"
  caption="Huis van bewaring aan de Weterinschans: 1:2500-kaart in kleur uit 1943." class="vh-75" %}
{% include full-width-end.liquid %}
