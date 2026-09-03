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

## What is in here

One formula, `Formula/correlux.rb`, written by
[GoReleaser](https://goreleaser.com) whenever a Correlux release is tagged. It
points at the release archives on GitHub and installs a single static binary —
there is nothing to build, and nothing to run in your cluster.

Do not edit the formula by hand: the next release overwrites it. Anything that
needs changing belongs in `.goreleaser.yaml` in the
[Correlux repository](https://github.com/aronk11/correlux).

## Licence

Apache-2.0, the same as Correlux.
