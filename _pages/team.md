---
layout: page
permalink: /team/
title: team
description: Our team
nav: true
nav_order: 1
---

{% for person in site.data.members %}

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px;">
    <img style="float: right; width: 200px; padding-right: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{person.name}}">
    <div>
        <h4>{{person.name}}{% if person.degrees %}, {{person.degrees}} {% endif %}</h4> 
        {{person.position}} <br>
        <!---
        <i class="fa fa-envelope"></i> <em>{{person.email}}</em> <br>
        {% if person.twitter %}
          <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{person.twitter}}" target="_blank"> @{{person.twitter}} </a> <br>
        {% endif %}
        {% if person.website %}
          <i class="fa fa-globe"></i> <a href= "{{person.website}}" target="_blank">{{person.website}}</a> <br>
        {% endif %}
        -->
        {% if person.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{person.github}}" target="_blank"> {{person.github}} </a> <br>
        {% endif %}
        <!---
        {% if person.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank"> Google Scholar </a> <br>
        {% endif %}
        {% if person.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://https://orcid.org/{{person.orcid}}" target="_blank"> ORCID</a> <br>
        {% endif %}
        {% if person.researchgate %}
          <i class="ai ai-researchgate"></i> <a href="http://https://www.researchgate.net/profile/{{person.researchgate}}" target="_blank"> Research Gate</a> <br>
        {% endif %}
        {% if person.orcid %}<a href="http://https://orcid.org/{{person.orcid}}" target="_blank" title="ORCID"><i class="ai ai-orcid"></i></a>{% endif %}
        {% if person.scholar %}<a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
        {% if person.researchgate %}<a href="http://https://www.researchgate.net/profile/{{person.researchgate}}" target="_blank" title="Research Gate"><i class="ai ai-researchgate"></i></a>{% endif %}
        -->
        {%- if person.email -%}
        <a href="mailto:{{ person.email | encode_email }}" title="email"><i class="fas fa-envelope"></i></a>
        {% endif %}
        {%- if person.orcid_id -%}
        <a href="https://orcid.org/{{ site.orcid_id }}" title="ORCID"><i class="ai ai-orcid"></i></a>
        {% endif %}
        {%- if person.scholar_userid -%}
        <a href="https://scholar.google.com/citations?user={{ site.scholar_userid }}" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>
        {% endif %}
    </div>
    <div class="col-sm-8">
        <p class="text-justify">{{person.description | markdownify}}</p>
        {% reference bera_topological_2023 %}
    </div>
</div>
<hr>
{% endfor %}

{% if site.data.affiliates %}
  <h2>affiliate members</h2>
  {% for person in site.data.affiliates %}
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px;">
    <img style="float: right; width: 42%; padding-left: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{person.name}}">
    <div>
        <h4>{{person.name}}{% if person.degrees %}, {{person.degrees}} {% endif %}</h4> 
        {{person.position}} <br>
        <i class="fa fa-envelope"></i> <em>{{person.email}}</em> <br>
        {% if person.twitter %}
          <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{person.twitter}}" target="_blank"> @{{person.twitter}} </a> <br>
        {% endif %}
        {% if person.website %}
          <i class="fa fa-globe"></i> <a href= "{{person.website}}" target="_blank">{{person.website}}</a> <br>
        {% endif %}
        {% if person.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{person.github}}" target="_blank"> {{person.github}} </a> <br>
        {% endif %}
        {% if person.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank"> Scholar Citations </a> <br>
        {% endif %}
        {% if person.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://{{person.orcid}}" target="_blank"> {{person.orcid}}</a> <br>
        {% endif %}

    </div>
    <div class="col-sm-8">
        <p class="text-justify">{{person.description | markdownify}}</p>
    </div>
</div>
<hr>
  {% endfor %}
{% endif %}

<!-- ## students -->

{% if site.data.students %}
{% for student in site.data.students %} 

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{student.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; padding-bottom: 20px;">
  <strong>{{student.name}}{% if student.degrees %}, {{student.degrees}} {% endif %}</strong> <br>
  {{student.position}} <br>
  <i class="fa fa-envelope"></i> <em>{{student.email}}</em> <br>
  {% if student.description %}
  <div style="margin-left: 2.5em; padding-top: 8px; padding-bottom: 5px; ">{{student.description}}</div>
  {% else %}
  {% for paper in site.data.publications %}
  {% if paper.authors contains student.pubmed_name %}
  <div style="margin-left: 2.5em; padding-top: 8px; padding-bottom: 5px; ">{{paper.authors | remove: '**'}} <a href="/papers/index.html#{{paper.title}}">{{paper.title}}</a> {{paper.details}}</div>
  {% endif %}
  {% endfor %}
  {% endif %}
</div>

{% endfor %}
{%endif %}

<!--
---
## alumni
-->
{% if site.data.alumni %}
{% for alum in site.data.alumni %}

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{alum.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; padding-bottom: 20px;">
  <strong>{{alum.name}}{% if alum.degrees %}, {{alum.degrees}} {% endif %}</strong> <br>
  <i>previously:</i> {{alum.previously}} <br>
  <i>now:</i> {{alum.now}}<br>
    {% if alum.twitter %}
      <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{alum.twitter}}" target="_blank"> @{{alum.twitter}} </a> <br>
    {% endif %}
    {% if alum.website %} <i class="fa fa-globe"></i> <a href= "{{alum.website}}" target="_blank">{{alum.website}}</a>  {% endif %}
    {% for paper in site.data.publications %}
  {% if paper.authors contains alum.pubmed_name %}
  <div style="margin-left: 2.5em; padding-top: 8px; padding-bottom: 5px; ">{{paper.authors | remove: '**'}} <a href="/papers/index.html#{{paper.title | replace: ' ', '-' |  remove: '.'}}">{{paper.title}}</a> {{paper.details}}</div>
  {% endif %}
  {% endfor %}
</div>
{% endfor %}
{% endif %}

<!--
---
## collaborators
-->
{% if site.data.collaborators %}}
{% for collaborator in site.data.collaborators %}
- <strong>{{collaborator.name}}{% if collaborator.degrees %}, {{collaborator.degrees}} {% endif %}</strong>  
  {{collaborator.position}}  
  {% if collaborator.website %} <i class="fa fa-globe"></i> <a href= "{{collaborator.website}}" target="_blank">{{collaborator.website}}</a>  {% endif %}
{% endfor %}
{% endif %} 

