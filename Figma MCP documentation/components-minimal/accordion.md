# Accordion

## Overview

The Accordion component is a collapsible container for organizing content into expandable sections. It consists of a header and a content area that is revealed when expanded.

---

## Component Properties

### Variants

#### Open State (on/off)
Controls the visibility of the accordion's content area.

---

### Header Elements

#### Title
The main heading text in the accordion header.

#### Subtext (optional)
Optional descriptive text below the title.

#### Left Icon (optional)
An optional icon displayed to the left of the title.

#### Expandable Indicator
The chevron icon indicating expand/collapse functionality.

#### Actions Area
A container for the expandable icon and optional custom action buttons.

#### Custom Action Buttons (optional)
Up to two optional icon buttons in the header's actions area.

---

### Interactive States

#### Is Button (on/off)
Determines if the header is interactive with hover, focus, and pressed states.

#### Hover (on/off)
Visual state on mouse hover (if `isButton` is `on`).

#### Focus (on/off)
Visual state on keyboard focus (if `isButton` is `on`).

#### Pressed (on/off)
Visual state when the header is clicked (if `isButton` is `on`).

---

## Visual Specifications

### Accordion Container
- **Structure:** Flex column.
- **Border:** `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6).
- **Border Radius:** `nova/radii/component/accordion` (12px).
- **Sizing:** Full width, hugs content height.

### Accordion Header
- **Structure:** Flex row, items centered.
- **Sizing:** Full width, hugs content height.
- **Padding:** `nova/spacing/close` (12px) vertical, `nova/spacing/near` (16px) horizontal.
- **Gap:** `nova/spacing/tight` (8px) between title and actions.
- **Background:** `nova/drawer/color/background` (#ffffff).
- **Border:** `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6).
- **Border Radius:** 
    - **Open:** `nova/radii/component/accordion` (12px) on top corners.
    - **Closed:** `nova/radii/component/accordion` (12px) on all corners.

#### Header Content
- **Title Typography:** `nova/typography/body/strong` (16px SemiBold), color `nova/color/typography/base` (#151d1e).
- **Subtext Typography:** `nova/typography/base/regular` (14px Regular), color `nova/color/typography/muted` (rgba(0,0,0,0.62)).
- **Expandable Icon Button:** 36px × 36px container with `nova/radii/component/button` (8px) radius. Icon is 20px × 20px.

### Accordion Content Section
- **Structure:** Flex row, items aligned to start.
- **Visibility:** Shown when accordion is open.
- **Padding:** `nova/spacing/near` (16px) on all sides.
- **Gap:** `nova/spacing/near` (16px) between child elements.
- **Background:** `nova/surfaces/color/workspace` (#ffffff).
- **Border:** `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6) on sides and bottom (no top border).
- **Border Radius:** `nova/radii/gentle` (12px) on bottom corners.
- **Sizing:** Full width, hugs content height.

---

## Design Tokens

### Typography
- **Header Title:** `nova/typography/body/strong`
- **Header Subtext:** `nova/typography/base/regular`
- **Content Labels:** `nova/typography/supporting/regular`
- **Content Text:** `nova/typography/base/regular`

### Spacing
- **Header Padding:** `nova/spacing/close` (vertical), `nova/spacing/near` (horizontal)
- **Content Padding:** `nova/spacing/near`
- **Gaps:** `nova/spacing/tight` (header actions), `nova/spacing/near` (content items)

### Colors
- **Header Title:** `nova/color/typography/base`
- **Header Subtext:** `nova/color/typography/muted`
- **Backgrounds:** `nova/drawer/color/background` (Header), `nova/surfaces/color/workspace` (Content)
- **Border:** `nova/surfaces/color/workspace-border`

### Border & Radius
- **Border Width:** `nova/border/basic`
- **Radius:** `nova/radii/component/accordion`, `nova/radii/gentle` (Content bottom), `nova/radii/component/button` (Icon button)

---

## Accessibility

### ARIA Attributes
- **Header Button (`isButton="on"`):**
  - `role="button"`
  - `aria-expanded`: "true" or "false" based on open state.
  - `aria-controls`: ID of the content section.
- **Content Section:**
  - `id`: Unique ID referenced by `aria-controls`.
  - `role="region"`
  - `aria-labelledby`: ID of the header title.

### Keyboard Navigation
- **Tab:** Focuses the header button.
- **Enter/Space:** Toggles the accordion's open/close state.
- A visible focus indicator should be present on the header button.
