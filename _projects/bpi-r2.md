---
<<<<<<< HEAD
=======
layout: default
>>>>>>> c395102 (update project pages)
title: Banana Pi BPI-R2
description: FreeBSD on MediaTek MT7623 — the whole clock and pinctrl foundation, built from nothing
soc: MediaTek MT7623
status: In progress
order: 5
repo: https://github.com/Martinfx/freebsd-src/tree/max-support-bananapi-bpi-r2-7623
---

<<<<<<< HEAD
## The board

| Hardware | Banana Pi BPI-R2 |
=======
# {{ page.title }}

{{ page.description }}

## The board

| | |
>>>>>>> c395102 (update project pages)
| --- | --- |
| SoC | MediaTek MT7623N, quad Cortex-A7 @ 1.3 GHz |
| Network | 5x GbE |
| Memory | 2 GB DDR3 |
| Storage | eMMC, microSD, SATA |
| Extras | HDMI, Mali-450 GPU, PCIe / mPCIe, USB |

The MT7623 is the older, more multimedia-heavy sibling of the router SoCs — a 32-bit Cortex-A7 part with video decode, imaging and audio blocks alongside the networking. FreeBSD had none of it.

## What is done

This is bring-up at its least glamorous and most necessary: before a single peripheral driver can work, the SoC's clock tree and pin multiplexing have to exist.

**Foundation**

- Board support for MT7623
- SMP startup — all four cores come up
- Debug flags for the platform

**Clocks** — the infrastructure plus every clock subsystem on the die:

`topgen` · `infracfg` · `pericfg` · `pll` · `hifsys` · `bdpsys` · `imgsys` · `vdecsys` · `audsys`

**Pins and I/O**

- `mt7623_pinctrl` — pin multiplexing
- `mt7623_gpio` — GPIO
- `mt7623_syscfg` — system configuration

## What is next

The platform layer is in place; the peripherals are what is left. Ethernet is the obvious next target — the board's five ports are the reason anyone wants it — followed by storage and USB.

This is a good arena to join precisely because the hard, invisible part is finished. A driver written on top of a working clock tree is an ordinary driver.

- Work branch: [`max-support-bananapi-bpi-r2-7623`]({{ page.repo }})
- Bring-up runs through [SoCBSD]({{ '/projects/socbsd.html' | relative_url }})
