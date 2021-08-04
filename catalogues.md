---
layout: default
permalink: /catalogues/
title: Numismatic Catalogue Archive
---
<div class="container mb-3">
  <div class="row">
{% assign rows = site.catalogues.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
{% assign offset = forloop.index0 | times: 2 %}
{% assign sorted = site.catalogues | sort:"order" %}
    {% for catalog in sorted limit:2 offset:offset %}
    <div class="col-md-4 mb-3">
      <div class="card h-100" >
        <div class="card-body">
          <h3 class="lead mt-2">
            <a href="{{site.url}}{{site.baseurl}}{{ catalog.permalink }}" class="stretched-link">{{catalog.title}}</a>
          </h3>
          <a href="{{site.baseurl}}/pdf/{{catalog.file}}.pdf" class="btn btn-dark btn-large">PDF</a>
          <a href="{{site.baseurl}}/txt/{{catalog.file}}.txt" class="btn btn-dark btn-large">TXT</a>

        </div>
      </div>
    </div>
    {% endfor %}
  {% endfor %}
  </div>
</div>
