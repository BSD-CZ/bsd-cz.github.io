---
layout: default
title: Banana Pi BPI-R64
description: FreeBSD on MediaTek MT7622 — ethernet, switch and WiFi drivers written from scratch
soc: MediaTek MT7622
status: In progress
order: 4
repo: https://github.com/Martinfx/freebsd-src/tree/max-support-mediatek-7622-bananapir64
---

# {{ page.title }}

{{ page.description }}

## The board

| | |
| --- | --- |
| SoC | MediaTek MT7622, dual Cortex-A53 @ 1.35 GHz |
| Switch | MediaTek MT7531 — 4x GbE LAN + 1x GbE WAN |
| WiFi | MT7615, 802.11ac wave 2 |
| Extras | SFP cage, PCIe, SATA, USB 3.0, eMMC, Bluetooth 5.0 |

The MT7622 was built to be a router SoC: hardware NAT, a network accelerator, an integrated switch interface. All of that is dead weight without drivers.

## What is done

Three drivers, written against the hardware:

- **`mtge` — MT7622 ethernet.** The SoC's own ethernet controller. This is the piece that makes the board a network device instead of a serial console.
- **MT7531 switch.** Same switch family as the [R2 Pro]({{ '/projects/bpi-r2-pro.html' | relative_url }}) — which is exactly the point: the second board on a switch is far cheaper than the first, and the shared driver is the part worth lifting to the SoC family level.
- **MT7615 WiFi.** 802.11ac on FreeBSD, on a board that ships with the radio.

The `mtge` driver has been through a style(9) pass, so it reads like FreeBSD rather than like a port.

## What is next

The drivers exist and the board is a working network platform; what remains is the unglamorous half — edge cases, errata, the paths nobody hits until they do. That is the work that decides whether this goes upstream as something FreeBSD can merge with confidence or as another patchset reviewers are afraid of.

If you own a BPI-R64, verifying these drivers on your board is worth more right now than new code.

- Work branch: [`max-support-mediatek-7622-bananapir64`]({{ page.repo }})
- Bring-up runs through [SoCBSD]({{ '/projects/socbsd.html' | relative_url }})
