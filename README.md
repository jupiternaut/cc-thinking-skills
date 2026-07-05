# Claude Code Thinking Skills

Claude/Codex-compatible thinking skills collection packaged as a Claude Code plugin.

This repository is a skills collection, not a Rust, Go, Make, or application build project. The source boundary is Markdown skill files, Claude plugin metadata, and small Node.js quality scripts.

## Table of Contents

- [Background](#background)
- [Install](#install)
- [Usage](#usage)
- [Repository Layout](#repository-layout)
- [Status](#status)
- [Maintainer](#maintainer)
- [Contributing](#contributing)
- [License and Upstream](#license-and-upstream)

## Background

The repository packages mental-model and reasoning frameworks as reusable Claude Code skills. It is a fork of `tjboudreaux/cc-thinking-skills`.

The collection includes 39 `thinking-*` skills such as first principles, Bayesian reasoning, systems thinking, OODA, inversion, pre-mortem, theory of constraints, and model routing.

The local tree contains:

- skill Markdown files under `skills/`,
- Claude plugin metadata under `.claude-plugin/`,
- a marketplace descriptor,
- quality framework docs,
- Node.js validation and enhancement scripts.

It does not contain app runtime code, compiled binaries, Rust crates, Go modules, or Make-based build tooling.

## Install

Install through Claude Code plugin marketplace support:

```text
/plugin marketplace add tjboudreaux/cc-thinking-skills
/plugin install thinking-skills@thinking-skills-marketplace
```

Manual install:

```sh
git clone https://github.com/jupiternaut/cc-thinking-skills.git
cp -R cc-thinking-skills/skills/* ~/.claude/skills/
```

Project-local install:

```sh
cp -R cc-thinking-skills/skills/* /path/to/project/.claude/skills/
```

## Usage

Invoke the skills by name in Claude Code or another compatible agent runtime:

```text
Use thinking-first-principles to analyze this architecture decision.
Apply thinking-pre-mortem to this release plan.
Use thinking-model-router to choose a reasoning framework.
```

Quality scripts are plain Node.js scripts:

```sh
node scripts/validate-skills.js
node scripts/enhance-skill.js thinking-first-principles
node scripts/generate-improvement-prompt.js thinking-bayesian
```

No `npm install`, `make`, Rust toolchain, or Go toolchain is required by the current repository layout.

## Repository Layout

- `.claude-plugin/plugin.json` - plugin metadata for the thinking skills package.
- `.claude-plugin/marketplace.json` - marketplace descriptor.
- `skills/thinking-*/SKILL.md` - individual thinking framework skills.
- `scripts/QUALITY_FRAMEWORK.md` - quality rubric for skill content.
- `scripts/validate-skills.js` - validates skill structure and quality markers.
- `scripts/enhance-skill.js` - prints improvement suggestions.
- `scripts/generate-improvement-prompt.js` - generates prompts for improving a selected skill.
- `scripts/quality-report.json` - generated or checked-in quality snapshot.
- `FUTURE_SKILLS.md` - candidate future skills.
- `CONTRIBUTING.md` - contribution guide.

## Status

Usable skills collection. The implementation surface is Markdown plus Node.js maintenance scripts. README readers should not infer a compiled language project from this repository.

## Maintainer

Local fork: `jupiternaut/cc-thinking-skills`.

Upstream parent: `tjboudreaux/cc-thinking-skills`.

## Contributing

When adding or changing a skill:

- Use a `skills/thinking-name/SKILL.md` directory.
- Include YAML frontmatter with `name` and `description`.
- Keep descriptions short enough for tool and skill selection.
- Include clear usage guidance, examples, templates, and verification checklists.
- Run the Node.js validator before committing.

```sh
node scripts/validate-skills.js
```

## License and Upstream

Licensed under MIT. See [LICENSE](LICENSE).

Upstream: [`tjboudreaux/cc-thinking-skills`](https://github.com/tjboudreaux/cc-thinking-skills).

Local fork: [`jupiternaut/cc-thinking-skills`](https://github.com/jupiternaut/cc-thinking-skills).
