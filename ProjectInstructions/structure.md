# Project Structure

## Shopify Theme Directory Layout

### `/layout`

Theme wrapper templates that define the overall HTML structure.

- `theme.liquid` - Main layout for storefront pages
- `password.liquid` - Layout for password-protected stores

### `/templates`

JSON or Liquid page templates for products, collections, pages, search, customers, cart, blogs, and other Shopify resources.

Templates use Shopify Online Store 2.0 JSON format to compose sections.

### `/sections`

Reusable, modular UI components that can be added to templates and configured in the theme editor.

- `header.liquid`, `footer.liquid` - Site-wide navigation and footer
- `main-*.liquid` - Core page content sections
- `featured-*.liquid` - Homepage and merchandising sections
- `cart-*.liquid` - Cart components
- `header-group.json`, `footer-group.json` - Section groups

### `/snippets`

Small, reusable Liquid fragments included with `{% render %}`. Keep snippets focused on one reusable concern such as cards, icons, prices, forms, or controls.

### `/assets`

Static files served directly to the browser.

- `*.css` - Component and section styles
- `*.js` - Progressive-enhancement scripts and Web Components
- `*.svg`, `*.png`, `*.gif` - Theme graphics and media
- `base.css` - Foundation styles
- `global.js` - Shared JavaScript utilities

Use Dawn's existing naming conventions such as `component-*.css` and `section-*.css`.

### `/config`

Theme configuration and settings.

- `settings_schema.json` - Defines theme customization options
- `settings_data.json` - Stores theme setting values

### `/locales`

Internationalization JSON files. Keep user-facing text translatable and update `en.default.json` when adding new translation keys.

## File Organization Principles

### Liquid Files

- Layouts remain minimal and structural.
- Templates define page composition.
- Sections contain self-contained Liquid, markup, schema, and section-specific behavior.
- Snippets contain atomic, reusable presentation or logic.

### Asset Files

- Keep component styles isolated where practical.
- Load JavaScript with `defer` when it is not required for initial markup.
- Prefer progressive enhancement: HTML and CSS should provide the core experience before JavaScript adds interaction.

### Configuration

- Use schema-driven settings for merchant-editable values.
- Keep settings types explicit, such as color, range, select, image, and URL.
- Keep user-facing strings in locale files.

## Key Architectural Patterns

### Section-Based Architecture

Sections are the primary building blocks. Each section should:

- Contain a valid schema.
- Be independently configurable in the theme editor.
- Support useful settings and blocks without unnecessary complexity.
- Be safe to reorder, disable, and reuse.

### Web Component Pattern

Interactive JavaScript modules may extend `HTMLElement` as custom elements, following Dawn's existing patterns such as cart drawers, modal dialogs, and disclosure controls.

### Progressive Enhancement

- Render usable HTML server-side through Liquid.
- Use CSS for the baseline presentation.
- Add JavaScript only for behavior that cannot be handled natively.
- Preserve a functional experience when JavaScript is unavailable.
