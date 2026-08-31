---
layout: default
title: FreeBSD ports
description: >-
  Every FreeBSD port maintained by BSD-CZ/SK — boot firmware for ARM boards,
  the ARM machine learning stack, Czech eGovernment clients, VFX tooling,
  developer tools and Linux compatibility packages.
permalink: /ports/
---

{% assign port_total = 0 %}
{% for g in site.data.ports %}{% assign port_total = port_total | plus: g.ports.size %}{% endfor %}

<div class="page-head">
  <div class="wrap">
    <h1>FreeBSD ports</h1>
    <p class="lede">
      {{ port_total }} ports, maintained and staged before they go into the FreeBSD ports tree.
      New ports for software nobody has packaged, build fixes for software that
      quietly stopped compiling, and the boot firmware that makes ARM boards usable at all.
    </p>
    <div class="meta-row">
      <span class="badge badge-ongoing">Ongoing</span>
      <a class="badge badge-plain" href="https://github.com/Martinfx/FreeBSD-Ports" rel="noopener">Ports tree &rarr;</a>
    </div>
  </div>
</div>

<div class="section section-flush">
  <div class="ports-toolbar">
    <div class="wrap">
      <label class="visually-hidden" for="port-filter">Filter ports</label>
      <input
        id="port-filter"
        class="ports-search"
        type="search"
        placeholder="Filter by name or description — try 'u-boot', 'arm', 'browser'"
        autocomplete="off">
      <p class="ports-count" id="port-count">{{ port_total }} ports</p>
    </div>
  </div>

  <div class="wrap">
    <div id="port-groups">
      {% for group in site.data.ports %}
      <section class="port-group" data-group>
        <h2 id="{{ group.key }}">
          {{ group.label }}
          <span class="n">{{ group.ports.size }}</span>
        </h2>
        <ul class="port-list">
          {% for port in group.ports %}
          <li class="port" data-name="{{ port.name | downcase }}" data-desc="{{ port.desc | downcase | escape }}">
            <div class="port-name">
              {{ port.name }}{% if port.version %}<span class="port-ver">{{ port.version }}</span>{% endif %}
            </div>
            <div class="port-desc">{{ port.desc }}</div>
          </li>
          {% endfor %}
        </ul>
      </section>
      {% endfor %}
    </div>

    <p class="ports-empty" id="port-empty">No port matches that filter.</p>

    <div class="prose" style="margin-top:48px">
      <h2>Why these</h2>
      <p>
        The list is not random. <strong>Boot firmware and board tooling</strong> is a
        prerequisite for the <a href="{{ '/projects/' | relative_url }}">board bring-up work</a> —
        without a U-Boot port there is no SD card image, and without
        <code>rkdeveloptool</code> a bricked board means going to find a Linux machine.
        The <strong>ARM machine learning stack</strong> exists because aarch64 is the
        architecture those boards run. <strong>Datovka</strong> is there because running
        FreeBSD in Czechia should not mean booting something else to talk to the state.
      </p>
      <p>
        The rest is the ordinary work of a ports tree: software that had no FreeBSD build,
        or had one until it broke.
      </p>

      <h2>Contributing</h2>
      <p>
        Found something that does not build, or software you need on FreeBSD that nobody has
        packaged? Open an issue on the
        <a href="https://github.com/Martinfx/FreeBSD-Ports" rel="noopener">ports repository</a> —
        a failing build log is a perfectly good bug report.
      </p>
    </div>

  </div>
</div>

<script>
(function () {
  var input = document.getElementById('port-filter');
  var groups = Array.prototype.slice.call(document.querySelectorAll('[data-group]'));
  var count = document.getElementById('port-count');
  var empty = document.getElementById('port-empty');
  if (!input) return;

  var total = 0;
  groups.forEach(function (g) { total += g.querySelectorAll('.port').length; });

  function apply() {
    var q = input.value.trim().toLowerCase();
    var shown = 0;

    groups.forEach(function (group) {
      var visible = 0;
      Array.prototype.forEach.call(group.querySelectorAll('.port'), function (row) {
        var hit = !q ||
          row.getAttribute('data-name').indexOf(q) !== -1 ||
          row.getAttribute('data-desc').indexOf(q) !== -1;
        row.hidden = !hit;
        if (hit) visible++;
      });
      group.hidden = visible === 0;
      shown += visible;
    });

    count.textContent = q ? shown + ' of ' + total + ' ports' : total + ' ports';
    empty.style.display = shown === 0 ? 'block' : 'none';
  }

  input.addEventListener('input', apply);
  apply();
})();
</script>
