# Badge

## Overview

The Badge component is a compact visual indicator used to label, categorize, or display counts and statuses. Badges provide quick visual cues through color-coded states and can be used to highlight important information, show counts, or tag content with categorical labels. The component supports multiple semantic states with appropriate color combinations for clear communication.

---

## Component Properties

### Variant Properties

#### 1. **Type** (2 options)
- **Tag**: Rectangular badge with standard corner radius, used for labels and categories
- **Count**: More rounded badge (pill-shaped), typically used for numerical counts or compact indicators

#### 2. **State** (7 options)
- **Neutral**: Default state for general-purpose labels without specific semantic meaning
- **Critical**: Indicates critical issues, errors, or highest priority items
- **Severe**: Indicates severe issues or high-risk items
- **Warning**: Indicates caution, potential issues, or items requiring attention
- **Success**: Indicates successful completion, positive status, or approval
- **Information**: Provides informational context or neutral highlights
- **Feature**: Highlights new features, promotions, or special items

#### 3. **Size** (2 options)
- **Small**: Compact badge for dense layouts or secondary information
- **Medium**: Slightly larger badge for improved readability

#### 4. **Show Icon** (boolean)
- When enabled: Displays an optional icon before the label text
- When disabled: Shows text label only

### Variant Combinations

The component supports **28 variant combinations**:
- Type (2) × State (7) × Size (2) = 28 combinations
- Icon visibility is controlled independently for all combinations

---

## Visual Specifications

### Type=Tag, Size=Small

**Container:**
- Display: Flex row
- Align items: Center
- Gap: `nova/spacing/next` (4px) between icon and text
- Padding: Horizontal `nova/spacing/next` (4px), Vertical `nova/spacing/slight` (2px)
- Border: `nova/border/basic` (1px) solid
- Border Radius: `nova/radii/component/badge` (4px)
- Width: Hug contents
- Height: Hug contents

**Typography:**
- Font: `nova/typography/supporting/regular` (12px Regular, 120% line height)
- Font Size: `global/typography/fontsize/12` (12px)
- Line Height: 14px
- Text: No wrap, whitespace preserved

### Type=Tag, Size=Medium

**Container:**
- Display: Flex row
- Align items: Center
- Gap: `nova/spacing/next` (4px) between icon and text
- Padding: Horizontal `nova/spacing/tight` (8px), Vertical `nova/spacing/next` (4px)
- Border: `nova/border/basic` (1px) solid
- Border Radius: `nova/radii/component/badge` (4px)
- Width: Hug contents
- Height: Hug contents

**Typography:**
- Same as Small: `nova/typography/supporting/regular` (12px Regular, 120% line height)

### Type=Count, Size=Small

**Container:**
- Display: Flex row
- Align items: Center
- Justify content: Center
- Gap: `nova/spacing/next` (4px) between icon and text
- Padding: Horizontal `nova/spacing/next` (4px), Vertical `nova/spacing/slight` (2px)
- Border: `nova/border/basic` (1px) solid
- Border Radius: 9px (more rounded than Tag type)
- Width: Hug contents
- Height: Hug contents

**Typography:**
- Same as Tag type: `nova/typography/supporting/regular` (12px Regular, 120% line height)

### Type=Count, Size=Medium

**Container:**
- Display: Flex row
- Align items: Center
- Justify content: Center
- Gap: `nova/spacing/next` (4px) between icon and text
- Padding: Horizontal `nova/spacing/tight` (8px), Vertical `nova/spacing/next` (4px)
- Border: `nova/border/basic` (1px) solid
- Border Radius: 9px (more rounded than Tag type)
- Width: Hug contents
- Height: Hug contents

**Typography:**
- Same as Small: `nova/typography/supporting/regular` (12px Regular, 120% line height)

---

## Color Specifications by State

### State=Neutral

**Tag & Count:**
- Background: `nova/color/neutral/secondary` (#f6fafa - very light gray)
- Border: `nova/color/neutral/primary` (#889192 - medium gray)
- Text: `nova/color/neutral/dark` (#333b3b - dark gray)

### State=Critical

**Tag & Count:**
- Background: `nova/color/critical/secondary` (#fdf2f2 - very light red)
- Border: `nova/color/critical/primary` (#d52020 - bright red)
- Text: `nova/color/critical/accent` (#4f0808 - dark red)

### State=Severe

**Tag & Count:**
- Background: `nova/color/severe/secondary` (light red, similar to Critical)
- Border: `nova/color/severe/primary` (red)
- Text: `nova/color/severe/dark` (#4f0808 - dark red)

### State=Warning

**Tag & Count:**
- Background: `nova/color/warning/secondary` (very light orange)
- Border: `nova/color/warning/primary` (orange)
- Text: `nova/color/warning/dark` (#4a1c02 - dark brown/orange)

### State=Success

**Tag & Count:**
- Background: `nova/color/success/secondary` (very light green)
- Border: `nova/color/success/primary` (green)
- Text: `nova/color/brand/dark` (#002d2d - dark teal/green)

### State=Information

**Tag & Count:**
- Background: `nova/color/informative/secondary` (very light blue)
- Border: `nova/color/informative/primary` (blue)
- Text: `nova/color/informative/dark` (#112e3b - dark blue)

### State=Feature

**Tag & Count:**
- Background: `nova/color/feature/secondary` (very light purple)
- Border: `nova/color/feature/primary` (purple)
- Text: `nova/color/feature/dark` (#291f5b - dark purple)

---

## Design Tokens Reference

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `nova/typography/supporting/regular` | 12px Regular, 120% line height | Badge label text |
| `global/typography/fontsize/12` | 12px | Font size |
| `nova/typography/font-stack` | Geist, sans-serif | Font family |

### Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `nova/spacing/next` | 4px | Horizontal padding, gap between icon and text |
| `nova/spacing/slight` | 2px | Vertical padding |

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `nova/radii/component/badge` | 4px | Tag type border radius |
| Custom | 9px | Count type border radius (more rounded) |

### Borders

| Token | Value | Usage |
|-------|-------|-------|
| `nova/border/basic` | 1px | Border width |

### Colors by State

#### Neutral
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/neutral/secondary` | #f6fafa | Background |
| `nova/color/neutral/primary` | #889192 | Border |
| `nova/color/neutral/dark` | #333b3b | Text |

#### Critical
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/critical/secondary` | #fdf2f2 | Background |
| `nova/color/critical/primary` | #d52020 | Border |
| `nova/color/critical/accent` | #4f0808 | Text |

#### Severe
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/severe/secondary` | Light red | Background |
| `nova/color/severe/primary` | Red | Border |
| `nova/color/severe/dark` | #4f0808 | Text |

#### Warning
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/warning/secondary` | Light orange | Background |
| `nova/color/warning/primary` | Orange | Border |
| `nova/color/warning/dark` | #4a1c02 | Text |

#### Success
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/success/secondary` | Light green | Background |
| `nova/color/success/primary` | Green | Border |
| `nova/color/brand/dark` | #002d2d | Text |

#### Information
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/informative/secondary` | Light blue | Background |
| `nova/color/informative/primary` | Blue | Border |
| `nova/color/informative/dark` | #112e3b | Text |

#### Feature
| Token | Value | Usage |
|-------|-------|-------|
| `nova/color/feature/secondary` | Light purple | Background |
| `nova/color/feature/primary` | Purple | Border |
| `nova/color/feature/dark` | #291f5b | Text |

---

## States & Behavior

### Interactive States

Badges are typically **non-interactive** elements (not clickable). However, they may be placed inside interactive elements:
- When inside a button or link, the entire parent element is interactive
- Badges themselves do not have hover or pressed states
- Focus states apply to the parent interactive element, not the badge

### Visual States by Type

**Tag Type:**
- Rectangle with slight rounding (4px radius)
- Clear corners provide more formal appearance
- Suitable for labels, categories, tags

**Count Type:**
- More rounded appearance (9px radius, approaching pill shape)
- Softer, more compact visual style
- Suitable for numerical counts, compact indicators

### Size Variations

**Small:**
- Horizontal padding: `nova/spacing/next` (4px)
- Vertical padding: `nova/spacing/slight` (2px)
- More compact for dense layouts
- Suitable for dense interfaces, tables, lists

**Medium:**
- Horizontal padding: `nova/spacing/tight` (8px)
- Vertical padding: `nova/spacing/next` (4px)
- More breathing room and better readability
- Suitable for cards, standalone badges, primary content

---

## Usage Guidelines

### When to Use

**Badge Component:**
- Labeling or categorizing items (e.g., "New", "Draft", "Approved")
- Displaying counts (e.g., notification counts, item totals)
- Showing status or state (e.g., "Active", "Pending", "Completed")
- Highlighting important attributes or properties
- Tagging content with keywords or categories

**Type=Tag:**
- Text labels and categories
- Status indicators with words
- Feature highlights ("New Feature", "Beta")
- Classification tags

**Type=Count:**
- Numerical values (counts, quantities)
- Compact indicators
- Notification badges
- Item counts in lists or tabs

**State Selection:**
- **Neutral**: Default tags, general categorization, no semantic meaning
- **Critical**: Errors, critical failures, urgent items, highest priority
- **Severe**: Serious issues, high-risk items, important warnings
- **Warning**: Caution items, potential problems, items needing attention
- **Success**: Completed items, approved status, positive outcomes
- **Information**: Helpful context, neutral information, FYI items
- **Feature**: New features, special promotions, highlighted items

### When Not to Use

- Long text content (use labels or paragraphs instead)
- Interactive elements that require clicking (use buttons or chips instead)
- Primary navigation (use navigation components)
- Form inputs (use form field components)

### Best Practices

1. **Concise Text**: Keep badge text short (1-3 words or short numbers)
2. **Consistent States**: Use the same state colors consistently across the application
3. **Meaningful Colors**: Only use semantic states when the meaning applies
4. **Appropriate Type**: Use Tag for words, Count for numbers (as a general rule)
5. **Don't Overuse**: Too many badges reduce their effectiveness
6. **Contrast**: Ensure sufficient contrast between background, border, and text
7. **Grouping**: When showing multiple badges, maintain consistent spacing

### Content Guidelines

**Text Content:**
- Keep to 1-3 words maximum
- Use Title Case for labels ("New Feature", "In Progress")
- Use uppercase for abbreviations ("PDF", "API")
- Numbers should be concise (use "99+" for counts over 99)

**State Usage:**
- Don't rely on color alone to convey meaning (use text + color)
- Use consistent terminology across similar badges
- Match badge state to the severity/type of information

---

## Accessibility

### Semantic HTML
- Use `<span>` for badge container (non-interactive)
- Use `<strong>` or `<em>` for badge text if emphasizing importance
- If badge is inside a clickable element, ensure parent has proper semantics

### ARIA Attributes
- `aria-label` if badge meaning isn't clear from text alone (e.g., "3 unread messages" for a "3" badge)
- `role="status"` for dynamic badges that update (like notification counts)
- `aria-live="polite"` for badges that change and should be announced

### Visual Considerations
- **Color Contrast**: All state combinations meet WCAG AA requirements
- **Text Contrast**: Dark text on light backgrounds ensures readability
- **Border Visibility**: 1px borders provide clear boundaries
- **Don't Rely on Color Alone**: Text should convey meaning without color

### Screen Reader Considerations
- Badge text is read by default
- Context should be clear from surrounding content or aria-label
- For counts, consider adding context (e.g., "5 notifications" vs just "5")

---

## Layout Specifications

### Dimensions

**Tag Type - Small:**
- Width: Hug contents
- Height: Hug contents
- Horizontal padding: `nova/spacing/next` (4px)
- Vertical padding: `nova/spacing/slight` (2px)
- Border Radius: `nova/radii/component/badge` (4px)

**Tag Type - Medium:**
- Width: Hug contents
- Height: Hug contents
- Horizontal padding: `nova/spacing/tight` (8px)
- Vertical padding: `nova/spacing/next` (4px)
- Border Radius: `nova/radii/component/badge` (4px)

**Count Type - Small:**
- Width: Hug contents
- Height: Hug contents
- Horizontal padding: `nova/spacing/next` (4px)
- Vertical padding: `nova/spacing/slight` (2px)
- Border Radius: 9px (more rounded for pill shape)

**Count Type - Medium:**
- Width: Hug contents
- Height: Hug contents
- Horizontal padding: `nova/spacing/tight` (8px)
- Vertical padding: `nova/spacing/next` (4px)
- Border Radius: 9px (more rounded for pill shape)

### Spacing

**Internal Spacing:**
- Horizontal padding: 4px on each side
- Vertical padding: 2px on top and bottom
- Gap (when icon present): 4px between icon and text

**External Spacing (Recommendations):**
- When multiple badges in a row: 4-8px gap between badges
- When badge is inline with text: 4px gap from adjacent text
- When badge is above/below content: 4-8px vertical margin

### Responsive Behavior

- Width and height hug contents (adapt to text and icon)
- Text does not wrap (nowrap, single line)
- Size is determined by padding, typography, and content
- Consider reducing number of visible badges on smaller screens

---

## Visual Behavior Notes

### Component Architecture

**Color System:**
- Three-color system per state: secondary (background), primary (border), dark/accent (text)
- Light backgrounds with darker borders and darkest text
- Creates clear visual hierarchy and readability

**Shape Variations:**
- Tag type: Subtle rounding (4px) for formal appearance
- Count type: More rounding (9px) for softer, pill-like appearance
- Both types maintain consistent internal spacing

### Visual Hierarchy

1. **State Color**: Primary visual indicator of badge meaning
2. **Border**: Reinforces boundary and state
3. **Text**: Conveys specific information
4. **Shape**: Secondary indicator (Tag vs Count type)

### Design Principles

**Clarity:**
- High contrast between background, border, and text
- Clear borders define badge boundaries
- Sufficient padding for readability

**Consistency:**
- Identical padding across all variants
- Predictable color patterns (light bg, medium border, dark text)
- Consistent typography across all states

**Scalability:**
- Auto-width accommodates various content lengths
- Compact vertical height maintains scanability
- Clear at various zoom levels and screen densities

---

## Examples

### Common Use Cases

**Status Indicators:**
```
State=Success, Type=Tag, Text="Approved"
State=Warning, Type=Tag, Text="Pending"
State=Critical, Type=Tag, Text="Rejected"
```

**Notification Counts:**
```
State=Critical, Type=Count, Text="5"
State=Information, Type=Count, Text="12"
State=Neutral, Type=Count, Text="99+"
```

**Feature Highlights:**
```
State=Feature, Type=Tag, Text="New"
State=Information, Type=Tag, Text="Beta"
```

**Category Tags:**
```
State=Neutral, Type=Tag, Text="Finance"
State=Neutral, Type=Tag, Text="HR"
State=Neutral, Type=Tag, Text="IT"
```

**Priority Indicators:**
```
State=Critical, Type=Tag, Text="High"
State=Warning, Type=Tag, Text="Medium"
State=Success, Type=Tag, Text="Low"
```

---

## Integration Patterns

### With Tables
- Place badges in table cells to indicate status
- Keep badge size Small for better density
- Align badges consistently (usually left-aligned)

### With Cards/Tiles
- Position badges in card headers or corners
- Use for categorization or status indication
- Consider using Type=Tag for better visual balance

### With Lists
- Inline badges next to list item titles
- Use for counts, status, or categories
- Maintain consistent spacing between badge and text

### With Navigation
- Use Count type badges to show notification counts
- Place badges on top-right of icons or labels
- Critical or Warning states for attention items

---

## Related Components

- **Icon Button** - May contain badges for notification counts
- **Tile (Card)** - Badges can be used within card headers or content
- **Header Top Nav** - Badges may appear on navigation items for counts

---

## Version History

- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** 2025-10-22

---

## Notes

- Size=Small uses 4px horizontal padding and 2px vertical padding for maximum compactness
- Size=Medium uses 8px horizontal padding and 4px vertical padding for better readability and larger touch targets
- Badges are designed to be non-interactive; wrap them in interactive elements if clickability is needed
- The Icon feature (Show Icon property) allows for icon placement before text, but icons are not included in the base specification
- Count type uses slightly more rounding (9px) than Tag type (4px) to create a more pill-like appearance
- All color combinations are designed to meet WCAG AA contrast requirements
- Text content should always be kept concise to maintain badge compactness and scannability
