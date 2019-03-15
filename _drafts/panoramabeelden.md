---
title: 360° Panoramafoto’s van de hele stad
lang: nl
ref: panorama
author: bert
---

Via het dataportaal is de hele stad te bekijken, 360° Panoramafoto’s van Amsterdam, open data. In deze blogpost laten we zien hoe je deze afbeeldingen kunt gebruiken! En, leuker nog, wat je ermee kan maken!

Geschiedenis: ambtenaren moeten kunnen zien hoe de stad er uit ziet. Werkzaamheden, WOZ, gevaarlijke kruispunten, dit zijn een paar voorbeelden.

Google Street View: autootje komt niet overal, niet in parken, in stegen, op de grachten, wijken in aanbouw, en bovendien bepaalt Google zélf wanneer ze ergens nieuwe foto's maken. In het verleden gebruikte de gemeente de diensten van https://www.cyclomedia.com/, maar de afbeeldingen blijven eigendom van dit bedrijf. tot dat besloten werd dat het zelf beter en goedkoper kan, bovendien afbeeldingen open aanbieden. (Ook leuk voorbeeld (ook om belasting-waarde te bepalen): http://80s.nyc/.)

Afgelopen jaren: eigen auto met panoramacamera, rijd elk jaar overal, soms meerdere keren voor nieuwe wijken en bv. WOZ, zoveel km, zoveel foto's, straten. Ook gemeente Weesp, Almere en Amstelveen.

Dataportaal: voorbeeldlinks! Screenshot! Paar gekke plekken, links of plaatjes. De foto's kunnen door iedereen worden gebruikt, en de afbeeldingen kunnen worden gezocht en benaderd via een REST API!

Wat doen we nu met deze foto's? Ambtenaren, in dataportaal bij elk adres en gebouw, andere gemeentetoepassingen. Maar ook: experimenten met beeldherkenning, kunnen we nummberbordeen herkennen, kwaliteit van strepen op de weg, andere objecten in de openbare ruimte. Ook in Mapillary, bv.

Idee: geoguessr voor amsterdam met marzipano. Waar ben je in de stad, raad je plek aan hand van willekeurige panoramafoto. Applicatie bestaat uit 3 onderdelen: kaart, panoviewer, en stukje dat steeds de afstand uitrekent.
Hoe kun je dit maken? Je kunt aan REST API niet vragen: geef me willekeurige foto. Wél: geef me dichstbijzijnde foto bij punt (tot max x meter).

Laat zien hoe API werkt. Voorbeeld: JS fetch, grijp pano, welke data krijg je terug.
hoe pak je willekeurige punt in amsterdam waar foto's zijn gemaakt?

visualisatie van alle routes!

Als we alle routes hebben, kunnen we daar polygoon van maken, en dan met algoritme (bv https://stackoverflow.com/questions/19481514/how-to-get-a-random-point-on-the-interior-of-an-irregular-polygon) een willekeurig punt in deze polygoon pakken.

Hoe laten we in JS panoramabeeld zien: voorbeeld: marzipano!

hoe laten we in JS met Leaflet Amsterdamse kaart zien. Voorbeeld: leaflet amsterdam tiles.

Met Turf.js kunnen we uitrekenen wat de afstand is tussen de gekozen locatie en de panoramafoto.
Voorbeeld Turf.

Link naar applicatie! GitHub!
