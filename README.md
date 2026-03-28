# Synthetic Skills

Local agent skills for building good desktop and web apps, plus the planning systems needed to ship them.

This repository packages two reusable `SKILL.md`-based skills:

- `product-design` for designing good desktop and web applications that feel production-ready
- `planning-setup` for bootstrapping persistent planning files and project instruction updates for complex work

The layout follows the common agent-skills pattern: each skill lives in its own folder with a `SKILL.md` entrypoint plus optional `references/` and `templates/` files.

## Included Skills

| Skill | Purpose | Use When |
| --- | --- | --- |
| `product-design` | Helps design production-quality desktop and web apps with strong UX structure, interaction patterns, state design, and information hierarchy | Building apps, dashboards, admin panels, settings flows, multi-step workflows, or data-dense interfaces that need to feel real and operational |
| `planning-setup` | Creates `task_plan.md`, `findings.md`, `progress.md`, planning rules, and instruction-file guidance for long-running work | Starting a project that will span many tool calls, multiple sessions, research loops, or several implementation phases |

## Repository Layout

```text
synthetic-skills/
├── README.md
├── planning-setup/
│   ├── SKILL.md
│   ├── references/
│   └── templates/
└── product-design/
    ├── SKILL.md
    └── references/
```

## Compatibility

These skills are written to be usable across agents that support `SKILL.md`-style skills or the broader Agent Skills ecosystem. In practice, that includes Codex and other tools that can load skill folders, discover `SKILL.md`, and follow linked references and templates.

`planning-setup` is designed to work with repositories that use `AGENTS.md`, `CLAUDE.md`, or both. If both files already exist, the intended behavior is to keep the planning guidance in sync across both.

## How To Use

1. Open the skill folder you want to use.
2. Read its `SKILL.md`.
3. Load only the linked references or templates needed for the current task.

If your agent supports skill installation from a local path or GitHub URL, install the individual skill folder rather than the whole repo when possible.

## Skill Notes

### `product-design`

Use this skill when you are designing a desktop or web app and want the product to feel thoughtful, usable, and production-ready. It helps choose the right product paradigm, define the job to be done, shape the critical path, inventory states, and apply strong interaction and layout patterns before coding.

Good triggers:
- "Make this feel like a real app"
- "Improve the UX for this dashboard"
- "This table/admin flow feels clunky"
- "Add keyboard-first interactions"

### `planning-setup`

Use this skill when the work needs durable context outside the chat thread. It scaffolds a planning system with separate files for phase tracking, findings, and session progress, then adds planning guidance to the repo's instruction surface.

Good triggers:
- "Set up planning for this project"
- "This will take multiple sessions"
- "Create a persistent research workflow"
- "Bootstrap project planning files"

## Working On These Skills

- Keep each `SKILL.md` concise and under 500 lines.
- Link large guidance from `references/` instead of embedding it directly.
- Keep references one level deep from `SKILL.md`.
- Update the root README when adding or removing skills.
