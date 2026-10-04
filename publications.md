---
layout: page
permalink: /publications/
title: Publications and Patents
tags: [about, publications, patents]
---

{% assign pubs = site.data.publications %}
{% assign years = pubs | map: 'year' | uniq %}
<div class="pub-filters">
  <div class="pub-row" role="group" aria-label="Year">
    <span class="pub-label">Year</span>
    {% for y in years %}<button type="button" class="pub-btn" data-year="{{ y }}">{{ y }}</button>{% endfor %}
    <button type="button" class="pub-btn" data-year="all">All</button>
  </div>
  <div class="pub-row" role="group" aria-label="Type">
    <span class="pub-label">Type</span>
    <button type="button" class="pub-btn" data-type="all">All</button>
    <button type="button" class="pub-btn" data-type="journal">Journal</button>
    <button type="button" class="pub-btn" data-type="conference">Conference</button>
    <button type="button" class="pub-btn" data-type="patent">Patent</button>
  </div>
</div>

<p class="pub-count" id="pub-count"></p>

<ul class="pub-list notranslate" id="pub-list">
{% for p in pubs %}<li data-year="{{ p.year }}" data-type="{{ p.type }}"><span class="pub-tag pub-tag-{{ p.type }}">{% if p.type == 'patent' %}Patent{% if p.status %} · {{ p.status }}{% endif %}{% elsif p.type == 'journal' %}Journal{% else %}Conference{% endif %}</span> <span class="pub-year">{{ p.year }}</span><br>{{ p.text | markdownify | remove: '<p>' | remove: '</p>' }}</li>
{% endfor %}
</ul>
<p class="pub-empty" id="pub-empty" hidden>Nothing for this year and type. Try another year or <strong>All</strong>.</p>

<noscript><style>.pub-filters,.pub-count{display:none}</style></noscript>

<script>
(function(){
  var list=document.getElementById('pub-list'); if(!list) return;
  var items=[].slice.call(list.children), yb=[].slice.call(document.querySelectorAll('.pub-btn[data-year]')), tb=[].slice.call(document.querySelectorAll('.pub-btn[data-type]'));
  var year=yb.length?yb[0].getAttribute('data-year'):'all', type='all';
  if(location.hash==='#patents'){type='patent';year='all';}
  else if(location.hash==='#journals'){type='journal';year='all';}
  else if(location.hash==='#conferences'){type='conference';year='all';}
  function render(){
    var n=0;
    items.forEach(function(li){var ok=(year==='all'||li.getAttribute('data-year')===year)&&(type==='all'||li.getAttribute('data-type')===type);li.hidden=!ok;if(ok)n++;});
    yb.forEach(function(b){var on=b.getAttribute('data-year')===year;b.classList.toggle('is-on',on);b.setAttribute('aria-pressed',on);});
    tb.forEach(function(b){var on=b.getAttribute('data-type')===type;b.classList.toggle('is-on',on);b.setAttribute('aria-pressed',on);});
    document.getElementById('pub-empty').hidden=n>0;
    document.getElementById('pub-count').textContent=n+(n===1?' item':' items')+' · '+(year==='all'?'all years':year);
  }
  yb.forEach(function(b){b.addEventListener('click',function(){year=b.getAttribute('data-year');render();});});
  tb.forEach(function(b){b.addEventListener('click',function(){type=b.getAttribute('data-type');render();});});
  render();
})();
</script>
