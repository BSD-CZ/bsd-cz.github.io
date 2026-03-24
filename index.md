---
layout: default
title: Home
permalink: /
---

# BSD-CZ/SK

**FreeBSD community focused on embedded systems, driver development, and modern hardware support.**

---

## What we do

We work on bringing FreeBSD to modern hardware and embedded platforms. Our focus areas include:

- **Driver development** — writing and porting drivers for hardware that lacks FreeBSD support
- **Embedded systems** — running FreeBSD on ARM boards, SBCs, and custom hardware
- **Modern hardware support** — ensuring FreeBSD works on current-generation laptops, GPUs, and peripherals
- **Documentation** — guides, howtos, and notes from real-world FreeBSD deployments

## Get involved

Check out our [projects]({{ site.baseurl }}/projects) or find us on [GitHub](https://github.com/BSD-CZ).

## Latest updates

{% for post in site.posts limit:5 %}
- **{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}

{% if site.posts.size == 0 %}
_No posts yet. Stay tuned._
{% endif %}
