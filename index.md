---
title: Home
---

# Whistler Blackcomb Wintastic 2023

Welcome to the Winetastic

# Sponsors

<div>
  {% for row in site.data.sponsors %}
    {% if row['Image'] and row['URL'] %}
      <span>{{row['Name']}}</span>
      <span>{{row['URL']}}</span>
      <img src="{{row['Image']}}">
    {% endif %}
  {% endfor %}
</div>
