# Title Bar / Section Title

## Overview
The Title Bar / Section Title component is a flexible header element used to present page or section titles with an optional subtitle and action area. It provides three visual hierarchy levels (SH1, SH2, SH3) to support different heading weights, and includes mobile-optimized layouts for responsive designs. The component features title text, optional subtitle, and a buttons container for contextual actions.

## Component Properties

### Variant
Controls the width behavior of the component:

**Property:** `variant` (wide)
**Default:** `wide`

**Variant = wide:**
- Component stretches to fill available width
- Only variant available in the design system

### Hierarchy
Controls the visual weight and size of the title:

**Property:** `hierarchy` (SH1/SH2/SH3)
**Default:** `SH1`

**Hierarchy = SH1:**
- Largest title size using Heading 3 typography (18px)
- Used for primary page titles
- Title minimum height: 28px
- Horizontal layout with title and subtitle side-by-side

**Hierarchy = SH2:**
- Medium title size using Body Strong typography (16px)
- Used for secondary section headings
- Horizontal layout with title and subtitle side-by-side
- Minimum title height: 16px

**Hierarchy = SH3:**
- Same title size as SH2 (Body Strong, 16px)
- Includes decorative horizontal line separator below title area
- Mobile=on variant stacks title and subtitle vertically
- Compact layout for subsection headers

### Mobile
Controls layout optimization for different viewport sizes:

**Property:** `mobile` (on/off)
**Default:** `off`

**Mobile = off:**
- Standard desktop layout
- SH1, SH2: Title and subtitle horizontal with 8px gap
- SH3: Title and subtitle horizontal with 4px gap

**Mobile = on:**
- Mobile-optimized layout
- SH1, SH2: Same horizontal layout as desktop
- SH3: Title and subtitle stack vertically with 4px gap, max-width 260px

### Show Subtitle
Controls whether the subtitle text is displayed:

**Property:** `showSubtitle` (boolean)
**Default:** `true`

**showSubtitle = true:**
- Displays subtitle text using Base Regular typography
- Subtitle uses muted color for visual hierarchy

**showSubtitle = false:**
- Subtitle is hidden
- Only title is displayed

### Other Properties

**Title Text:**
- **Property:** `title` (string)
- **Default:** "Title"
- Main heading text displayed in the component

**Subtitle Text:**
- **Property:** `subtitle` (string)
- **Default:** "Lorem ipsum"
- Descriptive text displayed when showSubtitle=true

**Show Icon/Badge Properties:**
- **showIcon1, showIcon2, showIcon3:** (boolean) - Controls icon visibility
- **showBadge:** (boolean) - Controls badge visibility
- These properties available but not visually demonstrated in base variants

## Design Tokens

### Typography

**Title Text (SH1):**
- **Font:** `nova/typography/heading/3`
- **Font Family:** Geist
- **Font Size:** 18px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Color:** `nova/color/typography/base` (#151d1e)

**Title Text (SH2, SH3):**
- **Font:** `nova/typography/body/strong`
- **Font Family:** Geist
- **Font Size:** 16px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Color:** `nova/color/typography/base` (#151d1e)

**Subtitle Text (All Hierarchies):**
- **Font:** `nova/typography/base/regular`
- **Font Family:** Geist
- **Font Size:** `global/typography/fontsize/14` (14px)
- **Line Height:** 130% (1.3)
- **Weight:** Regular (400)
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

### Spacing

**SH1, SH2 (Mobile=off and Mobile=on):**
- **Gap between title and subtitle:** `nova/spacing/tight` (8px)

**SH3 (Mobile=off):**
- **Gap between title and subtitle:** `nova/spacing/next` (4px)

**SH3 (Mobile=on):**
- **Gap between title and subtitle:** `nova/spacing/next` (4px) - vertical gap when stacked

**Buttons Container (All variants):**
- **Gap:** `nova/spacing/next` (4px)

**Subtitle Container (SH1):**
- **Padding bottom:** 3px - for baseline alignment with title

### Colors

**Title Text:**
- **Color:** `nova/color/typography/base` (#151d1e)

**Subtitle Text:**
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

**Decorative Line (SH3 only):**
- **Color:** `nova/surfaces/color/workspace border` (#e0e6e6)

**Background Tokens (available in design):**
- **Surface:** `nova/surfaces/color/workspace` (#ffffff)
- **Background:** `nova/surfaces/color/background` (#f5f7fa)

### Border & Radius

**Border (SH3 only):**
- **Decorative line:** Horizontal separator below title area
- **Color:** `nova/surfaces/color/workspace border` (#e0e6e6)
- **Height:** 1px

**Radius Token (available in design):**
- **Input radius:** `nova/radii/component/input` (8px)

## Layout Specifications

### Structure - SH1 (All Mobile Variants)

**Root Container:**
- Horizontal flex layout
- Full width

**Title Wrapper:**
- Horizontal flex layout
- Gap: `nova/spacing/tight` (8px)
- Minimum height: 28px
- Grows to fill space (flex-grow, basis-0)
- Items aligned to end (bottom)

**Title Text:**
- Font: Heading 3 (18px SemiBold)
- Overflow: Ellipsis
- Text nowrap
- Flex column for vertical centering

**Subtitle Container (when shown):**
- Horizontal flex layout
- Padding bottom: 3px (baseline alignment)
- Gap: 8px

**Subtitle Text:**
- Font: Base Regular (14px)
- Overflow: Ellipsis
- Text nowrap

**Buttons Container:**
- Horizontal flex layout
- Gap: `nova/spacing/next` (4px)
- Contains spacer or action elements

### Structure - SH2 (Mobile=off and Mobile=on)

**Root Container:**
- Horizontal flex layout
- Full width

**Title and Subtitle Container:**
- Horizontal flex layout with flex-wrap
- Gap: `nova/spacing/tight` (8px)
- Grows to fill space (flex-grow, basis-0)
- Items aligned to end (bottom)
- Text nowrap

**Title Text:**
- Font: Body Strong (16px SemiBold)
- Overflow: Ellipsis
- Text nowrap

**Subtitle Text (when shown):**
- Font: Base Regular (14px)
- Minimum height: 16px
- Overflow: Ellipsis
- Text nowrap

**Buttons Container:**
- Same as SH1
- Gap: `nova/spacing/next` (4px)

### Structure - SH3, Mobile=off

**Root Container:**
- Horizontal flex layout
- Full width

**Title and Subtitle Container:**
- Horizontal flex layout with flex-wrap
- Gap: `nova/spacing/next` (4px)
- Items aligned to end (bottom)
- Text nowrap

**Title Text:**
- Font: Body Strong (16px SemiBold)
- Overflow: Ellipsis
- Text nowrap

**Subtitle Text (when shown):**
- Font: Base Regular (14px)
- Minimum height: 16px
- Overflow: Ellipsis

**Decorative Line:**
- Full width horizontal separator
- Grows to fill space (flex-grow, basis-0)
- Color: `nova/surfaces/color/workspace border` (#e0e6e6)

**Buttons Container:**
- Same as other hierarchies

### Structure - SH3, Mobile=on

**Root Container:**
- Horizontal flex layout
- Full width

**Title and Subtitle Container:**
- **Vertical flex column layout** (different from Mobile=off)
- Gap: `nova/spacing/next` (4px)
- **Maximum width: 260px** (mobile constraint)
- Items aligned to start
- Text nowrap

**Title Text:**
- Font: Body Strong (16px SemiBold)
- Overflow: Ellipsis
- Text nowrap

**Subtitle Text (when shown):**
- Font: Base Regular (14px)
- Minimum height: 16px
- Stacked below title (vertical layout)

**Decorative Line:**
- Same as Mobile=off
- Full width separator

**Buttons Container:**
- Same as other variants

### Dimensions

**SH1 Title:**
- **Font Size:** 18px
- **Line Height:** 1.4 (25.2px calculated)
- **Minimum Height:** 28px

**SH2, SH3 Title:**
- **Font Size:** 16px
- **Line Height:** 1.4 (22.4px calculated)
- **Minimum Height (SH2):** 16px

**Subtitle (All Hierarchies):**
- **Font Size:** 14px
- **Line Height:** 1.3 (18.2px calculated)
- **Minimum Height:** 16px (SH2, SH3)

**SH3 Mobile=on Container:**
- **Maximum Width:** 260px

**Decorative Line (SH3):**
- **Height:** 1px
- **Width:** Full width (grows to fill)

### Text Overflow Behavior
- **Title:** Ellipsis overflow with nowrap
- **Subtitle:** Ellipsis overflow with nowrap
- Both use `overflow-ellipsis` and `overflow-hidden` with `text-nowrap`

## Component Architecture

The Title Bar / Section Title is a composite component consisting of:

1. **Title Wrapper / Container**
   - Title text (Heading 3 or Body Strong based on hierarchy)
   - Subtitle text (Base Regular) - optional
   - Layout varies by hierarchy and mobile setting

2. **Decorative Line** (SH3 only)
   - Horizontal separator below title area
   - Uses workspace border color token

3. **Buttons Container**
   - Slot for action buttons or spacer
   - Positioned to the right of title area

### Visual Composition

**SH1 (All Mobile):**
```
┌──────────────────────────────────────┐
│ Title  Lorem ipsum            [Btns] │
└──────────────────────────────────────┘
   ↑         ↑                     ↑
  18px      14px                spacer/
Heading 3  Base Reg            actions
(8px gap)
```

**SH2 (Mobile=off and Mobile=on):**
```
┌──────────────────────────────────────┐
│ Title  Lorem ipsum            [Btns] │
└──────────────────────────────────────┘
   ↑         ↑                     ↑
  16px      14px                spacer/
Body Strong Base Reg           actions
(8px gap)
```

**SH3, Mobile=off:**
```
┌──────────────────────────────────────┐
│ Title  Lorem ipsum            [Btns] │
├──────────────────────────────────────┤ ← Line
└──────────────────────────────────────┘
   ↑         ↑                     ↑
  16px      14px               separator
(4px gap)                      line below
```

**SH3, Mobile=on:**
```
┌────────────────┬───────────────────┐
│ Title          │              [Btns]│
│ Lorem ipsum    │                    │
├────────────────┴───────────────────┤ ← Line
└──────────────────────────────────────┘
  ↑ (max 260px)
  Stacked vertically
  (4px gap)
```

## Accessibility Considerations

### Semantic Structure
- Map hierarchy to appropriate heading levels:
  - SH1 → h1 or h2 for page titles
  - SH2 → h2 or h3 for section headings
  - SH3 → h3 or h4 for subsection headings
- Ensure logical heading hierarchy in page structure
- Subtitle should be associated with heading (not marked aria-hidden)

### Text Overflow
- Title and subtitle use ellipsis for overflow
- Full text should be accessible via tooltips or screen reader announcement
- Consider aria-label with full text when truncated
- Ensure full text is accessible to assistive technologies

### Focus Management
- Action buttons in buttons container should be keyboard accessible
- Tab order should follow natural visual order: title → actions
- Focus indicators should be visible on interactive elements

### Decorative Elements
- Decorative line separator (SH3) should be marked as presentational
- Spacer images should use aria-hidden or role=presentation

## Usage Guidelines

### When to Use

**Hierarchy = SH1:**
- Primary page titles
- Main section headings
- High-level content organization
- When maximum visual emphasis is needed

**Hierarchy = SH2:**
- Secondary section headings
- Subsection titles within a page
- Medium visual weight needed
- Supporting organizational structure

**Hierarchy = SH3:**
- Compact section headings
- Subsection or card headers
- When decorative separator is appropriate
- Lower visual weight, more compact spacing

**Mobile = off:**
- Desktop and tablet viewports
- Standard responsive layouts
- When horizontal space is available

**Mobile = on:**
- Mobile viewports
- Responsive mobile layouts
- SH3 with stacked title/subtitle (max 260px)

**showSubtitle = true:**
- When additional context is helpful
- Descriptive metadata (author, date, etc.)
- Most use cases requiring context

**showSubtitle = false:**
- When title alone is sufficient
- Cleaner, simpler headers
- Space-constrained layouts

### Best Practices

#### Do:
- Use clear, concise titles
- Choose hierarchy level based on content importance
- Provide meaningful subtitles when needed
- Use SH3 when visual separator is helpful
- Place contextual actions in buttons container
- Use Mobile=on for responsive mobile designs
- Maintain consistent heading hierarchy throughout page

#### Don't:
- Use excessively long titles (they will truncate)
- Skip hierarchy levels (e.g., SH1 → SH3)
- Place critical information only in subtitle
- Overuse SH1 for non-primary headings
- Mix mobile variants inconsistently
- Overcrowd the buttons container

### Content Guidelines

**Title:**
- Keep concise and descriptive
- Use sentence case or title case consistently
- Maximum effectiveness at 1-5 words
- Examples: "User Profile", "Project Dashboard", "Risk Assessment"

**Subtitle:**
- Provide contextual information
- Keep brief to avoid truncation
- Use consistent formatting
- Examples: "Last updated today", "Created by John", "Draft version"

## Visual Behavior Notes

### Text Truncation
- Title and subtitle both use ellipsis overflow
- Text nowrap prevents multi-line display
- Maintains single-line, clean appearance

### Hierarchy Visual Differences
- SH1: Largest at 18px with 28px minimum height
- SH2, SH3: Same size at 16px, differ in spacing and decorative elements
- SH3 includes decorative horizontal line separator

### Mobile Layout Adaptations
- SH1, SH2: Mobile=on uses same layout as Mobile=off
- SH3: Mobile=on stacks title and subtitle vertically with 260px max width
- All variants maintain consistent typography regardless of mobile setting

### Decorative Line (SH3)
- Full-width horizontal separator below title area
- Uses workspace border color (#e0e6e6)
- Provides visual separation for subsections
- Present in both Mobile=off and Mobile=on variants

## Related Components

- **Workspace:** Uses Title Bar / Section Title as header component
- **Title Bar / Page Title:** Alternative page-level title component
- **Icon Button:** Typically placed in buttons container
- **Badge:** Can be used in buttons container for status

## Variant Combinations

The Title Bar / Section Title component supports the following variant combinations:

1. **Variant=wide, Hierarchy=SH1, Mobile=off** (default)
   - Largest title (18px Heading 3)
   - Horizontal layout with 8px gap
   - 28px minimum height

2. **Variant=wide, Hierarchy=SH1, Mobile=on**
   - Same as Mobile=off
   - Optimized for mobile viewports

3. **Variant=wide, Hierarchy=SH2, Mobile=off**
   - Medium title (16px Body Strong)
   - Horizontal layout with 8px gap
   - Flex-wrap enabled

4. **Variant=wide, Hierarchy=SH2, Mobile=on**
   - Same as Mobile=off
   - Mobile viewport optimization

5. **Variant=wide, Hierarchy=SH3, Mobile=off**
   - Compact title (16px Body Strong)
   - Horizontal layout with 4px gap
   - Includes decorative line separator

6. **Variant=wide, Hierarchy=SH3, Mobile=on**
   - Vertical stacked layout
   - Title and subtitle in column with 4px gap
   - Maximum width: 260px
   - Includes decorative line separator

## Version History
- **Version 1.0** - Initial title bar / section title component with Variant (wide), Hierarchy (SH1/SH2/SH3), Mobile (on/off), and showSubtitle (true/false) variants
