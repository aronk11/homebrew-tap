# Homebrew tap for Correlux

[Correlux](https://github.com/aronk11/correlux) is fleet-first Kubernetes
troubleshooting from your terminal: it starts at the whole fleet, ranks what is
broken, and explains why from the cluster's own evidence.

```bash
brew install aronk11/tap/correlux
```

To upgrade later:

```bash
brew upgrade correlux
```

Install it by that full name rather than tapping first and installing by the
bare one. Homebrew 6 ignores a third-party tap until it is trusted, and reports
everything in it as unavailable rather than as untrusted; the full name trusts
this one cask as it installs it. If you have already tapped,
`brew trust --cask aronk11/tap/correlux` says the same thing after the fact.

If Homebrew insists the cask does not exist, it is holding a clone of this tap
from before the cask was published. `brew untap aronk11/tap` and install again.

## What is in here

One cask, `Casks/correlux.rb`, written by [GoReleaser](https://goreleaser.com)
whenever a Correlux release is tagged. It points at the release archives on
GitHub and installs a single static binary — there is nothing to build, and
nothing to run in your cluster.

A cask rather than a formula because the binaries are pre-built rather than
compiled by Homebrew. Casks are macOS-only, so on Linux take
`go install github.com/aronk11/correlux/cmd/correlux@latest` or an archive from
the [releases page](https://github.com/aronk11/correlux/releases) instead.

The binaries are not notarised with an Apple developer certificate, so the cask
strips the quarantine attribute on install. Without that, macOS refuses the
first run.

Do not edit the cask by hand: the next release overwrites it. Anything that
needs changing belongs in `.goreleaser.yaml` in the
[Correlux repository](https://github.com/aronk11/correlux).

## Licence

Apache-2.0, the same as Correlux.
