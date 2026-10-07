---
layout: layouts/base.njk
permalink: /mappe/
title: "Atlante & Mappe"
templateEngineOverride: njk
---
<div class="pergamena-container">
  <h1 style="text-align: center;">Atlante di Krynn</h1>
  <p style="text-align: center; margin-bottom: 2rem;">Le mappe e i luoghi esplorati durante la campagna.</p>

  <div style="display: flex; flex-wrap: wrap; gap: 2rem; justify-content: center;">
  {% for mappa in collections.mappe %}
    <div style="width: 320px; text-align: center; background: rgba(255,255,255,0.4); padding: 1rem; border-radius: 8px; border: 2px solid #8b5a2b; box-shadow: 2px 2px 8px rgba(0,0,0,0.3);">
      <h3 style="margin-top: 0;">{{ mappa.data.title }}</h3>
      {% if mappa.data.image %}
        <a href="{{ mappa.url }}">
          <img src="{{ mappa.data.image }}" alt="{{ mappa.data.title }}" style="width: 100%; height: 220px; object-fit: cover; border: 3px solid #4a2f1d; border-radius: 4px; margin: 1rem 0;">
        </a>
      {% endif %}
      <p style="margin-bottom: 0;"><a href="{{ mappa.url }}" style="font-weight: bold; text-decoration: none; color: #4a2f1d;">Esplora la mappa &rarr;</a></p>
    </div>
  {% else %}
    <p><em>Nessuna mappa disponibile al momento.</em></p>
  {% endfor %}
  </div>
</div>
