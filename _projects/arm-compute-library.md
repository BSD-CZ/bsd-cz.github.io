---
layout: default
title: Port ARM Compute library
description: Porting  ARM Compute library to FreeBSD
status: Done
order: 6
repo: https://github.com/Martinfx/FreeBSD-Ports/tree/master/computelibrary
---

# {{ page.title }}

{{ page.description }}

FreeBSD support has been committed to ARM Compute Library!
This is a great step forward for running optimized ARM workloads on FreeBSD, especially for embedded and aarch64 platforms.
Looking forward to testing and integrating it into real-world FreeBSD setups.

#FreeBSD #ARM #ComputeLibrary ⁠embedded #OpenSource

## Follow-up

The port lives in our [ports tree]({{ '/projects/freebsd-ports.html' | relative_url }}) as `computelibrary`, alongside the rest of the ARM machine learning stack — `kleidiai` and `openvino` — so an aarch64 FreeBSD box can actually run optimized inference workloads, not just build the library.
