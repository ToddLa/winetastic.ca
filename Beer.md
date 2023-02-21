---
title: Beer
---

# Beer

<div style="text-align:left">
  {% for row in site.data.beer %}
    {% if row['Name'] and row['Price'] %}
        <div>
        {{row['Name']}}
        {{row['Price']}}
        </div>
    {% endif %}
  {% endfor %}
</div>


