---
layout: default
title: FreeBSD ports
description: Creating and maintaining ports so software that never ran on FreeBSD does
status: Ongoing
order: 2
repo: https://github.com/Martinfx/FreeBSD-Ports
---

# {{ page.title }}

{{ page.description }}

FreeBSD ships tens of thousands of ports, but there is always software that has never been packaged, or that quietly stopped building on current releases and architectures. This is the ongoing work of closing those holes: new ports, build fixes, dependency updates, and patches sent upstream so the fix does not have to live in a local tree forever.

Over 80 ports are currently maintained here, staged before they go into the FreeBSD ports tree.

## Boot firmware and board tooling

The half of board support that is not kernel code. A board the kernel supports is still useless if you cannot boot it or recover it:

- **`u-boot-bananapi-r2-pro`** — [Banana Pi R2 Pro]({{ '/projects/bpi-r2-pro.html' | relative_url }}), `bpi-r2-pro-rk3568_defconfig` (RK3568)
- **`u-boot-cm3588-nas`** — FriendlyELEC CM3588 NAS, `cm3588-nas-rk3588_defconfig` (RK3588)
- **`u-boot-radxa-zero3`** — Radxa Zero 3, `radxa-zero-3-rk3566_defconfig` (RK3566)
- **`atf-rk3288`** — ARM Trusted Firmware for RK3288
- **`rkdeveloptool`** — Rockchip's Rockusb tool, so a bricked board gets reflashed from FreeBSD instead of from a Linux box you had to go find

Without these there is no SD card image and no recovery path. Getting them into the tree means the next person bringing up a Rockchip board starts from a working boot chain instead of building one.

## ARM machine learning

`computelibrary` · `kleidiai` · `openvino`

Optimized inference on aarch64 — the same architecture the [board work]({{ '/projects/socbsd.html' | relative_url }}) targets. See the [ARM Compute Library port]({{ '/projects/arm-compute-library.html' | relative_url }}).

## Czech desktop

`datovka` · `libdatovka`

The client for the Czech data mailbox system (ISDS). If you run FreeBSD in Czechia, this is the port that lets you deal with the state without booting something else.

## Graphics and content pipeline

`openusd` · `openvdb` · `materialx` · `natron` · `luxcorerenderer` · `cycles` · `openfx-io` · `zeno` · `cortex`

Most of this stack assumes Linux. It does not have to.

## Networking, analysis and reverse engineering

`sniffnet` · `sniffglue` · `dsview` · `apitrace` · `tracy` · `keystone` · `zydis` · `iaito` · `seer`

## Desktop and media

OBS plugins (`obs-backgroundremoval`, `obs-multi-rtmp`, `obs-advanced-scene-switcher`), `tenacity`, browser ports (`librewolf`, `waterfox`, `mullvad-browser`, `tor-browser`), and Linux compatibility packages for applications that still have no native build.

## Contributing

Found something that does not build, or software you need on FreeBSD that nobody has packaged? Open an issue on the ports repository — a failing build log is a perfectly good bug report.

- Ports tree: [Martinfx/FreeBSD-Ports]({{ page.repo }})
