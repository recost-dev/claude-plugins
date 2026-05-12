# recost-dev/claude-plugins

Claude Code plugin marketplace for recost-dev.

## Install

In Claude Code (CLI, Desktop, or claude.ai/code):

```
/plugin marketplace add recost-dev/claude-plugins
/plugin install design-toolkit@recost
/plugin install superpowers@recost
```

## Plugins

### design-toolkit

30 skills for frontend design, UI critique, image-direction, and output discipline. Invoke as `/design-toolkit:<skill-name>` (e.g. `/design-toolkit:critique`, `/design-toolkit:impeccable`).

### superpowers

Core skills library: TDD, debugging, collaboration patterns, and proven techniques. Vendored from [github.com/obra/superpowers](https://github.com/obra/superpowers) v5.1.0, MIT licensed, © Jesse Vincent. License preserved at `plugins/superpowers/LICENSE`. Invoke as `/superpowers:<skill-name>` (e.g. `/superpowers:brainstorming`, `/superpowers:test-driven-development`).

## Layout

```
.claude-plugin/marketplace.json      # marketplace manifest
plugins/
  design-toolkit/
    .claude-plugin/plugin.json
    skills/<skill-name>/SKILL.md
  superpowers/
    .claude-plugin/plugin.json
    skills/<skill-name>/SKILL.md
    hooks/ scripts/ LICENSE …       # full upstream tree preserved
```

## Maintenance

- **Add a skill to design-toolkit:** create `plugins/design-toolkit/skills/<name>/SKILL.md`, bump `version` in its `plugin.json`, commit, push. Installed users update via `/plugin update`.
- **Update superpowers:** re-copy from upstream when a new version drops; preserve LICENSE.
- **Add a new plugin:** create `plugins/<new>/`, register in `.claude-plugin/marketplace.json`.
