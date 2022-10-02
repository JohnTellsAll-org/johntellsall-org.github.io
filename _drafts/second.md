---
beer: tasty
layout: post
title: Second
author: John
---


titl {{ page.beer }} -- {{ "hi" | capitalize }}

<h1>{{ "Hello World!" | downcase }}</h1>

<HR>

{% if page.beer %}
  <div class="sidebar">
    sidebar content
  </div>
{% endif %}
