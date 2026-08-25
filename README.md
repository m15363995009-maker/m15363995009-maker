# Reproducible maintainer automation

I build small, read-only tools that help maintainers review pull requests without hiding the evidence behind the result. Every featured project has a tagged release, automated checks, a credential-free first run, and a structured path for positive or negative feedback.

## Featured projects

| Project | What it does | Reproducible entry point |
| --- | --- | --- |
| [codex-maintainer-automation](https://github.com/m15363995009-maker/codex-maintainer-automation) | Checkout-free GitHub Action and CLI for deterministic PR review, producing both human-readable Markdown and schema-versioned JSON | [Marketplace](https://github.com/marketplace/actions/codex-maintainer-pr-review) / [v0.5.0 release](https://github.com/m15363995009-maker/codex-maintainer-automation/releases/tag/v0.5.0) / [one-minute pilot](https://github.com/m15363995009-maker/codex-maintainer-automation/issues/16) |
| [claude-builders-bounty](https://github.com/m15363995009-maker/claude-builders-bounty) | Read-only PR review CLI for Claude Code and heuristic workflows, including a network-free synthetic fixture | [v0.4.0 release](https://github.com/m15363995009-maker/claude-builders-bounty/releases/tag/v0.4.0) / [one-minute pilot](https://github.com/m15363995009-maker/claude-builders-bounty/discussions/16) |

![codex-maintainer-automation CI](https://github.com/m15363995009-maker/codex-maintainer-automation/actions/workflows/ci.yml/badge.svg)
![claude-builders-bounty CI](https://github.com/m15363995009-maker/claude-builders-bounty/actions/workflows/ci.yml/badge.svg)
[![Codex Maintainer PR Review on GitHub Marketplace](https://img.shields.io/badge/GitHub%20Marketplace-Codex%20Maintainer%20PR%20Review-2ea44f?logo=github)](https://github.com/marketplace/actions/codex-maintainer-pr-review)

## Try without credentials

CODEX v0.5.0 can generate Markdown and JSON in one read-only run:

```bash
git clone --branch v0.5.0 --depth 1 https://github.com/m15363995009-maker/codex-maintainer-automation.git
cd codex-maintainer-automation
npm ci --ignore-scripts
node bin/codex-maintainer.js \
  --fixture fixtures/sample-pr.json \
  --mode heuristic \
  --dry-run \
  --out review.md \
  --json-out review.json
```

Claude workflow with a network-free fixture:

```bash
git clone --branch v0.4.0 --depth 1 https://github.com/m15363995009-maker/claude-builders-bounty.git
cd claude-builders-bounty
npm ci --ignore-scripts
npm run check
node bin/claude-review.js --fixture fixtures/sample-pr.json --mode heuristic --out review.md
```

## Evidence policy

- A same-owner or alternate-account run is recorded as a self-test, not independent adoption.
- Stars, clones, releases, and repository activity are not treated as user counts.
- Negative and failed trials are welcome when they include a reproducible command and environment.
- Do not include credentials, private source, or sensitive generated output in a report.
- A Star is optional and never required for support or feedback.

## Report a real trial

- [CODEX structured pilot report](https://github.com/m15363995009-maker/codex-maintainer-automation/issues/new?template=pilot_report.yml)
- [CLAUDE structured pilot report](https://github.com/m15363995009-maker/claude-builders-bounty/issues/new?template=pilot_report.yml)

The most useful contribution is a reproducible result: what you ran, what happened, whether the output helped, and one concrete improvement.

## Contribute a focused improvement

- [CODEX: add a JSON-to-job-summary consumer example](https://github.com/m15363995009-maker/codex-maintainer-automation/issues/25)
- [CLAUDE: add cross-platform offline fixture CI](https://github.com/m15363995009-maker/claude-builders-bounty/issues/18)

Both are bounded `good first issue` tasks with explicit acceptance criteria. They are unpaid and voluntary; please choose a task because it is useful, not to manufacture activity.
