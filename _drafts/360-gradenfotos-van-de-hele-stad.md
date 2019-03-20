---
title: 360-gradenfoto’s van de hele stad
lang: nl
ref: panorama
author: bert
---

Hier misschien een intro die wat minder feitelijk is? Een bekende truc is om te beginnen met een of meer vragen: Wat ligt er recht tegenover adres ..., Hoeveel deurbellen kent adres ..., Wat hangt er voor poster op het raam van adres ...? De antwoorden vind je op data.amsterdam.nl, waar je vanaf bijna ieder punt in de stad 360 graden in het rond kunt kijken

Op [data.amsterdam.nl](https://data.amsterdam.nl/data/panorama/TMX7316060226-000012_pano_0000_004024/?heading=-139&pitch=-22.8) zijn 360-gradenfoto’s van de hele gemeente Amsterdam beschikbaar (en zelfs daarbuiten). Vanaf elke weg, elk fietspad, elke gracht en elk kanaal is gefotografeerd; met je browser ben je zo in [Landelijk Noord](https://data.amsterdam.nl/data/panorama/TMX7315120208-000038_pano_0002_001693/?modus=volledig&heading=44.75&pitch=-25.48), in [het Amsterdamse Bos](https://data.amsterdam.nl/data/panorama/TMX7316010203-000115_pano_0001_001022/?modus=volledig&heading=-106), of in [de havens van Westpoort](https://data.amsterdam.nl/data/panorama/TMX7316010203-000173_pano_0003_000028/?modus=volledig&heading=177&pitch=-9) tussen de olietankers. Deze panoramafoto’s van Amsterdam en hun metadata zijn beschikbaar als open data. In deze post laten we zien hoe je deze afbeeldingen kunt gebruiken, en, leuker nog, wat je ermee kan maken!

Voor de dagelijkse werkzaamheden van veel gemeentemedewerkers is het van belang om te weten hoe de stad eruit ziet. Samen met kaarten en luchtfoto’s helpen panoramafoto’s, gemaakt vanaf de straat op ooghoogte, bijvoorbeeld bij het beoordelen van vergunningsaanvragen en het herinrichten van straten en kruispunten Ze zouden daarvoor natuurlijk [Google Street View](https://www.google.com/maps/@52.3885574,4.8901644,3a,60y,185.21h,104.13t/data=!3m6!1e1!3m4!1sg8ZYRrNPP_HV-geiL-RgOg!2e0!7i13312!8i6656) kunnen gebruiken. Maar het Google-autootje komt niet in parken, op fiets- en wandelpaden, in stegen, op de grachten of in wijken in aanbouw. Bovendien bepaalt Google zélf wanneer ze ergens nieuwe foto’s maken, en mogen de foto’s niet voor andere doeleinden gebruikt worden.

Sinds 2016 heeft Amsterdam een eigen panoramacamera die bovenop een auto of een schip gemonteerd kan worden. Straat voor straat en gracht voor gracht wordt de stad elk jaar opnieuw vastgelegd. Sinds 2016 zijn er meer dan 2,5 miljoen foto’s gemaakt en is meer dan 14,000 kilometer weg en kade gefotografeerd. Ook de gemeentes Weesp, Almere en Amstelveen doen mee met dit project en maken gebruik van de camera en de foto’s. Na een dag op straat of op het water worden de afbeeldingen en GPS-data uitgelezen waarna ze automatisch op data.amsterdam.nl belanden. Deze methode maakt het mogelijk snel en efficient grote stukken van de stad in één dag te fotograferen.

{% include figure.liquid
  caption="<a href=\"https://data.amsterdam.nl/data/panorama/TMX7315120208-000038_pano_0002_001691/?center=52.3927943%2C4.9932496&heading=34.45&locatie=52.3927943%2C4.9932496&pitch=-27.75&zoom=13\">Panoramafoto van de kerk van Ransdorp in data.amsterdam.nl</a>."
  alt="Panoramafoto van de kerk van Ransdorp in data.amsterdam.nl"
  src="ransdorp.jpg" %}

Voor de uitvinding van GPS en digitale fotografie was er uiteraard ook behoefte aan vergelijkbare foto’s. De gemeente New York heeft tweemaal, eind jaren 30 en halverwege de jaren 80, fotografen op pad gestuurd om elk gebouw en perceel te laten fotograferen. Deze foto’s zijn onlangs gedigitaliseerd en online te bekijken. Zie bijvoorbeeld [Every Building on Every Block: A Time Capsule of 1930s New York](https://www.nytimes.com/interactive/2018/12/28/nyregion/nyc-property-tax-photos.html) en [80s.NYC](http://80s.nyc/).

{% include full-width-start.liquid %}
{% include figure.liquid
  caption="<a href=\"https://data.amsterdam.nl/data/panorama/TMX7316010203-000173_pano_0008_000608/?modus=volledig&heading=-116&pitch=-2.3\">Panoramafoto genomen vanaf een schip in Zijkanaal H</a>"
  alt="Panoramafoto genomen vanaf een schip in Zijkanaal H"
  src="zijkanaal-h.jpg" %}
{% include full-width-end.liquid %}


Wat doen we nu met deze foto's? Ambtenaren, in dataportaal bij elk adres en gebouw, andere gemeentetoepassingen.

maar er kan meer: beeldherkenning objecten openbare ruimte.
Ook in Mapillary, bv.

Bovendien goede manier om Amsterdam te ontdekken
ik herinner me nog goed
Google Earth, nachtenlang
En met Google Street View deed ik hetzelfde, reisde  de hele wereld over.
(en ik ben zeker niet de enige die dat doet)

http://9-eyes.com/

foto geoguessr

__In deze post gaan we een Amsterdamse versie van GeoGuessr maken, zonder Google, maar met open source-tools en Amsterdamse open data!__

##

 met open data en open source
Stappen

1. willekeurige plek in amsterdam waar foto is
2. panoramabeeld laten zien marzipano
3. kaart met leaflet
4. afstand berekenen met turf
5. een webapplicatie, iedereen op ontdekkingsreis in Amsterdam

## Foto's zoeken

De eerste stap is gelijk ook de meest ingewikkelde

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
