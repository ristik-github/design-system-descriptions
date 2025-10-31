# Title Bar / Page Title

## Overview
The Title Bar / Page Title component is a flexible header element for displaying a page title with an optional subtitle and action elements. It supports responsive layouts for both desktop and mobile viewports.

## Component Properties

### Layout
- **Mobile (`on`/`off`):** Controls the layout variant.
    - **`off` (Desktop):** Optimized for wider viewports with a horizontal layout and a minimum width of 343px for the context section.
    - **`on` (Mobile):** Optimized for narrow screens, allowing the context section to grow and fill available space.

### Content
- **Subtitle (`With`/`Without`):** Toggles the display of a subtitle below the main title.
- **Title Bar Action Area (`With`/`Without`):** Toggles the display of an action area on the right side of the title bar.

### Optional Elements
- **Title Text:** The main heading text.
- **Subtitle Text:** Descriptive text displayed below the title.
- Other elements like action slots, badges, or navigation buttons can be included as needed.

## Design Tokens

### Typography
- **Title Text:** `nova/typography/heading/1` (24px SemiBold), `nova/color/typography/base`.
- **Subtitle Text:** `nova/typography/base/regular` (14px Regular), `nova/color/typography/muted`.

### Spacing
- **Context Section Gap:** `nova/spacing/tight` (8px) between title and subtitle.
- **Mobile Layout Gap:** `nova/spacing/next` (4px) between the context and action sections.
- **Actions Slot Padding:** `nova/spacing/near` (16px) horizontal, `nova/spacing/tight` (8px) vertical.

### Colors
- **Title:** `nova/color/typography/base` (#151d1e).
- **Subtitle:** `nova/color/typography/muted` (rgba(0,0,0,0.62)).

## Layout Specifications

### Structure
- **Desktop (`Mobile=off`):** A horizontal flex layout where the context section (title and subtitle) grows to fill space, and the actions section is positioned to the right.
- **Mobile (`Mobile=on`):** A horizontal flex layout with wrapping, where the context section has a flexible basis to adapt to screen size.

### Dimensions
- **Title Text:** 24px font size with 1.4 line height.
- **Subtitle Text:** 14px font size with 1.3 line height, fixed width of 84px.
- **Text Overflow:** Both title and subtitle use ellipsis for overflow.

## Accessibility
- **Semantic Structure:** The title should use an appropriate heading level (typically `<h1>`).
- **Text Overflow:** Full text for truncated titles and subtitles should be accessible via tooltips or `aria-label`.
- **Focus Management:** All interactive elements in the actions section must be keyboard accessible with visible focus indicators.