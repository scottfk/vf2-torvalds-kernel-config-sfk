# Contributing

Thanks for stopping by. This is a personal project — a minimalist upstream kernel config
for the StarFive VisionFive 2 (JH7110 SoC) — but contributions are genuinely welcome.
Here's how things work.

## What this project is

A `.config` trimmed to exactly what the JH7110 hardware requires to boot and run usefully,
built against Linus Torvalds' upstream tree (not StarFive's BSP fork). The goal is fast
build times and a clean, auditable config — not maximum feature coverage.

## What's useful to contribute

- **Bug reports** — kernel panics, missing drivers, things that used to work and don't after
  a config bump. A `dmesg` excerpt and kernel version go a long way.
- **Omissions** — if something is clearly needed for standard VF2 hardware (onboard NIC,
  eMMC, GPIO, etc.) and is missing or broken, please open an issue or PR.
- **Kernel version bumps** — if you've tested the config against a newer upstream tag and
  needed to adjust options, a PR with a brief note on what changed and why is very welcome.
- **Documentation** — corrections or additions to the README, especially anything clarifying
  build steps for different host distros.

## What doesn't fit

This config intentionally leaves out things that aren't needed for the base VF2 hardware:
USB gadget stacks, exotic filesystems, most security frameworks, etc. PRs that add optional
features without a clear JH7110-hardware justification are likely to be declined — not because
the features are bad, but because scope creep defeats the purpose. If you have a legitimate
use case, explain it; I'll reconsider.

## How to submit changes

1. Fork the repo and create a branch.
2. Make your change to the `.config` (or docs).
3. In your PR description, explain **what** you changed and **why** — ideally referencing a
   Kconfig symbol by name (e.g. `CONFIG_SPI_SIFIVE`) and the hardware or function it serves.
4. If it's a config change, note the kernel version you tested against.

There's no CI, no automated test suite, no CLA. Just a short description and a clear reason.

## Issues

Issues are fine for questions too, not just bugs. If something about the build process is
confusing, ask. I can't promise a fast response, but I do read them.

## Code of conduct

Be straightforward and respectful. That's the whole policy.
