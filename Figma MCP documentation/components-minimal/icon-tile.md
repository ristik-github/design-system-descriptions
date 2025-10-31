# Icon Tile

## Overview
The Icon Tile is a composite card component designed to display modular content with a large icon, title, descriptive text, badges, action buttons, and optional favoriting functionality. It is suitable for showcasing items like alerts, incidents, or features, with visual branding through colored icon backgrounds.

## Component Properties

### Variants
- **Tooltip:** `on` or `off`. Controls the display of a tooltip on hover.
- **Status:** Controls the semantic color scheme of the icon section.
    - `Error` (Critical)
    - `Warning`
    - `Informative`
    - `Success`
    - `Feature`
    - `Brand`
    - `Neutral`

### Optional Visual Elements
- **Body Text:** Descriptive text below the title (max 3 lines).
- **Action Buttons:** Buttons at the bottom of the tile.
- **Status Badge:** A small badge next to the title.
- **Icon Button:** A favorite/bookmark icon button in the top-right.

## Visual Specifications

### Structure
The component has two main sections:
1.  **Icon Section (Left):** Fixed 80px wide colored panel with a large icon.
2.  **Content Section (Right):** Flexible width area for title, text, and actions.

### Icon Section
- **Container:** 80px fixed width, full height, `26px` horizontal & `25px` vertical padding.
- **Icon:** 40x40px.
- **Status Variants:** Each status has a unique color set for background, border, and icon.
    - **Error:** `nova/color/critical/secondary` (bg), `nova/color/critical/quaternary` (border), `nova/color/critical/primary` (icon).
    - **Warning:** `nova/color/warning/secondary` (bg), `nova/color/warning/quaternary` (border), `nova/color/warning/primary` (icon).
    - **Informative:** `nova/color/informative/secondary` (bg), `nova/color/informative/quaternary` (border), `nova/color/informative/primary` (icon).
    - **Success:** `nova/color/success/secondary` (bg), `nova/color/success/quaternary` (border), `nova/color/success/primary` (icon).
    - **Feature:** `nova/color/feature/secondary` (bg), `nova/color/feature/quaternary` (border), `nova/color/feature/primary` (icon).
    - **Brand:** `nova/color/brand/secondary` (bg), `nova/color/brand/quaternary` (border), `nova/color/brand/primary` (icon).
    - **Neutral:** `nova/color/neutral/secondary` (bg), `nova/color/neutral/quaternary` (border), `nova/color/neutral/primary` (icon).

### Content Section
- **Container:** Flexible width, vertical flex layout with `4px` gap. Padding: `0px` top/left, `8px` right, `12px` bottom.
- **Title Row:** Min height `28px`, `4px` top padding.
- **Title Text:** `nova/typography/base/strong`, `nova/color/typography/base`. Single line with ellipsis.
- **Body Text:** `nova/typography/supporting/regular`, `nova/color/typography/muted`. Max 3 lines with ellipsis.
- **Buttons Section:** `4px` gap between buttons. Primary button is "Secondary" variant, Secondary button is "Tertiary" variant.

### Tooltip (when Tooltip=on)
- **Container:** `nova/tooltip/color/background`, `8px` horizontal & `4px` vertical padding, `350px` max width.
- **Text:** `nova/tooltip/color/foreground`, 12px font.
- **Pointer:** 6x3px triangle, matches tooltip background.

## Design Tokens

### Typography
- **Title:** `nova/typography/base/strong`
- **Body Text:** `nova/typography/supporting/regular`

### Spacing
- **Icon Section Padding:** `26px` horizontal, `25px` vertical
- **Content Section Padding:** `8px` right, `12px` bottom
- **Element Gaps:** `nova/spacing/next` (4px)

### Border & Radius
- **Icon Section Border:** `nova/border/basic` (1px)
- **Icon Section Border Radius:** `8px` (left corners only)

## Layout Specifications

### Structure
- **Icon Tile:** `div` with horizontal flex layout.
    - **Icon Section:** 80px fixed width.
    - **Content Section:** Flexible width, vertical flex layout.
        - **Title Row:** Horizontal flex, space-between.
        - **Body Text**
        - **Buttons Section**
- **Tooltip:** Absolutely positioned.

### Dimensions
- **Icon Tile:** Hugs content, typical width ~330px, height ~126px.
- **Icon:** 40x40px.
- **Buttons:** 28px height.

## Accessibility

### Semantic HTML
- Use `<article>` or `div[role="region"]` for the tile.
- Title should be a heading (`<h3>`, `<h4>`).
- Body text should be a `<p>`.
- Buttons should be `<button>`.

### ARIA Attributes
- **Container:** `aria-labelledby` pointing to the title's ID.
- **Icon:** `aria-hidden="true"` if decorative.
- **Icon Button (Favorite):** `aria-label` describing the action, `aria-pressed` for state.
- **Tooltip:** `role="tooltip"`, associated with trigger via `aria-describedby`.

### Keyboard Navigation
- **Tab order:** Title (if link) → Icon Button → Install Button → More Info Button.
- Space or Enter activates buttons.
- Tooltip should appear on keyboard focus.
- Escape should close the tooltip.