# Reproducible maintainer automation

I build small, read-only tools that help maintainers review pull requests without hiding the evidence behind the result. Every featured project has a tagged release, automated checks, a credential-free first run, and a structured path for positive or negative feedback.

## Featured projects

| Project | What it does | Reproducible entry point |
| --- | --- | --- |
| [codex-maintainer-automation](https://github.com/m15363995009-maker/codex-maintainer-automation) | GitHub Action and CLI for deterministic PR review, with optional OpenAI Responses API support and stable JSON output | [v0.4.0 release](https://github.com/m15363995009-maker/codex-maintainer-automation/releases/tag/v0.4.0) / [one-minute pilot](https://github.com/m15363995009-maker/codex-maintainer-automation/discussions/24) |
| [claude-builders-bounty](https://github.com/m15363995009-maker/claude-builders-bounty) | Read-only PR review CLI for Claude Code and heuristic workflows, including a network-free synthetic fixture | [v0.4.0 release](https://github.com/m15363995009-maker/claude-builders-bounty/releases/tag/v0.4.0) / [one-minute pilot](https://github.com/m15363995009-maker/claude-builders-bounty/discussions/16) |

![codex-maintainer-automation CI](https://github.com/m15363995009-maker/codex-maintainer-automation/actions/workflows/ci.yml/badge.svg)
![claude-builders-bounty CI](https://github.com/m15363995009-maker/claude-builders-bounty/actions/workflows/ci.yml/badge.svg)

## Try without credentials

CODEX workflow with schema-versioned JSON output:

```bash
git clone --branch v0.4.0 --depth 1 https://github.com/m15363995009-maker/codex-maintainer-automation.git
cd codex-maintainer-automation
npm ci --ignore-scripts
node bin/codex-maintainer.js --fixture fixtures/sample-pr.json --mode heuristic --dry-run --json
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
