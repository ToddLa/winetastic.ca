---
title: Wine
---

# Wine

<div>
  {% for row in site.data.wine %}
  
    {% if row.Name == nil %}
    {% continue %}
    {% endif %}

    {% if row.Info == nil %}
    <br><strong>{{row['Name']}}</strong>
    {% continue %}
    {% endif %}
   
    <div style="display:flex; align-items: center">
        <div>{{row['Name'] | strip}}</div>
        <div>{{row['Number'] | strip}}</div>
        <div>{{row['Price'] | strip}}</div>
    </div>
  {% endfor %}
</div>



