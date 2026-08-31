---
layout: default
title: Projects
permalink: /projects/
---

# Projects

Current and past work by BSD-CZ/SK — FreeBSD on hardware that does not support it yet.

{% assign all_projects = site.projects | sort: "order" %}
{% assign active = all_projects | where_exp: "p", "p.status != 'Done'" | where_exp: "p", "p.status != 'Planned'" %}
{% assign planned = all_projects | where: "status", "Planned" %}
{% assign done = all_projects | where: "status", "Done" %}

---

## In progress

{% for project in active %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.soc %}**SoC:** {{ project.soc }} · {% endif %}**Status:** {{ project.status }}{% if project.repo %} · [Repository]({{ project.repo }}){% endif %}

---
{% endfor %}

## Planned

{% for project in planned %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.soc %}**SoC:** {{ project.soc }} · {% endif %}**Status:** {{ project.status }}

---
{% endfor %}

## Done

{% for project in done %}
### [{{ project.title }}]({{ project.url | relative_url }})

{{ project.description }}

{% if project.repo %}[Repository]({{ project.repo }}){% endif %}

---
{% endfor %}

## Want to help?

Board bring-up is brutal alone and reasonable in a group. If you own one of the boards above — especially a [BPI-R3]({{ '/projects/bpi-r3.html' | relative_url }}), which nobody has started — or you are good at something a board needs, there is room for you. Drivers, documentation, hunting edge cases, verifying other people's boot logs: it all counts.

Say hello on [Signal or Discord]({{ '/about/' | relative_url }}), or open an issue on [GitHub](https://github.com/SoCBSD).
