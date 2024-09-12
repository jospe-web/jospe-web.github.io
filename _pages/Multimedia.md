---
title: Multimedia
date: 1900-01-01
order: 3
thumbnail: /images/orquesta1.jpg
bookmark: true
showinfo: false
comments: false
relatedpubs: false
---

A continuación se muestra una colección de imágenes y grabaciones tomadas en actuaciones y ensayos de la JOSPE:

{% assign number_printed = 0 %}
{% for teampic in site.data.gallerylist %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <h3> {{ teampic.date }} {{ teampic.caption }} </h3>
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ teampic.image }}" class="img-responsive" width="100%" style="float: bottom" />
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
