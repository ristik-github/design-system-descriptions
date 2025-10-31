# Vertical Navigation

## Overview
The Vertical Navigation component is a sidebar navigation system for application-level navigation, serving as an alternative to horizontal main navigation. It supports up to three levels of hierarchy and provides clear visual indicators for the selected item.

## Component Structure
1.  **Navigation Container:** The main sidebar frame.
2.  **Navigation List Items:** Clickable links with support for hierarchical levels.

## Visual Specifications

### Navigation Container
- **Width:** 256px.
- **Height:** Full available viewport height, with margins.
- **Layout:** Vertical flex column with `nova/spacing/slight` (2px) gap between items.
- **Padding:** `nova/spacing/tight` (8px) horizontal, `nova/spacing/near` (16px) vertical.
- **Appearance:** `nova/navigation/secondary` background, `nova/border/basic` border, and `nova/radii/softened` (8px) border-radius.
- **Spacing** `nova/spacing/tight` all around. The gap between neighboring components should be 8px. If the Vertical navigation have margins the ohter neighboring components should not have one.

### Navigation List Items
- **Height:** 45px.
- **Layout:** Horizontal flex, content centered.
- **Typography:** `nova/typography/base/regular` (14px).
- **Icon Size:** 20x20px.

#### Hierarchy Levels
- **Child=0 (Top Level):** No indentation.
- **Child=1 (Second Level):** 16px left indent.
- **Child=2 (Third Level):** 32px left indent.

#### Selection States
- **Unselected:** Transparent background, `nova/navigation/primary` text color.
- **Selected:** `global/color/neutral/white` background with a `nova/border/basic` border, creating an elevated appearance.

## Design Tokens

### Colors
- **Text:** `nova/navigation/primary` (#0f4146).
- **Background:** `nova/navigation/secondary` (#eff3f3).
- **Selected Background:** `global/color/neutral/white` (#ffffff).
- **Borders:** `nova/surfaces/color/workspace-border` (#e0e6e6).

### Typography
- **Labels:** `nova/typography/base/regular` (14px Regular).

### Spacing
- **Item Gap:** `nova/spacing/slight` (2px).
- **Item Padding:** `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical.
- **Container Padding:** `nova/spacing/tight` (8px) horizontal, `nova/spacing/near` (16px) vertical.

### Border Radius
- **Container & Items:** `nova/radii/softened` (8px).

## Interaction Guidelines
- **Selection:** Only one item can be selected at a time. Clicking an item selects it and deselects the previous one.
- **Hierarchy:** Child items are visually indented. Parent items can have expand/collapse indicators.
- **Hover & Focus:** Implement subtle background changes on hover and visible focus indicators for keyboard navigation.

## Accessibility
- **Semantic HTML:** Use `<nav>`, `<ul>`, and `<li>` for structure. Links should be `<a>` elements.
- **ARIA:** Use `role="navigation"`, `aria-current="page"` for the selected item, and `aria-expanded` for hierarchical menus.
- **Keyboard Navigation:** Support Tab for focus, Enter/Space for activation, and arrow keys for navigating between items.

## Integration
- **Hamburger Menu:** A hamburger menu in the top bar can be used to show/hide the vertical navigation.
- **Top Bar:** When using vertical navigation, the top bar should be modified to remove main navigation links and add the hamburger toggle.
- **Page Titles:** Page titles should have a `sticky` position to remain visible at the top of the viewport as the content scrolls.