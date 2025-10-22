# Vertical Navigation

## Overview

The Vertical Navigation component is a composite sidebar navigation system designed for application-level navigation. Some applications use vertical navigation as an alternative to horizontal main navigation. In these cases, the main navigation becomes a vertical menu on the left side of the screen, while the top bar remains mostly the same but without the main navigation items (which have moved to the vertical menu) and with the addition of a hamburger menu for showing/hiding the vertical navigation.

The component consists of a navigation container that houses a list of clickable navigation items. The component supports hierarchical navigation with up to three levels of depth and visual indicators for the currently selected item.

![Vertical Navigation](screenshot-reference)

## Component Structure

This is a **composite component** consisting of:

1. **Navigation Container** - The sidebar frame that contains all navigation items
2. **Navigation List Items** - Individual clickable items that represent navigation links with support for hierarchical levels

## Visual Specifications

### Navigation Container

**Dimensions:**
- Width: `256px`
- Height: Full available viewport height minus header height and margins (8px top + 8px bottom = 16px total)
  - When used with Header Top Nav: Height = `100vh - header height - 16px` (accounting for shared 8px margin between header and nav, plus 8px bottom margin)

**Layout:**
- Display: Flex column
- Gap: `nova/spacing/slight` (2px) - vertical spacing between items
- Padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/near` (16px) vertical
- Alignment: Items aligned to end (right-aligned)

**Positioning & Margins:**
- Margin: `nova/spacing/tight` (8px) on all sides from page edges
- When used with Header Top Nav: The 8px bottom margin of the header and 8px top margin of the vertical nav share the same space, resulting in a total 8px gap between the two components (not 16px)

**Visual Properties:**
- Background: `nova/navigation/secondary` (#eff3f3)
- Border: `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: `nova/radii/softened` (8px)

### Navigation List Items

Navigation items are interactive elements that display with different visual states and hierarchy levels.

**Base Dimensions:**
- Width: `240px` (Child=0), `224px` (Child=1 and Child=2 with adjusted container width)
- Height: `45px`

**Common Layout:**
- Display: Flex row
- Align items: Center
- Justify content: Space between
- Gap (content): `8px` between icon and label
- Padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Border Radius: `nova/radii/softened` (8px)

#### Child=0 (Top Level Navigation)

**Unselected State (Selected=off):**
- Background: Transparent (inherits from container)
- Border: None
- Padding Left: `nova/spacing/tight` (8px)
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 130% line height)
- Icon Size: `20px × 20px`

**Selected State (Selected=on):**
- Background: `global/color/neutral/white` (#ffffff)
- Border: `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: `8px`
- Padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Gap: `12px` (slightly larger than unselected)
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 150% line height)
- Icon Size: `20px × 20px`

#### Child=1 (Second Level Navigation)

**Unselected State (Selected=off):**
- Background: Transparent
- Border: None
- Padding Left: `16px` (creates visual hierarchy with 16px left indent)
- Inner content padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Inner content width: `224px`
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 130% line height)
- Icon Size: `20px × 20px`

**Selected State (Selected=on):**
- Background: `global/color/neutral/white` (#ffffff) on inner content area
- Border: `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: `8px`
- Padding Left: `16px` (outer container)
- Inner content padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Gap: `12px`
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 150% line height)
- Icon Size: `20px × 20px`

#### Child=2 (Third Level Navigation)

**Unselected State (Selected=off):**
- Background: Transparent
- Border: None
- Padding Left: `32px` (creates visual hierarchy with 32px left indent)
- Inner content padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Inner content width: `224px`
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 130% line height)
- Icon Size: `20px × 20px`

**Selected State (Selected=on):**
- Background: `global/color/neutral/white` (#ffffff) on inner content area
- Border: `nova/border/basic` (1px) solid `nova/surfaces/color/workspace-border` (#e0e6e6)
- Border Radius: `8px`
- Padding Left: `32px` (outer container)
- Inner content padding: `nova/spacing/tight` (8px) horizontal, `nova/spacing/close` (12px) vertical
- Gap: `12px`
- Text Color: `nova/navigation/primary` (#0f4146)
- Typography: `nova/typography/base/regular` (14px Regular, 150% line height)
- Icon Size: `20px × 20px`

## Design Tokens Reference

### Colors
- **Primary Navigation Text**: `nova/navigation/primary` (#0f4146)
- **Secondary Navigation Background**: `nova/navigation/secondary` (#eff3f3)
- **Selected Item Background**: `global/color/neutral/white` (#ffffff)
- **Primary Text**: `global/color/green/900` (#042f22)
- **Borders**: `nova/surfaces/color/workspace-border` (#e0e6e6)

### Typography
- **Navigation Labels**: `nova/typography/base/regular` (Font: Geist Regular, Size: 14px, Weight: 400, Line Height: 130% unselected / 150% selected)
- **Font Stack**: `nova/typography/font-stack` (Geist, Arial, 'Helvetica Neue', Helvetica, sans-serif)

### Spacing
- **Tight**: `nova/spacing/tight` (8px) - horizontal padding on items
- **Close**: `nova/spacing/close` (12px) - vertical padding on items
- **Slight**: `nova/spacing/slight` (2px) - gap between items in container
- **Near**: `nova/spacing/near` (16px) - vertical padding on container

### Border Radius
- **Softened**: `nova/radii/softened` (8px) - item and container corners

### Borders
- **Basic**: `nova/border/basic` (1px) - border width

## States

### Selection States
- **Unselected (Selected=off)**: Default state, transparent background, no border
- **Selected (Selected=on)**: Active state, white background with border, elevated appearance

### Hierarchy Levels
- **Child=0**: Top-level navigation items, no left indent
- **Child=1**: Second-level navigation items, 16px left indent
- **Child=2**: Third-level navigation items, 32px left indent

The hierarchy is communicated visually through progressive left padding:
- Child=0: 0px additional indent (base padding only)
- Child=1: 16px left indent + base padding
- Child=2: 32px left indent + base padding

## Content Structure

Each navigation list item contains:

1. **Icon** (20px × 20px)
   - Positioned at the start of the item
   - Icon color should match text color for visual consistency
   - Common icons: User Group, Building, Clipboard, Request, etc.

2. **Label Text**
   - Navigation item name/title
   - Typography: `nova/typography/base/regular` (14px)
   - Color: `nova/navigation/primary` (#0f4146)
   - Displayed to the right of the icon

3. **Optional Action Area** (right side)
   - Space reserved for optional elements like badges, chevrons, or action buttons
   - Gap: `nova/spacing/tight` (8px)
   - Common use: Expand/collapse indicators for items with children

## Variants

The component supports **6 variant combinations** based on two properties:

1. **Selected** (2 options):
   - `off` - Unselected state
   - `on` - Selected/active state

2. **Child** (3 options):
   - `0` - Top level navigation
   - `1` - Second level navigation (16px indent)
   - `2` - Third level navigation (32px indent)

**All Combinations:**
- Selected=off, Child=0
- Selected=off, Child=1
- Selected=off, Child=2
- Selected=on, Child=0
- Selected=on, Child=1
- Selected=on, Child=2

## Interaction Guidelines

### Selection Behavior
- Only one navigation item should be in the selected state at a time
- Clicking an unselected item should:
  - Deselect the currently selected item
  - Apply the selected state to the clicked item
  - Navigate to the corresponding view/page

### Hierarchy Navigation
- Top-level items (Child=0) can contain child items
- Child items (Child=1, Child=2) should be visually indented to show hierarchy
- If a parent item has children, consider adding an expand/collapse indicator

### Hover State (Implementation Guidance)
While not explicitly defined in the design, consider implementing:
- Subtle background color change on hover (lighter shade of selected state)
- Cursor change to pointer
- Smooth transition animation

### Focus State (Accessibility)
- Keyboard navigation support should be implemented
- Visible focus indicator for keyboard users
- Tab order should follow visual hierarchy

## Accessibility

### Semantic HTML
- Use `<nav>` element for the navigation container
- Use `<ul>` and `<li>` for the list structure
- Use proper link elements (`<a>`) or buttons with appropriate roles

### ARIA Attributes
- `role="navigation"` on the container (if not using `<nav>`)
- `aria-current="page"` on the selected navigation item
- `aria-label` or `aria-labelledby` to describe the navigation purpose
- For hierarchical navigation with expandable sections:
  - `aria-expanded` on parent items
  - `aria-controls` to associate parent with child list

### Keyboard Navigation
- **Tab**: Move focus between navigation items
- **Enter/Space**: Activate the focused navigation item
- **Arrow Up/Down**: Move focus between items (optional enhancement)
- For expandable items:
  - **Arrow Right**: Expand collapsed child items
  - **Arrow Left**: Collapse expanded child items

### Visual Considerations
- Sufficient color contrast for text and icons (currently meets WCAG AA)
- Selected state should be distinguishable by more than color alone (uses background + border)
- Focus indicators should be clearly visible
- Icon + text provides redundant information

## Integration with Application Layout

### Hamburger Menu Toggle
The vertical navigation can be hidden by clicking a hamburger menu button at the top of the page. This allows users to maximize screen space for content when needed. When implementing:
- Add a hamburger menu icon button in the top bar
- Implement smooth slide-in/slide-out animation for showing/hiding the navigation
- Consider persisting the user's preference (open/closed state) across sessions
- Ensure keyboard accessibility for the toggle control

### Top Bar Modifications
When using vertical navigation, the top bar (Header Top Nav) should be modified:
- Remove the main navigation items (as they're now in the vertical menu)
- Add a hamburger menu button on the left side
- Keep other top bar elements like search, notifications, and user profile
- The spacing between the header bottom and vertical nav top is a shared 8px (not additive)

### Page Title Positioning
Page titles behave differently when using vertical navigation compared to horizontal navigation:

**Single Workspace:**
- If there is only **1 Workspace** on the page, the page title should be attached to it with a **sticky position**
- The title scrolls with the workspace but remains visible at the top of the viewport

**Multiple Workspaces:**
- If there is **more than 1 Workspace**, the page title should be in a **workspace of its own**
- The title should still have a **sticky position** to remain at the top of the page as content scrolls
- This ensures the user always knows which section they're viewing

Note: The page title **cannot** be attached to the main navigation as it would be in the horizontal navigation case, since the vertical navigation is in a sidebar rather than spanning the top of the page.

## Usage Guidelines

### When to Use
- Application-level primary navigation
- Side navigation with persistent access to main sections
- Multi-level hierarchical navigation structures
- When users need to see the navigation context at all times
- Applications with many top-level sections (more than would fit comfortably in horizontal navigation)
- When you need to support deep hierarchical navigation (2-3 levels)

### When Not to Use
- Simple applications with fewer than 5-6 top-level sections (consider horizontal top navigation)
- Temporary or contextual navigation (use menus or dropdowns)

### Best Practices
1. **Limit Depth**: Avoid going beyond 3 levels of hierarchy (Child=2 is maximum)
2. **Clear Labels**: Use concise, descriptive labels for navigation items
3. **Consistent Icons**: Use icons consistently to aid recognition
4. **Visual Hierarchy**: Leverage indentation to clearly communicate structure
5. **Single Selection**: Only one item should be selected at a time
6. **Responsive Behavior**: Consider collapsing to a hamburger menu on smaller screens
7. **Persistent Container**: The navigation container should remain visible during navigation and fill the available viewport height
8. **Scrollable Content**: Navigation items within the container scroll when content exceeds the fixed container height

### Content Guidelines
- Navigation labels should be 1-2 words when possible
- Use sentence case for labels (e.g., "Requests" not "REQUESTS")
- Group related items together
- Most important items should appear at the top
- Use icons that clearly represent the section/functionality

## Related Components

- **Icon Button** - May be used for collapse/expand controls in the navigation
- **Badge** - Can be added to navigation items to show counts or status
- **Header Top Nav** - Often used together, with vertical navigation for sections and top nav for global actions

## Technical Implementation Notes

### Container Flexibility
- The container height is fixed to the available viewport height (minus header and margins)
- Implement overflow scrolling when navigation items exceed the container height
- The container itself does not expand beyond the viewport; internal content scrolls instead

### Hierarchy Indentation
The hierarchy is achieved through progressive left padding:
- Child=0: `padding-left: 8px` (base only)
- Child=1: `padding-left: 16px` (then inner content at full width minus indent)
- Child=2: `padding-left: 32px` (then inner content at full width minus indent)

