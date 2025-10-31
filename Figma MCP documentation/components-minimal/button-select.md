# Button Select

## Overview

The Button Select component is a selectable option button used in groups for single or multiple choices. It comes in a compact single-line layout and an expanded layout with a description.

---

## Component Properties

### Layouts

#### Single Line (No Description)
- **Height:** 36px
- **Typography:** `nova/typography/instructional/regular` (14px Regular)
- **Padding:** 12px

#### With Description
- **Height:** 64px
- **Label Typography:** `nova/typography/body/strong` (16px SemiBold)
- **Description Typography:** `nova/typography/instructional/regular` (14px Regular)
- **Gap:** 4px between label and description
- **Padding:** 12px

---

## States

### Default (Unselected)
- **Background:** `#FFFFFF`
- **Border:** 1px solid `nova/surfaces/color/workspace-border` (#E0E6E6)
- **Text Color:** `nova/color/typography/base` (#151D1E)

### Hover
- **Background:** `global/color/grey/200` (#EFF3F3)
- **Border:** Unchanged

### Selected
- **Background:** `global/color/alpha-dark-blue/400` (rgba(96, 177, 250, 0.27))
- **Border:** 1px solid `global/color/dark-blue/700` (#1F4CB3)
- **Single-line Text:** Becomes `nova/typography/instructional/strong` (SemiBold)

### Selected + Hover
- **Background:** `global/color/alpha-dark-blue/500` (rgba(51, 139, 245, 0.41))
- **Border:** Unchanged from Selected state

### Focus
- **Focus Ring:** 2px solid `nova/color/focus` (#9EF1E4), inset -2px.
- Background matches the current state (Default or Selected).

### Disabled
- **Unselected + Disabled:**
  - **Background:** `nova/input/color/disabled` (#EFF3F3)
  - **Border:** None
  - **Text Color:** `nova/color/typography/muted` (rgba(0, 0, 0, 0.62))
- **Selected + Disabled:**
  - **Background:** `nova/input/color/disabled` (#EFF3F3)
  - **Border:** 1px solid `nova/color/typography/muted`
  - **Text Color:** `nova/color/typography/base` (not muted)

---

## Design Tokens

### Colors
- **Backgrounds:** `global/color/neutral/white`, `global/color/grey/200`, `global/color/alpha-dark-blue/400`, `global/color/alpha-dark-blue/500`, `nova/input/color/disabled`
- **Borders:** `nova/surfaces/color/workspace-border`, `global/color/dark-blue/700`
- **Text:** `nova/color/typography/base`, `nova/color/typography/muted`
- **Focus:** `nova/color/focus`

### Typography
- **Single-line:** `nova/typography/instructional/regular`, `nova/typography/instructional/strong`
- **With Description:** `nova/typography/body/strong` (Label), `nova/typography/instructional/regular` (Description)

### Spacing & Borders
- **Padding:** `nova/spacing/close` (12px)
- **Border Radius:** `nova/radii/component/button` (8px)
- **Border Width:** 1px

---

## Accessibility

### Keyboard Navigation
- Must be focusable via `Tab`.
- `Enter` or `Space` toggles selection.
- A visible focus ring is required.

### Screen Readers
- Announce the label, state (selected/not selected), and description if present.
- Use `aria-describedby` to link the description to the button.
