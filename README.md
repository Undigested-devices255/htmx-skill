# htmx Skill for Claude Code

A comprehensive [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that gives Claude deep knowledge of [htmx](https://htmx.org) — the library that extends HTML with attributes for AJAX, CSS transitions, WebSockets, and Server-Sent Events.

## What This Skill Does

When activated, Claude gains access to:

- **Complete attribute reference** — all `hx-*` attributes with syntax, modifiers, inheritance rules, and edge cases
- **24 UI patterns** — click-to-edit, infinite scroll, active search, lazy loading, inline validation, modals, tabs, file upload, sortable, progress bars, and more
- **Server-side integration** — working endpoint examples for Flask, Express, Django, FastAPI, Spring Boot, Go, Rails, and Laravel
- **Extension guides** — SSE, WebSocket, Idiomorph (DOM morphing), head-support, response-targets, preload, and how to build custom extensions
- **Response handling** — HTTP headers, status code configuration, OOB swaps, and the 204 vs 200 gotcha
- **CSS animations** — htmx lifecycle classes (`htmx-swapping`, `htmx-settling`, `htmx-added`) and View Transitions API

## Installation

### From GitHub (recommended)

```bash
git clone https://github.com/mintarasss/htmx-skill.git
```

Then copy the `htmx/` folder into your Claude Code skills directory:

```bash
# Global (available in all projects)
cp -r htmx-skill/htmx ~/.claude/skills/htmx

# Project-specific (only this project)
mkdir -p .claude/skills
cp -r htmx-skill/htmx .claude/skills/htmx
```

### One-liner

```bash
# Global
git clone https://github.com/mintarasss/htmx-skill.git /tmp/htmx-skill && cp -r /tmp/htmx-skill/htmx ~/.claude/skills/htmx && rm -rf /tmp/htmx-skill

# Project-specific
git clone https://github.com/mintarasss/htmx-skill.git /tmp/htmx-skill && mkdir -p .claude/skills && cp -r /tmp/htmx-skill/htmx .claude/skills/htmx && rm -rf /tmp/htmx-skill
```

After installing, restart Claude Code or run `/reload-plugins`.

## When It Activates

The skill triggers automatically when you:

- Work with any `hx-*` attributes
- Ask about htmx by name
- Build hypermedia-driven / HTML-over-the-wire applications
- Implement patterns like live search, inline editing, infinite scroll
- Write server endpoints that return HTML fragments
- Ask about adding interactivity to server-rendered pages without a JS framework

## Skill Structure

```
htmx/
├── SKILL.md                        # Main skill (core concepts, attributes, patterns)
├── evals/
│   └── evals.json                  # Test cases and assertions
└── references/
    ├── attributes.md    # Complete attribute reference with all options
    ├── patterns.md      # 24 UI patterns with full HTML + server code
    ├── extensions.md    # SSE, WebSocket, Idiomorph, preload, etc.
    └── server-side.md   # Server integration, headers, framework examples
```

The skill uses **progressive disclosure** — the main `SKILL.md` (~320 lines) covers the most common attributes and patterns. Reference files are consulted only when deeper detail is needed, keeping context usage efficient.

## Examples

Here are some things you can ask Claude with this skill active:

> "Add a live search to my contacts page with debouncing. I'm using Flask."

> "How do I delete a table row with a fade-out animation and confirmation dialog?"

> "I need inline email validation that checks the server as the user types, plus OOB updates to a contacts table on form submit. Using Express.js."

> "Set up Server-Sent Events to push notifications to the page in real time."

> "What's the difference between hx-swap-oob and hx-select-oob? When should I use each?"

## What Makes This Skill Good

- **Working code, not just rules** — every pattern includes complete HTML and server-side code you can copy and run
- **Covers edge cases** — the 204 vs 200 gotcha, `<template>` wrapping for OOB table rows, GET excluding form values, body targeting quirk
- **Framework-agnostic server examples** — Flask, Express, Django, FastAPI, Spring Boot, Go, Rails, and Laravel
- **Full extension coverage** — SSE, WebSocket, Idiomorph, head-support, response-targets, preload
- **Inheritance documentation** — which attributes inherit and which don't, plus `hx-disinherit`/`hx-inherit` controls

## Built From Official Documentation

This skill was built by thoroughly reading and distilling the [official htmx documentation](https://htmx.org/docs/), including:

- Core documentation (`docs.md`)
- All 35 attribute reference pages
- 25 example pages with patterns
- JavaScript API reference
- Events reference
- Extension documentation (SSE, WS, Idiomorph, head-support, response-targets, preload)
- Server-side integration examples
- Response headers documentation
- Quirks and gotchas page

## Contributing

Contributions are welcome! If you find an htmx pattern or edge case that's missing, please open a PR.

## License

MIT
