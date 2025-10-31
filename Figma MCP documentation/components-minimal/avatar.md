# Avatar

## Overview

The Avatar component is a circular visual representation of a user or entity. It supports image, text initials, or icon variants, comes in three sizes, and includes interactive states.

---

## Component Properties

### Variants

#### Image
Displays a photographic image of the user, center-cropped to fit the circular container.

#### Initials
Displays 1-2 character text initials within a circular container with a background color and border.
- **Background:** `nova/color/brand/secondary` (#e7f4eb)
- **Border:** 1px solid `nova/color/brand/dark` (#002d2d)
- **Text Color:** `nova/color/brand/dark` (#002d2d)

#### Icon
Displays a generic person icon within a circular container with a background color and border.
- **Background:** `nova/color/brand/secondary` (#e7f4eb)
- **Border:** 1px solid `nova/color/brand/dark` (#002d2d)
- **Icon Color:** `nova/color/brand/dark` (#002d2d)

---

### Sizes

#### Small
- **Dimensions:** 24×24px
- **Initials Typography:** `nova/typography/supporting/strong` (12px SemiBold)
- **Icon Size:** 16×16px

#### Medium
- **Dimensions:** 32×32px
- **Initials Typography:** `nova/typography/supporting/strong` (12px SemiBold)
- **Icon Size:** 20×20px

#### Large
- **Dimensions:** 40×40px
- **Initials Typography:** `nova/typography/heading/3` (18px SemiBold)
- **Icon Size:** 24×24px

---

### States

#### Default
The resting state of the component.

#### Hover
Visual state when the cursor is over the avatar (if interactive).
- **Initials/Icon Border:** `nova/color/typography/base` (#151d1e)
- **Initials/Icon Text/Icon Color:** `nova/color/static/black` (#000000)

#### Focus
Visual state on keyboard focus.
- **Focus Ring:** Appears around the avatar with a 2px offset.
- **Focus Ring Color:** `nova/icon-button/color/accent` (#dbfbf5)

---

## Design Tokens

### Colors
- **Background (Initials/Icon):** `nova/color/brand/secondary`
- **Border/Text (Default):** `nova/color/brand/dark`
- **Border (Hover):** `nova/color/typography/base`
- **Text/Icon (Hover):** `nova/color/static/black`
- **Focus Ring:** `nova/icon-button/color/accent`

### Typography
- **Initials (Small/Medium):** `nova/typography/supporting/strong`
- **Initials (Large):** `nova/typography/heading/3`

### Borders
- **Width:** 1px
- **Radius:** 999px (circle)

---

## Layout Specifications

### Structure
A single circular element containing an image, initials, or an icon. Content is centered.

### Dimensions
| Size   | Diameter | Icon Size | Text Size |
|--------|----------|-----------|-----------|
| Small  | 24×24px  | 16×16px   | 12px      |
| Medium | 32×32px  | 20×20px   | 12px      |
| Large  | 40×40px  | 24×24px   | 18px      |

---

## Accessibility

### Alternative Text
- **Image:** Provide `alt` text describing the user (e.g., "Profile photo of [User Name]"). Use `alt=""` if decorative.
- **Initials/Icon:** Provide `aria-label` with the user's name.

### Keyboard Navigation
- Interactive avatars must be focusable and activatable with `Enter`/`Space`.
- A visible focus ring is required for focused interactive avatars.

### ARIA Attributes
- **Interactive:** Use `role="button"` or a `<button>` element with an `aria-label`.
- **Non-Interactive:** No role needed. Provide `alt` or `aria-label` for identification.
