---
layout: collection
title: seL4 releases
---

# seL4 releases

This page documents tagged releases of the seL4 kernel and proofs, for documentation on the release
process we follow see [here](/ReleaseProcess).

## Landmark releases

This section documents the version at which specific features were introduced to seL4. For future
features, see [seL4 status](/Status). For other previous features, see the release notes below.

*Verification Status* carries the following definitions and refers to the version specified in the
[verification manifest](/ReleaseProcess#verified-manifests) tagged for that specific release.

* No: As of this release, this feature is not verified.
* FC: the functional correctness proofs are complete.
* FCI: the integrity proofs are complete, in addition to functional correctness.
* Yes: this feature has functional correctness, integrity and infoflow proofs completed, for verified platforms, as of this release.

For the verification status of all platforms, see [Hardware](/Hardware).

| Feature                        | Hardware                          | Verification status | Available From      |
| -                              | -                                 | -                   | -                   |
| 32-bit RISC-V architecture support    | RISC-V (Spike simulation target)  | No                  | [10.0.0](seL4_10.0.0) |
| 64-bit RISC-V architecture support    | RISC-V (Spike simulation target)  | No                  | [9.0.1](seL4_9.0.1) |
| Meltdown mitigation            | x86                               | No                  | [9.0.0](seL4_9.0.0) |
| Spectre mitigation             | x86                               | No                  | [9.0.0](seL4_9.0.0) |
| Zynq UltraScale+ MPSoC         | Xilinx ZCU102, ARMv8a, Cortex A53 | No                  | [8.0.0](seL4_8.0.0) |
| Multiboot2 support             | x86                               | No                  | [8.0.0](seL4_8.0.0) |
| CMake based build system       | all                               | N/A                 | [7.0.0](seL4_7.0.0) |
| ARM 32-bit SMP                 | [Sabre](/Hardware/sabreLite)      | No                  | [6.0.0](seL4_6.0.0) |
| ARMv7 32-bit FPU support       | ARM                               | No                  | [6.0.0](seL4_6.0.0) |
| ARM 64-bit support             | Aarch64                           | No                  | [5.0.0](seL4_5.0.0) |
| 64-bit x86 support             | x86\_64                           | No                  | [4.0.0](seL4_4.0.0) |
| Raspberry Pi 3 support         | [RPI3](/Hardware/Rpi3)            | No                  | [4.0.0](seL4_4.0.0) |
| ARM Hypervisor initial support | ARM                               | FC                  | [3.2.0](seL4_3.2.0) |
| First ARMv8 support            | [HiKey](/Hardware/HiKey)          | No                  | [3.1.0](seL4_3.1.0) |
| NVIDIA Tegra K1 support        | [TK1](/Hardware/jetsontk1)        | No                  | [3.0.1](seL4_3.0.1) |
| Notification binding           | all                               | Yes                 | [2.0.0](seL4_2.0.0) |

## Master (verified kernel)
{% assign coll = page.collection %}
{% for release in site[coll] reversed  %}
{% if release.path != page.path %}
    {% if release.variant != "mcs" %}

[{{ release.title }}]({{ release.url }})
([manual](http://sel4.systems/Info/Docs/seL4-manual-{{ release.version }}.pdf))

    {% endif %}

{% endif %}
{% endfor %}

## Experimental Branches

We occasionally pre-release experimental branches for community feedback and availability.

### Mixed Criticality Support (MCS) / Realtime
{% for release in site[coll] reversed  %}
    {% if release.path != page.path %}
        {% if release.variant == "mcs" %}
[{{ release.title }}]({{ release.url }})
([manual](http://sel4.systems/Info/Docs/seL4-manual-{{ release.version }}.pdf))
        {% endif %}

    {% endif %}
{% endfor %}
