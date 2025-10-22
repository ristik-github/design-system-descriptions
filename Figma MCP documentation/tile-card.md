# Tile (Card)

## Overview

The Tile (Card) component is a versatile container used to display grouped information in a structured, visually contained format. It serves as a foundational building block for organizing content such as findings, records, summaries, or any related data that benefits from being grouped together. The component supports multiple visual styles and padding configurations to accommodate different layout needs and information density requirements.

---

## Component Properties

### Variant Properties

#### 1. **Type** (3 options)
- **Boxed**: Fully enclosed card with border and background, creating maximum visual separation
- **With Divider**: Card with bottom border divider only, no side/top borders or background
- **Note:** The "With Divider" type is typically used when cards are stacked vertically in a list

#### 2. **Padding** (2 options)
- **close**: Standard padding of `nova/spacing/close` (12px) on all sides
- **none**: No horizontal padding (0px left/right), reduced vertical padding (top: 0px, bottom: 12px)
- **Note:** The "none" padding option is only available for "With Divider" type

### Variant Combinations

The component supports **4 variant combinations**:
1. Type=Boxed, Padding=close
2. Type=With Divider, Padding=close
3. Type=With Divider, Padding=none
4. _(Type=Boxed, Padding=none is not a valid combination)_

---

## Component Structure

This is a **composite component** consisting of:

1. **Container** - The outer card wrapper that provides border, background, and spacing
2. **Tile (Card) Title** - Header section containing title text and optional action button
3. **Card Content** - Flexible content area for description text, label-value pairs, or custom content

---

## Visual Specifications by Variant

### Type=Boxed, Padding=close

**Container:**
- Background: `nova/surfaces/color/workspace` (#ffffff - white)
- Border: `nova/border/basic` (1px) solid, `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: `nova/radii/component/workspace` (12px)
- Padding: `nova/spacing/close` (12px) on all sides
- Internal gap: `nova/spacing/tight` (8px) between title and content

**Tile (Card) Title:**
- Display: Flex row
- Alignment: Center (vertically aligned)
- Gap: 8px between left content and right action
- Width: Full width of container

**Title Text:**
- Typography: `nova/typography/body/strong` (16px SemiBold, 140% line height)
- Color (default): `#000000` (black)
- Color (when Title Link=true): `nova/color/typography/link` (#1e5edb - blue)
- Gap below title: `nova/spacing/slight` (2px)

**Action Button (Icon Button):**
- Size: 28px × 28px
- Padding: 6px
- Border Radius: `nova/radii/component/button` (8px)
- Icon Size: 20px × 20px
- Common icon: Three-dot menu (more options)

**Card Content Area:**
- Display: Flex column
- Gap: 8px between content elements
- Width: Full width of container

**Description Text:**
- Typography: `nova/typography/body/regular` (16px Regular, 140% line height)
- Color: `nova/color/typography/base` (#151d1e)

**Label-Value Pairs:**
- Display: Flex column
- Gap: 1px between label and value
- Label Typography: `nova/typography/base/regular` (14px Regular, 130% line height)
- Label Color: `nova/color/typography/muted` (rgba(0,0,0,0.62))
- Value Typography: `nova/typography/body/regular` (16px Regular, 140% line height)
- Value Color: `nova/color/typography/base` (#151d1e)

### Type=With Divider, Padding=close

**Container:**
- Background: Transparent (no background color)
- Border: Bottom border only - `nova/border/basic` (1px) solid, `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: None (0px)
- Padding: `nova/spacing/close` (12px) on all sides
- Internal gap: `nova/spacing/tight` (8px) between title and content

**All other specifications:** Same as Type=Boxed variant (Tile (Card) Title, Title Text, Action Button, Card Content, etc.)

### Type=With Divider, Padding=none

**Container:**
- Background: Transparent (no background color)
- Border: Bottom border only - `nova/border/basic` (1px) solid, `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: None (0px)
- Padding: 
  - Top: 0px
  - Right: 0px
  - Bottom: `nova/spacing/close` (12px)
  - Left: 0px
- Internal gap: `nova/spacing/tight` (8px) between title and content

**All other specifications:** Same as other variants (Tile (Card) Title, Title Text, Action Button, Card Content, etc.)

---

## Design Tokens Reference

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `nova/typography/body/strong` | 16px SemiBold, 140% line height | Tile title text |
| `nova/typography/body/regular` | 16px Regular, 140% line height | Description text, label values |
| `nova/typography/base/regular` | 14px Regular, 130% line height | Label text (label-value pairs) |

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `nova/surfaces/color/workspace` | #ffffff | Card background (Boxed type) |
| `nova/surfaces/color/workspace-border` | #e0e6e6 | Border color |
| `nova/color/typography/base` | #151d1e | Primary text (description, values) |
| `nova/color/typography/muted` | rgba(0,0,0,0.62) | Secondary text (labels) |
| `nova/color/typography/link` | #1e5edb | Title text when Title Link=true |
| `#000000` | Black | Title text when Title Link=false |

### Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `nova/spacing/close` | 12px | Container padding, bottom padding (none variant) |
| `nova/spacing/tight` | 8px | Gap between title and content, internal content gaps |
| `nova/spacing/next` | 4px | Gap in action button area |
| `nova/spacing/slight` | 2px | Gap below title text |

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `nova/radii/component/workspace` | 12px | Card container (Boxed type) |
| `nova/radii/component/button` | 8px | Action icon button |

### Borders

| Token | Value | Usage |
|-------|-------|-------|
| `nova/border/basic` | 1px | Border width |

---

## Tile (Card) Title

The Tile (Card) Title is the header section that appears at the top of every Tile (Card). It provides a consistent header structure across all card variants.

### Properties

**Title Link** (boolean):
- **false**: Title text appears in black (`#000000`)
- **true**: Title text appears in link blue (`nova/color/typography/link` #1e5edb), indicating it's clickable

### Structure

**Layout:**
- Display: Flex row
- Justify content: Space between
- Align items: Center
- Width: Full width of parent container
- Height: 28px

**Left Section (Title Text):**
- Flex grow: 1 (takes available space)
- Display: Flex column
- Gap: `nova/spacing/slight` (2px)
- Typography: `nova/typography/body/strong` (16px SemiBold, 140% line height)
- Color: 
  - `#000000` when Title Link=false
  - `nova/color/typography/link` (#1e5edb) when Title Link=true

**Right Section (Action Area):**
- Flex shrink: 0 (fixed width)
- Display: Flex row
- Gap: `nova/spacing/next` (4px)
- Contains: Icon Button component (28px × 28px)

**Icon Button:**
- Size: 28px × 28px
- Padding: 6px
- Border Radius: `nova/radii/component/button` (8px)
- Icon: 20px × 20px (commonly three-dot menu icon)
- Background: Transparent (default state)

---

## Content Structure

### Typical Card Content Layout

The Card Content area typically contains:

1. **Description Text** (optional)
   - Single paragraph or multi-line text
   - Typography: `nova/typography/body/regular` (16px Regular, 140% line height)
   - Color: `nova/color/typography/base` (#151d1e)

2. **Label-Value Pairs** (optional, multiple allowed)
   - Label: `nova/typography/base/regular` (14px Regular, 130% line height)
   - Label Color: `nova/color/typography/muted` (rgba(0,0,0,0.62))
   - Value: `nova/typography/body/regular` (16px Regular, 140% line height)
   - Value Color: `nova/color/typography/base` (#151d1e)
   - Gap between label and value: 1px
   - Gap between pairs: 10px

3. **Custom Content** (flexible)
   - The content area can accommodate any custom elements
   - Follow 8px gap pattern for consistency

---

## States

### Title Link State
- **Title Link=false**: Title is static text, not interactive, appears in black
- **Title Link=true**: Title is a clickable link, appears in blue, may show underline on hover

### Container Type States
- **Boxed**: Full visual separation with border and background
- **With Divider**: Minimal visual separation with bottom border only, integrates into list layouts

### Padding States
- **close**: Standard padding for standalone cards or first/last items in a list
- **none**: Reduced padding for mid-list items where parent container provides horizontal padding

---

## Usage Guidelines

### When to Use

**Tile (Card) Component:**
- Displaying grouped, related information (findings, records, items)
- Creating scannable lists of structured data
- Organizing content into discrete, manageable chunks
- Showing summaries that may link to detailed views

**Type=Boxed:**
- Standalone cards that need visual separation
- Dashboard widgets or summary panels
- Cards on colored or complex backgrounds
- When maximum visual hierarchy is needed

**Type=With Divider:**
- Stacked lists of similar items
- When cards are in a vertical list layout
- Minimizing visual weight in dense interfaces
- When parent container provides sufficient visual structure

**Padding=close:**
- Standalone cards
- First or last items in a list
- When the card needs internal breathing room

**Padding=none:**
- Mid-list items where parent container has padding
- Maximizing content width within constrained spaces
- When horizontal alignment with other elements is important

### When Not to Use

- Single pieces of unrelated information (use plain text or label-value pairs instead)
- Navigation elements (use navigation components)
- Forms or input collection (use form components)
- Highly interactive content that needs more complex layouts

### Best Practices

1. **Consistent Card Types**: Use the same Type variant throughout a list or section
2. **Meaningful Titles**: Title should clearly identify the card's content or purpose
3. **Action Icon Usage**: Only include action button when actions are available
4. **Content Density**: Balance information completeness with scannability
5. **Link Indication**: Use Title Link=true only when title navigates to detail view
6. **Padding Consistency**: Match padding choice to layout context (standalone vs. list)

### Content Guidelines

**Title Text:**
- Keep concise (1-5 words or short ID/reference number)
- Use meaningful identifiers (#13243, "Finding Title", etc.)
- Avoid full sentences as titles

**Description Text:**
- Keep to 1-2 sentences for scannability
- Use full sentences with proper capitalization
- Provide enough context to understand the card's content

**Label-Value Pairs:**
- Labels: Use consistent terminology across cards
- Labels: Short, descriptive (1-2 words)
- Values: Can be longer, provide specific information

---

## Accessibility

### Semantic HTML
- Use `<article>` or `<div>` for card container
- Use `<h3>` or `<h4>` for title text (depending on page hierarchy)
- Use `<a>` for title when Title Link=true
- Use `<button>` for action icon button
- Use `<dl>`, `<dt>`, `<dd>` for label-value pairs (optional semantic enhancement)

### ARIA Attributes
- `role="article"` on card container (if not using `<article>`)
- `aria-label` on action icon button describing the action (e.g., "More options")
- `aria-labelledby` linking content to title (optional)

### Keyboard Navigation
- Title link (when Title Link=true) must be focusable and activatable
- Action button must be focusable and activatable
- Tab order: Title link → Action button → Next card
- **Enter/Space**: Activate focused link or button

### Visual Considerations
- Sufficient color contrast for all text (WCAG AA compliant)
- Link color distinguishes clickable titles from static titles
- Focus indicators clearly visible on interactive elements
- Border and spacing provide clear visual boundaries

---

## Layout Specifications

### Dimensions

**Boxed Type:**
- Width: Flexible (typically fills container)
- Height: Auto (expands based on content)
- Min Height: Approximately 131px (with typical content)

**With Divider Type:**
- Width: Flexible (same as Boxed)
- Height: Auto (expands based on content)
- Min Height: Approximately 119px with Padding=none, 131px with Padding=close

### Spacing Breakdown

**Type=Boxed, Padding=close:**
```
Container padding: 12px all sides
├── Tile (Card) Title (28px height)
├── Gap: 8px
└── Card Content (variable height)
    ├── Description text
    ├── Gap: 8px
    └── Label-Value Pair(s)
```

**Type=With Divider, Padding=close:**
```
Container padding: 12px all sides
Border bottom: 1px
├── Tile (Card) Title (28px height)
├── Gap: 8px
└── Card Content (variable height)
```

**Type=With Divider, Padding=none:**
```
Container padding: 0px top, 0px left/right, 12px bottom
Border bottom: 1px
├── Tile (Card) Title (28px height)
├── Gap: 8px
└── Card Content (variable height)
```

### Responsive Behavior

- Width adapts to parent container (100% width typical)
- Height grows based on content
- Content wraps appropriately for narrower screens
- Padding remains consistent across breakpoints
- Consider stacking cards vertically on mobile devices

---

## Visual Behavior Notes

### Component Architecture

**Boxed Type:**
- Creates visual "islands" of content
- White background contrasts with page background
- Border provides clear boundaries
- Rounded corners soften appearance

**With Divider Type:**
- Lighter visual weight than Boxed
- Integrates seamlessly into list layouts
- Bottom border provides subtle separation
- No background allows content to breathe

**Padding Variations:**
- `close`: Self-contained spacing, works standalone
- `none`: Relies on parent container for horizontal spacing, optimizes vertical space

### State Transitions

**Title Link Interaction:**
- Default: Title in black (static) or blue (link)
- Hover (when Title Link=true): Underline appears, color may darken slightly
- Focus: Focus indicator around title text
- Active: Slight color change during click

**Action Button Interaction:**
- Default: Transparent background, icon visible
- Hover: Background color appears (`nova/radii/component/button` background)
- Focus: Focus indicator around button
- Active: Background darkens during click

### Visual Hierarchy

1. **Title**: Strongest visual weight (SemiBold, 16px)
2. **Description**: Medium weight (Regular, 16px)
3. **Value text**: Medium weight (Regular, 16px)
4. **Label text**: Lightest weight (Regular, 14px, muted color)

---

## Related Components

- **Icon Button** - Used for action button in Tile Title
- **Label Value Pair** - Can be used within Card Content area (see examples)
- **Workspace** - Tiles often appear within Workspace containers

---

## Examples

### Common Use Cases

**Finding Card:**
```
Title: "#13243"
Description: "This is some description about the Finding"
Label-Value: "User" → "ChiTech Health System Manager"
```

**Record Summary:**
```
Title: "Incident Report"
Description: "Patient fall in room 305"
Label-Value Pairs:
  "Status" → "Under Review"
  "Date" → "Oct 21, 2025"
  "Assigned To" → "Safety Team"
```

**List Item in Vertical Stack:**
Use Type=With Divider with consistent padding across all items

---

## Version History

- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** 2025-10-22

---

## Notes

- The Tile (Card) Title is an integral part of the Tile (Card) component
- Action icon button is optional and can be hidden if no actions are needed
- The component is highly flexible and can accommodate custom content layouts
- When Title Link=true, the title should navigate to a detail view of the card's content
- Card Content area supports any combination of text, label-value pairs, or custom elements
- For optimal scannability, limit cards to 2-4 label-value pairs
