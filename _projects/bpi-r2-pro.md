---
layout: default
title: Banana Pi R2 Pro
description: FreeBSD on the Rockchip RK3568 router board — switch works, the board routes
soc: Rockchip RK3568
status: Working
order: 3
repo: https://github.com/SoCBSD/socbsd-src/tree/arena/bananapi-r2-pro
redirect_from:
  - /projects/support-bananapi-r2-pro.html
---

# {{ page.title }}

{{ page.description }}

## The board

| | |
| --- | --- |
| SoC | Rockchip RK3568, quad Cortex-A55 @ 2.0 GHz |
| Switch | MediaTek MT7531BE — 5x GbE (1 WAN, 4 LAN) |
| Storage | eMMC, microSD, SATA III, SPI flash |
| Expansion | M.2, mPCIe, 2x USB 3.0 |

An RK3568 with a MediaTek switch bolted on: a Rockchip board that is really a router. That split is also why it took so long — it needs both halves working.

## What works

**The board routes.** Not "it boots and prints something to serial" — it does the job it was bought for:

- **MT7531 switch driver** — the built-in switch is up, patches merged into the arena branch
- **Switching, port config and forwarding** are operational, so NAT and normal `pf` setups work in practice
- Deployable as a home router, a lab router, or an embedded networking platform

## What is not done

Honest state of things:

- The switch implementation carries several temporary hacks and workarounds that are known to be sub-optimal. They work; they are not what goes upstream.
- **PCIe is disabled** — there is a bug that has not been chased down yet.
- The switch support is still marked experimental in the commit history, and it deserves the label until someone else with an R2 Pro verifies it.

## Boot

U-Boot for this board is packaged as **`u-boot-bananapi-r2-pro`** (`bpi-r2-pro-rk3568_defconfig`) in our [ports tree]({{ '/projects/freebsd-ports.html' | relative_url }}), so you get a bootable image without building the boot chain yourself. If you brick it, `rkdeveloptool` is packaged too.

## Where the work happens

This is the arena that started [SoCBSD]({{ '/projects/socbsd.html' | relative_url }}) — ten months of one person carrying a board that existed in a fork and nowhere else. It is now open: the cleanup, the PCIe bug, and everything still missing are work anyone who owns an R2 Pro can pick up.

- Arena branch: [`arena/bananapi-r2-pro`]({{ page.repo }})
- Original work branch: [`max-support-bananapi-r2-pro`](https://github.com/Martinfx/freebsd-src/tree/max-support-bananapi-r2-pro)
