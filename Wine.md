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
   
    <div style="display:flex; justify-content: space-between;">
        <div>{{row['Name'] | strip}} &bull; {{row['Number'] | strip}}</div>
        <div>{{row['Price'] | strip}}</div>
    </div>
  {% endfor %}
</div>



