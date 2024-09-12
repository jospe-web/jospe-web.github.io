---
title: Galería
date: 1900-01-01
order: 3
thumbnail: /images/orquesta1.jpg
bookmark: true
showinfo: false
comments: false
relatedpubs: false
---

{% assign gallerypic = 
  [
    { "date": "", "caption": "", "image": ""}
  ] 
%}


{% assign number_printed = 0 %}
{% for teampic in gallerypic %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <h4>{{ teampic.date }}</h4>
  <h5>{{ teampic.caption }}</h5>
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ teampic.image }}" class="img-responsive" width="100%" style="float: bottom" />
  <ul style="overflow: hidden">
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}
