# Badge

## Overview

The Badge is a compact visual indicator for labels, counts, or statuses, available in various color-coded states, types, and sizes.

---

## Component Properties

### Variants

#### Type
- **Tag**: Rectangular badge with a `nova/radii/component/badge` (4px) radius.
- **Count**: Pill-shaped badge with a more rounded (9px) radius.

#### State
- **Neutral**: For general-purpose labels.
- **Critical**: For critical issues or errors.
- **Severe**: For severe issues or high-risk items.
- **Warning**: For potential issues or items needing attention.
- **Success**: For successful completion or positive status.
- **Information**: For informational context.
- **Feature**: For highlighting new features or promotions.

#### Size
- **Small**: Compact size for dense layouts.
- **Medium**: Larger size for better readability.

#### Show Icon (boolean)
- Displays an optional icon before the label text.

---

## Visual Specifications

### Container
- **Structure:** Flex row, items centered.
- **Sizing:** Hugs content width and height.
- **Border:** `nova/border/basic` (1px) solid.

### Sizing and Padding
- **Small:**
  - **Padding:** `nova/spacing/next` (4px) horizontal, `nova/spacing/slight` (2px) vertical.
  - **Gap (with icon):** `nova/spacing/next` (4px).
- **Medium:**
  - **Padding:** `nova/spacing/tight` (8px) horizontal, `nova/spacing/next` (4px) vertical.
  - **Gap (with icon):** `nova/spacing/next` (4px).

### Typography
- **Font:** `nova/typography/supporting/regular` (12px Regular, 120% line height) for all variants.

---

## Color Specifications by State

Each state has a specific color set for background, border, and text.

- **Neutral**: `nova/color/neutral/secondary` (bg), `nova/color/neutral/primary` (border), `nova/color/neutral/dark` (text).
- **Critical**: `nova/color/critical/secondary` (bg), `nova/color/critical/primary` (border), `nova/color/critical/accent` (text).
- **Severe**: `nova/color/severe/secondary` (bg), `nova/color/severe/primary` (border), `nova/color/severe/dark` (text).
- **Warning**: `nova/color/warning/secondary` (bg), `nova/color/warning/primary` (border), `nova/color/warning/dark` (text).
- **Success**: `nova/color/success/secondary` (bg), `nova/color/success/primary` (border), `nova/color/brand/dark` (text).
- **Information**: `nova/color/informative/secondary` (bg), `nova/color/informative/primary` (border), `nova/color/informative/dark` (text).
- **Feature**: `nova/color/feature/secondary` (bg), `nova/color/feature/primary` (border), `nova/color/feature/dark` (text).

---

## Design Tokens

### Typography
- `nova/typography/supporting/regular`

### Spacing
- `nova/spacing/next`
- `nova/spacing/slight`
- `nova/spacing/tight`

### Border & Radius
- `nova/border/basic`
- `nova/radii/component/badge` (for Tag type)

---

## Accessibility

- Badges are typically non-interactive; use a `<span>`.
- If a badge's meaning isn't clear from its text, use `aria-label` to provide context (e.g., `aria-label="3 unread messages"` for a "3" badge).
- For dynamic badges (like notification counts), consider using `role="status"` and `aria-live="polite"`.
- Text should convey meaning, as color should not be the only indicator.
