# Text Input Component

## Overview
The Text Input component is a standard input field for single-line text entry. It supports multiple interactive states, optional icons, and provides visual feedback for different conditions like focus, error, and disabled states.

## Component Properties

### States
- **Default:** The resting state.
- **Hover:** When the cursor is over the input.
- **Focus:** When the input is selected, indicated by a prominent focus ring.
- **Error:** When validation fails, indicated by a colored border.
- **Focus (Error):** A combination of the focus and error states.
- **Disabled:** The input is not interactive.
- **Readonly:** The input displays data but cannot be edited.

### Filled Status
- **Filled Off (Empty):** Displays placeholder text with `nova/input/color/placeholder` color.
- **Filled On (Has Content):** Displays user-entered text with `nova/color/typography/base` color.

### Optional Elements
- **Icon Display:** An optional icon on the right side (e.g., for a dropdown or search).
- **Clear Button:** An optional close icon to clear the input's value.

## Design Tokens

### Typography
- **Font:** `nova/typography/base/regular` (14px).

### Colors
- **Text:** `nova/color/typography/base` (filled), `nova/input/color/placeholder` (placeholder).
- **Background:** `nova/input/color/background`.
- **Border:** `nova/input/color/accent` (default), `nova/color/critical/primary` (error).
- **Focus Ring:** `nova/color/focus`.
- **Disabled:** `nova/input/color/disabled` (bg), `nova/color/typography/muted` (text).
- **Icon:** `nova/input/color/secondary`.

### Spacing
- **Internal Padding:** `nova/spacing/tight` (8px).
- **Gap to Icon:** `nova/spacing/next` (4px).

### Border & Radius
- **Border Radius:** `nova/radii/component/input`.
- **Border Width:** `nova/border/basic` (default), 2px (focus/error).

## State-Specific Styling
- **Default:** `nova/input/color/accent` border.
- **Focus:** 2px border using `nova/color/focus`.
- **Error:** `nova/color/critical/primary` border color.
- **Disabled:** `nova/input/color/disabled` background and `nova/color/typography/muted` text color.
- **Readonly (Empty):** Displays a hyphen "-" as the placeholder.

## Layout Specifications
- **Height:** 36px.
- **Width:** Flexible, stretches to fit its container.
- **Padding:** `nova/spacing/tight` (8px) on all sides.
- **Icon:** 20x20px, positioned on the right.

## Accessibility
- **Label:** Must have an associated `<label>` or `aria-label`.
- **Error State:** Use `aria-invalid="true"` and `aria-describedby` to link to an error message.
- **Disabled/Readonly:** Use the `disabled` and `readonly` HTML attributes.
- **Focus:** The focus state must be clearly visible.