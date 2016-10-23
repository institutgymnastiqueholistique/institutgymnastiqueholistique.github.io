---
layout: default
title: Contact
permalink: /contact/
---

Contact Lucie

<div class="container">
  <ul class="no-bullet">
    <li>Adresse: {{ site.contact.adresse_longue }}</li>
    <li>Téléphone: {{ site.contact.telephone }}</li>
    <li>Courriel: {% include email.html %}</li>
  </ul>
</div>
