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
    <br><img style="max-height:4em; margin-right:auto; margin-left:auto; display:block;" src="{{row['Image']}}">
    {% endif %}
    <br><strong>{{row['Name']}}</strong>
    <div style="display:flex; align-items: center">
        <div>
        {% if row['Image'] %}
        <br><img style="float:left; max-height:4em; margin-right:0.5em; margin-left:0; display:block;" src="{{row['Image']}}">
        {% endif %}
        {{row['Info'] | strip | newline_to_br | replace: "<br />", "<br /><br />"}}
        </div>    
        {% if row['ImageRight'] %}
        <img style="max-width:8em; padding-left:1em" src="{{row['Image']}}">
        {% endif %}
    </div>
    <div>
        {% if row['URL'] %}
        <a class="btn" href="{{row['URL']}}">
        {{row['URL'] | remove: 'http://' | remove: 'https://' | remove: 'www.' | split: "?" | first | split: "/" | first }}
        </a>
        {% endif %}
        {% if row['Phone'] %}
        <a class="btn" href="tel:{{row['Phone']}}">{{row['Phone']}}</a>
        {% endif %}
    </div>
  {% endfor %}
</div>
