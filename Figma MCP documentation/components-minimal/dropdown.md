# Dropdown

## Overview

The Dropdown is a form input for selecting one or multiple options from a list. It includes a label, an input field, and an expandable menu. It supports single and multi-select modes, with selected items displayed as removable chips.

---

## Component Properties

### States
- **Dropdown Off**: The menu is collapsed.
- **Dropdown On**: The menu is expanded and visible.
- **Dropdown Focused**: The trigger has keyboard focus, indicated by a focus ring.

### Filled State
- **Filled Off**: No selection is made; a placeholder is shown.
- **Filled On**: Selections are displayed as chips in the input field.

### Multi-Select Mode
- **Multi-Select Off (Single-select)**: Only one option can be selected.
- **Multi-Select On**: Multiple options can be selected, each appearing as a chip. Options in the menu have checkboxes.

---

## Visual Specifications

### Input Field
- **Border:** 1px solid, `nova/input/color/accent` (closed), `nova/input/color/secondary` (open).
- **Border Radius:** `nova/radii/component/input` (8px).
- **Padding:** `nova/spacing/tight` (8px).
- **Min Height:** 36px.
- **Focus Ring:** 2px solid `nova/color/focus` (#9ef1e4).

### Dropdown Menu
- **Layout:** Absolutely positioned below the input, full width.
- **Max Height:** 372px (scrollable).
- **Background:** `nova/input/color/background` (#ffffff).
- **Shadow:** `0px 8px 24px 0px rgba(0,0,0,0.13)`.
- **Padding:** `nova/spacing/tight` (8px).

### Dropdown Options
- **Min Height:** 32px.
- **Padding:** `nova/spacing/tight` (8px).
- **Gap between options:** `nova/spacing/next` (4px).
- **Hover/Focus Background:** `nova/link-option/color/accent` (#e9f7f5).
- **Multi-select Selected Background:** `nova/link-option/color/secondary` (#148d87) with `nova/color/static/white` text.

### Chips (Filled On)
- **Background:** `nova/color/neutral/secondary` (#f6fafa).
- **Border:** 1px solid `nova/color/neutral/primary` (#889192).
- **Padding:** 8px left, 4px right, 4px vertical.
- **Gap between chips:** 6px.
- Includes a close icon to remove the selection.

---

## Design Tokens

### Typography
- **Label:** `nova/typography/body/regular` (16px)
- **Input/Placeholder/Option Text:** `nova/typography/base/regular` (14px)
- **Chip Text:** 12px Regular

### Colors
- **Input:** `nova/input/color/background`, `nova/input/color/accent`, `nova/input/color/secondary`
- **Focus:** `nova/color/focus`
- **Placeholder:** `nova/input/color/placeholder`
- **Option Hover/Selected:** `nova/link-option/color/accent`, `nova/link-option/color/secondary`
- **Chips:** `nova/color/neutral/secondary`, `nova/color/neutral/primary`

### Spacing
- `nova/spacing/tight`, `nova/spacing/next`

### Borders & Radii
- `nova/radii/component/input`, `nova/radii/softened`, `nova/radii/component/checkbox`

---

## Accessibility

### Keyboard Navigation
- **Tab:** Moves focus to/from the dropdown trigger.
- **Space/Enter:** Opens/closes the menu and selects options.
- **Arrow Keys:** Navigate options when the menu is open.
- **Escape:** Closes the menu.

### ARIA Attributes
- **Input:** `role="combobox"`, `aria-expanded`, `aria-haspopup="listbox"`, `aria-labelledby`, `aria-controls`.
- **Menu:** `role="listbox"` (with `aria-multiselectable="true"` for multi-select).
- **Options:** `role="option"`, `aria-selected`.
- **Chips:** Close buttons should have an `aria-label` (e.g., "Remove [option name]").
