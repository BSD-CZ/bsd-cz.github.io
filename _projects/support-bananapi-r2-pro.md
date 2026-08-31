---
layout: default
title: Driver MT7531 for Bananpi R2 PRO
description: Added driver MT7531 switch to ChaosBSD
status: Done
order: 5
repo: https://github.com/SoCBSD/socbsd-src/tree/arena/bananapi-r2-pro
---

# {{ page.title }}

{{ page.description }}

Banana Pi R2 Pro can now be used as a real router + NAT on FreeBSD/ChaosBSD 🎉
I’ve added patches for the MT7531 switch, so the built-in switch on the Banana Pi R2 Pro is now working properly under FreeBSD/ChaosBSD
This means the board is no longer just a dev toy — it can actually be deployed as:
– a home router
– a lab router
– an embedded networking platform

Switching, ports, and forwarding are operational, so NAT and standard router setups using pf are usable in practice.
Another step toward proper MediaTek SoC support in the ChaosBSD kernel. If you have an R2 Pro, you can start testing it as an actual router, not just a boot experiment. 
IMPORTANT: The current implementation contains several temporary hacks and workarounds that are known to be sub-optimal.

Cleaning those up, and the rest of the board's bring-up, now runs in the Banana Pi R2 Pro arena in [SoCBSD]({{ '/projects/socbsd.html' | relative_url }}) — where other people who own the board can verify the work instead of it sitting in one fork.
