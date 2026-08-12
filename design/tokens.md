---
version: alpha
name: Coolify Global Design Tokens
description: Shared Coolify visual primitives used by every component spec.
colors:
  coollabs: "#6b16ed"
  coollabs-50: "#f5f0ff"
  coollabs-100: "#7317ff"
  coollabs-200: "#5a12c7"
  warning: "#fcd452"
  surface: "#ffffff"
  text: "#000000"
  white: "#ffffff"
  neutral-50: "#fafafa"
  neutral-100: "#f5f5f5"
  neutral-200: "#e5e5e5"
  neutral-300: "#d4d4d4"
  neutral-400: "#a3a3a3"
  neutral-500: "#737373"
  neutral-600: "#525252"
  neutral-700: "#404040"
  coolgray-100: "#181818"
  coolgray-200: "#202020"
  coolgray-300: "#242424"
  error: "#dc2626"
typography:
  body-sm:
    fontFamily: "'Geist Sans', Inter, sans-serif"
    fontSize: 0.875rem
    fontWeight: 400
    lineHeight: 1.25rem
  label-md:
    fontFamily: "'Geist Sans', Inter, sans-serif"
    fontSize: 0.875rem
    fontWeight: 500
    lineHeight: 1.25rem
  mono-sm:
    fontFamily: "'Geist Mono', ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: 0.875rem
    fontWeight: 400
    lineHeight: 1.25rem
rounded:
  sm: 0.25rem
  callout: 0.5rem
  pill: 9999px
spacing:
  control-height: 2rem
  control-padding-x: 0.5rem
  control-gap: 0.5rem
  dirty-bar-width: 0.25rem
components:
  default-control:
    typography: "{typography.label-md}"
    rounded: "{rounded.sm}"
    height: "{spacing.control-height}"
  focus-ring-light:
    color: "{colors.coollabs}"
  focus-ring-dark:
    color: "{colors.warning}"
---

# Coolify Global Design Tokens

## Overview

These tokens are the shared Coolify design primitives. Component files under `design/` may redeclare the subset they need for local lint/export, but must not contradict this file.

The design is dense, sharp, dark-first, and operational. Use shadcn/ui primitives as the implementation base, then apply these Coolify visual decisions.

## Colors

- Light-mode accent: `coollabs` purple.
- Dark-mode accent: `warning` yellow.
- Do not use purple as the general dark-mode accent. Purple in dark mode is allowed only where a component spec explicitly documents an exception, such as highlighted/promoted button fill.
- Dark operational surfaces use `coolgray-*`; light surfaces use white/neutral steps.

## Typography

- Default UI text uses Geist Sans at `text-sm` density.
- Labels and compact controls use `label-md`.
- Command/config/code-like text uses Geist Mono only where the component spec asks for it.

## Layout

- Default controls are compact: `h-8`, `px-2`, `gap-2`, `text-sm`.
- Favor dense operator dashboards over marketing spacing.
- Do not stretch controls unless the layout spec requires it.

## Elevation & Depth

- Prefer flat bordered or inset-shadow surfaces.
- Do not introduce gradients, glossy effects, large soft shadows, or decorative depth.
- Inputs/selects/textareas use the documented inset shadow system instead of normal borders.

## Shapes

- Default radius is `rounded-sm` / 4px.
- Callouts may use 8px.
- Pills may use full radius only when the component spec says so.

## Components

Component-specific tokens and variants live in the matching file under `design/`. If a component needs a new shared primitive, update this file and mention the affected components in `design/CHANGELOG.md`.

## Do's and Don'ts

Do:

- Preserve purple light accents and yellow dark accents.
- Keep controls compact and sharp.
- Reuse documented component specs before inventing local styles.

Don't:

- Mix large radii into normal views.
- Add undocumented icons, shadows, gradients, or spacing systems.
- Treat component-local duplicated tokens as permission to drift from this global contract.

## Implementation Notes

When a design update changes a global token, update:

1. this file,
2. every affected component file,
3. `design/CHANGELOG.md`,
4. `design/manifest.json` if lookup metadata changed,
5. relevant mockup routes/screenshots.

## Review Checklist

- Shared token change is recorded in `design/CHANGELOG.md`.
- Component files still agree with these global tokens.
- Mockups demonstrate light and dark behavior where the token affects theme.

## Claude Improvement Notes

Do not treat this section as approved design change. Use it only to collect future ideas.

## Source References

- Google DESIGN.md specification: https://github.com/google-labs-code/design.md
- Local router: `DESIGN.md`
