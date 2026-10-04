---
layout: page
title: Activities
permalink: /activities/
title_right: act-filter.html
---
{% assign A = site.data.activities %}
<div class="act-stats">
  <a class="stat" href="#talks"><b>{{ A.talks | size }}</b><span>Invited talks</span></a>
  <a class="stat" href="#service"><b>{{ A.service | size }}</b><span>Committee and chair roles</span></a>
  <a class="stat" href="#reviewing"><b>{{ site.data.reviewer | size }}</b><span>Journals reviewed</span></a>
  <a class="stat" href="#reviewing"><b>{{ A.conference_reviewing | size }}</b><span>Conferences reviewed</span></a>
</div>

<div class="act-sec" id="talks" markdown="1">

## Invited Talks
{% include act-timeline.html items=A.talks %}

</div>

<div class="act-sec" id="service" markdown="1">

## Professional Service

#### Program Committee, Chairs and Editorial Roles
{% include act-timeline.html items=A.service %}

#### Volunteering
{% include act-timeline.html items=A.volunteering %}

</div>

<div class="act-sec" id="reviewing" markdown="1">

## Reviewing

#### Journals

<style>
.rv-badges{display:flex;flex-wrap:wrap;gap:8px;margin:0 0 1.5em}
.rv-badge{display:inline-flex;font-size:13px;line-height:1.4;border-radius:4px;overflow:hidden;text-decoration:none !important;border:1px solid rgba(0,0,0,.12)}
.rv-badge span{padding:3px 9px}
.rv-badge .rv-l{background:#444441;color:#f1efe8}
.rv-badge:hover{opacity:.85}
.rv-elsevier{background:#faeeda;color:#633806}.rv-springer{background:#e6f1fb;color:#0c447c}.rv-nature{background:#e1f5ee;color:#085041}
.rv-wiley{background:#eeedfe;color:#3c3489}.rv-igi{background:#faece7;color:#712b13}.rv-tandf{background:#fbeaf0;color:#72243e}.rv-frontiers{background:#eaf3de;color:#27500a}
</style>
<div class="rv-badges notranslate">
{% for r in site.data.reviewer %}{% if r.certificate %}{% assign link = r.certificate | relative_url %}{% else %}{% assign link = r.url %}{% endif %}{% if link %}<a class="rv-badge" target="_blank" href="{{ link }}" title="{{ r.journal }} ({{ r.year }}){% if r.certificate %} - view certificate{% endif %}">{% else %}<span class="rv-badge" title="{{ r.journal }} ({{ r.year }})">{% endif %}<span class="rv-l">Reviewer</span><span class="rv-{{ r.publisher }}">{{ r.journal }}</span>{% if link %}</a>{% else %}</span>{% endif %}
{% endfor %}
</div>

#### Conferences
{% include act-timeline.html items=A.conference_reviewing older_than=2024 %}

</div>

<div class="act-sec" id="memberships" markdown="1">

## Professional Memberships
<div class="mem-pills notranslate">
{% for m in A.memberships %}<span class="mem-pill"><b>{{ m.org }}</b> {{ m.role }} · since {{ m.since }}</span>
{% endfor %}</div>

</div>

<div class="act-sec" id="teaching" markdown="1">

## Teaching

#### Courses Taught at C. V. Raman Global University

<div class="term-filter"><label class="pub-field"><span class="pub-label">Semester</span>
<select id="term-select" class="pub-select"></select></label></div>
<div class="course-grid notranslate" id="course-grid">
{% for c in A.courses %}{% if c.term == 'Autumn' %}{% assign tk = c.year | append: '-2' %}{% else %}{% assign tk = c.year | append: '-1' %}{% endif %}<div class="course" data-term="{{ tk }}" data-label="{{ c.term }} {{ c.year }}"><span class="role {% if c.kind == 'Lab' %}role-chair{% else %}role-pc{% endif %}">{{ c.kind }}</span><b>{{ c.name }}</b><span class="course-meta">{% if c.program %}{{ c.program }} · {% endif %}{{ c.term }} {{ c.year }}</span></div>
{% endfor %}</div>
<script>
(function(){
  var sel=document.getElementById('term-select'), cards=[].slice.call(document.querySelectorAll('#course-grid .course'));
  if(!sel||!cards.length) return;
  var seen={},terms=[];
  cards.forEach(function(c){var k=c.getAttribute('data-term');if(!seen[k]){seen[k]=c.getAttribute('data-label');terms.push(k);}});
  terms.sort().reverse();
  terms.forEach(function(k){var o=document.createElement('option');o.value=k;o.textContent=seen[k];sel.appendChild(o);});
  var all=document.createElement('option');all.value='all';all.textContent='All semesters';sel.appendChild(all);
  function show(){cards.forEach(function(c){c.hidden=!(sel.value==='all'||c.getAttribute('data-term')===sel.value);});}
  sel.addEventListener('change',show); show();
})();
</script>

#### Teaching Assistantships

<div class="table-scroll" markdown="1">

{:.mytable2}
| Semester     | Course Name |                       
| -------------| ------------|   
| Winter-20    | Data Structures and Algorithms at IISER, Bhopal |  
| Monsoon-19   | Theory of Computation at IISER, Bhopal         | 
| Monsoon-18   | Introduction to Software Modeling and Verification (lab session) using New Symbolic Model Verifier at IISER, Bhopal|
| Winter-17    | Database Management Systems Lab at IIT(ISM), Dhanbad | 
| Winter-16    | C Programming Lab at IIT(ISM), Dhanbad               | 
| Monsoon-15   | Software Engineering Lab at IIT(ISM), Dhanbad      | 
| Winter-14    | Algorithm Design and Analysis Lab at IIT(ISM), Dhanbad| 
| Monsoon-13   | Data Structures Lab at IIT(ISM), Dhanbad   |

</div>

</div>
