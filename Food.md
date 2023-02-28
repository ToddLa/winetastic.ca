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
   
    {% if row['Image'] %}
    <img style="max-height:4em; margin-right:auto; margin-left:auto;" src="{{row['Image']}}">
    {% endif %}
    <h2>{{row['Name']}}</h2>
    <div style="display:flex; align-items: center">
        <div>{{row['Info'] | strip | newline_to_br | replace: "<br />", "<br /><br />"}}</div>
        {% if row['ImageRight'] %}
        <img style="max-width:8em; padding-left:1em" src="{{row['Image']}}">
        {% endif %}
    </div>
    <div>
        {% if row['Phone'] %}<a class="btn" href="tel:{{row['Phone']}}">{{row['Phone']}}</a>{% endif %}
        {% if row['URL'] %}<a class="btn" href="{{row['URL']}}">{{row['URL'] | remove: 'http://' | remove: 'https://' }}</a>{% endif %}
    </div>
  {% endfor %}
</div>
