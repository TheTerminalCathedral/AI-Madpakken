# AI Madpakken

An openly licensed workflow foundation for doing consequential work with AI.

It answers the questions that decide whether AI-assisted work can be trusted: who may decide what
something means, how that meaning is locked before an implementation gets to prove itself correct,
how evidence is held to the claims it is used to support, how confidence is attacked rather than
accumulated, and how a human stays the authority without becoming the bottleneck.

The core is the **Human Sandwich Model** — `COULD → SHOULD → DID`. An upstream model explores what
could be done, a human decides what should be done, and a downstream executor does it. Around that
sit verification, research and assurance methods that keep the boundary real rather than
decorative.

This is prose, not software. It is meant to be given to a model as its operating context, and read
by a model before it acts.

Created by Dan Almer Jensen.  
Welcome to The Terminal Cathedral.

## What is in here

`MADPAKKEN/` is the package.

Start with **[`MADPAKKEN/README.md`](MADPAKKEN/README.md)**. It owns the package composition and
the reading order, and that order is deliberately not duplicated here.

The package contains both accepted doctrine and material explicitly marked `EXPERIMENTAL`. Those
labels are part of each document's meaning, and each document owns its own maturity status.
Preserve them — do not present experimental material as established practice.

## Canonical upstream

This repository is the canonical upstream distribution of AI Madpakken. The current canonical
state is the `main` branch.

Forks and adaptations are welcome. A fork is not canonical upstream, and is not endorsed by this
project.

## License

AI Madpakken is licensed under the
**[Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)**.

You are free to copy, redistribute, adapt and build upon this material, for any purpose, including
commercially, so long as you give appropriate credit, link to the license, and indicate whether you
made changes. The full legal text is in [`LICENSE`](LICENSE).

CC BY 4.0 is an open *content* license. It is not a software license, and this package is not
software — if that distinction matters for what you are building, read the license text rather
than assuming software-license norms apply.

## Attribution

The license asks for credit, a link to the license, and an indication of changes. It lets you do
that in any reasonable way that suits your medium and context.

If a ready-made form is useful, this one works:

```text
AI Madpakken
Created by Dan Almer Jensen.
Canonical upstream: https://github.com/TheTerminalCathedral/AI-Madpakken
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0).
https://creativecommons.org/licenses/by/4.0/
Changes: <none | describe what you changed>
```

That block is offered for convenience. It is **not** a required format and **not** an additional
condition on the license — the license terms are whatever `LICENSE` says, and nothing here adds to
them.

## Forks and adaptations

Fork it, adapt it, build on it, use it commercially. That is what the license is for.

Three things to keep straight, so that everyone downstream can tell what they are looking at:

- **Say what you changed.** Indicating modifications is a license condition, not a courtesy.
- **A fork is not canonical.** Canonical upstream is a fact about this project, not a restriction
  on yours. Your fork can be better; it still is not this one.
- **Do not imply endorsement.** The license does not grant permission to suggest that your version
  is connected with, sponsored by, or officially blessed by this project.

Names and trademarks are not licensed by CC BY 4.0. Please do not present a substantially modified
version as *AI Madpakken* itself without making the modification clear.

## Status

Public and readable. There is no contribution programme at this time — the package is maintained
upstream and published here, rather than developed here.
