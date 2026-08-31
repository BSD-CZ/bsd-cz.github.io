---
layout: default
title: Rockchip board support
description: Boot firmware and board enablement for Rockchip SBCs on FreeBSD — RK3566, RK3568, RK3588
status: In progress
order: 3
repo: https://github.com/Martinfx/FreeBSD-Ports
---

# {{ page.title }}

{{ page.description }}

A board that the kernel supports is still useless if you cannot boot it. This is the firmware and tooling side of Rockchip board support: U-Boot and ATF ports that produce a bootable image, plus the flashing tools to get it onto the board.

## What is ported

- **`u-boot-bananapi-r2-pro`** — Banana Pi R2 Pro, `bpi-r2-pro-rk3568_defconfig` (RK3568)
- **`u-boot-cm3588-nas`** — FriendlyELEC CM3588 NAS, `cm3588-nas-rk3588_defconfig` (RK3588)
- **`u-boot-radxa-zero3`** — Radxa Zero 3, `radxa-zero-3-rk3566_defconfig` (RK3566)
- **`atf-rk3288`** — ARM Trusted Firmware for RK3288
- **`rkdeveloptool`** — Rockchip's Rockusb flashing tool, so boards can be recovered and reflashed from FreeBSD instead of from a Linux box

## Why it matters

Every one of these is a prerequisite, not a nice-to-have. Without a U-Boot port there is no SD card image; without `rkdeveloptool` a bricked board means digging out another machine. Getting them into the ports tree means the next person bringing up a Rockchip board starts from a working boot chain instead of building one from scratch.

The kernel-side work on these boards runs through [SoCBSD]({{ '/projects/socbsd.html' | relative_url }}).

- Ports: [Martinfx/FreeBSD-Ports]({{ page.repo }})
