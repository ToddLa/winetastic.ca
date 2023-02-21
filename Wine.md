---
title: Wine
---

# Wine

<div>
  {% for row in site.data.wine %}
  
    {% if row.Name == nil %}
    {% continue %}
    {% endif %}

    {% if row.Number == nil and row.Price == nil %}
    <br><strong>{{row['Name']}}</strong>
    {% continue %}
    {% endif %}
   
    <div style="display:flex; align-items: center">
        <div>{{row['Name'] | strip}} &bull; {{row['Number'] | strip}}</div>
        <div>{{row['Price'] | default "$9.99" | strip}}</div>
    </div>
  {% endfor %}
</div>



