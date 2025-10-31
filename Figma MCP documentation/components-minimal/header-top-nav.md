# Header Top Nav

## Overview

The Header Top Nav is a comprehensive application-level navigation component providing primary and secondary navigation, branding, search, and global actions. It supports multiple layouts for different screen sizes.

---

## Component Properties

### Variants
- **Width**: `Large` (desktop, ≥1280px) or `Medium` (tablet, 640px-1279px).
- **Layout**: `Legacy=off` (modern, integrated) or `Legacy=on` (classic, separate rows).
- **Navigation**: `Vertical Nav=off` (horizontal) or `Vertical Nav=on` (hamburger menu).
- **Optional Elements**: `Show Secondary Navigation`, `Show Header Icons`, `Show Context`, `Show Help`.

---

## Visual Specifications (Large Desktop Default)

### Primary Navigation Bar
- **Background:** `nova/navigation/primary` (#0f4146)
- **Height:** 52px
- **Padding:** `nova/spacing/tight` (8px) vertical, `nova/spacing/close` (12px) horizontal.
- **Margin:** `nova/spacing/tight` (8px) on all sides from page edges. When used in combination with Vertical navigation the total spacing between neighboring components should be `nova/spacing/tight` (8px)

### Branding & Navigation
- **Logo & Product Name:** "Product Name" (`nova/typography/base/strong`, white text).
- **Context Tag:** Optional tag with `nova/radii/relaxed` (16px) radius.
- **Nav Items:**
  - **Active:** `global/color/pale-green/150` background, `global/color/green/900` text.
  - **Hover:** `global/color/muted-teal/700` background, white text.
  - **Focus:** Visible focus ring with `nova/color/focus` (#9ef1e4).
  - **Default:** White text.
  - **Typography:** `nova/typography/base/regular` (14px).

### Actions
- **Search Box:** 160px width, `global/color/muted-teal/700` background.
- **Global Actions (Help & Avatar):**
  - **Container:** Pill-shaped (`nova/radii/full`), `global/color/muted-teal/700` background.
  - **Icons:** 24px × 24px, white.

### Secondary Navigation (Optional)
- **Background:** `global/color/pale-green/150` (#e7f4eb).
- **Border:** 1px bottom/sides, `global/color/pale-green/200`.
- **Active Item:** `global/color/muted-teal/800` background, `global/color/pale-green/150` text.
- **Hover Item:** `global/color/pale-green/200` background.
- **Default Item:** `global/color/green/900` text.

---

## Interactive States

### State Transitions
- **Primary Nav Item:** The background transitions from transparent to `global/color/muted-teal/700` on hover, and then to `global/color/pale-green/150` when active. Text color changes accordingly for contrast.
- **Secondary Nav Item:** The background transitions to `global/color/pale-green/200` on hover, and `global/color/muted-teal/800` when active.
- **Animation:** State transitions use a `150ms ease-out` duration.

---

## Design Tokens

### Typography
- `nova/typography/base/strong` (14px SemiBold)
- `nova/typography/base/regular` (14px Regular)
- `nova/typography/supporting/regular` (12px Regular)

### Colors
- **Primary Nav:** `nova/navigation/primary`, `global/color/muted-teal/700`
- **Secondary Nav:** `global/color/pale-green/150`, `global/color/pale-green/200`
- **Text:** `nova/color/static/white`, `global/color/green/900`

### Spacing
- `nova/spacing/tight` (8px), `nova/spacing/close` (12px)

### Borders & Radii
- `nova/radii/component/button` (8px), `nova/radii/component/header` (12px), `nova/radii/full` (36px)

---

## Layout Specifications

- **Structure:** A primary navigation bar (52px height) with an optional secondary navigation row below it.
- **Margin System:** `nova/spacing/tight` (8px) margin on all sides from the page edges.
- **Responsive:** The layout condenses for medium widths, with navigation items overflowing into a scrollable area.

---

## Accessibility

### Keyboard Navigation
- All interactive elements (logo, nav items, search, icons) must be focusable via `Tab`.
- Use arrow keys to navigate between navigation items.

### ARIA Attributes
- `role="navigation"` for the main container.
- `aria-current="page"` for the active navigation item.
- `aria-label` for all icon-only buttons and the search input.
- `aria-expanded` for the hamburger menu in vertical navigation mode.
