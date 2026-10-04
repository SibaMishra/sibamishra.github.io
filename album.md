---
layout: page
title: Album
permalink: /album/
---

<div class="album notranslate">
{% for p in site.data.album %}  <figure class="album-item">
    <a href="{{ p.full | default: p.image | relative_url }}" target="_blank" rel="noopener"><img src="{{ p.image | relative_url }}" alt="{{ p.title | escape }}" loading="lazy"></a>
    <figcaption><b>{{ p.title }}</b><span>{{ p.event }}{% if p.date %} · {{ p.date }}{% endif %}</span>{% if p.link %}<a class="album-link" href="{{ p.link }}" target="_blank" rel="noopener">Event report</a>{% endif %}</figcaption>
  </figure>
{% endfor %}</div>
