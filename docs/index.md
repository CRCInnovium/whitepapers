---
layout: default
title: Research publications
---
<main id="main">
<section class="hero"><div class="eyebrow">InnoviumAI / Research</div><h1>Research publications</h1><p class="intro">Studies, technical reports and whitepapers<br>from the team behind InnoviumAI.</p></section>
{% assign papers = site.pages | where: 'layout', 'publication' | sort: 'document_date' | reverse %}
<div class="sectionhead"><h2>Latest research</h2><span class="count">{{ papers.size }} {% if papers.size == 1 %}PUBLICATION{% else %}PUBLICATIONS{% endif %}</span></div>
{% assign previous_year = '' %}
{% for paper in papers %}
{% assign year = paper.document_date | date: '%Y' %}
{% if year != previous_year %}<div class="year-title">{{ year }}</div>{% assign previous_year = year %}{% endif %}
<article class="publication">
  {% if paper.cover %}<a class="cover" href="{{ paper.url | relative_url }}" aria-label="Read {{ paper.title | escape }}"><img src="{{ paper.cover | relative_url }}" alt="Cover of {{ paper.title | escape }}" loading="lazy"></a>{% else %}<a class="cover" href="{{ paper.url | relative_url }}"><span class="eyebrow">{{ paper.document_type | escape }}</span><h2>{{ paper.title | escape }}</h2></a>{% endif %}
  <div><div class="meta"><span class="tag">{{ paper.document_type | escape }}</span><span>{{ paper.document_date | date: '%B %Y' }}</span></div>
    <h2 class="paper-title"><a href="{{ paper.url | relative_url }}">{{ paper.title | escape }}</a></h2>
    <p class="sub">{{ paper.subtitle | default: paper.description | escape }}</p>
    <p class="authors">{{ paper.authors | join: ' · ' | escape }}</p><p class="affiliation">{{ paper.affiliation | escape }}</p>
    <div class="actions"><a class="button" href="{{ paper.url | relative_url }}">Explore the research →</a><a class="textlink" href="{{ paper.pdf | relative_url }}">Read PDF ↗</a></div>
  </div>
</article>
{% endfor %}
</main>
