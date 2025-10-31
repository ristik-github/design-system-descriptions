# Icon Button Component

## Overview
The Icon Button component is a compact, icon-only interactive element used to trigger actions in a space-efficient manner. It provides visual feedback through multiple states and can be configured with different levels of visual prominence through the Subtle variant. The component supports a selected state for toggle-like behavior and includes optional tooltip functionality.

## Component Properties

### Visual Variants
- **Subtle Off (Standard):** Default prominence with visible borders.
- **Subtle On (Low Prominence):** Subdued appearance for blending into the interface.

### Sizes
- **Small:** 28x28px total size, 20x20px icon size, 6px padding.
- **Large:** 36x36px total size, 20x20px icon size, 6px padding.

### Selection State
- **Selected Off:** Default state, not active.
- **Selected On:** Indicates the button is active, with a distinct background color.

### States
- **Default:** Resting state.
- **Hover:** Cursor is over the button.
- **Focus:** Button has keyboard focus, indicated by a focus ring.
- **Pressed:** Button is being actively clicked.
- **Active:** Represents an active mode in the application.
- **Loading:** Asynchronous action is in progress, shows a skeleton loader.
- **Disabled:** Button is not interactive.

## Design Tokens

### Typography (Tooltip)
- **Font:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`

### Spacing
- **Padding (all sizes):** 6px (all sides)
- **Tooltip Padding Horizontal:** `semantic/spacing/tight`
- **Tooltip Padding Vertical:** `semantic/spacing/next`

### Border & Radius
- **Button Border Radius:** `nova/radii/component/button`
- **Tooltip Border Radius:** `semantic/radii/softened` (Subtle Off), `semantic/radii/regular` (Subtle On)

### Colors
- **Border:** `nova/icon-button/color/border`, `nova/icon-button/color/border-muted`
- **Icon:** `nova/color/typography/base`
- **Background/States:** `nova/icon-button/color/accent`, `global/color/alpha-dark-blue/400` (hover), `global/color/alpha-dark-blue/500` (pressed), `global/color/dark-blue/700` (selected)
- **Focus:** `nova/color/focus`
- **Disabled:** `nova/color/skeleton/primary`, `nova/color/skeleton/secondary`
- **Tooltip:** `nova/tooltip/color/background`, `nova/tooltip/color/foreground`

## Tooltip Feature
- **Position:** Below the button, centered.
- **Max Width:** 350px.
- **Shadow:** `0px 2px 4px 0px rgba(0,0,0,0.13)`

## Accessibility
- **Keyboard Navigation:** Must be focusable with a visible focus ring (`nova/color/focus`). Activated by Enter or Space.
- **Screen Readers:** Requires `aria-label` for description.
- **ARIA Attributes:**
    - `aria-pressed="true"` for selected toggle buttons.
    - `aria-busy="true"` for loading state.
    - `disabled` attribute for disabled state.

## Layout Specifications
- **Icon Size:** 20x20px for both Small and Large sizes.
- **Centering:** Icon is centered using flexbox.
- **Focus Ring:** 1px border, positioned -1px outside the button.
- **Box Sizing:** `border-box`.
