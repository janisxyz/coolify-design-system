# Coolify Design System

Extracted and isolated design system from the Coolify project (https://github.com/coollabsio/coolify) and the coollabsio/architecture repo.

This is a portable, AI-agent-friendly design system following the Google DESIGN.md specification.

## Structure

- `DESIGN.md` — Router / entry point for the design system (React + shadcn/ui oriented)
- `design/` — Component specs, global tokens, changelog, review checklist, and manifest
  - `tokens.md` — Shared design tokens (colors, typography, spacing, radii)
  - Individual component files under forms/, overlays/, navigation/, etc.
  - Each component follows YAML frontmatter + canonical markdown sections

## Key Visual Rules

- **Light mode accent**: Coolify purple `#6b16ed`
- **Dark mode accent**: Warning yellow `#fcd452` (purple does not provide enough contrast in dark)
- Sharp 4px radii (`rounded-sm`) almost everywhere
- Compact 32px controls, dense operator UI
- Inset box-shadow focus/dirty indicators on inputs
- Geist Sans / Inter for UI, Geist Mono for code-like text

## Usage

Drop these files into any project. AI coding agents (Claude, Cursor, Grok, etc.) can read `DESIGN.md` + `design/tokens.md` + relevant component specs to generate consistent Coolify-looking UI.

Source:
- https://github.com/coollabsio/coolify (Livewire/Blade DESIGN.md + UI)
- https://github.com/coollabsio/architecture (structured design system for React/shadcn migration)

Extracted 2026-08-12.
