# Button Component

## Overview
The Button component is a foundational interactive element used to trigger actions, submit forms, or navigate within the application. It provides multiple visual variants, states, and color options to support various use cases and maintain visual hierarchy.

---

## Component Properties

### Variants
The button supports three distinct visual variants:

#### 1. **Primary**
The primary variant is used for the main call-to-action on a page or within a section. It has the highest visual weight and should be used sparingly to maintain clear hierarchy.

#### 2. **Secondary**
The secondary variant is used for supporting actions that are important but not the primary focus. It has medium visual weight and can be used alongside primary buttons.

#### 3. **Tertiary**
The tertiary variant is used for less prominent actions or auxiliary functions. It has the lowest visual weight and can be used for tertiary actions or within dense UI areas.

---

### Sizes
The button is available in two sizes, each with different padding values:

#### Small
- **Height:** 28px
- **Width:** 59px (minimum, adjusts based on content)
- **Padding Horizontal:** `nova/spacing/tight`
- **Padding Vertical:** `nova/spacing/next`
- **Use case:** Compact layouts, toolbars, table actions, or space-constrained interfaces

#### Large
- **Height:** 36px
- **Width:** 67px (minimum, adjusts based on content)
- **Padding Horizontal:** `nova/spacing/close`
- **Padding Vertical:** `nova/spacing/tight`
- **Use case:** Main content areas, forms, prominent actions, or when larger touch targets are needed

---

### Color Variants
The button supports multiple color options to convey different semantic meanings:

#### Default
The standard color for general actions without specific semantic meaning.

#### Destructive
Used for dangerous or irreversible actions (e.g., delete, remove, cancel).

#### Error
Used to indicate error-related actions or states.

#### Success
Used to indicate positive or successful actions.

#### Neutral
Used for neutral actions that don't carry specific semantic weight.

#### Warning
Used to indicate caution or warning-related actions.

#### Informative
Used for informational actions or to draw attention to information.

#### Feature
Used to highlight new features or promotional actions.

> **Note:** Not all color variants are available for all button variants. Default and Destructive colors are available across all variants (Primary, Secondary, Tertiary), while Error, Success, Neutral, Warning, Informative, and Feature colors are primarily available for the Secondary variant.

---

### States
The button supports six interactive states that provide visual feedback for user interactions:

#### Default
The initial resting state when no user interaction is occurring.

**Visual Specifications:**
- Background color varies by variant and color (see Design Tokens)
- Text color varies by variant and color
- Border (Secondary variant only) using designated color token
- No additional visual effects

**Use When:**
- Button is ready for interaction
- No hover, focus, or press is active

#### Hover
The state when the user's cursor is positioned over the button.

**Visual Specifications:**
- Background color changes to hover state color token
- Text color may change (variant-dependent)
- Cursor changes to pointer
- Provides visual feedback of interactivity

**Behavior:**
- Indicates button is interactive and clickable
- Transitions smoothly from default state

#### Focus
The state when the button receives keyboard focus (via Tab key navigation).

**Visual Specifications:**
- All Default or Hover state properties, plus:
- **Focus indicator:** Visual ring or outline using `nova/color/focus`
- **Focus indicator position:** Outside the button border
- Highly visible indication of keyboard focus

**Behavior:**
- Essential for keyboard navigation and accessibility
- Can overlay other states (hover, pressed)
- Must be clearly distinguishable

#### Pressed
The state when the button is actively being clicked or tapped.

**Visual Specifications:**
- Background color changes to pressed state color token
- Provides immediate tactile visual feedback
- May have subtle transform or scale effect (implementation-specific)

**Behavior:**
- Active only during click/tap action
- Transitions quickly back to hover or default after release

#### Loading
The state displayed while an asynchronous action is in progress.

**Visual Specifications:**
- Button maintains its size and shape
- Loading indicator (spinner or skeleton) displayed
- Button text may be hidden or dimmed
- Button becomes non-interactive
- Visual indication of processing state

**Behavior:**
- Prevents multiple submissions
- Indicates action is being processed
- Returns to default state when action completes

#### Disabled
The state when the button is not interactive.

**Visual Specifications:**
- Background: `nova/color/skeleton/primary` or `nova/color/skeleton/secondary`
- Reduced visual weight (appears muted)
- Cursor indicates non-interactive state
- All interactive states (hover, focus, pressed) are inactive

**Behavior:**
- Button does not respond to user interactions
- Used when action is not currently available
- Should maintain visual structure for layout consistency

---

## Design Tokens

### Typography
- **Font Family & Size:** `nova/typography/instructional/regular`
- **Font Size:** `global/typography/fontsize/14`

### Spacing
- **Gap (internal spacing):** `nova/spacing/next` (applies to all sizes)

**Small Size:**
- **Padding Horizontal:** `nova/spacing/tight`
- **Padding Vertical:** `nova/spacing/next`

**Large Size:**
- **Padding Horizontal:** `nova/spacing/close`
- **Padding Vertical:** `nova/spacing/tight`

### Border & Radius
- **Border Radius:** `nova/radii/component/button`
- **Border Width:** `nova/border/basic`

### Colors

#### Primary Variant
**Default Color:**
- Background (default): `nova/button/primary/default/color/primary`
- Background (hover): `nova/button/primary/default/color/secondary`
- Background (pressed): `nova/button/primary/default/color/tertiary`
- Text: `nova/button/primary/default/color/neutral`

**Destructive Color:**
- Background (default): `nova/button/primary/destructive/color/primary`
- Background (hover): `nova/button/primary/destructive/color/secondary`
- Background (pressed): `nova/button/primary/destructive/color/tertiary`
- Text: `nova/button/primary/destructive/color/neutral`

#### Secondary Variant
**Default Color:**
- Background (default): `nova/button/secondary/default/color/neutral`
- Background (hover): `nova/button/secondary/default/color/tertiary`
- Text/Border: `nova/button/secondary/default/color/primary`
- Text/Border (hover): `nova/button/secondary/default/color/secondary`

**Destructive Color:**
- Background (default): `nova/button/secondary/destructive/color/neutral`
- Background (hover): `nova/button/secondary/destructive/color/tertiary`
- Text/Border: `nova/button/secondary/destructive/color/primary`
- Text/Border (hover): `nova/button/secondary/destructive/color/secondary`

**Error Color:**
- Background: `nova/color/critical/quaternary` (background states)
- Text/Border: `nova/color/critical/primary`
- Accent: `nova/color/critical/accent`

**Success Color:**
- Background: `nova/color/success/quaternary` (background states)
- Text/Border: `nova/color/success/primary`
- Dark accent: `nova/color/success/dark`

**Neutral Color:**
- Background: `nova/color/neutral/quaternary` (background states)
- Text/Border: `nova/color/neutral/primary`
- Dark accent: `nova/color/neutral/dark`

**Warning Color:**
- Background: `nova/color/warning/quaternary` (background states)
- Text/Border: `nova/color/warning/primary`
- Dark accent: `nova/color/warning/dark`

**Informative Color:**
- Background: `nova/color/informative/quaternary` (background states)
- Text/Border: `nova/color/informative/primary`
- Dark accent: `nova/color/informative/dark`

**Feature Color:**
- Background: `nova/color/feature/quaternary` (background states)
- Text/Border: `nova/color/feature/primary`
- Dark accent: `nova/color/feature/dark`

#### Tertiary Variant
**Default Color:**
- Background (default): `nova/button/tertiary/default/color/neutral`
- Background (hover): `nova/button/tertiary/default/color/tertiary`
- Text: `nova/button/tertiary/default/color/primary`
- Text (hover): `nova/button/tertiary/default/color/secondary`

**Destructive Color:**
- Background (default): `nova/button/tertiary/destructive/color/neutral`
- Background (hover): `nova/button/tertiary/destructive/color/tertiary`
- Text: `nova/button/tertiary/destructive/color/primary`
- Text (hover): `nova/button/tertiary/destructive/color/secondary`

#### Focus State
**All Variants:**
- Focus indicator: `nova/color/focus`

#### Disabled State
**All Variants:**
- Skeleton/Disabled primary: `nova/color/skeleton/primary`
- Skeleton/Disabled secondary: `nova/color/skeleton/secondary`

---

## Accessibility Considerations

### Keyboard Navigation
- Button must be focusable via keyboard (Tab key)
- Focus state must be clearly visible using `nova/color/focus`
- Enter or Space key should activate the button

### Screen Readers
- Button text should be clear and descriptive of the action
- If button uses only an icon, provide `aria-label` for screen readers
- Loading state changes should be announced to screen readers
- Disabled state should be conveyed using `disabled` attribute

### ARIA Attributes

**Loading State:**
- Use `aria-busy="true"` during loading
- Optionally use `aria-live="polite"` for status updates

**Disabled State:**
- Use `disabled` attribute on button element
- Button is automatically removed from tab order


---

## Usage Guidelines

### When to Use

**Primary Button:**
- The main action on a page (e.g., "Save", "Submit", "Continue")
- Only one primary button should be visible per section/context

**Secondary Button:**
- Supporting actions (e.g., "Cancel", "Back", "Learn More")
- Can be used multiple times in a section
- Often paired with a primary button

**Tertiary Button:**
- Subtle actions that don't need strong visual emphasis
- Navigation within dense UIs
- Optional or less critical actions

### Best Practices

#### Do:
- Use clear, action-oriented labels (verbs)
- Maintain consistent button usage throughout the application
- Use the appropriate color variant to match the action's intent
- Provide loading feedback for asynchronous actions
- Disable buttons when actions are not available

#### Don't:
- Use multiple primary buttons in the same context
- Use destructive colors for non-destructive actions
- Make button text too long (keep it concise)
- Use buttons for navigation (consider links instead)
- Rely only on color to distinguish button types

### Semantic Meaning
- **Destructive/Error:** Use for actions that delete data, remove items, or cannot be undone
- **Success:** Use for confirmations or completing positive actions
- **Warning:** Use for actions that require caution or might have unexpected consequences
- **Informative:** Use for actions that provide information or help
- **Neutral:** Use for neutral actions without specific semantic weight
- **Feature:** Use to highlight new features or special promotions

---

## Content Structure

The button contains a single text label that describes the action. The label should be:
- **Concise:** Keep text short (1-3 words typically)
- **Action-oriented:** Use verbs that describe what will happen (e.g., "Save", "Delete", "Send")
- **Clear:** Avoid ambiguous language
- **Consistent:** Use similar language for similar actions across the application

---

## Layout Specifications

### Internal Structure
- Text is horizontally and vertically centered within the button
- Content uses flexbox with center alignment
- Gap between elements (if icons are added): `nova/spacing/next`

### Spacing
- Internal gap: `nova/spacing/next` (all sizes)

**Small Size:**
- Horizontal padding: `nova/spacing/tight`
- Vertical padding: `nova/spacing/next`

**Large Size:**
- Horizontal padding: `nova/spacing/close`
- Vertical padding: `nova/spacing/tight`

### Visual Properties
- **Border radius:** `nova/radii/component/button`
- **Border width (Secondary variant only):** `nova/border/basic`
- **Overflow:** Hidden/clipped

### Dimensions

**Small Size:**
- **Height:** 28px
- **Width:** Minimum 59px, adjusts based on content (hug contents)

**Large Size:**
- **Height:** 36px
- **Width:** Minimum 67px, adjusts based on content (hug contents)

---

## Visual Behavior Notes

### Component Architecture
The Button is a single, self-contained component with visual variants (Primary, Secondary, Tertiary), multiple color options, and six interactive states.

**Visual Composition:**
- Text label (centered)
- Optional loading indicator (replaces or overlays text)
- Background with state-dependent colors
- Border (Secondary variant only)
- Focus indicator (when focused)

### Key Visual Behaviors

**State Transitions:**
- Default → Hover: Background color changes to hover token
- Hover → Pressed: Background color changes to pressed token
- Any state → Loading: Loading indicator appears, button becomes non-interactive
- Any state → Disabled: Colors change to skeleton tokens, all interactions disabled
- Focus can overlay any interactive state

**Color Progression (Primary & Secondary):**
- **Default:** Uses primary color token
- **Hover:** Uses secondary color token (darker/different shade)
- **Pressed:** Uses tertiary color token (darkest/most distinct)

**Focus Indicator:**
- Appears outside the button border
- Uses `nova/color/focus` token
- Remains visible when button is focused
- Can combine with hover and pressed states

**Loading State:**
- Button maintains same dimensions
- Loading indicator centered
- Button text may be hidden, dimmed, or remain visible
- Non-interactive during loading

**Disabled State:**
- Visual weight reduced using skeleton color tokens
- All state changes (hover, focus, pressed) are inactive
- Maintains layout structure

### Sizing Behavior
- **Width:** Hug contents (adjusts based on text length)
- **Minimum Width:** 59px (Small), 67px (Large)
- **Height:** Fixed based on size (28px Small, 36px Large)
- **Padding:** Size-specific (see Design Tokens > Spacing)

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** Comprehensive button component with all variants, states, and color options

---

## Questions or Clarifications
For implementation questions or design clarifications, refer to the design system documentation or consult with the design team to ensure proper token usage and component behavior.
