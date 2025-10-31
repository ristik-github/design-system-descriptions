# Tile (Card)

## Overview
The Tile (Card) component is a versatile container for displaying grouped information in a structured format. It supports multiple visual styles and padding configurations to suit different layout needs.

## Component Properties

### Variants
- **Type:**
    - **Boxed:** A fully enclosed card with a border and background for maximum visual separation.
    - **With Divider:** A card with only a bottom border, suitable for stacked lists.
- **Padding:**
    - **close:** Standard padding of `nova/spacing/close` (12px).
    - **none:** No horizontal padding, reduced vertical padding (only available for "With Divider" type).

## Component Structure
The component is composed of:
1.  **Container:** The outer wrapper providing border, background, and spacing.
2.  **Tile (Card) Title:** The header section with a title and an optional action button.
3.  **Card Content:** A flexible area for description text, label-value pairs, or other custom content.

## Visual Specifications

### Type=Boxed, Padding=close
- **Container:** `nova/surfaces/color/workspace` background, `nova/border/basic` border, `nova/radii/component/workspace` (12px) radius, and `nova/spacing/close` (12px) padding.
- **Title Text:** `nova/typography/body/strong` (16px SemiBold). Can be a link (`nova/color/typography/link`).
- **Action Button:** Optional 28x28px icon button.
- **Description Text:** `nova/typography/body/regular` (16px Regular).
- **Label-Value Pairs:**
    - **Label:** `nova/typography/base/regular` (14px Regular), `nova/color/typography/muted`.
    - **Value:** `nova/typography/body/regular` (16px Regular), `nova/color/typography/base`.

### Type=With Divider, Padding=close
- **Container:** Transparent background, bottom border only, `nova/spacing/close` (12px) padding. Other specs are the same as the Boxed variant.

### Type=With Divider, Padding=none
- **Container:** Transparent background, bottom border only, no horizontal padding, and `nova/spacing/close` (12px) bottom padding.

## Design Tokens

### Typography
- **Title:** `nova/typography/body/strong`
- **Description/Value:** `nova/typography/body/regular`
- **Label:** `nova/typography/base/regular`

### Colors
- **Background (Boxed):** `nova/surfaces/color/workspace`
- **Border:** `nova/surfaces/color/workspace-border`
- **Text:** `nova/color/typography/base` (primary), `nova/color/typography/muted` (secondary), `nova/color/typography/link` (links).

### Spacing
- **Padding:** `nova/spacing/close` (12px)
- **Internal Gaps:** `nova/spacing/tight` (8px)

### Border Radius
- **Container (Boxed):** `nova/radii/component/workspace` (12px)
- **Action Button:** `nova/radii/component/button` (8px)

## Accessibility
- **Semantic HTML:** Use `<article>` for the card, `<h3>` or `<h4>` for the title, and `<button>` for actions. Consider `<dl>` for label-value pairs.
- **ARIA:** Use `aria-label` for icon buttons (e.g., "More options").
- **Keyboard Navigation:** Ensure all interactive elements (links, buttons) are focusable and can be activated with a keyboard.