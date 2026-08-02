# Technology Stack

## Core Technologies

- **Shopify Liquid:** Server-side templating language for storefront HTML rendering
- **Vanilla JavaScript:** Modern browser JavaScript and Web Components for interaction
- **CSS:** Modern CSS with custom properties and responsive layout primitives
- **HTML5:** Semantic markup with accessibility best practices

## Development Tools

### Shopify CLI

Primary development tool for theme development and store workflows.

```bash
shopify theme dev
shopify theme push
shopify theme pull
shopify theme check
shopify theme init
```

### Theme Check

Use Theme Check to validate Liquid, schema, accessibility, and common Shopify theme issues.

```bash
shopify theme check
```

Configuration is stored in `.theme-check.yml`.

### Prettier

Use the repository's `.prettierrc.json` configuration when formatting Liquid, CSS, and JavaScript files.

## Code Architecture

### No Build Process by Default

- No bundlers, transpilers, or preprocessors are required.
- Browser-native code is served directly from `/assets`.
- Avoid adding dependencies unless the project explicitly requires them.

### Framework-Free

Keep the theme dependency-free and use Dawn's established patterns. Build interaction with native JavaScript, custom elements, and Shopify-provided APIs.

## CI/CD

GitHub Actions, when present, should run theme validation and project-specific quality checks on every relevant change.

## Performance Standards

- Server-render HTML through Shopify Liquid.
- Use progressive enhancement.
- Keep client-side logic focused and minimal.
- Defer non-critical scripts.
- Load heavier functionality only when the relevant section or setting requires it.
- Avoid introducing third-party libraries without a clear performance and maintenance justification.
