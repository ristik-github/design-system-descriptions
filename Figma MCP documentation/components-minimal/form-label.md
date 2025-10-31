# Form Label

## Overview

The Form Label is a text element that identifies and describes a form input field. It comes in three variants to indicate field requirements: Default, Required (with an asterisk), and Optional (with "optional" text).

---

## Component Properties

### Variants
- **Default**: A plain text label.
- **Required**: The label is followed by a red asterisk (`*`) to indicate a mandatory field.
- **Optional**: The label is followed by gray "optional" text.

---

## Design Tokens

### Typography
- **Label Text:** `nova/typography/body/regular` (16px)
- **Required Asterisk:** `nova/typography/base/strong` (14px)
- **Optional Text:** `nova/typography/supporting/regular` (12px)

### Colors
- **Label Text:** `nova/color/typography/base`
- **Required Asterisk:** `nova/color/critical/primary`
- **Optional Text:** `nova/color/typography/muted`

### Spacing
- **Gap between label and indicator:** 10px (for Required and Optional variants).

---

## Layout Specifications

- **Structure:** The Required and Optional variants use a horizontal flex layout to position the indicator next to the label text.
- **Spacing:** A 10px gap separates the label text from the indicator.
- **Alignment:** Content is vertically centered.

---

## Accessibility

### Label Association
- The label must be associated with its input field using the `for` attribute or by wrapping the input. This ensures screen readers announce the label when the input is focused.

### Requirement Indication
- **Required Fields:** In addition to the visual asterisk, the input element must have the `aria-required="true"` attribute for screen readers.
- **Optional Fields:** The "optional" text provides clear visual and audible context. No special ARIA attributes are needed.
