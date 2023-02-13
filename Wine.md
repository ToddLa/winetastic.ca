---
title: Wine
---

# Wine

<div style="text-align:left">
  {% for row in site.data.wine %}
    {% if row['Name'] and row['Price'] %}
        <div>
        {{row['Name']}}
        {{row['Price']}}
        </div>
    {% endif %}
  {% endfor %}
</div>


