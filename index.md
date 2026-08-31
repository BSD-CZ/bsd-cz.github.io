---
layout: default
title: BSD-CZ/SK
description: >-
  Czech/Slovak FreeBSD group bringing FreeBSD to SoC boards it does not
  support yet — MediaTek and Rockchip routers, kernel drivers, and 80+ ports.
permalink: /
---

{% assign boards = site.projects | where_exp: "p", "p.soc" | where_exp: "p", "p.soc != 'Multiple'" | sort: "order" %}
{% assign port_total = 0 %}
{% for g in site.data.ports %}{% assign port_total = port_total | plus: g.ports.size %}{% endfor %}

<section class="hero">
  <div class="wrap">
    <p class="eyebrow">FreeBSD · Embedded · Prague</p>
    <h1>Hundreds of boards run Linux. Only a handful run FreeBSD.</h1>
    <p class="lede">
      We are a Czech/Slovak group doing the unglamorous half of that problem:
      <strong>SoC board bring-up</strong>, kernel drivers, boot firmware and ports.
      Clocks, pinctrl, ethernet and switch drivers written against real hardware —
      then handed upstream to FreeBSD.
    </p>
    <div class="cta-row">
      <a class="btn btn-primary" href="{{ '/projects/socbsd.html' | relative_url }}">See the bring-up work</a>
      <a class="btn btn-ghost" href="{{ '/ports/' | relative_url }}">Browse {{ port_total }} ports</a>
    </div>

    <div class="stats">
      <div class="stat"><b>{{ boards.size }}</b><span>router boards in bring-up</span></div>
      <div class="stat"><b>{{ port_total }}</b><span>FreeBSD ports maintained</span></div>
      <div class="stat"><b>2</b><span>SoC families: MediaTek, Rockchip</span></div>
      <div class="stat"><b>1</b><span>board already routing</span></div>
    </div>
  </div>
</section>

<section class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>Boards</h2>
      <p>
        Every claim below is backed by code in a branch and a boot log from hardware on
        someone's desk. Where nothing has been done, the card says so.
      </p>
    </div>
    <div class="card-grid">
      {% for board in boards %}
      <a class="card" href="{{ board.url | relative_url }}">
        <h3>{{ board.title }}</h3>
        <p>{{ board.description }}</p>
        <div class="card-foot">
          {% assign badge = board.status | downcase | replace: ' ', '' %}
          <span class="badge badge-{{ badge }}">{{ board.status }}</span>
          <span>{{ board.soc }}</span>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>
</section>

<<<<<<< HEAD
<section class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>What we do</h2>
    </div>
    <div class="card-grid">
      <div class="card">
        <h3>Driver development</h3>
        <p>
          Ethernet, switch, WiFi, clocks, pinctrl and GPIO for SoCs FreeBSD has never
          run on. Written from datasheets, tested on the board, not ported blind.
        </p>
      </div>
      <div class="card">
        <h3>Boot firmware</h3>
        <p>
          U-Boot and ARM Trusted Firmware ports, plus recovery tooling. A kernel is
          useless if the board cannot boot it or you cannot unbrick it.
        </p>
      </div>
      <div class="card">
        <h3>Ports maintenance</h3>
        <p>
          {{ port_total }} ports so the software people actually want is there when the board
          comes up — including the ARM machine learning stack on aarch64.
        </p>
      </div>
      <div class="card">
        <h3>Upstreaming</h3>
        <p>
          The point is not a private fork. Work stabilizes, gets verified by someone
          else who owns the board, and goes to FreeBSD with every name on the patchset.
        </p>
      </div>
    </div>
  </div>
</section>

<section class="section">
  <div class="wrap">
    <div class="section-head">
      <h2>Why a group and not a fork per person</h2>
      <p>
        Solo bring-up is why FreeBSD is missing from so much hardware. One person carries
        a board for months, it half-works in their repo, and it never reaches the tree.
        <a href="{{ '/projects/socbsd.html' | relative_url }}">SoCBSD</a> exists to collapse that:
        partial work lands immediately, other owners of the same board fill in the rest,
        and every claim is verified against real hardware before it counts.
      </p>
    </div>
    <div class="cta-row">
      <a class="btn btn-primary" href="{{ '/projects/bpi-r3.html' | relative_url }}">Own a BPI-R3? Nobody has started it</a>
      <a class="btn btn-ghost" href="{{ '/about/' | relative_url }}">Get in touch</a>
    </div>
  </div>
</section>
=======
**[SoCBSD]({{ site.baseurl }}/projects/socbsd.html)** — a FreeBSD fork dedicated to SoC board bring-up. Hundreds of boards run Linux, only a handful run FreeBSD, and solo bring-up is why. Boards are brought up collaboratively, every claim is backed by a serial log from real hardware, and finished boards go upstream to FreeBSD with every contributor's name on the patchset.

### Boards

| Board | SoC | State |
| --- | --- | --- |
| [Banana Pi R2 Pro]({{ site.baseurl }}/projects/bpi-r2-pro.html) | Rockchip RK3568 + MT7531 | Routes — switch driver needs cleanup |
| [Banana Pi BPI-R64]({{ site.baseurl }}/projects/bpi-r64.html) | MediaTek MT7622 | Ethernet, switch and WiFi drivers written |
| [Banana Pi BPI-R2]({{ site.baseurl }}/projects/bpi-r2.html) | MediaTek MT7623 | Clocks, pinctrl, GPIO, SMP done |
| [Banana Pi BPI-R3]({{ site.baseurl }}/projects/bpi-r3.html) | MediaTek MT7986 | Not started — needs someone with the board |

Alongside the kernel work: [ports maintenance]({{ site.baseurl }}/projects/freebsd-ports.html) — boot firmware, recovery tooling, and 80+ ports so the software people actually want is there when the board boots.
>>>>>>> c395102 (update project pages)

{% if site.posts.size > 0 %}
<section class="section">
  <div class="wrap">
    <div class="section-head"><h2>Updates</h2></div>
    <ul class="post-list">
      {% for post in site.posts limit: 5 %}
      <li>
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
      {% endfor %}
    </ul>
  </div>
</section>
{% endif %}
