---
title: Food
---
# This evening's food generously provided by

<div>
  {% for row in site.data.food %}
  
    {% if row.Name == nil %}
    {% continue %}
    {% endif %}

    {% if row.Info == nil %}
    <h3>{{row.Name}}</h3>
    {% continue %}
    {% endif %}
   
    <h2>{{row['Name']}}</h2>
    <div style="display:flex; align-items: center">
        <div>{{row['Info']}}</div>
        {% if row['Image'] %}
        <img style="max-width:8em; padding-left:1em" src="{{row['Image']}}">
        {% endif %}
    </div>
    <div>
        {% if row['Phone'] %}<a href="tel:{{row['Phone']}}">{{row['Phone']}}</a>{% endif %}
        {% if row['URL'] %}<a href="{{row['URL']}}">{{row['URL']}}</a>{% endif %}
    </div>
  {% endfor %}
</div>
