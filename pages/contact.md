---
layout: default
title: Contact
permalink: /contact/
cssLinks:
  - https://unpkg.com/leaflet@1.0.1/dist/leaflet.css
---

<script src="https://unpkg.com/leaflet@1.0.1/dist/leaflet.js"></script>
<div id="mapid" style="height: 300px"></div>
<script>
(function() {
  var osmURL = 'http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png';
  var osmAttrib = 'Map data © <a href="http://openstreetmap.org">OpenStreetMap</a> contributors';

  var latlng = [45.52044794511424, -73.56827795505525];

  var map = L.map('mapid').setView(latlng, 15);

  L.tileLayer(osmURL, {
    minZoom: 8,
    maxZoom: 20,
    attribution: osmAttrib
  }).addTo(map);

  var marker = L.marker(latlng)
    .bindPopup([
      '{{ site.contact.adresse }}',
      '{{ site.contact.code_postal }}'
    ].join('<br>'))
    .addTo(map)
    .openPopup();
})();

</script>

<div class="container">
  <ul class="no-bullet">
    <li>Adresse: {{ site.contact.adresse_longue }}</li>
    <li>Téléphone: {{ site.contact.telephone }}</li>
    <li>Courriel: {% include email.html %}</li>
  </ul>
</div>
