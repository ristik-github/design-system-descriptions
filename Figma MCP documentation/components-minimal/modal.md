# Modal

## Overview
A Modal is an overlay component that displays content above the main page interface, requiring user interaction before returning to the primary content. It includes a header with a title, an optional close button, and a content area. It supports both wide "modal" and narrow "dialog" variants.

## Component Properties

### Variants
- **Modal:** A full-width modal overlay (720px width) for primary content.
- **Dialog:** A narrower dialog overlay (288px width) for confirmations or alerts.

### Padding Options
- **On:** Content area has `nova/spacing/near` (16px) padding.
- **Off:** Content area has no padding.

### Header Options
- **Closeable:** `true`/`false`. Toggles the visibility of the close icon button.
- **showSubtitle:** `true`/`false`. Toggles the visibility of a subtitle below the main title.
- **showActions:** `true`/`false`. Toggles visibility of additional action elements in the header.

### Footer Option
- **showFooter:** `true`/`false`. Toggles the visibility of a footer section.

## Design Tokens

### Typography
- **Title:** `nova/typography/heading/3` (18px SemiBold)
- **Slot Content:** Roboto Regular, 12px

### Spacing
- **Header Padding:** `16px` horizontal, `12px` vertical.
- **Header Gaps:** `12px` (title to actions), `2px` (title to subtitle), `8px` (between actions).
- **Content Padding (if on):** `nova/spacing/near` (16px).

### Colors
- **Title Text:** `nova/color/typography/base`
- **Header Border:** `nova/surfaces/color/workspace border`
- **Modal Background:** `nova/drawer/color/background`
- **Slot Content Text:** `nova/link/color/tertiary`

### Border & Radius
- **Header Border:** `nova/border/basic` (1px bottom)
- **Modal Border Radius:** `nova/radii/component/modal` (8px)

## Layout Specifications

### Structure
- A vertical flex layout: Header, Content Wrapper, and optional Footer.
- **Header:** Fixed height (56px for Modal, 60px for Dialog).
- **Content Wrapper:** Grows to fill remaining space, with a minimum height of 80px.

### Dimensions
- **Modal Variant:**
    - **Width:** 720px
    - **Min Height:** 136px
- **Dialog Variant:**
    - **Width:** 288px
    - **Min Height:** 140px
- **Close Button:** 36x36px with a 20x20px icon.

### Sizing Behavior
- **Width:** Fixed based on the variant.
- **Height:** Flexible, grows with content.

## Accessibility Considerations

### Keyboard Navigation
- **Focus Trap:** Focus must be trapped within the modal when it is open.
- **Tab Order:** Follows a logical order (e.g., close button → content → footer actions).
- **Escape Key:** Should close the modal.

### Screen Readers
- The modal's title should be announced as the dialog title.
- The close button needs a descriptive `aria-label` (e.g., "Close dialog").

### ARIA Attributes
- **`role="dialog"`** or `role="alertdialog"` on the root container.
- **`aria-modal="true"`** to indicate the content underneath is inert.
- **`aria-labelledby`** referencing the title's ID.
- **`aria-describedby`** referencing the content area's ID.

### Focus Management
- **Initial Focus:** When opened, focus should move to the first focusable element inside the modal.
- **Focus Return:** When closed, focus should return to the element that triggered the modal.