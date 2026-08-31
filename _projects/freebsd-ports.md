---
layout: default
title: FreeBSD ports
description: Creating and maintaining ports so software that never ran on FreeBSD does
status: Ongoing
order: 4
repo: https://github.com/Martinfx/FreeBSD-Ports
---

# {{ page.title }}

{{ page.description }}

FreeBSD ships tens of thousands of ports, but there is always software that has never been packaged, or that quietly stopped building on current releases and architectures. This is the ongoing work of closing those holes: new ports, build fixes, dependency updates, and patches sent upstream so the fix does not have to live in a local tree forever.

Over 80 ports are currently maintained here, staged before they go into the FreeBSD ports tree.

## Highlights

**ARM machine learning stack** — `computelibrary`, `kleidiai`, `openvino`. Optimized inference on aarch64, which is the same hardware the [board bring-up work]({{ '/projects/socbsd.html' | relative_url }}) targets. See the [ARM Compute Library port]({{ '/projects/arm-compute-library.html' | relative_url }}).

**Embedded and boot tooling** — U-Boot and ATF ports for Rockchip boards, plus `rkdeveloptool` for flashing. Detailed on the [Rockchip board support]({{ '/projects/rockchip-boards.html' | relative_url }}) page.

**Czech desktop** — `datovka` and `libdatovka`, the client for the Czech data mailbox system (ISDS). If you run FreeBSD in Czechia, this is the port that lets you deal with the state without booting something else.

**Graphics and content pipeline** — `openusd`, `openvdb`, `materialx`, `natron`, `luxcorerenderer`, `cycles`, `openfx-io`, `zeno`, `cortex`. Most of this stack assumes Linux; it does not have to.

**Networking and analysis** — `sniffnet`, `sniffglue`, `dsview`, `apitrace`, `tracy`, `keystone`, `zydis`.

**Desktop and media** — OBS plugins (`obs-backgroundremoval`, `obs-multi-rtmp`, `obs-advanced-scene-switcher`), `tenacity`, browser ports, and Linux compatibility packages for the applications that still have no native build.

## Contributing

Found something that does not build, or software you need on FreeBSD that nobody has packaged? Open an issue on the ports repository — a failing build log is a perfectly good bug report.

- Ports tree: [Martinfx/FreeBSD-Ports]({{ page.repo }})
