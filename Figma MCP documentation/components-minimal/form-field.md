# Form Field

## Overview

The Form Field is a unified component combining a label and an input field. It supports various label variants, input states, and optional features like help text and icons, designed for single-line data entry.

---

## Component Properties

### Label Variants
- **Default**: Plain label text.
- **Required**: Label with a red asterisk (`*`) to indicate a mandatory field.
- **Optional**: Label with gray "optional" text.

### Input States
- **Default**: The standard resting state.
- **Hover**: When the cursor is over the input.
- **Focus**: When the input is active, indicated by a `nova/color/focus` ring.
- **Error**: When validation fails, indicated by a `nova/color/critical/primary` border.
- **Focus (Error)**: A combination of the Error and Focus states.
- **Disabled**: The non-interactive state.
- **Readonly**: Displays data that cannot be edited.

### Optional Features
- **Icon Display**: An optional icon on the right side of the input.
- **Help Text**: Guidance text displayed below the input.
- **Badge**: A visual indicator near the label (e.g., "New").
- **Tooltip**: An interactive element for detailed information.

---

## Design Tokens

### Typography
- **Label:** `nova/typography/body/regular` (16px)
- **Required Asterisk:** `nova/typography/base/strong` (14px)
- **Optional Text:** `nova/typography/supporting/regular` (12px)
- **Input Text/Placeholder:** `nova/typography/base/regular` (14px)

### Colors
- **Label Text:** `nova/color/typography/base`
- **Required Asterisk:** `nova/color/critical/primary`
- **Optional Text:** `nova/color/typography/muted`
- **Input Background:** `nova/input/color/background`
- **Input Border (Default):** `nova/input/color/accent`
- **Input Border (Error):** `nova/color/critical/primary`
- **Focus Ring:** `nova/color/focus`
- **Placeholder:** `nova/input/color/placeholder`
- **Disabled State:** `nova/input/color/disabled` (bg), `nova/color/typography/muted` (text)

### Spacing
- **Label-Input Gap:** `nova/spacing/tight` (8px)
- **Input Padding:** `nova/spacing/tight` (8px)

### Borders & Radii
- **Border Width:** `nova/border/basic` (1px)
- **Border Radius:** `nova/radii/component/input` (8px)

---

## Layout Specifications

- **Structure:** A vertical flex layout with the label row above the input field row.
- **Spacing:** `nova/spacing/tight` (8px) gap between the label and input.
- **Sizing:** The component fills the available container width.

---

## Accessibility

### Label Association
- The label must be associated with the input using `for` and `id` attributes.

### Keyboard Navigation
- The input must be focusable via `Tab`.
- A visible focus ring is required.

### ARIA Attributes
- **Required:** `aria-required="true"`
- **Error:** `aria-invalid="true"` and `aria-describedby` to link to an error message.
- **Disabled:** `disabled` attribute.
- **Readonly:** `readonly` attribute.
- Help text should be linked via `aria-describedby`.
