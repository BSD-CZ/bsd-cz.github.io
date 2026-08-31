---
layout: default
title: Home
permalink: /
---

## What we do

We work on bringing FreeBSD to modern hardware and embedded platforms. Our focus areas include:

- **Driver development** — writing and porting drivers for hardware that lacks FreeBSD support
- **Embedded systems** — running FreeBSD on ARM boards, SBCs, and custom hardware
- **Modern hardware support** — ensuring FreeBSD works on current-generation laptops, GPUs, and peripherals
- **Documentation** — guides, howtos, and notes from real-world FreeBSD deployments

## Current focus

**[SoCBSD]({{ site.baseurl }}/projects/socbsd.html)** — a FreeBSD fork dedicated to SoC board bring-up. Hundreds of boards run Linux, only a handful run FreeBSD, and solo bring-up is why. Boards are brought up collaboratively, every claim is backed by a serial log from real hardware, and finished boards go upstream to FreeBSD with every contributor's name on the patchset. Open arenas right now: Banana Pi R2 Pro, Raspberry Pi 5, Raspberry Pi 3.

Alongside it: [MediaTek SoC support]({{ site.baseurl }}/projects/mediatek-soc-support.html), [Rockchip boot firmware]({{ site.baseurl }}/projects/rockchip-boards.html), and [ports maintenance]({{ site.baseurl }}/projects/freebsd-ports.html) so the software people actually want is there when the board boots.

## Get involved

Check out our [projects]({{ site.baseurl }}/projects) or find us on [GitHub](https://github.com/BSD-CZ). If you own one of the boards above, you are exactly who we need.

## Latest updates

{% for post in site.posts limit:5 %}
- **{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}

{% if site.posts.size == 0 %}
_No posts yet. Stay tuned._
{% endif %}
