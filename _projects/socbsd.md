---
layout: default
title: SoCBSD
description: FreeBSD fork dedicated to SoC board bring-up — collaborative, hardware-verified, upstream-bound
status: In progress
order: 1
repo: https://github.com/SoCBSD/socbsd-src
---

# {{ page.title }}

{{ page.description }}

Hundreds of boards run Linux. Only a handful run FreeBSD. **SoCBSD** exists to close that gap: a FreeBSD fork whose only job is bringing FreeBSD up on SoC boards it does not support today. It is a playground, not a distro — no ISOs, no wallpapers, no retro archaeology.

## Why a fork

Solo bring-up produces boards that exist in one person's repository and nowhere else — supported and unsupported at the same time — and it burns out the people carrying them. Our own Banana Pi R2 Pro work is exactly that story: ten months, one person, a board that boots but never reaches the tree.

A fork lets partial work land immediately instead of waiting for a board to be perfect. What works gets merged now, other people who own the same board fill in the parts the first person didn't need — USB, display, man pages — and the finished board goes upstream to FreeBSD as one patchset with every contributor's name on it.

## How it works

- **`gamemaster`** is the default branch: FreeBSD plus every board that has passed the gate.
- **`arena/<board>`** branches are cut per board. Fast iteration, fast merges inside the arena; the gate to `gamemaster` is where duplicate drivers get resolved and board-specific code gets refactored up to the SoC family level.
- **`freebsd/main` syncs** into `gamemaster` regularly, so arenas never drift into unmergeable territory.

## The rules that matter

Bring-up only works when claims are verifiable, so a few things are non-negotiable:

1. **Own the board.** Contributions are accepted only for hardware the contributor physically has, in working condition.
2. **Test on the hardware first.** Every claim ships with a serial boot log, verified by another contributor who owns the same board. Untested code gets you benched.
3. **Provenance is absolute.** No GPL code, ever. NetBSD and OpenBSD drivers are fair game — BSD-licensed, copyright notices intact — but a port is a port, not a paste, and it still has to boot.
4. **Real names.** Upstreaming to FreeBSD needs real names attached to real commits.

Every pull request is also reviewed by `gamemakerd`, the org's review bot: it builds the change, checks that no sibling board breaks, and comments on what it finds. Zero comments is the perfect score.

## Open arenas

- **Banana Pi R2 Pro** (Rockchip RK3568) — the board that started it, see the [MT7531 switch work]({{ '/projects/support-bananapi-r2-pro.html' | relative_url }})
- **Raspberry Pi 5** (Broadcom BCM2712) — no FreeBSD support today; the software that wants this class of hardware already exists
- **Raspberry Pi 3** (Broadcom BCM2837)

Have one of these on your desk? Open the arena issue with a photo of the board and a serial capture of whatever it currently does, and you are in.

- Organization: [github.com/SoCBSD](https://github.com/SoCBSD)
- Source: [SoCBSD/socbsd-src]({{ page.repo }})
