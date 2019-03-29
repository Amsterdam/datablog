---
title: "Re-using code to build an interactive website"
lang: en
ref: processing, vuejs, python, leaflet
author: eelke
---

As a data analist I was asked to create an interactive visualisation of a Machine Learning Pilot identifing our Traffic signs. The visualisation needed to provide end users the ability to interactively investigate the outcome to evaluate if machine learning could be a good solution for identifing maintance locations. 

For each official traffic sign:
- Show the locations of the traffic sign in our administration.
- Show the identified panoramic image location which contained a traffic sign including direction in the image.
- Ability to quickly move to different parts of the city by name
- Show the panoramic view

It also had to be build in one week.

I had experience in Javascript/Docker/SQL/Python/GIS but I am a junior/medior fullstack developper at best. So to save time, I re-used a lot of code from other repositories on https://www.github.com/amsterdam.

To build these parts I could have opted to download all needed data as files, wrangle this in a database and do some [QGIS](https://www.qgis.org) magic and exported this with Leaflet2web plugin and be done with it, or create one big flat table and import it in [Tableau](https://public.tableau.com) to create a dashboard. 

But having learned the hard way of:
- Needing to redo the data processing multiple times because of changing requirements
- The panoramic views not being interactive as an embed view with a solution above

The route of building this out from files and desktop applications would become very time consuming very quickly and not very interactive. 

So I opted for the webdevelopment route re-using as much code logic as possible and reused code for the specific front-end and backend development.

## Re-used Code:

### Frontend:
Boilerplate frontend styling:
  - https://github.com/Amsterdam/template_vue

Address search and map logic:
  - https://github.com/Amsterdam/iot


### Backend:

Docker with Postgres + Postgis
- https://hub.docker.com/u/amsterdam

Data processing ETL scripts:
- https://github.com/amsterdam/data-processing 

## API/Webservices used:
Panorama images:

- https://map.data.amsterdam.nl/maps/panorama?REQUEST=GetCapabilities&SERVICE=wfs
- https://api.data.amsterdam.nl/panorama/ 

Address autocomplete and zoom:

- api.data.amsterdam.nl/bag/typeahead
- api.data.amsterdam.nl/bag/nummeraanduiding

Offical Dutch traffic signs:

- https://repository.officiele-overheidspublicaties.nl/bwb/BWBR0004825/2014-03-20_0/xml/BWBR0004825_2014-03-20_0.xml

## STEP 1: Data preparation

### [Current Traffic signs](https://github.com/Amsterdam/mlvb/tree/master/current_traffic_signs)

The data of our current traffic administration was not available as a service unfortunatly (it will be available in 2020/2021) but I could use 7 database dumps which were also being used as a migration dump to our central asset management system and by using our import flow logic to be re-usable:

1. Upload your files in the cloud using our [Objectstore](stack.cloudvps.com) as a central storage for the project (This was the only manual step)
2. [Download these files](https://github.com/Amsterdam/mlvb/blob/master/current_traffic_signs/download_from_objectstore.py)
3. [Import the files into a Postgres docker database container](https://github.com/Amsterdam/mlvb/blob/master/current_traffic_signs/import_files_to_postgres.py)
3. [Transform your data](https://github.com/Amsterdam/mlvb/blob/master/current_traffic_signs/select_nearest_panos.py)
4. [Output your data in the required format for visualisation](https://github.com/Amsterdam/mlvb/blob/master/current_traffic_signs/write_table_to_geojson.py)

So my first timebox issue were the 7 different files which needed to be cleaned and merged to be used as base layer to evaluate against.

### Data processing(https://github.com/amsterdam/data-processing)

Luckily we created a [data-processing repository]() to re-use these always returning Extract, Transform, Load (ETL) functions. 
But it was missing and Access MDB filetype of import. So for this project I created this import as a generic function and added this to the data-procssing repository after finising the project.

This repo and python package on pypi contains a growing set of small  you can re-use in projects to speed up your ETL process. If you have some usefull functions to share or improve the current ones, please do by creating a PR!

This processing repository was inspired by these 3 examples how they chose to do data-processing more efficenty:

1. [BlueYonder](https://www.blueyonder.ai) runs 500 miljoen pipelines, They use the 2/3 work principe to reuse functions in  projecten on a large scale: https://www.youtube.com/watch?v=R1em4C0oXo8 

“The data flow library presented in this talk provides a thin abstraction layer between data pipeline declarations and specific execution backends. As exceptions are the rule, the library allows the user to introduce limited control flow into pipelines. At the same time, it also offers composability of pipelines, as many of our projects share similar building blocks.”

2. Wolfram Alfa uses 10 steps to create enriched structured data: https://blog.stephenwolfram.com/2017/04/launching-the-wolfram-data-repository-data-publishing-that-really-works/

{% include figure.liquid
  caption="https://blog.stephenwolfram.com/data/uploads/2017/04/Data-Hierarchy-Levels-Zoom1.png">Wolfram Alpha Data Hierarchy Levels</a>."
  alt="Data-Hierarchy-Levels"
  src="Data-Hierarchy-Levels-Zoom1.png" %}

3. [Datahub.io](https://datahub.io) provides an ecosystem using the command line data retrieval and processing: http://docs.datahub.io/developers/user-stories/



## Some Examples

For maps you normally use a CSV or GeoJSON as a file based solution. 

Our WFS and WMS service can also provide these, but providing the correct parameters is a bit dawnting at first if you look at the XML of what the service can provide:
https://map.data.amsterdam.nl/maps/gebieden?REQUEST=GetCapabilities&SERVICE=wfs

To get a geojson from the service you can use these parameters:
https://map.data.amsterdam.nl/maps/gebieden?REQUEST=GetFeature&SERVICE=wfs&TYPENAME=buurtcombinatie&SRSNAME=EPSG:4326&OUTPUTFORMAT=geojson&VERSION=2.0.0

But what if you want to use multiple layers and want to have this data in a database to join your own data with?

Most of the times in data driven projects we still use the old way of dumping a CSV view from a system's database, but with our REST API and Webservices we can now retrieve more realtime data using these type of scripts.

You can use ogr2ogr as a powerfull opensoruce commandline executable to achieve this.

With our mapserver you can now get these types of files easily on a Leaflet map by using the WFS service parameters:
https://github.com/Amsterdam/datapunt_base_layer






__In deze post gaan we een Amsterdamse versie van GeoGuessr maken, zonder Google, maar met open source-tools en Amsterdamse open data!__

{% include figure.liquid
  caption="Raad waar op de wereld je bent: <a href=\"https://geoguessr.com/world/play\">GeoGuessr</a> met Google Street View."
  alt="GueGuessr"
  src="geoguessr.jpg" %}

## Op ontdekkingsreis in Amsterdam

Aan de slag! Met de webservices van data.amsterdam.nl en wat kennis van webtechnologie en JavaScript-frameworks maken we zo ons eigen online _panorama-dropping-spel_. Hoe beginnen we?

1. Ten eerste moeten we een manier vinden om steeds van een willekeurige plek in Amsterdam een panoramafoto te downloaden;
2. Deze foto kunnen we vervolgens laten zien met [Marzipano](http://www.marzipano.net/);
3. [Leaflet](https://leafletjs.com/) zorgt dat spelers kunnen raden waar ze zijn, met een kaartlaag uit het dataportaal;
4. Met [Turf.js](https://turfjs.org/docs/#distance) kunnen we uitrekenen of de speler in de buurt is van de echte fotolocatie;
5. Een simpele webapplicatie, gemaakt met [Vue](https://vuejs.org/), voegt alles samen.
6. Klaar! We kunnen op ontdekkingsreis in Amsterdam!

## De panoramafoto van een willekeurige plek in Amsterdam

De eerste stap is gelijk de moeilijkste. De panoramafoto’s kunnen worden gezocht en benaderd via de REST API op [api.data.amsterdam.nl/panorama](https://api.data.amsterdam.nl/panorama). Met deze API is het ook mogelijk om de foto te vinden die het dichtst bij een bepaalde geografische locatie ligt. In het voorbeeld hieronder zie je hoe dit gaat met JavaScript en [axios](https://github.com/axios/axios), maar het kan uiteraard met elke willekeurige programmeertaal:

```js
const lonLat = [4.96165, 52.38250]
const apiUrl = 'https://api.data.amsterdam.nl/panorama/panoramas/'
const url =  `${apiUrl}?near=${lonLat.join(',')}&srid=4326&radius=250&page_size=1`

return axios.get(url)
  .then((response) => response.data)
  .then((data) => {
    // Als er een foto gevonden is hebben we nu
    // alle metadata en links naar de foto:
    console.log(data)
  })
```

Je kunt de JSON-data die deze API-call teruggeeft ook [bekijken in de browser](https://api.data.amsterdam.nl/panorama/panoramas/?near=4.96165,52.38250&srid=4326&radius=250&page_size=1). Als je met de API wilt spelen en de foto’s en de data direct wilt bekijken kun je ook dit [Observable-notebook](https://observablehq.com/@bertspaan/nearest-panorama-photo) gebruiken.

Via de Panorama-API is het mogelijk om een foto te zoeken in de buurt van een locatie. Echter, het kiezen van een willekeurige locatie in de gemeente Amsterdam is niet zo eenvoudig. De meest simpele oplossing is om steeds een punt te kiezen in de rechthoek waar de [gemeentegrenzen van Amsterdam](https://maps.amsterdam.nl/gebiedsindeling/) precies inpassen, grofweg tussen Uitdam, Nederhorst den Berg, Hoofddorp en Assendelft.

Omdat dit gebied veel groter is dan de gemeente zelf, zul je relatief vaak een punt kiezen wat ver buiten de stad ligt. De foto hier het dichtst bij is er dan een van de rand van de stad. Deze methode zal er dus voor zorgen dat je steeds aan de rand van de stad wordt neergezet, middenin het groen.

Ook als we de precieze omtrek van de gemeente gebruiken om een willekeurig punt te kiezen hebben we hetzelfde probleem: er zijn niet overal panoramafoto’s gemaakt, en ook dan zullen de lege gebieden ons te vaak op een afgelegen plek afzetten. We zouden ook een kleine zoekradius kunnen gebruiken, en de zoekopdracht kunnen blijven herhalen tot een foto gevonden is, maar dat is helemaal een onaantrekkelijke oplossing.

Alleen door alle routes te bekijken waarlangs foto’s genomen zijn, en een willekeurig punt te kiezen langs een van deze routes, kunnen we op de correcte manier een willekeurige panoramafoto kiezen. Deze methode levert bovendien ook een mooie datavisualisatie van alle gefotografeerde routes op!

Via de Panorama-API of via de [WFS-server](https://map.data.amsterdam.nl/maps/panorama?REQUEST=GetCapabilities&SERVICE=wfs) kunnen we alle opnamelocaties downloaden. Aan de hand van het ID en het tijdstip van een foto is af te leiden welke foto’s bij elkaar horen en achter elkaar genomen zijn. Voor deze post hebben we speciaal een dataset gemaakt van alle routes. Deze dataset staat [op GitHub](https://github.com/Amsterdam/panorama-visualization-data) en bevat GeoJSON-bestanden en _vector tiles_.

{% include full-width-start.liquid %}
{% include iframe.liquid
  src="https://amsterdam.github.io/panorama-visualization" class="vh-100"
  caption="Visualisatie van alle routes waarlangs panoramafoto’s genomen zijn." %}
{% include full-width-end.liquid %}

Vervolgens kunnen we deze routes openen met [QGIS](https://qgis.org/), van de lijnen polygonen maken, deze polygonen samenvoegen en het stuk dat niet binnen de gemeente Amsterdam valt verwijderen. Met QGIS kan dit op de volgende manier:

1. Download `sequences.geojson` van [GitHub](https://github.com/Amsterdam/panorama-visualization-data)), en open dit bestand met QGIS;
2. Kies _Vector_ ⟶ _Geoprocessing Tools_ ⟶ _Buffer…_ om een rand van een aantal meter dik om de lijnen te genereren en er zo polygonen van te maken. Hoe dikker deze rand, hoe vaker we in gebieden terecht zullen komen waar geen foto’s gemaakt zijn. Als de rand te dun is worden routes waar meerdere keren foto’s zijn genomen maar niet precies op elkaar liggen niet samengevoegd, en zullen straten die vaker gefotografeerd zijn vaker worden gekozen. In dit voorbeeld hebben we voor een afstand van 200 meter gekozen. __Belangrijk: de bewerkingen kunnen het beste worden uitgevoerd in EPSG:28992 (ofwel Rijksdriehoekscoördinaten), alle afstanden zijn dan in meters.__
3. Kies vervolgens _Vector_ ⟶ _Geoprocessing Tools_ ⟶ _Dissolve…_ om de losse polygonen samen te voegen tot één vorm.
4. Open `gemeente-amsterdam.geojson` (wederom te vinden in het GitHub-project), met _Vector_ ⟶ _Geoprocessing Tools_ ⟶ _Intersection…_ kunnen we het stuk van de samengevoegde polygonen die buiten Amsterdam liggen verwijderen.

{% include figure.liquid
  caption="Alle panorama-routes, samengevoegd, en met een extra rand van 200 meter breed."
  alt="Panoramaroutes in QGIS"
  src="qgis.jpg" %}

We zijn er bijna! Het enige dat nog ontbreekt is een algoritme om een willekeurige punt in een polygoon te selecteren. Voor rechthoeken en driehoeken is dit eenvoudig, maar complexere veelhoeken is er een extra stap nodig. Door de polygoon eerst op te delen in driehoeken, en bij elke zoekopdracht naar een nieuwe panoramafoto eerst een willekeurige driehoek te kiezen en dan een willekeurig punt in die driehoek, hebben we een efficiente en elegante manier om een willekeurige panoramafoto in Amsterdam te vinden. Let wel: we kunnen niet zomaar een willekeurige driehoek te kiezen, maar we moeten grotere driehoeken vaker kiezen dan kleine. Wie meer wil lezen over dit algoritme verwijzen we wederom naar een [Observable-notebook](https://observablehq.com/@scarysize/finding-random-points-in-a-polygon).

{% include figure.liquid
  caption="De oppervlakte onderverdeeld in driehoeken met een <a href=\"https://nl.wikipedia.org/wiki/Delaunay-triangulatie\">Delaunay-triangulatie</a>
."
  alt="triangulation"
  src="sequences-triangulation.svg" %}

Het opdelen van polygonen in driehoeken kan op veel manieren. Het kan in de browser met JavaScript, bijvoorbeeld met [Earcut](https://github.com/mapbox/earcut). Wij kozen wederom voor QGIS:

1. Maak eerst losse punten van de polyoon: _Vector_ ⟶ _Geometry Tools_ ⟶ _Extract Vertices…_.
2. Daarna kan van deze punten een [Delaunay-triangulatie](https://nl.wikipedia.org/wiki/Delaunay-triangulatie) worden berekend: _Vector_ ⟶ _Geometry Tools_ ⟶ _Delaunau Triangulation…_
3. Als laatste gebruiken we weer een _Intersection_ om de gaten uit de triangulatie te knippen.

Het resultaat kunnen we nu exporteren als GeoJSON, en gebruiken in de webapplicatie. Kies altijd de projectie EPSG:4326 als je GeoJSON-bestanden exporteert voor gebruik op het web!

## Marzipano, Leaflet en Turf.js

De webapplicatie bestaat uit twee onderdelen: de gebruikers zien de panoramafoto zo groot mogelijk in beeld. Rechtsonder in beeld staat een kleine kaart waarmee de locatie van de foto kan worden gezocht. [Marzipano](http://www.marzipano.net/) kan als volgt worden toegevoegd:

```js
var marzipanoElement = document.getElementById('marzipano')

var viewerOptions = {
  stageType: null,
  stage: {
    preserveDrawingBuffer: true,
    width: 960
  }
}

var viewer = new Marzipano.Viewer(marzipanoElement, viewerOptions)

// panoramaImage bevat een object van de Panorama-API
var source = Marzipano.ImageUrlSource
  .fromString(panoramaImage.cubic_img_pattern, {
    cubeMapPreviewUrl: panoramaImage._links.cubic_img_preview.href
  })

var initialView = {
  yaw: Math.random() * 360,
  fov: 90 * Math.PI / 180,
  pitch: 0,
}

var viewLimiter = Marzipano
  .RectilinearView
  .limit.traditional(12 * 1024, Math.PI / 2)

var view = new Marzipano.RectilinearView(initialView, viewLimiter)

var levelPropertiesList = [{
  tileSize: 256,
  size: 256,
  fallbackOnly: true
}, {
  tileSize: 512,
  size: 512
}, {
  tileSize: 512,
  size: 1024
}, {
  tileSize: 512,
  size: 2048
}]

var scene = this.viewer.createScene({
  source,
  geometry: new Marzipano.CubeGeometry(levelPropertiesList),
  view,
  pinFirstLevel: true
})

scene.switchTo()
```

{% include figure.liquid
  caption="Een Amsterdamse panoramafoto, weergegeven met Marzipano (waar is dit?)."
  alt="Een Amsterdamse panoramafoto, weergegeven met Marzipano"
  src="marzipano.jpg" %}

Op [het dataportaal](https://api.data.amsterdam.nl/api/) zijn naast webservices ook kaarttiles en luchtfoto’s te vinden. Met [Leaflet](https://leafletjs.com/) gebruik je deze zo:

```js
var mapElement = document.getElementById('map')
var map = L.map(mapElement).setView([52.369, 4.922], 12)

var tileUrl = 'https://{s}.data.amsterdam.nl/topo_wm_light/{z}/{x}/{y}.png'

L.tileLayer(tileUrl, {
  subdomains: ['t1', 't2', 't3', 't4'],
  maxZoom: 19
}).addTo(map)
```

Als de speler denkt te weten waar de foto genomen is kunnen we met [Turf.js](http://turfjs.org/docs/#distance) uitrekenen wat de afstand in meters is tussen deze locatie en de plek waar de foto genomen is.

## Waar ben ik?

Nu moeten alles wat hierboven beschreven is samenvoegen tot een webapplicatie. Uiteindelijk heeft ons spel ook een goede naam nodig, maar laten we voorlopig __Waar ben ik?__ als naam gebruiken. Voor wie precies wil weten hoe de applicatie, gemaakt met [Vue.js](https://vuejs.org/), in elkaar zit kan [op GitHub kijken](https://github.com/bertspaan/waar-ben-ik).

We hebben al genoeg technologie besproken in deze post, we kunnen 't spel beter gaan spelen: __[bertspaan.nl/waar-ben-ik](https://bertspaan.nl/waar-ben-ik)__.

{% include figure.liquid
  caption="<a href=\"https://bertspaan.nl/waar-ben-ik\">Waar ben ik?</a>"
  alt="Waar ben ik?"
  src="waar-ben-ik.jpg" %}

__Wie wil meehelpen om van _Waar ben ik?_ een multiplayer-spel te maken? Stuur een bericht op [Twitter](https://twitter.com/bertspaan)!__
