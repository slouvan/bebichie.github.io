---
layout: page
title: Publications
description: ""
header-img: images/edin.jpg
comments: false
modified: 2016-03-18
---

## Conference Papers 
-----

<div class='panel-pub'>
<ol>
{% for article in site.data.journal.references %}
    <li>
    <div class="title">
    <span class="title">{{ article.title }}</span>
    {% if article.fulltext %}
        <a title="fulltext" href="{{ site.url }}/downloads/journal/{{ thesis.fulltext }}"><i class="fa fa-file-pdf-o"></i></a>
    {% endif %}
    </div>
    <div class='author'>
    {% for author in article.author %}
        <span class='{{ author.role }}'>{{ author.family }}, {{ author.given }}{% if author.role contains 'corr' %}*{% endif %}; </span>
    {% endfor %}
    </div>
    <div class="pubinfo">
    <span class="source">{{ article.container-title }} </span>
    <span class="year">{{ article.issued.date-parts[0][0] }},</span>
    <span class="volume">{{ article.volume }}, </span>
    <span class="page">{{ article.page }}.</span>
    </div>
    <div class="url">
        <a href="{{ article.URL }}">{{ article.URL }}</a>
    </div>
    </li>
{% endfor %}
</ol>
</div>


## Theses
-----

<div class='panel-pub'>
<ol>
{% for thesis in site.data.thesis %}
    <li>
    <div class="title">
    <span class="title">{{ thesis.title }}</span>
    {% if thesis.fulltext %}
        <a title="fulltext" href="{{ site.url }}/downloads/thesis/{{ thesis.fulltext }}"><i class="fa fa-file-pdf-o"></i></a>
    {% endif %}
    </div>
    <div class='author'>
    {% for author in thesis.author %}
        <span class='{{ author.role }}'>{{ author.literal }}</span>
    {% endfor %}
    </div>
    {% for advisor in thesis.advisor %}
        <span class='advisor'>{{ advisor.role }} : {{ advisor.literal }}</span>
    {% endfor %}
    <div class="pubinfo">
    <span class="source">{{ thesis.source }} </span>
    <span class="publisher">{{ thesis.publisher }}, </span>
    <span class="year">{{ thesis.issued.date-parts[0][0] }}.</span>
    </div>
    </li>
{% endfor %}
</ol>
</div>
