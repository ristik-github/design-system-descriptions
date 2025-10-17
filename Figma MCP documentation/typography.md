# Typography

## Overview
The typography system defines a comprehensive set of text styles for consistent, readable, and hierarchical text presentation across the application. All text should use one of these defined styles to maintain visual consistency and ensure proper readability. The typography system uses Geist as the primary font family with Regular and SemiBold weights.

## Font Basics

### Font Family
- **Primary:** Geist
- **Fallback:** Geist, Arial, 'Helvetica Neue', Helvetica, sans-serif

### Font Weights
- **Regular:** 400 weight - Used for standard body text and readable content
- **SemiBold:** 600 weight - Used for headings, emphasis, and strong text

### Font Size Range
- **Largest:** 30px (Title)
- **Smallest:** 12px (Supporting text)

## Typography Styles

### Title
The Title style is the largest text style, used for page titles and primary headings.

**Design Token:** `nova/typography/title`

**Specifications:**
- **Size:** 30px
- **Line Height:** 100% (1.0)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

---

### Heading 1
The largest heading level for major content sections.

**Design Token:** `nova/typography/heading/1`

**Specifications:**
- **Size:** 24px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

---

### Heading 2
The second-level heading for subsections.

**Design Token:** `nova/typography/heading/2`

**Specifications:**
- **Size:** 20px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

---

### Heading 3
The third-level heading for smaller subsections.

**Design Token:** `nova/typography/heading/3`

**Specifications:**
- **Size:** 18px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Modal/Dialog: Header titles (ref: modal.md)

---

### Body Regular
Standard body text for readable content.

**Design Token:** `nova/typography/body/regular`

**Specifications:**
- **Size:** 16px
- **Line Height:** 140% (1.4)
- **Weight:** Regular (400)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Form Label: Label text for all variants (ref: form-label.md)

---

### Body Strong
Emphasized body text for highlighting important information.

**Design Token:** `nova/typography/body/strong`

**Specifications:**
- **Size:** 16px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

---

### Base Regular
The default text style for most UI components.

**Design Token:** `nova/typography/base/regular`

**Specifications:**
- **Size:** 14px
- **Line Height:** 130% (1.3)
- **Weight:** Regular (400)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Text Input: Input field text (ref: text-input.md)

---

### Base Strong
Emphasized version of the base text style.

**Design Token:** `nova/typography/base/strong`

**Specifications:**
- **Size:** 14px
- **Line Height:** 130% (1.3)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Form Label: Required asterisk text (ref: form-label.md)

---

### Supporting Regular
Smaller text for supplementary information.

**Design Token:** `nova/typography/supporting/regular`

**Specifications:**
- **Size:** 12px
- **Line Height:** 120% (1.2)
- **Weight:** Regular (400)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Form Label: "optional" indicator text (ref: form-label.md)

---

### Supporting Strong
Emphasized version of supporting text.

**Design Token:** `nova/typography/supporting/strong`

**Specifications:**
- **Size:** 12px
- **Line Height:** 120% (1.2)
- **Weight:** SemiBold (600)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

---

### Instructional
Specialized text style for instructional or informational content with compact line height.

**Design Token:** `nova/typography/instructional/regular`

**Specifications:**
- **Size:** 14px
- **Line Height:** 100% (1.0)
- **Weight:** Regular (400)
- **Font Family:** Geist
- **Color:** `nova/color/typography/base` (#151d1e)

**Known Uses (from component documentation):**
- Button: Button text for all variants (ref: button.md)

---

## Inline Links

### Overview
Links don't use a separate typography style. Instead, they modify the existing style of the surrounding text with color and decoration changes.

### Link Modifications
When text becomes a link, apply the following changes to the existing typography style:

**Color:** `nova/color/typography/link` (#1e5edb)  
**Text Decoration:** Underline

### Applicable Styles
Links can be applied to any of the following styles:
- Body Regular
- Body Strong
- Base Regular
- Base Strong
- Supporting Regular
- Supporting Strong

### Visual Behavior
- The underlined link text maintains the same size, weight, and line height as its parent style
- Only the color changes to the link color
- Underline decoration is added
- Text decoration position: from-font (aligns with font metrics)

### Use Cases
- Hyperlinks within paragraphs
- Navigation links with text
- Inline references
- Action links within instructional text

---

## Design Tokens Reference

### Typography Tokens
All typography tokens include font family, size, weight, and line height as composite values:

- `nova/typography/title` - 30px SemiBold, 100% line height
- `nova/typography/heading/1` - 24px SemiBold, 140% line height
- `nova/typography/heading/2` - 20px SemiBold, 140% line height
- `nova/typography/heading/3` - 18px SemiBold, 140% line height
- `nova/typography/body/regular` - 16px Regular, 140% line height
- `nova/typography/body/strong` - 16px SemiBold, 140% line height
- `nova/typography/base/regular` - 14px Regular, 130% line height
- `nova/typography/base/strong` - 14px SemiBold, 130% line height
- `nova/typography/supporting/regular` - 12px Regular, 120% line height
- `nova/typography/supporting/strong` - 12px SemiBold, 120% line height
- `nova/typography/instructional/regular` - 14px Regular, 100% line height

### Font Size Tokens
Individual font size tokens (for special cases):
- `global/typography/fontsize/14` - 14px
- `global/typography/fontsize/12` - 12px

### Color Tokens
- `nova/color/typography/base` (#151d1e) - Default text color
- `nova/color/typography/link` (#1e5edb) - Link text color

---

## Typography Hierarchy

### Size Hierarchy (Largest to Smallest)
1. **Title:** 30px
2. **Heading 1:** 24px
3. **Heading 2:** 20px
4. **Heading 3:** 18px
5. **Body Regular/Strong:** 16px
6. **Base Regular/Strong:** 14px
7. **Instructional:** 14px
8. **Supporting Regular/Strong:** 12px

### Line Height Patterns
- **100% (1.0):** Title, Instructional - Compact, single-line text
- **120% (1.2):** Supporting - Minimal breathing room for small text
- **130% (1.3):** Base - Comfortable for UI components
- **140% (1.4):** Headings, Body - Optimal for readable content

### Weight Distribution
- **Regular (400):** All "Regular" variants - Standard readable text
- **SemiBold (600):** All "Strong" variants and all Headings/Title - Emphasis and hierarchy

---

## Usage Guidelines

### Best Practices

#### Do:
- Use Title for page-level headings and primary titles
- Use Heading hierarchy (1, 2, 3) to create clear content structure
- Use Body styles for longer-form readable content
- Use Base styles for UI components (buttons, forms, navigation)
- Use Supporting styles for helper text, captions, and metadata
- Use Instructional for compact form instructions and error messages
- Apply link modifications only to the designated typography styles
- Maintain the defined line heights for optimal readability
- Use Strong variants to emphasize important information within the same size category

#### Don't:
- Don't create custom font sizes outside the defined scale
- Don't mix font families - always use Geist (with fallbacks)
- Don't use weights other than Regular (400) and SemiBold (600)
- Don't apply link styling to Title or Heading styles
- Don't reduce line height below specified values for better visual density
- Don't use Title style for repetitive elements (use Headings instead)
- Don't use Supporting text for primary content (use Body or Base)
- Don't override line heights arbitrarily

### When to Use Each Style

> **Note:** The following usage patterns are based on actual component documentation in this design system. Refer to individual component documentation for specific implementation details.

#### Title (30px SemiBold, 100% line height)
- **Documented Uses:** None yet
- **Suggested Uses:** Page titles, major section headers, primary headings

#### Heading 1 (24px SemiBold, 140% line height)
- **Documented Uses:** None yet
- **Suggested Uses:** Main content sections, article titles

#### Heading 2 (20px SemiBold, 140% line height)
- **Documented Uses:** None yet
- **Suggested Uses:** Subsections, card group headers

#### Heading 3 (18px SemiBold, 140% line height)
- **Documented Uses:**
  - Modal/Dialog header titles
- **Suggested Uses:** Component titles, tertiary sections

#### Body Regular (16px Regular, 140% line height)
- **Documented Uses:**
  - Form Label: Label text for all variants
- **Suggested Uses:** Article content, descriptions, longer-form readable text

#### Body Strong (16px SemiBold, 140% line height)
- **Documented Uses:** None yet
- **Suggested Uses:** Emphasized text within body content, important highlights

#### Base Regular (14px Regular, 130% line height)
- **Documented Uses:**
  - Text Input: Input field text
- **Suggested Uses:** General UI component text

#### Base Strong (14px SemiBold, 130% line height)
- **Documented Uses:**
  - Form Label: Required asterisk
- **Suggested Uses:** Emphasized UI text, table headers

#### Supporting Regular (12px Regular, 120% line height)
- **Documented Uses:**
  - Form Label: "optional" indicator text
- **Suggested Uses:** Helper text, captions, metadata, timestamps

#### Supporting Strong (12px SemiBold, 120% line height)
- **Documented Uses:** None yet
- **Suggested Uses:** Emphasized helper text, important captions

#### Instructional (14px Regular, 100% line height)
- **Documented Uses:**
  - Button: Button text for all variants
- **Suggested Uses:** Compact informational text, inline instructions

### Accessibility Considerations

#### Readability
- Line heights are optimized for readability at each size
- Minimum font size is 12px (Supporting) to maintain legibility
- Base color (#151d1e) provides strong contrast against light backgrounds

#### Semantic HTML
- Use appropriate HTML heading tags (h1-h3) with corresponding typography styles
- Maintain logical heading hierarchy in content
- Don't skip heading levels for visual appearance

#### Color Contrast
- Default text color `nova/color/typography/base` (#151d1e) meets WCAG AA standards on white backgrounds
- Link color `nova/color/typography/link` (#1e5edb) maintains sufficient contrast for accessibility

#### Line Length
- Optimal line length for Body and Base styles: 50-75 characters
- Break long content into paragraphs for better scanability
- Use appropriate container widths to prevent excessive line length

---

## Implementation Notes

### Font Loading
Ensure the Geist font family is loaded with both Regular (400) and SemiBold (600) weights. Include the fallback stack for browsers that don't support variable fonts or when fonts fail to load.

### Responsive Typography
The documented styles provide fixed sizes. For responsive implementations:
- Consider scaling Title and Heading sizes on smaller viewports if needed
- Maintain minimum readable sizes (don't go below 12px)
- Keep line heights consistent across breakpoints
- Test readability on various screen sizes

### CSS Implementation Example Structure
```
Base text color: #151d1e
Link text color: #1e5edb
Font family: Geist, Arial, 'Helvetica Neue', Helvetica, sans-serif

Title: 30px / 100% line height / 600 weight
Heading 1: 24px / 140% line height / 600 weight
Heading 2: 20px / 140% line height / 600 weight
Heading 3: 18px / 140% line height / 600 weight
Body Regular: 16px / 140% line height / 400 weight
Body Strong: 16px / 140% line height / 600 weight
Base Regular: 14px / 130% line height / 400 weight
Base Strong: 14px / 130% line height / 600 weight
Supporting Regular: 12px / 120% line height / 400 weight
Supporting Strong: 12px / 120% line height / 600 weight
Instructional: 14px / 100% line height / 400 weight
```

### Design Token Integration
When implementing, reference design tokens directly rather than hardcoded values:
- Use composite typography tokens (e.g., `nova/typography/body/regular`) which include all properties
- Reference color tokens for text colors
- Maintain token naming in your CSS variables or design system

---

## Related Design Tokens

### Spacing Tokens (Used in Typography Layouts)
- `nova/spacing/near` (16px) - Spacing in typography documentation
- `nova/spacing/breathe` (32px) - Vertical spacing between text sections
- `nova/spacing/distant` (64px) - Large spacing for documentation padding

### Surface Tokens (Background Colors for Typography Display)
- `nova/surfaces/color/workspace` (#ffffff) - White background
- `nova/surfaces/color/background` (#f5f7fa) - Light gray background for examples
- `nova/surfaces/color/workspace border` (#e0e6e6) - Border color for sections

### Border Radius Tokens
- `nova/radii/component/workspace` (12px) - Rounded corners for documentation cards

---

## Version History
- **Version 1.0** - Initial typography system with Title, Headings (1-3), Body (Regular/Strong), Base (Regular/Strong), Supporting (Regular/Strong), Instructional, and Inline Link styles
