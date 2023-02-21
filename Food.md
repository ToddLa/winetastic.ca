---
title: Food
---
<div>
  {% for row in site.data.food %}
  
    {% if row.Name == nil %}
    {% continue %}
    {% endif %}

    {% if row.Info == nil %}
    <h1>{{row.Name}}</h1>
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
        {% if row['Phone'] %}<div><a href="tel:{{row['Phone']}}">{{row['Phone']}}</a></div>{% endif %}
        {% if row['URL'] %}<div><a href="{{row['URL']}}">{{row['URL'] | remove: 'http://' | remove: 'https://' }}</a></div>{% endif %}
    </div>
  {% endfor %}
</div>
