# Icon Button Component

## Overview
The Icon Button component is a compact, icon-only interactive element used to trigger actions in a space-efficient manner. It provides visual feedback through multiple states and can be configured with different levels of visual prominence through the Subtle variant. The component supports a selected state for toggle-like behavior and includes optional tooltip functionality.

---

## Component Properties

### Visual Variants

#### Subtle Off (Standard)
The default visual prominence level with visible borders and stronger visual presence. Used when the icon button needs to be clearly distinguishable and prominent in the interface.

#### Subtle On (Low Prominence)
A more subdued appearance with reduced visual weight. Used when the icon button should blend more with the interface or when multiple icon buttons are grouped together.

---

### Sizes
The icon button is available in two sizes, both using the same padding:

#### Small
- **Total Size:** 28x28px
- **Icon Size:** 20x20px
- **Padding:** 6px (all sides)
- **Use case:** Dense layouts, toolbars, tables, compact interfaces

#### Large
- **Total Size:** 36x36px
- **Icon Size:** 20x20px (same as small)
- **Padding:** 6px (all sides)
- **Use case:** Primary actions, mobile interfaces, areas requiring larger touch targets

> **Note:** Both sizes use the same icon size (20x20px) and padding (6px). The difference in total size comes from the border and container structure.

---

### Selection State

#### Selected Off
The default state indicating the button is not currently selected or active in a toggle context.

#### Selected On
Indicates the button is currently selected or active, providing visual feedback for toggle-like behavior. This state features a distinct background color to clearly indicate selection.

---

### States
The icon button supports seven interactive states that provide visual feedback:

#### Default
The initial resting state when no user interaction is occurring and the button is not selected.

**Visual Specifications:**
- **Border (Subtle Off):** `nova/icon-button/color/border-muted`
- **Border (Subtle On):** No visible border
- **Icon Color:** `nova/color/typography/base`
- **Icon Size:** 20x20px
- **Padding:** 6px (all sides)

**Use When:**
- Button is ready for interaction
- No selection, hover, focus, or press is active

#### Hover
The state when the user's cursor is positioned over the button.

**Visual Specifications:**
- All Default state properties, plus:
- **Background Overlay (Subtle Off):** `global/color/alpha-dark-blue/400`
- **Background Overlay (Subtle On):** More subdued overlay
- Cursor changes to pointer

**Behavior:**
- Provides visual feedback that button is interactive
- Tooltip may appear on hover (if enabled)

#### Focus
The state when the button receives keyboard focus (via Tab key navigation).

**Visual Specifications:**
- All Default or Hover state properties, plus:
- **Focus Ring:** 1px border using `nova/color/focus`
- **Focus Ring Position:** -1px outside button border
- **Focus Ring Radius:** `nova/radii/component/button`
- Highly visible indication of keyboard focus

**Behavior:**
- Essential for keyboard navigation and accessibility
- Can overlay other states (hover, pressed, selected)
- Must be clearly distinguishable

#### Pressed
The state when the button is actively being clicked or tapped.

**Visual Specifications:**
- All Default state properties, plus:
- **Background Overlay (Subtle Off):** `global/color/alpha-dark-blue/500`
- Provides immediate tactile visual feedback

**Behavior:**
- Active only during click/tap action
- Transitions back to hover or default after release

#### Active
The state when the button represents an active action or mode in the application.

**Visual Specifications:**
- Similar to Pressed state
- Background overlay indicates active mode
- Icon color may remain same or adjust for contrast

**Use When:**
- Button represents currently active tool or mode
- In tool palettes or mode selectors

#### Loading
The state displayed while an asynchronous action is in progress.

**Visual Specifications:**
- **Loading Skeleton Size:** 32x32px (slightly smaller than button container)
- **Background:** `nova/color/skeleton/primary`
- **Border:** `nova/color/skeleton/primary`
- Button maintains overall size (28x28px Small or 36x36px Large)
- Optional tooltip can be displayed with loading information
- Button becomes non-interactive

**Behavior:**
- Indicates action is being processed
- Prevents multiple submissions
- Returns to default state when action completes

#### Disabled
The state when the button is not interactive.

**Visual Specifications:**
- **Icon Color:** `nova/color/skeleton/secondary`
- **Border/Background:** Muted using skeleton colors
- Reduced visual weight (appears muted)
- Cursor indicates non-interactive state
- All interactive states (hover, focus, pressed) are inactive

**Behavior:**
- Button does not respond to user interactions
- Used when action is not currently available
- Should maintain visual structure for layout consistency

---

## Design Tokens

### Typography (Tooltip)
- **Font:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`

### Spacing
- **Padding (all sizes):** 6px (all sides)
- **Internal Gap:** 10px (when multiple elements present)
- **Tooltip Padding Horizontal:** `semantic/spacing/tight`
- **Tooltip Padding Vertical:** `semantic/spacing/next`

### Border & Radius
- **Button Border Radius:** `nova/radii/component/button`
- **Tooltip Border Radius (Subtle Off):** `semantic/radii/softened`
- **Tooltip Border Radius (Subtle On):** `semantic/radii/regular`

### Colors

#### Icon Button Colors
**Border:**
- Border (standard): `nova/icon-button/color/border`
- Border (muted): `nova/icon-button/color/border-muted`

**Icon:**
- Icon color: `nova/color/typography/base`

**Background/States:**
- Background accent: `nova/icon-button/color/accent`
- Alpha overlay (hover - Subtle Off): `global/color/alpha-dark-blue/400`
- Alpha overlay (pressed - Subtle Off): `global/color/alpha-dark-blue/500`
- Solid color (selected): `global/color/dark-blue/700`

**Focus:**
- Focus indicator: `nova/color/focus`

**Disabled:**
- Skeleton/Disabled primary: `nova/color/skeleton/primary`
- Skeleton/Disabled secondary: `nova/color/skeleton/secondary`

#### Surface Colors
- Workspace background: `nova/surfaces/color/workspace`
- Surface background: `nova/surfaces/color/background`

#### Tooltip Colors
- Tooltip background: `nova/tooltip/color/background`
- Tooltip foreground: `nova/tooltip/color/foreground`

---

## Tooltip Feature

The Icon Button supports an optional tooltip that appears on hover or in the loading state to provide additional context about the button's function.

### Tooltip Properties
- **Position:** Appears below the button, centered horizontally
- **Max Width:** 350px
- **Background:** `nova/tooltip/color/background`
- **Text Color:** `nova/tooltip/color/foreground`
- **Font:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`
- **Padding Horizontal:** `semantic/spacing/tight`
- **Padding Vertical:** `semantic/spacing/next`
- **Border Radius:** Varies by Subtle variant
  - Subtle Off: `semantic/radii/softened`
  - Subtle On: `semantic/radii/regular`
- **Shadow:** `0px 2px 4px 0px rgba(0,0,0,0.13)`
- **Pointer:** Small arrow pointing upward to the button

---

## Accessibility Considerations

### Keyboard Navigation
- Button must be focusable via keyboard (Tab key)
- Focus state must be clearly visible with focus ring using `nova/color/focus`
- Enter or Space key should activate the button
- Focus ring appears as 1px border, -1px outside button

### Screen Readers
- Must provide `aria-label` describing the button's action (no visible text)
- Tooltip text can supplement but not replace `aria-label`
- Selected state changes should be announced to screen readers
- Loading state changes should be announced
- Disabled state conveyed using `disabled` attribute

### ARIA Attributes

**Selected State:**
- Use `aria-pressed="true"` for toggle buttons when selected
- Or use `aria-selected="true"` in appropriate contexts (e.g., tool palettes)

**Loading State:**
- Use `aria-busy="true"` during loading
- Optionally use `aria-live="polite"` for status updates

**Disabled State:**
- Use `disabled` attribute on button element
- Button is automatically removed from tab order

**Required:**
- `aria-label` must always be present (e.g., "Search", "Close", "Menu")

---

## Usage Guidelines

### When to Use

**Icon Buttons:**
- For actions that are universally understood by an icon (e.g., search, close, menu)
- In toolbars and action bars where space is limited
- When grouping multiple related actions
- For secondary or tertiary actions that don't require prominent labeling

**Subtle Off:**
- When the icon button needs clear visual definition
- In areas with minimal visual clutter
- When the button is a primary action in its context
- For standalone icon buttons

**Subtle On:**
- When grouping multiple icon buttons together
- In dense interfaces where visual weight should be reduced
- When the button should blend more with the surrounding UI
- Within data tables or lists

**Selected State:**
- For toggle-like functionality (e.g., favorite/unfavorite, bookmark)
- To indicate the current active tool or mode
- In button groups where one option is selected at a time

### Best Practices

#### Do:
- Always provide tooltips or accessible labels for screen readers
- Use universally recognized icons for common actions
- Maintain consistent icon button sizes within the same context
- Use the selected state to provide clear feedback for toggle actions
- Ensure adequate spacing between icon buttons in groups
- Use the loading state for asynchronous actions

#### Don't:
- Use obscure or ambiguous icons without tooltips
- Mix small and large sizes randomly in the same toolbar
- Overuse icon buttons for actions that require text labels
- Rely solely on color to indicate state changes
- Make icons too complex or detailed at small sizes
- Use icon buttons for critical actions without additional confirmation

### Icon Selection
- Use clear, simple, and recognizable icons
- Ensure icons are legible at 20x20px size
- Maintain consistent icon style across the application
- Consider cultural differences in icon interpretation
- Test icons with users to ensure understanding

---

## Content Structure

The icon button contains:
1. **Icon:** The primary visual element (20x20px for both sizes)
2. **Optional Tooltip:** Descriptive text that appears on hover or in loading state
3. **Focus Indicator:** Visual ring that appears when focused
4. **Background/Border:** Visual container that changes based on state and variant

### Icon Requirements
- Size: 20x20px (consistent across both button sizes)
- Format: SVG preferred for scalability and clarity
- Style: Should match the design system's icon library
- Clarity: Must be recognizable and clear at the specified size

---

## Layout Specifications

### Dimensions

**Small Size:**
- **Overall Size:** 28×28px (fixed dimensions)
- **Icon Size:** 20×20px (center aligned)
- **Padding:** 6px (all sides)

**Large Size:**
- **Overall Size:** 36×36px (fixed dimensions)
- **Icon Size:** 20×20px (center aligned)
- **Padding:** 6px (all sides)

### Internal Structure
- Icon is centered within the button using flexbox
- Content uses flexbox with center alignment (both horizontal and vertical)
- Border is applied to the outer container
- Focus indicator appears outside the button border

### Visual Properties
- **Border radius:** `nova/radii/component/button`
- **Border width:** 1px
- **Box-sizing:** border-box
- **Overflow:** clip (hidden)
- **Cursor:** pointer (when not disabled)
- **Focus ring:** 1px border using `nova/color/focus`, positioned -1px outside button

---

## Visual Behavior Notes

### Component Architecture
- Icon Button is a **compact, icon-only** button component with no text label
- Icon size is **fixed at 20×20px** for both Small and Large sizes
- Optional **tooltip** appears on hover to provide context (not part of button structure)
- Focus indicator appears as a **1px ring** outside the button boundary
- Component uses **fixed dimensions** (28×28px Small, 36×36px Large)

### Key Visual Behaviors

**State Transitions:**
- All interactive states use **background overlays** with alpha channels
- Default → Hover: Background overlay (`global/color/alpha-dark-blue/400`) appears
- Hover → Pressed: Background overlay darkens (`global/color/alpha-dark-blue/500`)
- All transitions preserve the base border and icon color

**Subtle Off vs Subtle On:**
- **Subtle Off:** Shows visible border in default state using `nova/icon-button/color/border-muted`
- **Subtle On:** No visible border in default state (more minimal appearance)
- Both variants use same hover/pressed overlays and focus ring behavior

**Focus Indicator:**
- Focus ring is **positioned outside** the button (-1px offset)
- Ring uses `nova/color/focus` token
- Focus ring appears **in addition to** any hover/pressed background overlays

**Loading Overlay:**
- Loading skeleton is **32×32px** (smaller than button container)
- Uses `nova/color/skeleton/primary` for both background and border
- Completely **replaces** button content while loading

**Selection State (Active):**
- Active/selected state uses **solid background** (`global/color/dark-blue/700`)
- Selection state **persists** across interactions (stays selected after click)
- Icon color adjusts for contrast with solid background
- Used in tool palettes or mode selectors

**Tooltip Behavior:**
- Tooltip appears **on hover** to explain icon action
- Tooltip is **separate element**, not part of button structure
- Tooltip text should match button's `aria-label`

### Sizing Behavior
- Icon Button has **fixed dimensions** (not full width or hug contents)
- Small size: **28×28px** fixed
- Large size: **36×36px** fixed
- Icon size remains **constant at 20×20px** regardless of button size
- Padding remains **constant at 6px** regardless of button size
- Larger size increases **visual prominence**, not icon size

---

## State Behavior Details

### Subtle Off Variant

**Default State:**
- Visible border using `nova/icon-button/color/border-muted`
- Icon in base color

**Hover State:**
- Background overlay using `global/color/alpha-dark-blue/400`

**Pressed State:**
- Background overlay using `global/color/alpha-dark-blue/500`

**Selected State:**
- Solid background using `global/color/dark-blue/700`
- Icon color adjusted for contrast

### Subtle On Variant

**Default State:**
- No visible border in default state
- More subtle appearance

**Hover State:**
- Similar visual feedback to Subtle Off but more subdued

**Selected State:**
- Clear visual indication of selection
- Maintains subtle aesthetic

### Common States

**Focus State:**
- Focus ring appears outside the button
- Ring color: `nova/color/focus`
- Ring width: 1px
- Ring offset: -1px (outside the button border)

**Loading State:**
- Shows loading skeleton
- Background: `nova/color/skeleton/primary`
- Border: `nova/color/skeleton/primary`
- Size: 32x32px (appears slightly smaller than button container)
- Optional tooltip can be displayed

**Disabled State:**
- Icon color muted using skeleton colors
- Button is non-interactive
- Cursor indicates disabled state

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** Comprehensive icon button component with Subtle variants, states, sizes, and selection support

---

## Questions or Clarifications
For implementation questions or design clarifications, refer to the design system documentation or consult with the design team to ensure proper token usage and component behavior.
