# Checkbox

## Overview

The Checkbox is a form input for toggling between checked and unchecked states. It supports default, hover, focus, disabled, and indeterminate states.

---

## Component Properties

### States
- **Default**: The standard, resting state.
- **Hover**: When the mouse is over the checkbox.
- **Focus**: When the checkbox has keyboard focus.
- **Disabled**: The non-interactive state.

### Selection
- **Unchecked (`Selected=off`)**: The checkbox is empty.
- **Checked (`Selected=on`)**: The checkbox displays a checkmark.
- **Indeterminate (`Indeterminate=on`)**: The checkbox displays a dash, indicating a partial selection (e.g., in a tree structure).

---

## Visual Specifications

### Base
- **Container Size:** 20px × 20px
- **Border Radius:** `nova/radii/component/checkbox` (4px)
- **Icon Size:** 16px × 16px, centered.
- **Icon Color:** `nova/color/static/white` (#ffffff)
- **Focus Indicator:** 2px solid `nova/color/focus` (#9ef1e4) overlay.

### Unchecked States
- **Border:** 1px solid.
- **Background:** `nova/input/color/background` (#ffffff).
- **Border Colors:**
  - **Default:** `nova/input/color/accent` (#c1cacb)
  - **Hover/Focus:** `nova/input/color/secondary` (#889192)
  - **Disabled:** `nova/color/skeleton/secondary` (#c1cacb)
- **Disabled Background:** `nova/color/skeleton/primary` (#e0e6e6)

### Checked & Indeterminate States
- **Border:** None.
- **Icon:** Checkmark (for checked) or dash (for indeterminate).
- **Background Colors:**
  - **Default:** `nova/input/color/highlight1` (#185956)
  - **Hover/Focus:** `nova/input/color/highlight2` (#148d87)
  - **Disabled:** `nova/color/skeleton/secondary` (#c1cacb)

---

## Design Tokens

### Colors
- **Unchecked Background:** `nova/input/color/background`
- **Unchecked Border:** `nova/input/color/accent`, `nova/input/color/secondary`
- **Checked Background:** `nova/input/color/highlight1`, `nova/input/color/highlight2`
- **Focus Ring:** `nova/color/focus`
- **Icon:** `nova/color/static/white`
- **Disabled:** `nova/color/skeleton/primary`, `nova/color/skeleton/secondary`

### Border & Radius
- `nova/radii/component/checkbox`

---

## Accessibility

### Semantic HTML
- Use `<input type="checkbox">` with a unique `id`.
- Associate with a `<label for="[id]">`.

### State Attributes
- Use the `checked` attribute for selected state.
- Use the `disabled` attribute for disabled state.
- Set the `indeterminate` property via JavaScript for the indeterminate state.
- Use `required`, `aria-required`, `aria-invalid`, and `aria-describedby` for form validation.

### Keyboard Navigation
- **Tab:** Focuses the checkbox.
- **Space:** Toggles the checked/unchecked state.
- A visible focus indicator is required.

### Screen Readers
- Announce the label, role, and state (checked, not checked, or mixed).
- Use `aria-checked="mixed"` for the indeterminate state.
