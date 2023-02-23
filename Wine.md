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
    <pre>
    {{row.Name.first}}
    </pre>
    <br><strong>{{row['Name']}}</strong>
    {% continue %}
    {% endif %}
   
    <div style="display:flex; justify-content: space-between;">
        <div>
          {{row['Name'] | strip}}
          {% if row.Number != '' %}
            <a href="https://www.bcliquorstores.com/product-catalogue?search={{row['Number'] | strip}}">
              {{row['Number'] | strip}}
            </a>
          {% endif %}
        </div>
        <div>{{row['Price'] | strip}}</div>
    </div>
  {% endfor %}
</div>



