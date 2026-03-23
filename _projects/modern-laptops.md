---
layout: default
title: FreeBSD on Modern Laptops
description: Testing and documenting FreeBSD support on current-generation laptops — suspend/resume, WiFi, GPU, touchpad.
status: Active
repo: https://github.com/BSD-CZ
---

# {{ page.title }}

{{ page.description }}

## Goals

- Test FreeBSD on popular laptop models (ThinkPad, Framework, Dell XPS)
- Document what works out of the box and what needs patches
- Write or port missing drivers (WiFi chipsets, fingerprint readers)
- Provide ready-to-use configuration files and kernel modules

## Hardware tested

| Laptop | WiFi | Suspend | GPU | Notes |
|--------|------|---------|-----|-------|
| ThinkPad T14s Gen 4 | ✅ iwlwifi | ✅ S3 | ✅ Intel | Fully functional |
| Framework 13 | ✅ iwlwifi | ⚠️ partial | ✅ Intel | Resume glitch on lid open |

_More entries added as we test._

## How to help

- Test FreeBSD on your laptop and report results
- Submit dmesg output and `pciconf -lv` for untested machines
- Help with driver debugging and kernel patches
