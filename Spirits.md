---
title: Spirits
order: 5
hide: true
---
<div>
  {% for row in site.data.spirits %}
  
    {% if row.Name == nil %}
    {% continue %}
    {% endif %}

    {% if row.Number == nil and row.Price == nil and row.Name contains "## " %}
    <h2>{{row['Name'] | remove:"#" | strip}}</h2>
    {% continue %}
    {% endif %}
    
    {% if row.Number == nil and row.Price == nil and row.Name contains "# " %}
    <h1>{{row['Name'] | remove:"#" | strip}}</h1>
    {% continue %}
    {% endif %}
    
    {% if row.Number == nil and row.Price == nil %}
    <br><strong>{{row['Name'] | strip}}</strong>
    {% continue %}
    {% endif %}
   
    <div style="display:flex; justify-content: space-between;">
        <div>
          {{row['Name'] | strip}}
          {% if row.Number != "" and row.Number != "0" %}
            <a href="https://www.bcliquorstores.com/product-catalogue?search={{row['Number'] | strip}}">
              {{row['Number'] | strip}}
            </a>
          {% endif %}
        </div>
        {% if row.Price != "" and row.Price != "0" %}
          <div>{{row['Price'] | strip}}</div>
        {% endif %}
    </div>
  {% endfor %}
</div>



