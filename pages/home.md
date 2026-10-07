---
layout: layouts/base.njk
permalink: /
title: "Cronache di Krynn"
templateEngineOverride: njk
---
<div class="pergamena-container home-portal">
  <header class="home-intro">
    <img src="/static/img/Gemini_Generated_Image_Dragonlance.jpg" alt="Logo Dragonlance" style="width: 100%; max-width: 800px; height: auto; display: block; margin: 0 auto 1.5rem auto; border-radius: 4px; box-shadow: 0 4px 8px rgba(0,0,0,0.5);">
    <p class="citazione-motto"><em>"I veri eroi non nascono dalla gloria, ma dalla necessità di proteggere ciò che amano."</em></p>
    <p>Benvenuti nell'archivio della campagna. Attraverso queste pergamene potrete consultare le gesta dei compagni, conoscere gli alleati e i nemici incontrati lungo il cammino, e consultare la cartografia delle terre di Ansalon.</p>
  </header>

  <hr>

  <div class="sezioni-grid">
    <div class="sezione-card">
      <h2>Diario di Campagna</h2>
      <p>I resoconti dettagliati delle sessioni di gioco, registrati cronologicamente dagli avventurieri.</p>

      <h3>Ultimi Capitoli</h3>
      <ul class="lista-breve">
      {% for capitolo in (collections.diario | reverse) %}
        {% if loop.index <= 3 %}
          <li><a href="{{ capitolo.url }}">{{ capitolo.data.title }}</a></li>
        {% endif %}
      {% endfor %}
      </ul>

      <p class="cta-link"><a href="/diario/">Leggi tutto il Diario &rarr;</a></p>
    </div>

    <div class="sezione-card">
      <h2>Dramatis Personae</h2>
      <p>Le schede dei Protagonisti (PC) e dei principali Personaggi Non Giocanti (PNG) della storia.</p>
      <p class="cta-link"><a href="/personaggi/">Esplora i Personaggi &rarr;</a></p>
    </div>

    <div class="sezione-card">
      <h2>Atlante di Krynn</h2>
      <p>Mappe, città, punti d'interesse e note storiche sui luoghi esplorati dal gruppo.</p>
      <p class="cta-link"><a href="/mappe/">Consulta le Mappe &rarr;</a></p>
    </div>
  </div>
</div>
