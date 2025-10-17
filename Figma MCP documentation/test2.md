# Title Bar / Section Title

## Overview
This component is a title/header block used to present a page or section title with an optional subtitle and action area (buttons/spacers). It exists as a single component set with explicit variant axes for visual hierarchy and a mobile toggle.

## Component Properties

- Purpose: Present a primary title (and optional subtitle) at the top of a page or section, with room for contextual actions on the right.
- Visible parts: title text, optional subtitle text, action area (buttons container / spacer), optional decorative bottom stroke in some variants.
- Sizing behaviour: "wide" variant is the default width behaviour. Some mobile variants constrain the title column (example: max width ~260px in one mobile variant).

### Variant axes (from metadata)
- Variant: `wide` (only listed variant)
- Hierarchy: `SH1` | `SH2` | `SH3` (visual weight / size differences)
- Mobile: `off` | `on` (mobile layout adjustments)

### Available combinations (explicit in metadata)
- Variant=wide, Hierarchy=SH1, Mobile=off
- Variant=wide, Hierarchy=SH1, Mobile=on
- Variant=wide, Hierarchy=SH2, Mobile=off
- Variant=wide, Hierarchy=SH2, Mobile=on
- Variant=wide, Hierarchy=SH3, Mobile=off
- Variant=wide, Hierarchy=SH3, Mobile=on

## Sizes & Typography

- SH1 (largest): uses `nova/typography/heading/3` (Font: Geist SemiBold, 18px, weight 600, lineHeight ~1.4). Typically used for primary page titles.
- SH2: uses `nova/typography/body/strong` (Font: Geist SemiBold, 16px, weight 600, lineHeight ~1.4). Used for secondary titles.
- SH3: uses `nova/typography/body/strong` (16px Semibold) in compact arrangements (may include an optional divider line below the title in some variants).
- Subtitle (when present): uses `nova/typography/base/regular` (Font: Geist Regular, 14px, weight 400, lineHeight ~1.3).

## States

This component is primarily static visually. Variants describe layout and hierarchy rather than interactive states. Visible state differences to document:

- Default: Title and optional subtitle visible, actions area (buttons/spacer) visible at right.
- Mobile-on variants: title column may stack or limit width (example: max width 260px in SH3 mobile-on).
- SH3 variants (off/on) show a decorative stroke (a light horizontal line) visually positioned beneath the title area in some instances.

No hover/pressed/disabled visual states are defined in the Figma metadata for this component itself — actions in the right-side area (buttons) should be documented on their respective components.

## Design Tokens (tokens extracted from component variable defs)

### Typography tokens
- `nova/typography/heading/3` (Font: Geist SemiBold, 18px, weight 600, lineHeight: ~1.4)
- `nova/typography/body/strong` (Font: Geist SemiBold, 16px, weight 600, lineHeight: ~1.4)
- `nova/typography/base/regular` (Font: Geist Regular, 14px, weight 400, lineHeight: ~1.3)
- `global/typography/fontsize/14` (14)

### Spacing tokens
- `nova/spacing/tight` (`8`)
- `nova/spacing/next` (`4`)
- `nova/spacing/near` (`16`)
- `nova/spacing/close` (`12`)

### Color tokens
- `nova/color/typography/base` (`#151d1e`) — primary title color
- `nova/color/typography/muted` (`#0000009e`) — subtitle / muted text
- `nova/surfaces/color/workspace` (`#ffffff`) — surface used in background of the workspace
- `nova/surfaces/color/workspace border` (`#e0e6e6`) — border/stroke used for the thin separator that appears under some variants
- `nova/surfaces/color/background` (`#f5f7fa`) — general background token present in design context

### Radii & effects
- `nova/radii/component/input` (`8`) — radius token is present in the design token list (component itself does not show a rounded container). Included for reference as it appears in the token set.

## Layout & Structure

Visible structure (top → bottom / left → right):

- Title wrapper (left): contains title text and optional subtitle stacked or aligned depending on hierarchy & mobile flag.
- Actions container (right): flexible container for small action buttons and spacing tokens; often implemented as a horizontal group with a spacer image in the design export.
- In some SH3 variants a full-width decorative stroke appears below the title area; the stroke uses `nova/surfaces/color/workspace border`.

Layout details visible in the design context:
- Left title block uses a gap of `nova/spacing/tight` (8) between title and subtitle.
- Right actions area uses `nova/spacing/next` (4) as the gap between action items.
- Minimum title row height visually driven by typography: Title line height and small vertical padding produce a visible minimum height (code shows min heights like 28px for SH1 in some instances). Where present, the title block uses explicit min height values derived from typography and spacing.

## Dimensions

- Title size examples (calculated from tokens and typography):
  - SH1 total visual height example: typography height (18px line) + vertical gaps (e.g., `nova/spacing/close` (12) top + bottom in some layouts) → visually ~52px in the exported layout.
  - Subtitle line height: 14px with 1.3 leading.
- Width: component is designed to fill the available wide container. Mobile-on variants constrain the title column (example: max 260px in SH3 mobile-on).

Note: exact pixel totals are visible in Figma snapshots / generated code; when a precise numeric dimension is not backed by a token it is documented here as a measured value from the design.

## Accessibility Considerations

- Semantic role: The title is a heading; map visual hierarchy to heading level (e.g., SH1 → h1/h2 depending on page; SH2 → h2/h3; SH3 → h3/h4). This mapping is a visible guidance derived from the hierarchy variants.
- Subtitle: Use a descriptive element (e.g., <span> or <p>) associated with the heading visually. If the subtitle contains critical descriptive text, expose it to assistive tech (do not mark it aria-hidden).
- Decorative elements (spacer images, decorative strokes): treat as presentational (aria-hidden or role=presentation) unless they convey information.
- Action area: make sure any actionable controls placed in the right-side container have accessible names, focus indicators, and correct keyboard order relative to the heading.

## Content Structure

- Title (required): single-line or multi-line short string.
- Subtitle (optional): short supportive text line.
- Actions container (optional): inline action buttons or icons aligned to the right.

## Visual Behavior Notes

- Mobile-on variants adapt layout: title column may be constrained, and subtitle may wrap differently — visually the same tokens are used but container widths change.
- SH3 variants can include a thin decorative divider line; the divider uses `nova/surfaces/color/workspace border` and visually appears as a subtle stroke under the title area.

## Reference / Node IDs & Assets (from exported design context)

- Component frame name: "Title Bar / Section Title"
- Example node IDs (useful when cross-referencing the Figma source):
  - Variant=wide, Hierarchy=SH1, Mobile=off → `2058:8795`
  - Variant=wide, Hierarchy=SH1, Mobile=on  → `9646:12089`
  - Variant=wide, Hierarchy=SH2, Mobile=off → `9084:1910`
  - Variant=wide, Hierarchy=SH3, Mobile=off → `9120:3271`
  - (Design export also includes data-node-id attributes on internal elements for precise mapping.)

- Image assets referenced in the design export are served from a local MCP dev server (example constants available in the design context). These are decorative spacer / line assets used in screenshots and exported preview code.

## Usage Guidance (advisory)

> Note: The following guidance is interpretative and should be verified against product conventions.

- Use SH1 for primary page titles or major section headings.
- Use SH2 for secondary headings where visual emphasis should remain strong but not primary.
- Use SH3 for compact section headings, especially where a decorative divider is appropriate.
- Keep subtitle text brief — it is visually compact and uses the base regular token.

## Related Components

- Action buttons and icon buttons that appear in the right-side area are separate components and should be documented in their own files (e.g., `icon-button.md`, `button.md`).

## Version / Notes

- Documentation created from the Figma design context and variable definitions extracted via MCP. Tokens listed here are exactly those returned by the component's `get_variable_defs` output.
