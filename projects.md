---
layout: default
title: Projects
description: >-
  FreeBSD SoC board bring-up, MediaTek and Rockchip drivers, boot firmware and
  ports — what BSD-CZ/SK is working on, what is planned, and what is finished.
permalink: /projects/
---

{% assign all = site.projects | sort: "order" %}
{% assign active = all | where_exp: "p", "p.status != 'Done'" | where_exp: "p", "p.status != 'Planned'" %}
{% assign planned = all | where: "status", "Planned" %}
{% assign done = all | where: "status", "Done" %}

<div class="page-head">
  <div class="wrap">
    <h1>Projects</h1>
    <p class="lede">
      Current and past work. Board pages say what is done, what is broken and what is
      untouched — a card that claims nothing is a board nobody has started.
    </p>
  </div>
</div>

<<<<<<< HEAD
<div class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>In progress</h2>
    </div>
    <div class="card-grid">
      {% for project in active %}
      <a class="card" href="{{ project.url | relative_url }}">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div class="card-foot">
          {% assign badge = project.status | downcase | replace: ' ', '' %}
          <span class="badge badge-{{ badge }}">{{ project.status }}</span>
          {% if project.soc %}<span>{{ project.soc }}</span>{% endif %}
        </div>
      </a>
      {% endfor %}
    </div>
  </div>
</div>

{% if planned.size > 0 %}
<div class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>Planned</h2>
      <p>Listed honestly: hardware we want FreeBSD on, with no work started yet.</p>
    </div>
    <div class="card-grid">
      {% for project in planned %}
      <a class="card" href="{{ project.url | relative_url }}">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div class="card-foot">
          <span class="badge badge-planned">{{ project.status }}</span>
          {% if project.soc %}<span>{{ project.soc }}</span>{% endif %}
        </div>
      </a>
      {% endfor %}
    </div>
  </div>
</div>
{% endif %}

{% if done.size > 0 %}
<div class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>Done</h2>
    </div>
    <div class="card-grid">
      {% for project in done %}
      <a class="card" href="{{ project.url | relative_url }}">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div class="card-foot">
          <span class="badge badge-done">{{ project.status }}</span>
          {% if project.soc %}<span>{{ project.soc }}</span>{% endif %}
        </div>
      </a>
      {% endfor %}
    </div>
  </div>
</div>
{% endif %}

<div class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>Want to help?</h2>
      <p>
        Board bring-up is brutal alone and reasonable in a group. If you own one of these
        boards — especially a <a href="{{ '/projects/bpi-r3.html' | relative_url }}">BPI-R3</a>,
        which nobody has started — you are exactly who we need. You do not have to be a
        bring-up person either: a board needs its edge cases hunted, its man pages written,
        its boot logs verified and its code reviewed by someone with the same hardware.
      </p>
    </div>
    <div class="cta-row">
      <a class="btn btn-primary" href="https://github.com/SoCBSD" rel="noopener">Open an arena on GitHub</a>
      <a class="btn btn-ghost" href="{{ '/about/' | relative_url }}">Signal &amp; Discord</a>
    </div>
  </div>
</div>
=======
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
>>>>>>> c395102 (update project pages)
