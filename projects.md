---
layout: default
title: Projects
permalink: /projects/
---

# Projects

Current and past work by BSD-CZ/SK.

---

{% for project in site.projects %}
## [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.status %}**Status:** {{ project.status }}{% endif %}
{% if project.repo %}[Repository]({{ project.repo }}){% endif %}

---
{% endfor %}

{% if site.projects.size == 0 %}

_Projects coming soon. Check our [GitHub](https://github.com/BSD-CZ) for current repositories._

{% endif %}
