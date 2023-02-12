---
title: Table test
---

# Wine

{% assign row = site.data.wine[0] %}
{{ row | inspect }}

<table>
  {% for row in site.data.wine %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>

