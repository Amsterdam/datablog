---
title: Historische Kaarten in het Dataportaal
lang: nl
ref: historical-maps
author: bert
---

Via het Dataportaal van de Gemeente Amsterdam kunnen historische kaarten van de Dienst der Publieke Werken worden bekeken. Het kaartmateriaal is ook beschikbaar voor eigen gebruik.

In 1909 was Amsterdam een stuk kleiner dan nu: ten westen van het Vondelpark, ten zuiden van de Pijp en ten oosten van de Dapperbuurt hield de stad op. Daarbuiten lagen polders met boerderijen. Ook het gebied aan de overkant van het IJ was grotendeels nog leeg, op een paar fabrieken en scheepswerven en de dijkdorpen Buiksloot en Nieuwendam na.

75 jaar later, in 1985, had de stad bijna dezelfde omvang als vandaag, alhoewel Amsterdam toen maar 100,000 inwoners meer had dan in 1909. Na jaren van groei daalde het inwonertal vanaf eind jaren zestig en bereikte in 1984 het laagste punt. Inwoners vertrokken naar plaatsen zoals Purmerend, Hoofddorp en Almere, en veel industrie en bedrijvigheid verliet de stad. De fabrieken, havens, pakhuizen en rangeerterreinen die achterbleven zouden pas jaren later worden gerenoveerd of gesloopt.

In dezelfde periode produceerde de gemeentelijke Dienst der Publieke Werken (in 1980 hernoemd tot de Dienst Openbare Werken) een collectie gedetailleerde topografische kaarten van de stad, waarvan de kaartbladen bij elke stadsvernieuwing en uitbreiding herzien werden. Het Amsterdamse Stadsarchief heeft een groot gedeelte van deze kaarten gedigitaliseerd, ze zijn te bekijken en downloaden via de [Beeldbank van het Stadsarchief](https://beeldbank.amsterdam.nl/beeldbank/indeling/grid?q_searchfield=publieke+werken&f_sk_documenttype%5B0%5D=kaart). (Vóór 1909 werden er door de gemeente ook kaarten gemaakt, maar pas vanaf 1909 gebeurde dit voor de hele stad en volgens een vast stramien. Na 1985 werden de kaarten alleen nog digitaal uitgegeven.)

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

De kaarten van de Dienst der Publieke Werken geven prachtig weer hoe Amsterdam in de twintigste eeuw groeide en veranderde, maar via het Stadsarchief zijn alleen de losse kaartbladen te raadplegen. Om van de losse kaartbladen een digitale historische atlas van Amsterdam te maken moeten de kaarten allereerst worden _gegeorefereerd_. Georefereren is het zó draaien, uitrekken en soms vervormen van scans van kaartmateriaal zodat ze precies passend op bijvoorbeeld Google Maps gelegd kunnen worden. Als daarna de kaarten worden uitgeknipt zodat de lege randen wegvallen kunnen de kaartbladen vervolgens met geografische software tot één kaart worden samengevoegd. Het georefereren en uitknippen van kaarten is tijdrovend precisiewerk, maar gelukkig heeft [Jan Hartmann](https://www.uva.nl/profiel/h/a/j.l.h.hartmann/j.l.h.hartmann.html) van de Universiteit van Amsterdam een aantal jaar geleden een groot gedeelte van dit werk al gedaan. Op de website van de [Amsterdam Time Machine](https://tiles.amsterdamtimemachine.nl) kan het resultaat van zijn werk worden bekeken.

__Een selectie van de kaarten van de Dienst der Publieke Werken zijn vanaf nu beschikbaar via het Dataportaal van de gemeente Amsterdam!__

{% include figure.liquid
  caption="<a href=\"https://data.amsterdam.nl/data/monumenten/monumenten/id8ce679b8-86b4-4331-bb79-bdc6d340d01d/?modus=kaart&center=52.3681675%2C4.9373697&lagen=pw1909%3A1%7Ctcmnmt%3A1&legenda=true&zoom=13\">Gemeente- en rijksmonumenten op het voormalige veemarktterrein</a>."
  alt="Veemarkt"
  src="1909-in-city-data.jpg" %}

Om de kaarten geschikt te maken voor het dataportaal heb ik scripts en databestanden van Jan Hartmann – met zijn hulp – verbeterd en aangevuld. Ook heb ik een aantal onnauwkeurigheden gerepareerd en ontbrekende kaartbladen toegevoegd. Binnenkort zal ik nog een aantal jaargangen van de Dienst der Publieke Werken-kaarten publiceren.

