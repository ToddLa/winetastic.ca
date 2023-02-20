---
title: Food
---
# This evening's food generously provided by

<div>
  {% for row in site.data.food %}
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
