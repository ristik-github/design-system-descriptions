# Form File Upload

## Overview

The Form File Upload component is a drag-and-drop area for uploading files. It supports multiple states, including default, hover, focus, pressed, error, and loading, and provides guidance on file types and size limits.

---

## Component Properties

### States
- **Default**: The initial resting state, ready to accept files.
- **Hover**: When the cursor is over the upload area.
- **Focus**: When the component has keyboard focus, indicated by a `nova/color/focus` ring.
- **Pressed**: When the area is being clicked or a file is dragged over it.
- **Error**: When file validation fails, displaying an error message below.
- **Loading**: When a file is uploading, showing a spinner and dimming the content.

### Optional Elements
- **Helper Text**: Provides guidance on file size limits and accepted types.

---

## Visual Specifications

### Upload Area
- **Border:** 1px dashed `nova/button/secondary/default/color/primary` (#1f4cb3).
- **Border Radius:** `nova/radii/component/button` (8px).
- **Padding:** `nova/spacing/tight` (8px).
- **Layout:** Vertical flex column, content centered.

### Background Colors by State
- **Default/Error/Loading:** `global/color/dark-blue/10` (#f5f7fa)
- **Hover/Focus:** `global/color/dark-blue/50` (#e6f3ff)
- **Pressed:** `global/color/dark-blue/100` (#dbedfe)

### Content
- **Label Text:** `nova/typography/instructional/regular` (14px), color `nova/button/secondary/default/color/primary`.
- **Helper Text:** `nova/typography/supporting/regular` (12px), color `nova/color/typography/muted`.
- **Gap:** `nova/spacing/next` (4px) between label and helper text.

### Error Message
- **Typography:** `nova/typography/supporting/regular` (12px), color `nova/color/critical/primary`.
- **Layout:** Appears below the upload area, right-aligned, with a warning icon.

### Loading Indicator
- An animated spinner centered over the upload area, with the text content dimmed to 20% opacity.

---

## Design Tokens

### Typography
- `nova/typography/instructional/regular`
- `nova/typography/supporting/regular`

### Colors
- **Backgrounds:** `global/color/dark-blue/10`, `global/color/dark-blue/50`, `global/color/dark-blue/100`
- **Border/Label:** `nova/button/secondary/default/color/primary`
- **Focus Ring:** `nova/color/focus`
- **Helper Text:** `nova/color/typography/muted`
- **Error:** `nova/color/critical/primary`

### Spacing
- `nova/spacing/tight`, `nova/spacing/next`

### Borders & Radii
- `nova/border/basic`, `nova/radii/component/button`

---

## Accessibility

### Keyboard Navigation
- The upload area must be focusable via `Tab`.
- `Enter` or `Space` should trigger the file selection dialog.
- A visible focus ring is required.

### ARIA Attributes
- Use `role="button"` for the upload area.
- Link helper text with `aria-describedby`.
- For errors, use `aria-invalid="true"` and `aria-errormessage`. The error message should have `role="alert"`.
- During uploads, use `aria-busy="true"`.
