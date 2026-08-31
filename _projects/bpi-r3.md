---
layout: default
title: Banana Pi BPI-R3
description: MediaTek MT7986 (Filogic 830) — the next router board, not started yet
soc: MediaTek MT7986
status: Planned
order: 6
repo: https://github.com/SoCBSD/socbsd-src
---

# {{ page.title }}

{{ page.description }}

## The board

| | |
| --- | --- |
| SoC | MediaTek MT7986 "Filogic 830", quad Cortex-A53 @ 2.0 GHz |
| Network | 2x 2.5GbE SFP (fixed 2.5GBASE-X) + 5x GbE |
| WiFi | WiFi 6/6E, dual 4x4 — MT7975N (2.4 GHz) and MT7975P (5 GHz) |
| Memory | 2 GB DDR |
| Storage | 8 GB eMMC, microSD, NAND, SPI |
| Extras | M.2 key-E, mini PCIe, USB 3.0, 26-pin GPIO |

This is the board people actually want to build a modern FreeBSD router on: 2.5 gigabit uplinks, SFP cages, WiFi 6, and hardware offload on the SoC. It runs OpenWrt today. It does not run FreeBSD.

## Status: not started

No arena branch, no driver work, no claim to make. Listing it honestly rather than as vapour.

## Why it is next

The path to it is already half built. The MT7986 sits in the same family we have been working through:

- The MT7531 switch driver from the [R2 Pro]({{ '/projects/bpi-r2-pro.html' | relative_url }}) and [BPI-R64]({{ '/projects/bpi-r64.html' | relative_url }}) is the same switch generation
- The MT7623 work on the [BPI-R2]({{ '/projects/bpi-r2.html' | relative_url }}) built the MediaTek clock and pinctrl patterns FreeBSD did not have
- The `mtge` ethernet driver from the R64 is the starting point for the MT7986's ethernet

Every one of those was written once and gets reused here. That is the whole argument for doing bring-up in one place instead of in four private forks.

## What it needs

Somebody who owns an R3. Under the [SoCBSD]({{ '/projects/socbsd.html' | relative_url }}) rules that is not a formality — the board has to be on your desk, and every claim ships with a serial log from it.

Open the arena with a photo of the board and a capture of what it currently does, and this page stops saying "Planned".

- Organization: [github.com/SoCBSD]({{ page.repo }})
