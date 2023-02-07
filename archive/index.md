---
layout: default
---

# Archive of previous HUST websites

{% for p in site.pages %}
{% if p.url contains "archive" and page.url != "/archive/" %}
- [{{ p.year }} Site](/archive/{{ p.year }}-index.html)
{% endif %}
{% endfor %}
