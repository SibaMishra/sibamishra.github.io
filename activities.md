---
layout: page
title: Professional Affiliations
permalink: /activities/
---
---
<ol>
<li><strong>Professional Member</strong>. Association for Computing Machinery (ACM). </li>
<li><strong>Member</strong>. India SOFTware Engineering community (ISOFT). </li>
<li><strong>Graduate Student Member</strong>. Institute of Electrical and Electronics Engineers (IEEE). </li>
<li><strong>Member</strong>. Computer Science and Engineering (CSE) Society, IIT(ISM) Dhanbad. </li>
</ol>{: style="text-align: justify !important;text-justify: inter-word"}

# Journal Reviewer
---
<style>
.rv-badges{display:flex;flex-wrap:wrap;gap:8px;margin:0 0 1.5em}
.rv-badge{display:inline-flex;font-size:13px;line-height:1.4;border-radius:4px;overflow:hidden;text-decoration:none !important;border:1px solid rgba(0,0,0,.12)}
.rv-badge span{padding:3px 9px}
.rv-badge .rv-l{background:#444441;color:#f1efe8}
.rv-badge:hover{opacity:.85}
.rv-elsevier{background:#faeeda;color:#633806}.rv-springer{background:#e6f1fb;color:#0c447c}.rv-nature{background:#e1f5ee;color:#085041}
.rv-wiley{background:#eeedfe;color:#3c3489}.rv-igi{background:#faece7;color:#712b13}.rv-tandf{background:#fbeaf0;color:#72243e}.rv-frontiers{background:#eaf3de;color:#27500a}
</style>
<div class="rv-badges">
{% for r in site.data.reviewer %}{% if r.certificate %}{% assign link = r.certificate | relative_url %}{% else %}{% assign link = r.url %}{% endif %}{% if link %}<a class="rv-badge" target="_blank" href="{{ link }}" title="{{ r.journal }} ({{ r.year }}){% if r.certificate %} - view certificate{% endif %}">{% else %}<span class="rv-badge" title="{{ r.journal }} ({{ r.year }})">{% endif %}<span class="rv-l">Reviewer</span><span class="rv-{{ r.publisher }}">{{ r.journal }}</span>{% if link %}</a>{% else %}</span>{% endif %}
{% endfor %}
</div>

# Professional Activities
---
- **Volunteer**. The Fourth Paradigm : From Data to Discovery, Bhopal, India.
{: style="text-align: justify !important;text-justify: inter-word"}

# Teaching Assistantships

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

<small> For complete list, please visit my <a target="_blank" href="https://sibamishra.github.io/assets/cv/SIBA_CV.pdf"><span style="text-align:right;font-size:15px;text-color:black;"></span><u>CV</u></a>.</small>
