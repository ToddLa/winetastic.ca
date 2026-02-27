---
title: Wine
order: 3
---
<div>
  {% for row in site.data.wine %}
  
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
    {% assign title =  row['Name'] | split: " -- " | first | strip %}
    {% assign url   =  row['Name'] | split: " -- " | last | strip %}

    {% if title != url %}
    <br>
    <a href="{{url}}">
    <strong>{{title}}</strong>
    </a>
    {% else %}
    <br><strong>{{title}}</strong>
    {% endif %}
    
    {% continue %}
    {% endif %}
   
    <div style="display:flex; justify-content: space-between;">
        <div>
          {{row['Name'] | strip}}
          {% if false and row.Number != "" and row.Number != "0" %}
            <a href="https://www.bcliquorstores.com/product-catalogue?search={{row['Number'] | strip}}">
              {{row['Number'] | strip}}
            </a>
          {% endif %}
          {% if row.Store | upcase == "YES" %}
            <img src="images/store_icon_red circle.png" style="display:inline-block;max-height:1.25em;vertical-align:middle">
          {% endif %}
        </div>
        {% if row.Price != "" and row.Price != "0" %}
          <div>{{row['Price'] | strip}}</div>
        {% endif %}
    </div>
  {% endfor %}
</div>



