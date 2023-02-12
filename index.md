---
title: Home
---

# Wintastic

Welcome to the home of `TEAM WOMBAT`

# Posts

{% for post in site.posts %}
* [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})  
{{ post.excerpt | strip_html  | truncatewords:50 }}
{% endfor %}
