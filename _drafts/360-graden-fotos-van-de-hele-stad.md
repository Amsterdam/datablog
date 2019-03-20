---
title: 360-gradenfoto’s van de hele stad
lang: nl
ref: panorama
author: bert
---

Op [data.amsterdam.nl](https://data.amsterdam.nl/data/panorama/TMX7316060226-000012_pano_0000_004024/?heading=-139&pitch=-22.8) zijn 360-gradenfoto’s van de hele gemeente Amsterdam beschikbaar (en zelfs daarbuiten). Vanaf elke weg, elk fietspad, elke gracht en elk kanaal is gefotografeerd; met je browser ben je zo in [Landelijk Noord](https://data.amsterdam.nl/data/panorama/TMX7315120208-000038_pano_0002_001693/?modus=volledig&heading=44.75&pitch=-25.48), in [het Amsterdamse Bos](https://data.amsterdam.nl/data/panorama/TMX7316010203-000115_pano_0001_001022/?modus=volledig&heading=-106), of in [de havens van Westpoort](https://data.amsterdam.nl/data/panorama/TMX7316010203-000173_pano_0003_000028/?modus=volledig&heading=177&pitch=-9) tussen de olietankers. Deze panoramafoto’s van Amsterdam en hun metadata zijn beschikbaar als open data. In deze blogpost laten we zien hoe je deze afbeeldingen kunt gebruiken, en, leuker nog, wat je ermee kan maken!

Voor de dagelijkse werkzaamheden van veel gemeentemederwerkers is het van belang om te zien hoe de stad eruit ziet. Samen met kaarten en luchtfotografie helpen panoramafoto’s, gemaakt vanaf de straat op ooghoogte, bijvoorbeeld bij het beoordelen van vergunningsaanvragen en het herinrichten van straten en kruispunten. Google biedt met [Street View](https://www.google.com/maps/@52.3885574,4.8901644,3a,60y,185.21h,104.13t/data=!3m6!1e1!3m4!1sg8ZYRrNPP_HV-geiL-RgOg!2e0!7i13312!8i6656) sinds 2008 dit soort foto’s aan. Helaas komt het Google-autootje niet in parken, op fiets- en wandelpaden, in stegen, op de grachten of in wijken in aanbouw. Bovendien bepaalt Google zélf wanneer ze ergens nieuwe foto’s maken, en mogen de foto’s niet voor andere doeleinden gebruikt worden.

Sinds 2016
Afgelopen jaren: eigen auto met panoramacamera, rijd elk jaar overal, soms meerdere keren voor nieuwe wijken en bv. WOZ, zoveel km, zoveel foto's, straten. Ook gemeente Weesp, Almere en Amstelveen.

Ook voor  (Ook leuk voorbeeld (ook om belasting-waarde te bepalen): http://80s.nyc/.)

https://www.nytimes.com/interactive/2018/12/28/nyregion/nyc-property-tax-photos.html


hier foto! Ransdorp!

Dataportaal: voorbeeldlinks! Screenshot! Paar gekke plekken, links of plaatjes.
Wat doen we nu met deze foto's? Ambtenaren, in dataportaal bij elk adres en gebouw, andere gemeentetoepassingen. Maar ook: experimenten met beeldherkenning, kunnen we nummberbordeen herkennen, kwaliteit van strepen op de weg, andere objecten in de openbare ruimte. Ook in Mapillary, bv.

## Foto's zoeken

De foto's kunnen door iedereen worden gebruikt, en de afbeeldingen kunnen worden gezocht en benaderd via een REST API!

```js
const apiUrl = 'https://api.data.amsterdam.nl/panorama/panoramas'
const url = apiUrl + '?near=4.96165,52.38250&srid=4326&radius=250'

fetch(url)
  .then((response) => response.json()) // Transform the data into JSON
  .then((data) => {

  })
```

https://github.com/axios/axios
https://github.com/d3/d3-fetch
https://api.jquery.com/jquery.get/

Laat zien hoe API werkt. Voorbeeld: JS fetch, grijp pano, welke data krijg je terug.
hoe pak je willekeurige punt in amsterdam waar foto's zijn gemaakt?

https://api.data.amsterdam.nl/panorama/panoramas/?near=4.96165,52.38250&srid=4326&radius=250


https://observablehq.com/@bertspaan/nearest-panorama-photo

## Idee: Amsterdam ontdekken

spelletje

Idee: geoguessr voor amsterdam met marzipano. Waar ben je in de stad, raad je plek aan hand van willekeurige panoramafoto. Applicatie bestaat uit 3 onderdelen: kaart, panoviewer, en stukje dat steeds de afstand uitrekent.

foto marzipano!


## Hoe dan?


Hoe kun je dit maken? Je kunt aan REST API niet vragen: geef me willekeurige foto. Wél: geef me dichstbijzijnde foto bij punt (tot max x meter).


visualisatie van alle routes!




{% include full-width-start.liquid %}
{% include iframe.liquid src="https://amsterdam.github.io/panorama-visualization" class="vh-100" %}
{% include full-width-end.liquid %}

Als we alle routes hebben, kunnen we daar polygoon van maken, en dan met algoritme (bv https://stackoverflow.com/questions/19481514/how-to-get-a-random-point-on-the-interior-of-an-irregular-polygon) een willekeurig punt in deze polygoon pakken.

Hoe laten we in JS panoramabeeld zien: voorbeeld: marzipano!

hoe laten we in JS met Leaflet Amsterdamse kaart zien. Voorbeeld: leaflet amsterdam tiles.

Met Turf.js kunnen we uitrekenen wat de afstand is tussen de gekozen locatie en de panoramafoto.
Voorbeeld Turf.

Link naar applicatie! GitHub!
