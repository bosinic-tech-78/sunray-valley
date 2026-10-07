---
layout: layouts/base.njk
permalink: /personaggi/
title: "Dramatis Personae"
templateEngineOverride: njk
---
<div class="pergamena-container">
  <h1 style="margin-bottom: 0.5rem;">Dramatis Personae</h1>
  <p style="text-align: center; margin-bottom: 3rem;">Qui trovate l'elenco dei Protagonisti (PG) e dei principali Personaggi Non Giocanti (PNG) incontrati durante l'avventura nelle terre di Ansalon.</p>

  <!-- =============================== -->
  <!-- SEZIONE EROI (PG)               -->
  <!-- =============================== -->
  <h2 style="text-align: center; color: #5c2018; margin-bottom: 1.5rem; font-family: 'Cinzel', serif; font-size: 2rem;">Gli Eroi</h2>
  
  <div class="sezioni-grid">
  {% for pg in collections.personaggi %}
    {% if pg.data.tipo != "PNG" %}
      <div class="sezione-card scheda-personaggio">
        <div class="personaggio-header">
          <h2>{{ pg.data.title }}</h2>
          {% if pg.data.tipo %}
            <div class="tipo-badge">[{{ pg.data.tipo }}]</div>
          {% else %}
            <div class="tipo-badge">[PG]</div>
          {% endif %}
        </div>

        {% if pg.data.image %}
          <div class="ritratto-container" style="margin: 0 auto 1rem auto;">
            <img src="{{ pg.data.image }}" alt="{{ pg.data.title }}" class="ritratto-img">
          </div>
        {% endif %}

        <p style="text-align: center;">
          <strong>
            {# Stampa la razza se esiste #}
            {% if pg.data.info_base.razza %}{{ pg.data.info_base.razza }}{% endif %}
            
            {# Va a capo solo se ci sono sia razza che classe #}
            {% if pg.data.info_base.razza and (pg.data.info_base.classi or pg.data.info_base.classe) %}<br>{% endif %}
            
            {# Gestione Classi/Professioni #}
            {% if pg.data.info_base.classi %}
              {% for c in pg.data.info_base.classi %}
                {{ c.nome }}{% if c.livello %} (Liv. {{ c.livello }}){% endif %}{% if not loop.last %} / {% endif %}
              {% endfor %}
            {% elif pg.data.info_base.classe %}
              {{ pg.data.info_base.classe }}{% if pg.data.info_base.livello %} (Liv. {{ pg.data.info_base.livello }}){% endif %}
            {% endif %}
          </strong>
        </p>

        <div class="statistiche-grid" style="margin-bottom: 1rem;">
          {% if pg.data.combattimento.ca %}
            <div class="stat-box">
              <span class="stat-label">CA</span>
              <span class="stat-value">{{ pg.data.combattimento.ca }}</span>
            </div>
          {% endif %}
          {% if pg.data.combattimento.pf_max %}
            <div class="stat-box">
              <span class="stat-label">PF</span>
              <span class="stat-value">{{ pg.data.combattimento.pf_max }}</span>
            </div>
          {% endif %}
        </div>

        <p class="cta-link"><a href="{{ pg.url }}">Leggi la scheda completa &rarr;</a></p>
      </div>
    {% endif %}
  {% endfor %}
  </div>

  <!-- =============================== -->
  <!-- DIVISORE GRAFICO                -->
  <!-- =============================== -->
  <div style="text-align: center; margin: 4rem 0 3rem 0;">
    <hr style="border: 0; height: 2px; background-color: #8b5a2b; width: 70%; margin: 0 auto; opacity: 0.6;">
    <span style="display: inline-block; position: relative; top: -14px; background: var(--pergamena-bg, #f4e8d1); padding: 0 15px; color: #8b5a2b; font-size: 1.5rem;">✦</span>
  </div>

  <!-- =============================== -->
  <!-- SEZIONE ALLEATI E AVVERSARI (PNG)-->
  <!-- =============================== -->
  <h2 style="text-align: center; color: #5c2018; margin-bottom: 1.5rem; font-family: 'Cinzel', serif; font-size: 2rem;">Alleati e Avversari</h2>
  
  <div class="sezioni-grid">
  {% for pg in collections.personaggi %}
    {% if pg.data.tipo == "PNG" %}
      <div class="sezione-card scheda-personaggio">
        <div class="personaggio-header">
          <h2>{{ pg.data.title }}</h2>
          <div class="tipo-badge">[{{ pg.data.tipo }}]</div>
        </div>

        {% if pg.data.image %}
          <div class="ritratto-container" style="margin: 0 auto 1rem auto;">
            <img src="{{ pg.data.image }}" alt="{{ pg.data.title }}" class="ritratto-img">
          </div>
        {% endif %}

        <p style="text-align: center;">
          <strong>
            {# Stampa la razza se esiste #}
            {% if pg.data.info_base.razza %}{{ pg.data.info_base.razza }}{% endif %}
            
            {# Va a capo solo se ci sono sia razza che classe #}
            {% if pg.data.info_base.razza and (pg.data.info_base.classi or pg.data.info_base.classe) %}<br>{% endif %}
            
            {# Gestione Classi/Professioni #}
            {% if pg.data.info_base.classi %}
              {% for c in pg.data.info_base.classi %}
                {{ c.nome }}{% if c.livello %} (Liv. {{ c.livello }}){% endif %}{% if not loop.last %} / {% endif %}
              {% endfor %}
            {% elif pg.data.info_base.classe %}
              {{ pg.data.info_base.classe }}{% if pg.data.info_base.livello %} (Liv. {{ pg.data.info_base.livello }}){% endif %}
            {% endif %}
          </strong>
        </p>

        <div class="statistiche-grid" style="margin-bottom: 1rem;">
          {% if pg.data.combattimento.ca %}
            <div class="stat-box">
              <span class="stat-label">CA</span>
              <span class="stat-value">{{ pg.data.combattimento.ca }}</span>
            </div>
          {% endif %}
          {% if pg.data.combattimento.pf_max %}
            <div class="stat-box">
              <span class="stat-label">PF</span>
              <span class="stat-value">{{ pg.data.combattimento.pf_max }}</span>
            </div>
          {% endif %}
        </div>

        <p class="cta-link"><a href="{{ pg.url }}">Leggi la scheda completa &rarr;</a></p>
      </div>
    {% endif %}
  {% endfor %}
  </div>

</div>
