---
layout: default
title: MediaTek SoC support
description: FreeBSD kernel support for MediaTek networking SoCs — MT7622, MT7623 and NIO12L
status: In progress
order: 2
repo: https://github.com/Martinfx/freebsd-src
---

# {{ page.title }}

{{ page.description }}

MediaTek's networking SoCs are everywhere in cheap, capable router hardware, and FreeBSD support for them is thin. This is the ongoing work to change that — clocks, pinctrl, ethernet and switch support for the MT76xx family, developed on real boards and staged in work branches before it goes anywhere near upstream.

## Boards and SoCs

| Board | SoC | Branch |
| --- | --- | --- |
| Banana Pi BPI-R64 | MT7622 | `max-support-mediatek-7622-bananapir64` |
| Banana Pi BPI-R2 | MT7623 | `max-support-bananapi-bpi-r2-7623` |
| MediaTek NIO12L | NIO12L | `max-support-mediatek-nio12l` |
| Banana Pi R2 Pro | RK3568 + MT7531 | `max-support-bananapi-r2-pro` |

The [MT7531 switch driver]({{ '/projects/support-bananapi-r2-pro.html' | relative_url }}) came out of this line of work and is the piece that is furthest along — the R2 Pro is usable as a real router today.

## Status

Work in progress, board by board, developed against hardware on the desk — under the SoCBSD rule that a claim without a boot log from the real board does not count. The shared parts — switch driver, clock and pinctrl plumbing — are the ones worth lifting to the SoC family level so the next MediaTek board is cheaper to bring up than the last.

This work is moving into [SoCBSD]({{ '/projects/socbsd.html' | relative_url }}), where it can be reviewed and verified by other people who own the same boards instead of living in one fork.

- Work branches: [Martinfx/freebsd-src]({{ page.repo }}/branches)
