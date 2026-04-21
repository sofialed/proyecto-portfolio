# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Workflow

Before making any edit to a file, show the proposed change in the chat and wait for the user to confirm. Only write to files after explicit approval.

## Project overview

Static portfolio site — pure HTML and CSS, no build tools or JavaScript framework. Open `index.html` directly in a browser to preview.

## CSS architecture

Styles are split by section and loaded in this order in `index.html`:

| File | Covers |
|------|--------|
| `css/style.css` | Global reset, body, typography, shared utilities |
| `css/header.css` | Navigation, branding, social icons |
| `css/hero-container.css` | Hero section, CTA button, wave divider |
| `css/about-me.css` | About section, quote, values cards |
| `css/projects.css` | Projects section, card layouts, wave dividers |

`style_curso.css` at the root is a legacy course reference file — do not edit or import it.

## Naming convention

BEM-inspired with a custom variation:
- Block/element separator: single underscore → `.hero_title`, `.values_icon`
- Modifier separator: single hyphen → `.nav_link-active`, `.project--horizontal`
- BEM double underscore only for SVG wave parts → `.wave-divider__bottom`

## Color palette

| Role | Value |
|------|-------|
| Background | `#F9F9F7` |
| Body text | `#6D6875` |
| Headings | `#0a100d` |
| About section bg | `#F7CB46` |
| Projects section bg | `#FF8118` |
| Cards bg | `#FEF6E1` |

## Typography

- Body: `Montserrat` (Google Fonts), `1rem`, color `#6D6875`
- Headings (h1/nav): `Figtree` (Google Fonts)
- Both fonts are loaded via `<link>` tags in `<head>`

## Key layout patterns

- Flexbox is used throughout (header, hero, values grid, project cards)
- Values cards use `display: grid` with 4 columns in `about-me.css`
- Project card with screenshot uses `.project--horizontal` (column flex: image top, two boxes below)
- Wave dividers between sections are inline SVGs with fill colors matching adjacent section backgrounds
- Cards use `box-shadow: 4px 4px 0px rgba(0,0,0,0.85)` (solid offset shadow, brutalist style)
