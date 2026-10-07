---
layout: layouts/base.njk
permalink: /diario/
title: "Diario di Campagna"
templateEngineOverride: njk
---
<div class="pergamena-container">
  <h1>Diario di Campagna</h1>
  <p>Qui trovate tutti i resoconti delle sessioni di gioco, in ordine cronologico dal più recente al più antico.</p>
  
  <ul class="lista-capitoli">
  {% for capitolo in collections.diario | reverse %}
    <li>
      <strong><a href="{{ capitolo.url }}">{{ capitolo.data.title }}</a></strong>
      {% if capitolo.data.date %}
        <span class="data-sessione"> — {{ capitolo.data.date }}</span>
      {% endif %}
    </li>
  {% endfor %}
  </ul>
</div>
