---
title: Home
---

# Whistler Blackcomb Wintastic 2023

Welcome to the Winetastic

# Sponsors we **LOVE**

<div>
  {% for row in site.data.sponsors %}
    {% if row['Image'] and row['URL'] %}
    <div style="display:inline-block;height:4em">
      <a href="{{row['URL']}}"><img src="{{row['Image']}}"></a>
    </div>
    {% endif %}
  {% endfor %}
</div>
