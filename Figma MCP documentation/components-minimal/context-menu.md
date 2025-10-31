# Context Menu

## Overview

The Context Menu is a floating overlay that displays a list of contextual actions. It supports sections, separators, selection states, and optional checkboxes.

---

## Component Properties

### Structure
- **Menu Items**: A vertical list of actions.
- **Sections**: Items can be grouped into sections.
- **Section Headers**: Optional labels for categorizing sections.
- **Separators**: 1px horizontal lines dividing sections.

### Menu Item Properties
- **States**: Default, Hover, Focus, Active.
- **Selection (`Selected=on/off`)**: Indicates if an item is selected.
- **Checkbox (`Checkbox=on/off`)**: Adds a checkbox for multi-select.

---

## Design Tokens

### Typography
- **Menu Item Label:** `nova/typography/base/regular` (14px)
- **Section Header:** `nova/typography/supporting/regular` (12px)

### Spacing
- **Padding/Gaps:** `nova/spacing/tight` (8px), `nova/spacing/next` (4px), `nova/spacing/slight` (2px)

### Colors
- **Menu Background:** `nova/link-option/color/background` (#ffffff)
- **Unselected Item Text:** `nova/link-option/color/neutral` (#151d1e)
- **Unselected Item Backgrounds:** `nova/link-option/color/accent` (Hover/Focus), `nova/link-option/color/tertiary` (Active)
- **Selected Item Background:** `nova/link-option/color/primary` (#14716d)
- **Selected Item Text/Icon:** `nova/color/static/white` (#ffffff)
- **Focus Ring:** `nova/color/focus` (#9ef1e4)
- **Section Header/Separator:** `nova/color/typography/muted`, `nova/color/divider`

### Border & Radius
- **Menu Container Radius:** `nova/radii/component/workspace` (12px)
- **Menu Item Radius:** `nova/spacing/next` (4px)

### Effects
- **Shadow:** Two-layer drop shadow on the menu container.

---

## Layout Specifications

### Structure
- **Menu Container:** Vertical flex column with `nova/spacing/tight` (8px) padding.
- **Menu Item:** Horizontal flex row with `nova/spacing/tight` (8px) padding and a minimum height of 32px.
- **Separator:** 1px height, full width.

### Dimensions
- **Menu Width:** Fixed (e.g., 167px), height adapts to content.
- **Checkbox Size:** 20px × 20px.
- **Selected Icon Size:** 20px × 20px.

---

## Interactive States

### Unselected Item
- **Default:** Transparent background.
- **Hover/Focus:** `nova/link-option/color/accent` background.
- **Active:** `nova/link-option/color/tertiary` background.
- **Focus:** Displays a 2px solid `nova/color/focus` border.

### Selected Item
- **All States:** `nova/link-option/color/primary` background with white text and a white checkmark icon.
- **Focus:** Also displays the focus ring.

---

## Accessibility

### Semantic Structure
- **Menu Container:** `role="menu"`
- **Menu Items:** `role="menuitem"`, `role="menuitemcheckbox"`, or `role="menuitemradio"`.
- **Separators:** `role="separator"`

### Keyboard Navigation
- **Arrow Keys:** Navigate between items.
- **Enter/Space:** Activate an item.
- **Escape:** Close the menu.
- Focus should be managed within the menu and return to the trigger on close.

### ARIA Attributes
- Use `aria-checked` for checkable items.
- Use `aria-activedescendant` on the menu container to indicate the focused item.
