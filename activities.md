---
layout: page
title: Activities
permalink: /activities/
title_right: act-filter.html
---
{% assign A = site.data.activities %}
<div class="act-stats">
  <div class="stat"><b>{{ A.talks | size }}</b><span>Invited talks</span></div>
  <div class="stat"><b>{{ A.service | size }}</b><span>Committee and chair roles</span></div>
  <div class="stat"><b>{{ site.data.reviewer | size }}</b><span>Journals reviewed</span></div>
  <div class="stat"><b>{{ A.conference_reviewing | size }}</b><span>Conferences reviewed</span></div>
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
{% include act-timeline.html items=A.conference_reviewing %}

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
<div class="course-grid notranslate">
{% for c in A.courses %}<div class="course"><span class="role {% if c.kind == 'Lab' %}role-chair{% else %}role-pc{% endif %}">{{ c.kind }}</span><b>{{ c.name }}</b><span class="course-meta">{{ c.program }}{% if c.year %} · {{ c.year }}{% endif %}</span></div>
{% endfor %}</div>

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
