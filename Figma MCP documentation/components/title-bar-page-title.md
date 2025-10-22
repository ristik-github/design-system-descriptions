# Title Bar / Page Title

## Overview
The Title Bar / Page Title component is a flexible header element that displays a title with optional subtitle and action elements. It supports both desktop and mobile layouts, with different visual arrangements optimized for each viewport. The component provides multiple configuration options for showing/hiding various elements like subtitles, badges, action buttons, and context actions.

## Component Properties

### Mobile
Controls the layout variant optimized for different viewports:

**Property:** `mobile` (on/off)
**Default:** `off`

**Mobile = off (Desktop):**
- Title and subtitle displayed in horizontal layout
- Context section has minimum width of 343px
- Actions positioned to the right
- Optimized for wider viewports

**Mobile = on:**
- Same horizontal layout as desktop
- Context section grows to fill available space (basis-0, grow)
- Title and subtitle arrangement consistent with desktop
- Optimized for mobile viewports

### Show Subtitle
Controls whether the subtitle text is displayed below the title:

**Property:** `showSubtitle` (boolean)
**Default:** `true`

**showSubtitle = true:**
- Displays subtitle text below the title
- Uses Base Regular typography style
- Text is muted color with ellipsis overflow

**showSubtitle = false:**
- Subtitle is hidden
- Only title is displayed in the context section

### Show Title Bar Action
Controls whether the title bar action slot is displayed:

**Property:** `showTitleBarAction` (boolean)
**Default:** `true`

**showTitleBarAction = true:**
- Displays the title bar actions slot on the right side
- Slot component or actual actions can be placed here

**showTitleBarAction = false:**
- Action slot is hidden
- Title context takes full width

### Other Properties

**Title Text:**
- **Property:** `title` (string)
- **Default:** "Title"
- Main heading text displayed in the component

**Subtitle Text:**
- **Property:** `subtitle` (string)
- **Default:** "Lorem ipsum"
- Descriptive text displayed below title when showSubtitle=true

**Show Title Action Slot:**
- **Property:** `showTitleActionSlot` (boolean)
- **Default:** `false`
- Controls additional action slot visibility

**Show Sidebar Button:**
- **Property:** `showSidebarButton` (boolean)
- **Default:** `false`
- Controls sidebar toggle button visibility

**Show Badge:**
- **Property:** `showBadge` (boolean)
- **Default:** `false`
- Controls status badge visibility

**Show Back Button:**
- **Property:** `showBackButton` (boolean)
- **Default:** `false`
- Controls back navigation button visibility

## Design Tokens

### Typography

**Title Text:**
- **Font:** `nova/typography/heading/1`
- **Font Family:** Geist
- **Font Size:** 24px
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Color:** `nova/color/typography/base` (#151d1e)

**Subtitle Text:**
- **Font:** `nova/typography/base/regular`
- **Font Family:** Geist
- **Font Size:** `global/typography/fontsize/14` (14px)
- **Line Height:** 130% (1.3)
- **Weight:** Regular (400)
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

### Spacing

**Context Section:**
- **Gap:** `nova/spacing/tight` (8px) - Between title and subtitle

**Mobile=on Variant:**
- **Top-level gap:** `nova/spacing/next` (4px) - Between context and actions

**Actions Slot Wrapper:**
- **Padding horizontal:** `nova/spacing/near` (16px)
- **Padding vertical:** `nova/spacing/tight` (8px)
- **Internal gap:** 10px

### Colors

**Title Text:**
- **Color:** `nova/color/typography/base` (#151d1e)

**Subtitle Text:**
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

**Actions Placeholder:**
- **Color:** `nova/link/color/tertiary` (#7c6fdc)

## Layout Specifications

### Structure - Mobile=off (Desktop)

**Root Container:**
- Horizontal flex layout
- Full width

**Context Section:**
- Horizontal flex layout
- Gap: `nova/spacing/tight` (8px)
- Grows to fill available space (flex-grow)
- Items aligned to end (bottom)
- Text nowrap enabled

**Title Text:**
- Font: Heading 1 style (24px, SemiBold)
- Overflow: Ellipsis
- Text nowrap
- Flex column layout for vertical alignment

**Subtitle Text (when shown):**
- Font: Base Regular style (14px)


**Actions Section (when shown):**
- Positioned to the right of context section
- Slot component displays "Actions" text

### Structure - Mobile=on

**Root Container:**
- Horizontal flex layout
- Full width
- Gap: `nova/spacing/next` (4px)

**Context Section:**
- Horizontal flex layout with flex-wrap
- Gap: `nova/spacing/tight` (8px)
- Basis: 0 (allows equal distribution)
- Grows to fill space (flex-grow)
- Items aligned to end (bottom)
- Text nowrap enabled

**Title Text:**
- Same as desktop variant
- Font: Heading 1 style (24px, SemiBold)
- Overflow: Ellipsis
- Text nowrap

**Subtitle Text (when shown):**
- Same as desktop variant
- Overflow: Ellipsis

**Actions Section (when shown):**
- Positioned after context section
- 4px gap from context

### Dimensions

**Title Text:**
- **Font Size:** 24px
- **Line Height:** 1.4 (33.6px calculated)
- **Height:** Auto (based on line height)

**Subtitle Text:**
- **Font Size:** 14px
- **Line Height:** 1.3 (18.2px calculated)
- **Fixed Height:** 23px
- **Fixed Width:** 84px

**Context Section (Mobile=off):**
- **Minimum Width:** 343px
- **Height:** Auto (based on content)

**Context Section (Mobile=on):**
- **Width:** Flexible (flex-basis: 0, flex-grow: 1)
- **Height:** Auto (based on content)

**Actions Slot:**
- **Height:** Auto (based on content)
- **Width:** Auto (based on content)
- **Padding:** `nova/spacing/near` (16px) horizontal, `nova/spacing/tight` (8px) vertical

### Text Overflow Behavior
- **Title:** Ellipsis overflow with nowrap
- **Subtitle:** Ellipsis overflow with nowrap, fixed dimensions (23px height, 84px width)
- Both use `overflow-ellipsis` and `overflow-hidden` with `text-nowrap`

## Component Architecture

The Title Bar / Page Title is a composite component consisting of:

1. **Context Section**
   - Title text (Heading 1)
   - Subtitle text (Base Regular) - optional
   - Horizontal layout with gap between elements

2. **Actions Section** (optional)
   - Slot component for action buttons or controls
   - Positioned to the right of context section

### Visual Composition

**Mobile=off (Desktop) with Subtitle:**
```
┌──────────────────────────────────────┐
│ Title  Lorem ipsum         [Actions] │
└──────────────────────────────────────┘
     ↑         ↑                  ↑
  24px       14px            slot/actions
  Heading 1  Base Regular
  (Title)    (Subtitle)
```

**Mobile=on with Subtitle:**
```
┌────────────────────────────┐
│ Title  Lorem ipsum         │
│                   [Actions]│
└────────────────────────────┘
```

**Without Subtitle:**
```
┌──────────────────────────────────────┐
│ Title                      [Actions] │
└──────────────────────────────────────┘
```

## Accessibility Considerations

### Semantic Structure
- Use appropriate heading level for title text (typically h1 for page titles)
- Ensure subtitle provides meaningful context for screen readers
- Maintain logical heading hierarchy

### Text Overflow
- Title and subtitle use ellipsis for overflow
- Full text should be accessible via tooltips or screen reader announcement
- Consider aria-label with full text when truncated

### Focus Management
- Actions in the actions section should be keyboard accessible
- Tab order should follow natural visual order: title → actions
- Focus indicators should be visible on interactive elements

## Usage Guidelines

### When to Use

**Title Bar / Page Title Component:**
- Page-level headers with main title
- Section headers requiring title and metadata
- Headers with contextual actions (edit, share, etc.)
- Mobile and desktop responsive layouts

**Mobile=off (Desktop):**
- Desktop and tablet viewports
- When minimum width of 343px is available
- Standard page header layouts

**Mobile=on:**
- Mobile viewports
- Responsive layouts optimizing for narrow screens
- When flexible width distribution is needed

**showSubtitle=true:**
- When additional context is helpful (author, date, description)
- For descriptive metadata below title
- Most use cases requiring context

**showSubtitle=false:**
- When title alone is sufficient
- For simpler, cleaner headers
- When space is limited

### Best Practices

#### Do:
- Use clear, concise titles (1-5 words recommended)
- Provide meaningful subtitles that add context
- Place primary actions in the actions section
- Use appropriate heading level based on page structure
- Consider text truncation for long titles/subtitles
- Use Mobile=on variant for responsive mobile layouts

#### Don't:
- Use excessively long titles (they will truncate with ellipsis)
- Place critical information only in subtitle (it may be hidden)
- Overcrowd the actions section
- Mix mobile and desktop variants inconsistently
- Ignore the minimum width requirement (343px for Mobile=off)

### Content Guidelines

**Title:**
- Keep concise and descriptive
- Use sentence case or title case consistently
- Clearly identify the page or section
- Examples: "User Profile", "Project Dashboard", "Risk Assessment"

**Subtitle:**
- Provide contextual information
- Keep brief to avoid wrapping (84px width limit)
- Use consistent formatting
- Examples: "Last updated today", "Created by John", "Draft version"

## Visual Behavior Notes

### Text Truncation
- Title and subtitle both use ellipsis overflow
- Text nowrap prevents multi-line display
- Maintains single-line, clean appearance
- Consider tooltips for full text display

### Flexible Width
- Desktop variant (Mobile=off) has 343px minimum width for context
- Mobile variant (Mobile=on) uses flex-basis: 0 with grow for equal distribution
- Actions section has fixed width based on content

### Alignment
- All items align to bottom (flex items-end) for baseline alignment
- Title and subtitle positioned horizontally with 8px gap
- Context section and actions section separated by layout gap

## Reference Components

This Title Bar / Page Title component uses the following child components:

1. **Slot Component** (Actions)
   - Placeholder for action buttons or controls
   - Default text: "Actions"
   - Styled with purple color (#7c6fdc)

## Related Components

- **Workspace:** Uses Title Bar as header component
- **Header Top Nav:** Alternative navigation header component
- **Badge:** Can be used within actions section for status
- **Icon Button:** Typically placed in actions section

## Variant Combinations

The Title Bar / Page Title component supports the following variant combinations:

1. **Mobile=off, showSubtitle=true, showTitleBarAction=true** (common desktop)
   - Full desktop layout with title, subtitle, and actions
   - Context section: 343px minimum width
   - All elements visible

2. **Mobile=off, showSubtitle=false, showTitleBarAction=true**
   - Desktop layout with title and actions only
   - No subtitle displayed
   - Cleaner, simpler header

3. **Mobile=off, showSubtitle=true, showTitleBarAction=false**
   - Desktop layout with title and subtitle only
   - No actions section
   - Full-width context

4. **Mobile=on, showSubtitle=true, showTitleBarAction=true** (common mobile)
   - Mobile layout with all elements
   - Flexible width distribution
   - 4px gap between context and actions

5. **Mobile=on, showSubtitle=false, showTitleBarAction=true**
   - Mobile layout with title and actions
   - No subtitle
   - Simpler mobile header

6. **Mobile=on, showSubtitle=true, showTitleBarAction=false**
   - Mobile layout with title and subtitle only
   - No actions
   - Full-width mobile context

## Version History
- **Version 1.0** - Initial title bar / page title component with Mobile (on/off), showSubtitle (true/false), and showTitleBarAction (true/false) variants
