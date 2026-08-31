---
layout: default
title: Projects
permalink: /projects/
---

# Projects

Current and past work by BSD-CZ/SK — FreeBSD on hardware that does not support it yet.

{% assign all_projects = site.projects | sort: "order" %}
{% assign active = all_projects | where_exp: "project", "project.status != 'Done'" %}
{% assign done = all_projects | where_exp: "project", "project.status == 'Done'" %}

---

## What we are working on

{% for project in active %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.status %}**Status:** {{ project.status }}{% endif %}
{% if project.repo %}· [Repository]({{ project.repo }}){% endif %}

---
{% endfor %}

## Done

{% for project in done %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.repo %}[Repository]({{ project.repo }}){% endif %}

---
{% endfor %}

{% if site.projects.size == 0 %}

_Projects coming soon. Check our [GitHub](https://github.com/BSD-CZ) for current repositories._

{% endif %}

## Want to help?

Board bring-up is brutal alone and reasonable in a group. If you own one of the boards we are working on, or you are good at something a board needs — drivers, documentation, hunting edge cases, verifying other people's boot logs — there is room for you. Say hello on [Signal or Discord]({{ '/about/' | relative_url }}), or open an issue on [GitHub](https://github.com/SoCBSD).
