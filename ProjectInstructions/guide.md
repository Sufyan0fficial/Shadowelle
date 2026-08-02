---
inclusion: always
---

# Shopify Theme Fidelity Standard

## Source of Truth

When a design reference is provided, inspect it fully before building or modifying a section. Treat the approved design as the single source of truth for visual decisions.

Here is the Reference shopify store :
https://dynamic-rich.myshopify.com/


## Pixel-Fidelity Requirements

The developed theme should closely match the approved design. Match:

- Font family, size, weight, and line-height
- Spacing, margins, padding, and gaps
- Layout structure, alignment, and responsive behavior
- Colors, borders, radius, shadows, and other visual details

## Responsiveness

Every section and element must be fully responsive across desktop, tablet, and mobile. Check mobile behavior explicitly rather than assuming desktop layouts will scale correctly.

## Shopify Admin Editability

Every section and element built must be editable through the Shopify theme editor wherever practical. Use schema settings and blocks for text, images, colors, links, and layout options instead of hardcoding merchant-controlled content.

## Visual QA Workflow

After implementing a section, render and inspect the theme at representative desktop and mobile viewport sizes. Confirm spacing, hierarchy, interactions, accessibility, and responsive behavior before moving to the next section.

Avoid full-page screenshots of unusually long pages when a scoped section or viewport-sized capture is sufficient. Prefer focused visual checks that are easy to compare and review.

## Shopify Theme Constraints

- Follow Online Store 2.0 section and block conventions.
- Keep Liquid, HTML, CSS, and JavaScript valid and maintainable.
- Preserve Dawn's accessibility and performance patterns unless there is a clear project requirement to change them.
- Prefer progressive enhancement and native browser capabilities.
