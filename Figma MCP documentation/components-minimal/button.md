# Button

## Overview

The Button component is a foundational interactive element for triggering actions, submitting forms, or navigating. It comes in multiple variants, sizes, colors, and states.

---

## Component Properties

### Variants
- **Primary**: For the main call-to-action. High visual weight.
- **Secondary**: For important but not primary supporting actions. Medium visual weight.
- **Tertiary**: For less prominent, auxiliary functions. Low visual weight.

### Sizes
- **Small**: 28px height. For compact layouts.
- **Large**: 36px height. For prominent actions.

### Color Variants
- **Default**: For general actions.
- **Destructive**: For dangerous or irreversible actions (e.g., delete).

### States
- **Default**: The resting state.
- **Hover**: On mouse-over.
- **Focus**: When focused via keyboard, displays a focus ring (`nova/color/focus`).
- **Pressed**: While being clicked.
- **Loading**: Indicates an in-progress action, becomes non-interactive.
- **Disabled**: Non-interactive state.

---

## Design Tokens

### Typography
- **Font:** `nova/typography/instructional/regular` (14px)

### Spacing
- **Small Size Padding:** `nova/spacing/tight` (horizontal), `nova/spacing/next` (vertical).
- **Large Size Padding:** `nova/spacing/close` (horizontal), `nova/spacing/tight` (vertical).
- **Internal Gap:** `nova/spacing/next`.

### Border & Radius
- **Radius:** `nova/radii/component/button`
- **Width:** `nova/border/basic`

### Colors

#### Primary Variant
- **Default/Destructive Backgrounds:** `primary`, `secondary`, `tertiary` color tokens for default, hover, pressed states.
- **Text:** `neutral` color token.

#### Secondary Variant
- **Default/Destructive Backgrounds:** `neutral` for default/hover, `tertiary` for pressed.
- **Borders:** `primary` for default/pressed, `secondary` for hover.
- **Text:** `primary` for default/pressed, `secondary` for hover.

#### Tertiary Variant
- **Default/Destructive Backgrounds:** `neutral` (transparent) for default/hover, `tertiary` for pressed.
- **Borders:** None for default, `secondary` for hover, `primary` for pressed.
- **Text:** `primary` for default/pressed, `secondary` for hover.

#### Disabled State
- Uses `nova/color/skeleton/secondary` for backgrounds, borders, or text depending on the variant.

---

## Layout Specifications

### Structure
- Text is centered horizontally and vertically.
- Uses flexbox for content alignment.

### Dimensions
- **Small:** 28px height, min-width 59px.
- **Large:** 36px height, min-width 67px.
- Width adjusts to content.

---

## Accessibility

### Keyboard Navigation
- Must be focusable via `Tab`.
- Activates with `Enter` or `Space`.
- A visible focus ring is required.

### Screen Readers
- Button text must be descriptive.
- Use `aria-label` for icon-only buttons.
- Announce loading and disabled states.

### ARIA Attributes
- **Loading:** `aria-busy="true"`.
- **Disabled:** `disabled` attribute.
