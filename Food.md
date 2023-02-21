---
title: Food
---
# This evening's food generously provided by

<div>
  {% for row in site.data.food %}
  
    {% if row['Name'] == nil %}
    <h3>ZERO ROW!</h3>
    {% continue %}
    {% endif %}
    
    {% row['Info'] == nil %}
    <h3>TITLE ROW: {{row.Name}}</h3>
    <h3>TITLE ROW: {{row.name}}</h3>
    <h3>TITLE ROW: {{row['Name']}}</h3>
    {% continue %}
    {% endif %}
    
	{% if row['Name'] and row['Info'] and row['Image'] %}
	    <h2>{{row['Name']}}</h2>
		<div style="display:flex; align-items: center">
			<div>{{row['Info']}}</div>
			<img style="max-width:8em; padding-left:1em" src="{{row['Image']}}">
		</div>
		<div>
			{% if row['Phone'] %}<a href="tel:{{row['Phone']}}">{{row['Phone']}}</a>{% endif %}
			{% if row['URL'] %}<a href="{{row['URL']}}">{{row['URL']}}</a>{% endif %}
		</div>
	{% endif %}
  {% endfor %}
</div>
