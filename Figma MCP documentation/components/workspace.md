# Workspace

## Overview
The Workspace component is a container element that provides a structured area for displaying content with an optional title bar. It supports two padding configurations and can optionally show or hide the title bar, making it flexible for various content display scenarios. The component includes a title bar with heading text, metadata information, a status badge, and a content area.

## Component Properties

### Padding
The Workspace supports two padding configurations:

#### Padding On
- **Content area includes padding:** `nova/spacing/near` (16px) on all sides
- **Use case:** Standard content display with comfortable spacing around the content

#### Padding Off
- **Content area has no padding:** Content extends to the edges
- **Use case:** When content needs to fill the entire workspace (e.g., tables, images, full-width layouts)

### Show Title
Controls whether the title bar is displayed:

**Property:** `showTitle` (boolean)
**Default:** `true`

**showTitle = true:**
- Displays the complete title bar with heading, metadata, badge, and buttons container
- Title bar is separated from content with a bottom border

**showTitle = false:**
- Title bar is hidden
- Content area starts immediately at the top of the workspace

### Content
The content area accepts custom content to be displayed within the workspace:

**Property:** `content` (component/slot)
**Default:** Placeholder text "Workspace content"

## Design Tokens

### Typography

**Title Text:**
- **Font:** `nova/typography/heading/3`
- **Font Size:** 18px (embedded in typography token)
- **Line Height:** 140% (1.4)
- **Weight:** SemiBold (600)
- **Color:** `nova/color/typography/base` (#151d1e)

**Metadata Text:**
- **Font:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14` (14px)
- **Line Height:** 130% (1.3)
- **Weight:** Regular (400)
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

**Badge Text:**
- **Font:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12` (12px)
- **Line Height:** 120% (14px)
- **Weight:** Regular (400)
- **Color:** `nova/color/neutral/dark` (#333b3b)

### Spacing

**Title Bar:**
- **Padding Horizontal:** `nova/spacing/near` (16px)
- **Padding Vertical:** `nova/spacing/close` (12px)
- **Internal gap:** 8px (between title elements)

**Title Wrapper:**
- **Gap:** `nova/spacing/tight` (8px) - Between title and metadata

**Badge:**
- **Padding Horizontal:** `nova/spacing/tight` (8px)
- **Padding Vertical:** `nova/spacing/next` (4px)
- **Internal gap:** `nova/spacing/next` (4px)

**Content Area (Padding=on):**
- **Padding:** `nova/spacing/near` (16px) on all sides
- **Internal gap:** 8px

**Buttons Container:**
- **Gap:** `nova/spacing/next` (4px)

### Colors

**Title Bar:**
- **Background:** `nova/surfaces/color/workspace` (#ffffff)
- **Border Bottom:** `nova/surfaces/color/workspace border` (#e0e6e6)
- **Title Text:** `nova/color/typography/base` (#151d1e)
- **Metadata Text:** `nova/color/typography/muted` (rgba(0,0,0,0.62))

**Badge:**
- **Background:** `nova/color/neutral/secondary` (#f6fafa)
- **Border:** `nova/color/neutral/primary` (#889192)
- **Text:** `nova/color/neutral/dark` (#333b3b)

**Placeholder Content:**
- **Text Color:** `nova/link/color/tertiary` (#7c6fdc)

### Border & Radius

**Workspace:**
- **Border Radius:** `nova/radii/component/workspace` (12px) - Applied to entire component

**Badge:**
- **Border Radius:** `nova/radii/component/badge` (4px)
- **Border Width:** 1px

**Title Bar:**
- **Border Bottom Width:** 1px

## Layout Specifications

### Structure
The Workspace follows a vertical flex layout:

**Root Container:**
- Flex column layout
- Rounded corners using `nova/radii/component/workspace` (12px)
- Overflow clipped to respect border radius

**Title Bar (when showTitle=true):**
- Fixed height: 52px (12px top + 28px content + 12px bottom)
- Full width
- Bottom border for separation
- Horizontal flex layout with three sections:
  1. Title wrapper (grows to fill space)
  2. Badge (fixed width based on content)
  3. Buttons container (fixed width)

**Content Area:**
- Grows to fill remaining vertical space
- Full width
- **Padding=on:** 16px padding on all sides
- **Padding=off:** No padding, content extends to edges

### Title Bar Components

**Title Wrapper:**
- Grows to fill available horizontal space (flex-grow: 1)
- Horizontal flex layout with baseline alignment
- Minimum height: 28px
- Contains:
  1. Title text (Heading 3 style)
  2. Metadata text (Base Regular style)

**Title Text:**
- 18px font size
- Text overflow: Ellipsis
- Nowrap (single line)

**Metadata Text:**
- 14px font size
- Muted color
- Padding bottom: 3px (for baseline alignment with title)

**Badge:**
- Fixed width based on content
- 12px font size
- Padding: 4px vertical, 8px horizontal
- Border: 1px solid neutral primary
- Border radius: 4px

**Buttons Container:**
- Fixed width based on content
- Height: 28px
- Gap: 4px between elements

### Dimensions

**Title Bar:**
- **Height:** Calculated from padding + content
  - Top padding: `nova/spacing/close` (12px)
  - Content: 28px (minimum height based on typography)
  - Bottom padding: `nova/spacing/close` (12px)
  - Total: ~52px
- **Width:** Full width of workspace
- **Border:** 1px bottom

**Content Area:**
- **Height:** Flexible (grows to fill available space)
- **Width:** Full width of workspace
- **Padding (when on):** `nova/spacing/near` (16px) on all sides

**Badge:**
- **Height:** Auto (based on text + padding)
- **Width:** Auto (based on text + padding)
- **Padding vertical:** `nova/spacing/next` (4px)
- **Padding horizontal:** `nova/spacing/tight` (8px)

### Sizing Behavior
- **Width:** Full width (stretches to container)
- **Height:** Flexible (grows with content)
- **Title Bar:** Fixed height when shown
- **Content Area:** Grows to fill remaining space

## Component Architecture

The Workspace is a composite component consisting of:

1. **Title Bar / Section Title** (optional)
   - Title text (Heading 3)
   - Metadata text (author/date information)
   - Status badge
   - Buttons container (for actions)

2. **Content Area**
   - Flexible container for custom content
   - Optional padding based on `padding` prop
   - Supports any content type

### Visual Composition

**With Title (showTitle=true, Padding=on):**
```
┌─────────────────────────────────┐
│ Title Bar (52px)                │
│ ┌─────────────────┬───┬────┐   │
│ │Title + Metadata │Badge│Btns│  │
│ └─────────────────┴───┴────┘   │
├─────────────────────────────────┤ ← Border
│                                 │
│  Content (16px padding)         │
│                                 │
└─────────────────────────────────┘
```

**Without Title (showTitle=false, Padding=off):**
```
┌─────────────────────────────────┐
│                                 │
│  Content (no padding)           │
│                                 │
└─────────────────────────────────┘
```

## Accessibility Considerations

### Semantic Structure
- Use appropriate heading level for title text (typically h2 or h3)
- Ensure logical heading hierarchy in nested content
- Content area should maintain semantic structure

### Text Overflow
- Title text uses ellipsis for overflow (text-overflow: ellipsis)
- Metadata text also truncates with ellipsis
- Consider using tooltips for truncated text
- Ensure full text is accessible via screen readers

### Focus Management
- Buttons in the buttons container should be keyboard accessible
- Tab order should follow natural visual order: title → badge → buttons → content
- Focus indicators should be visible on interactive elements

## Usage Guidelines

### When to Use

**Workspace Component:**
- Primary content containers in applications
- Form containers with title and status
- Card-like content displays with headers
- Sectioned layouts with clear titles

**Padding=on:**
- Standard content display (text, forms, lists)
- When content needs breathing room
- Most use cases

**Padding=off:**
- Full-width tables or data grids
- Images or media that should extend to edges
- Custom layouts that manage their own spacing
- Dense data displays

**showTitle=true:**
- When content needs a clear heading
- When metadata or status information is relevant
- When actions are needed in the title bar

**showTitle=false:**
- When workspace is nested within another titled container
- When title is redundant or unnecessary
- For simple content display without context

### Best Practices

#### Do:
- Use clear, descriptive titles
- Include relevant metadata (author, date, etc.) when applicable
- Use status badges to communicate state clearly
- Choose appropriate padding based on content type
- Ensure content within workspace is well-structured
- Use consistent workspace styling throughout the application

#### Don't:
- Use excessively long titles (they will truncate)
- Mix padding styles inconsistently across similar contexts
- Nest workspaces unnecessarily deep
- Remove title bar when status information is important
- Use workspace for every container (consider simpler containers when appropriate)

### Content Guidelines

**Title:**
- Keep concise (1-5 words recommended)
- Use sentence case
- Describe the content clearly
- Examples: "Risk Form", "User Profile", "Project Details"

**Metadata:**
- Format consistently (e.g., "Name, MM-DD-YYYY")
- Include relevant context (author, date, version)
- Keep brief to avoid wrapping

**Badge:**
- Use for status indicators
- Keep text short (1-2 words)
- Examples: "Incomplete", "Draft", "Active", "Archived"

## Visual Behavior Notes

### Border Radius
- Entire workspace has 12px border radius
- Content area inherits border radius
- Overflow is clipped to maintain rounded corners

### Title Bar Separation
- 1px border bottom creates clear visual separation
- Border uses workspace border color token
- Consistent spacing above and below title elements

### Text Truncation
- Title and metadata use ellipsis overflow
- Text nowrap prevents wrapping
- Maintains single-line display for cleanliness

### Content Flexibility
- Content area grows to fill available vertical space
- Supports any type of content
- Padding only applies when Padding=on

## Reference Components

This Workspace component uses the following child components:

1. **Title Bar / Section Title**
   - Contains title text, metadata, badge, and buttons
   - 52px fixed height
   - Full-width layout with border bottom

2. **Badge**
   - Status indicator component
   - Neutral color variant shown
   - 4px border radius

3. **Slot Component** (Content)
   - Placeholder representing custom content injection area
   - Should be replaced with actual workspace content during implementation

## Related Components

- **Title Bar / Section Title:** The header component used within this workspace
- **Badge:** Used for status indication in the title bar
- **Card:** Similar container component without title bar
- **Panel:** Alternative layout container

## Variant Combinations

The Workspace component supports the following variant combinations:

1. **Padding=on, showTitle=true** (default)
   - Full title bar with all elements
   - Content padding: 16px on all sides
   - Most common use case

2. **Padding=off, showTitle=true**
   - Full title bar with all elements
   - Content extends to edges (no padding)
   - For tables, images, full-width layouts

3. **Padding=on, showTitle=false**
   - No title bar
   - Content padding: 16px on all sides
   - For nested or untitled content

4. **Padding=off, showTitle=false**
   - No title bar
   - Content extends to edges
   - Minimal container use case

## Version History
- **Version 1.0** - Initial workspace component with Padding (on/off) and showTitle (true/false) variants, including title bar with heading, metadata, badge, and buttons container
