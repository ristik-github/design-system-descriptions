# Label Value Pair

## Overview
The Label Value Pair component displays a label-value combination in a vertical stack layout. It's designed for presenting read-only data in a consistent, scannable format, commonly used in detail views, summary sections, and information displays.

## Component Properties
- **Label (string):** The descriptive label text. Default: `"First Name"`.
- **Value (string):** The actual data associated with the label. Default: `"Value"`.

## Visual Specifications

### Container
- **Layout:** Vertical flex column with a `1px` gap between label and value.
- **Width:** Full width of the parent container.
- **Height:** Hugs content.

### Label Text
- **Typography:** `nova/typography/base/regular` (14px Regular, 130% line height).
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62)).

### Value Text
- **Typography:** `nova/typography/body/regular` (16px Regular, 140% line height).
- **Color:** `nova/color/typography/base` (#151d1e).

## Design Tokens

### Typography
- **Label:** `nova/typography/base/regular`
- **Value:** `nova/typography/body/regular`

### Colors
- **Label:** `nova/color/typography/muted`
- **Value:** `nova/color/typography/base`

### Spacing
- **Gap:** `1px` between label and value.

## Layout Specifications
- **Structure:** A simple vertical stack with the label on top and the value below.
- **Alignment:** Left-aligned.
- **Sizing:** The component takes the full width of its parent, and the height adapts to the text content. Text wraps by default if it exceeds the container width.

## Accessibility Considerations

### Semantic HTML
- For groups of pairs, use a description list: `<dl>` with `<dt>` for the label and `<dd>` for the value. This semantically associates the label and value for screen readers.

### Screen Readers
- A proper semantic structure ensures the label and value are announced together (e.g., "First Name: Ben").

### Text Readability
- The color contrast between text and background meets accessibility standards for primary and secondary text.