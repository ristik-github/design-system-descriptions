# Title Bar / Section Title

## Overview
The Title Bar / Section Title component is a flexible header for page or section titles, featuring optional subtitles and action areas. It offers three hierarchy levels (SH1, SH2, SH3) for different visual weights and includes mobile-optimized layouts.

## Component Properties

### Hierarchy
- **SH1:** Largest title size (`nova/typography/heading/3`, 18px). Used for primary page titles.
- **SH2:** Medium title size (`nova/typography/body/strong`, 16px). Used for secondary section headings.
- **SH3:** Same size as SH2, but includes a decorative horizontal line separator. Suitable for subsection headers.

### Layout
- **Mobile (`on`/`off`):** Controls layout optimization.
    - **`off` (Desktop):** Standard horizontal layout for title and subtitle.
    - **`on` (Mobile):** Optimizes for narrow screens. In SH3, it stacks the title and subtitle vertically.

### Content
- **Subtitle (`With`/`Without`):** Toggles the display of a subtitle.
- **Title Text:** The main heading text.
- **Subtitle Text:** Descriptive text displayed below the title.

## Design Tokens

### Typography
- **Title (SH1):** `nova/typography/heading/3` (18px SemiBold).
- **Title (SH2, SH3):** `nova/typography/body/strong` (16px SemiBold).
- **Subtitle:** `nova/typography/base/regular` (14px Regular), `nova/color/typography/muted`.
- **Color:** `nova/color/typography/base` for titles.

### Spacing
- **Gap (Title-Subtitle):** `nova/spacing/tight` (8px) for SH1/SH2, `nova/spacing/next` (4px) for SH3.
- **Buttons Container Gap:** `nova/spacing/next` (4px).

### Colors & Borders
- **Decorative Line (SH3):** 1px height, `nova/surfaces/color/workspace border` color.

## Layout Specifications

### Structure
- **Root Container:** A horizontal flex layout that fills the available width.
- **Title Area:** Contains the title and optional subtitle. The layout varies by hierarchy and mobile settings.
- **Decorative Line (SH3 only):** A full-width horizontal separator.
- **Buttons Container:** A slot for action buttons, positioned to the right.

### Hierarchy Layouts
- **SH1 & SH2:** Title and subtitle are arranged horizontally with an 8px gap.
- **SH3 (Desktop):** Title and subtitle are horizontal with a 4px gap, followed by a decorative line.
- **SH3 (Mobile):** Title and subtitle are stacked vertically with a 4px gap and a max-width of 260px.

### Text Overflow
- Both title and subtitle use ellipsis for overflow to maintain a single-line appearance.

## Accessibility
- **Semantic Structure:** Map the hierarchy levels to appropriate heading tags (`<h1>`, `<h2>`, etc.) to maintain a logical page structure.
- **Text Overflow:** Ensure full text is accessible to screen readers, for example, via tooltips or `aria-label`.
- **Focus Management:** All interactive elements (e.g., action buttons) must be keyboard accessible with visible focus indicators.