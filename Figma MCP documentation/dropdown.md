# Dropdown Component

## Overview
The Dropdown component is a form input that allows users to select one or multiple options from a list of choices. It includes a label, an input field that displays the current selection or placeholder text, and an expandable dropdown menu containing selectable options. The component supports both single and multi-select modes, and visually displays selected items as removable chips when in filled state.

**Use Cases:** Form selects, filterable option lists, single-choice pickers, multi-select lists, category selection, tag selection, any scenario requiring users to choose from predefined options.

---

## Component Properties

### Dropdown State

#### Dropdown Off
The dropdown menu is collapsed and hidden. Only the input field with label is visible.

**Visual State:**
- Input field shows placeholder text or selected value(s)
- Dropdown icon (chevron) points down
- No dropdown menu visible
- Border color: `nova/input/color/accent` (#c1cacb)

**Use When:**
- Component is in resting state
- User has not clicked to open dropdown
- Selection has been made and dropdown auto-closed

#### Dropdown On
The dropdown menu is expanded and visible below the input field.

**Visual State:**
- Input field shows focus ring
- Border color: `nova/input/color/secondary` (#889192)
- Focus ring: 2px `nova/color/focus` (#9ef1e4)
- Dropdown menu visible below with list of options
- Dropdown menu has shadow: `0px 8px 24px 0px rgba(0,0,0,0.13)`
- First/hovered option highlighted with background color

**Use When:**
- User clicks on the input field
- User uses keyboard to open dropdown (Space/Enter)
- Dropdown is actively being interacted with

---

### Filled State

#### Filled Off
No selection has been made. Input field shows placeholder text.

**Visual Specifications:**
- **Input Field:**
  - Background: `nova/input/color/background` (#ffffff)
  - Border: 1px solid `nova/input/color/accent` (#c1cacb) when closed
  - Border: 1px solid `nova/input/color/secondary` (#889192) when open
  - Border Radius: `nova/radii/component/input` (8px)
  - Padding: `nova/spacing/tight` (8px all sides)
  - Min Height: 36px

- **Placeholder Text:**
  - Typography: `nova/typography/base/regular`
  - Font Size: `global/typography/fontsize/14` (14px)
  - Color: `nova/input/color/placeholder` (#6e7778)
  - Text: "Lorem Ipsum" (example)

- **Dropdown Icon:**
  - Size: 20×20px
  - Chevron down icon
  - Positioned at right side of input

**Use When:**
- Component is newly rendered
- User has cleared their selection
- No default value is set

#### Filled On
One or more selections have been made. Selected items display as chips.

**Visual Specifications:**
- **Chip Container:**
  - Wraps chips in horizontal flex layout
  - Gap between chips: 6px
  - Padding: 4px horizontal, 4px vertical
  - Background: transparent

- **Individual Chip:**
  - Background: `nova/color/neutral/secondary` (#f6fafa)
  - Border: 1px solid `nova/color/neutral/primary` (#889192)
  - Border Radius: 4px
  - Padding Left: `nova/spacing/tight` (8px)
  - Padding Right: `nova/spacing/next` (4px)
  - Padding Vertical: 4px
  - Gap between text and close icon: `nova/spacing/next` (4px)

- **Chip Text:**
  - Typography: Geist Regular
  - Font Size: 12px
  - Color: `nova/color/typography/base` (#151d1e)
  - Line Height: 1 (none)
  - Example: "Venenatis"

- **Chip Close Icon:**
  - Size: 20×20px
  - Small close/X icon
  - Allows removing individual selections

- **Placeholder Text (after chips):**
  - Shows remaining placeholder
  - Same styling as Filled Off placeholder
  - Positioned after chip(s)

**Use When:**
- User has made selection(s)
- Showing current selected value(s)
- Allowing user to remove selections via chip close button

---

### Multi Select Mode

#### Multi Select Off (Single Selection)
Only one option can be selected at a time. Selecting a new option replaces the previous selection.

**Visual Specifications:**
- **Dropdown Menu Options:**
  - No checkboxes visible
  - Options are plain text labels
  - Minimum Height: 32px per option
  - Padding: `nova/spacing/tight` (8px all sides)
  - Border Radius: `nova/spacing/next` (4px)
  - Gap between options: `nova/spacing/next` (4px)

- **Default Option:**
  - Background: transparent
  - Text Color: `nova/link-option/color/neutral` (#151d1e)
  - Typography: `nova/typography/base/regular`
  - Font Size: `global/typography/fontsize/14` (14px)

- **Hover/Selected Option:**
  - Background: `nova/link-option/color/accent` (#e9f7f5)
  - Text Color: same as default
  - Indicates current selection or hover state

**Use When:**
- Only one choice is allowed
- Selecting new option should replace current selection
- Examples: Country selector, status picker, single category

**Behavior:**
- Clicking option selects it and closes dropdown
- Previously selected option is automatically deselected
- Input field shows single selected value (no chip, just text)

#### Multi Select On (Multiple Selection)
Multiple options can be selected simultaneously. Selected items show as chips in the input field.

**Visual Specifications:**
- **Dropdown Menu Options (Unselected):**
  - Checkbox visible at left of each option
  - Checkbox Size: 20×20px
  - Checkbox Border: 1px solid `nova/input/color/accent` (#c1cacb)
  - Checkbox Background: `nova/input/color/background` (#ffffff)
  - Checkbox Border Radius: `nova/radii/component/checkbox` (4px)
  - Gap between checkbox and text: `nova/spacing/tight` (8px)
  - Option Padding: `nova/spacing/tight` (8px all sides)
  - Minimum Height: 32px per option

- **Dropdown Menu Options (Selected):**
  - Option Background: `nova/link-option/color/secondary` (#148d87)
  - Checkbox Background: `nova/input/color/highlight1` (#185956)
  - Checkbox shows white checkmark icon (16×16px)
  - Text Color: `nova/color/static/white` (#ffffff)

- **Hover State (Unselected):**
  - Option Background: `nova/link-option/color/accent` (#e9f7f5)
  - Text Color: `nova/link-option/color/neutral` (#151d1e)
  - Checkbox unchanged

**Use When:**
- Multiple choices are allowed
- User needs to select several options from list
- Examples: Tag selector, multi-category filter, skill picker

**Behavior:**
- Clicking option toggles checkbox on/off
- Dropdown remains open after selection
- Each selected option creates a chip in input field
- Chips can be removed individually via close icon
- Removing chip unchecks option in dropdown

---

## Design Tokens

### Typography

**Label Text:**
- **Token:** `nova/typography/body/regular`
- **Font Size:** 16px
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Line Height:** 1.4
- **Usage:** Field label above input

**Input Placeholder/Selected Text:**
- **Token:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14` (14px)
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Line Height:** 1.3
- **Usage:** Placeholder text and selected value in input field

**Dropdown Option Text:**
- **Token:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14` (14px)
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Line Height:** 1.3
- **Usage:** Text in dropdown menu options

**Chip Text:**
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Font Size:** 12px
- **Line Height:** 1 (none)
- **Usage:** Selected item text in chips

---

### Colors

**Input Background:**
- **Token:** `nova/input/color/background`
- **Value:** #ffffff
- **Usage:** Input field background, dropdown menu background, checkbox background

**Input Border (Closed):**
- **Token:** `nova/input/color/accent`
- **Value:** #c1cacb
- **Usage:** Input field border when dropdown is closed

**Input Border (Open):**
- **Token:** `nova/input/color/secondary`
- **Value:** #889192
- **Usage:** Input field border when dropdown is open/focused

**Focus Ring:**
- **Token:** `nova/color/focus`
- **Value:** #9ef1e4
- **Usage:** Focus indicator around input when dropdown is open

**Placeholder Text:**
- **Token:** `nova/input/color/placeholder`
- **Value:** #6e7778
- **Usage:** Placeholder text in input field

**Label Text:**
- **Token:** `nova/color/typography/base`
- **Value:** #151d1e
- **Usage:** Field label, chip text, dropdown option text (default)

**Dropdown Option Hover/First Item Background:**
- **Token:** `nova/link-option/color/accent`
- **Value:** #e9f7f5
- **Usage:** Background color for hovered or first dropdown option

**Dropdown Option Selected Background (Multi-select):**
- **Token:** `nova/link-option/color/secondary`
- **Value:** #148d87
- **Usage:** Background color for selected options in multi-select mode

**Dropdown Option Selected Text (Multi-select):**
- **Token:** `nova/color/static/white`
- **Value:** #ffffff
- **Usage:** Text color for selected options in multi-select mode

**Checkbox Selected Background:**
- **Token:** `nova/input/color/highlight1`
- **Value:** #185956
- **Usage:** Checkbox background when checked in multi-select

**Chip Background:**
- **Token:** `nova/color/neutral/secondary`
- **Value:** #f6fafa
- **Usage:** Background color for selection chips

**Chip Border:**
- **Token:** `nova/color/neutral/primary`
- **Value:** #889192
- **Usage:** Border color for selection chips

---

### Spacing

**Input Padding:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Padding inside input field (all sides)

**Dropdown Option Padding:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Padding inside each dropdown option (all sides)

**Dropdown Menu Padding:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Padding around dropdown menu content

**Gap Between Options:**
- **Token:** `nova/spacing/next`
- **Value:** 4px
- **Usage:** Vertical gap between dropdown options

**Gap Between Checkbox and Text:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Horizontal gap between checkbox and option text in multi-select

**Gap Between Label and Input:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Vertical gap between label and input field

**Gap Between Chips:**
- **Value:** 6px
- **Usage:** Horizontal gap between selection chips

**Chip Padding Horizontal:**
- **Left:** `nova/spacing/tight` (8px)
- **Right:** `nova/spacing/next` (4px)
- **Usage:** Horizontal padding in chips

**Chip Padding Vertical:**
- **Value:** 4px
- **Usage:** Vertical padding in chips

**Chip Internal Gap:**
- **Token:** `nova/spacing/next`
- **Value:** 4px
- **Usage:** Gap between chip text and close icon

---

### Borders & Radii

**Input Border Width:**
- **Token:** `nova/border/basic`
- **Value:** 1px
- **Usage:** Input field border width

**Input Border Radius:**
- **Token:** `nova/radii/component/input`
- **Value:** 8px
- **Usage:** Input field corners

**Dropdown Menu Border Radius:**
- **Token:** `nova/radii/softened`
- **Value:** 8px
- **Usage:** Dropdown menu container corners

**Dropdown Option Border Radius:**
- **Token:** `nova/spacing/next`
- **Value:** 4px
- **Usage:** Individual option item corners (for hover/selected background)

**Checkbox Border Radius:**
- **Token:** `nova/radii/component/checkbox`
- **Value:** 4px
- **Usage:** Checkbox corners in multi-select mode

**Chip Border Radius:**
- **Value:** 4px
- **Usage:** Selection chip corners

**Focus Ring Width:**
- **Value:** 2px
- **Usage:** Focus indicator border width

---

### Effects

**Dropdown Menu Shadow:**
- **Value:** `0px 8px 24px 0px rgba(0,0,0,0.13)`
- **Usage:** Shadow around dropdown menu when open

---

## Layout Specifications

### Structure
The dropdown component consists of three main sections:

1. **Form Field Container:**
   - Vertical flex layout (column)
   - Gap: `nova/spacing/tight` (8px)
   - Minimum Width: 120px
   - Full width of parent container

2. **Label Row:**
   - Horizontal flex layout
   - Contains label text
   - Gap: 10px (for optional elements like required indicator)

3. **Input Field:**
   - Horizontal flex layout
   - Background: white
   - Border: 1px solid (color depends on open/closed state)
   - Border Radius: 8px
   - Min Height: 36px
   - Padding: 8px all sides
   - Contains: placeholder/chips + dropdown icon

4. **Dropdown Menu (when open):**
   - Absolutely positioned below input field
   - Position: Top 68px (below form field)
   - Left: 0, Right: 0 (full width of input)
   - Max Height: 372px
   - Overflow: auto (scrollable if needed)
   - Background: white
   - Shadow: 0px 8px 24px rgba(0,0,0,0.13)
   - Border Radius: 8px
   - Padding: 8px
   - Z-index layering for options

5. **Chip Container (when filled):**
   - Horizontal flex wrap layout
   - Gap: 6px between chips
   - Padding: 4px
   - Positioned inside input field

### Dimensions

**Input Field:**
- **Width:** Full width of container
- **Min Height:** 36px
- **Padding:** 8px (all sides)

**Dropdown Icon:**
- **Size:** 20×20px
- **Position:** Right side of input

**Dropdown Menu:**
- **Width:** Matches input field width
- **Max Height:** 372px (scrollable if more options)
- **Position:** Below input with 2px gap

**Dropdown Option:**
- **Min Height:** 32px
- **Width:** Full width of dropdown menu
- **Padding:** 8px (all sides)

**Checkbox (Multi-select):**
- **Size:** 20×20px
- **Border:** 1px solid
- **Border Radius:** 4px

**Checkmark Icon (when checked):**
- **Size:** 16×16px
- **Centered in checkbox**

**Selection Chip:**
- **Height:** Auto (based on text + padding)
- **Padding:** 8px left, 4px right, 4px vertical
- **Border:** 1px solid
- **Border Radius:** 4px

**Chip Close Icon:**
- **Size:** 20×20px

---

## Accessibility Considerations

### Label Association
- Label must be properly associated with input field
- Use `for` attribute on label pointing to input `id`
- Or wrap label around input structure

### Keyboard Navigation
- **Tab:** Moves focus to/from dropdown
- **Space/Enter:** Opens dropdown menu when closed
- **Arrow Up/Down:** Navigate through options when open
- **Space/Enter:** Select highlighted option
- **Escape:** Close dropdown without selection
- **Tab:** Close dropdown and move to next focusable element

### Screen Readers
- Input field should announce current selection or placeholder
- Opening dropdown should announce "listbox expanded" or "menu opened"
- Options should be announced as user navigates
- Selected state should be announced ("checked" for multi-select)
- Chip removal should announce "removed [option name]"

### Focus Management
- Focus ring must be clearly visible when dropdown is open
- Focus should move to first option when dropdown opens
- Focus should return to input when dropdown closes
- Removing chip should maintain focus on input

### ARIA Attributes

**Input Field:**
- `role="combobox"` - Indicates combo box pattern
- `aria-expanded="false"` - When dropdown is closed
- `aria-expanded="true"` - When dropdown is open
- `aria-haspopup="listbox"` - Indicates dropdown menu type
- `aria-labelledby` - Points to label element ID
- `aria-controls` - Points to dropdown menu element ID
- `aria-activedescendant` - Points to currently focused option (when open)

**Dropdown Menu:**
- `role="listbox"` - For single select
- `role="listbox"` with `aria-multiselectable="true"` - For multi-select
- Hidden when `dropdown=off`

**Dropdown Options:**
- `role="option"` - Each selectable option
- `aria-selected="true"` - When option is selected
- `aria-selected="false"` - When option is not selected

**Checkboxes (Multi-select):**
- `role="checkbox"` - For each checkbox
- `aria-checked="true"` - When checked
- `aria-checked="false"` - When unchecked

**Chips:**
- Each chip should have accessible label
- Close button should have `aria-label="Remove [option name]"`
- Close button should be keyboard accessible (Tab + Enter/Space)

---

## Usage Guidelines

### When to Use

**Single Select Dropdown (Multi select=off):**
- User must choose exactly one option from a list
- Options are mutually exclusive
- Examples: Country, State, Status, Priority, Category

**Multi Select Dropdown (Multi select=on):**
- User can choose multiple options from a list
- Multiple simultaneous selections are valid
- Examples: Tags, Skills, Categories, Filters, Interests

**With Chips (Filled=on):**
- Showing selected values prominently
- Allowing easy removal of selections
- When multiple selections create meaningful context
- Space allows for displaying chips

### Best Practices

#### Do:
- Provide clear, descriptive label for the dropdown
- Use placeholder text that hints at expected input
- Keep option text concise and scannable
- Order options logically (alphabetical, by frequency, by category)
- Show visual feedback for hover and selected states
- Allow keyboard navigation for all interactions
- Provide clear visual distinction between selected/unselected in multi-select
- Use chips to show selected items clearly
- Make chip close icons easy to click/tap
- Consider default selections for common use cases
- Limit dropdown height and make it scrollable for long lists

#### Don't:
- Use dropdown for 2-3 options (use radio buttons or tabs instead)
- Create extremely long option lists without search/filter
- Use vague placeholder text like "Select..."
- Hide selected values in multi-select
- Make chips too large or cluttered
- Forget to handle overflow for many selections
- Use dropdown when free text input is more appropriate
- Make options too similar or ambiguous
- Forget focus states and keyboard accessibility

### Content Guidelines

**Label Text:**
- **Be specific:** "Country" not "Select an option"
- **Keep it short:** 1-3 words when possible
- **Use sentence case:** "Preferred language" not "Preferred Language"

**Placeholder Text:**
- **Be instructive:** "Select a category" or "Choose options"
- **Don't repeat label:** If label is "Country", don't use "Select country"
- **Be concise:** Should fit in input without truncation

**Option Text:**
- **Be clear and distinct:** Each option should be unambiguous
- **Use consistent formatting:** All options in same case, structure
- **Keep it scannable:** Short enough to read quickly
- **Order logically:** Alphabetical, by frequency, or by relevance

**Chip Text:**
- Uses the option text automatically
- Should be kept short to prevent chip overflow
- Long text should truncate with ellipsis if needed

---

## Component Structure

The Dropdown component consists of:

1. **Form Field Container (Required)**
   - Wraps entire component
   - Provides structural layout

2. **Label (Required)**
   - Text label above input
   - Describes the field purpose

3. **Input Field (Required)**
   - Shows placeholder or selected value(s)
   - Contains dropdown icon
   - Shows chips when filled (multi-select)
   - Clickable to open dropdown

4. **Dropdown Icon (Required)**
   - Chevron down icon (20×20px)
   - Positioned at right of input
   - Indicates expandable menu

5. **Dropdown Menu (Conditional - when dropdown=on)**
   - List of selectable options
   - Positioned below input field
   - Scrollable if exceeds max height
   - Has shadow for elevation

6. **Dropdown Options (Required in menu)**
   - Individual selectable items
   - May include checkboxes (multi-select mode)
   - Hover and selected states

7. **Checkboxes (Conditional - when multi select=on)**
   - Appear before option text
   - Show checked/unchecked state
   - 20×20px with checkmark when selected

8. **Chips (Conditional - when filled=on)**
   - Display selected options
   - Include close icon for removal
   - Wrap horizontally in input field

9. **Chip Close Icon (Required in chips)**
   - Small X icon (20×20px)
   - Removes selection when clicked

---

## Visual Behavior Notes

### Component Architecture
The Dropdown is a **composite form component** combining a label, input field, dropdown menu, and optional chips for showing selections.

**Visual Composition:**
- Label + Input field (always visible)
- Dropdown menu (conditionally visible when open)
- Chips (conditionally visible when selections made in multi-select)
- Focus ring (conditionally visible when input focused)

### Key Visual Behaviors

**Dropdown Open/Close:**
- **Closed:** Input shows placeholder or selected text, border is `nova/input/color/accent`
- **Open:** Input shows focus ring (2px `nova/color/focus`), border changes to `nova/input/color/secondary`, dropdown menu appears below with shadow
- Opening animates menu into view (implementation detail, not specified in Figma)

**Single vs Multi-Select:**
- **Single Select:** No checkboxes, clicking option selects it and closes dropdown, input shows selected value as text
- **Multi-Select:** Checkboxes visible, clicking toggles checkbox, dropdown stays open, input shows chips for selections

**Selection Display:**
- **Filled Off:** Placeholder text visible in input
- **Filled On (Single):** Selected option text replaces placeholder
- **Filled On (Multi):** Selected options display as chips, placeholder shows after chips

**Chip Behavior:**
- Chips appear in horizontal wrapping layout
- Each chip has close icon on right
- Clicking close icon removes that selection
- Removing chip unchecks corresponding option in dropdown
- Chips have subtle background and border for visual separation

**Option States:**
- **Default:** Transparent background, black text
- **Hover:** Light teal background (`nova/link-option/color/accent`)
- **Selected (Single):** Same as hover
- **Selected (Multi):** Dark teal background (`nova/link-option/color/secondary`), white text, checkbox filled with checkmark

**Checkbox States:**
- **Unchecked:** White background, gray border
- **Checked:** Dark teal background (`nova/input/color/highlight1`), white checkmark icon (16×16px)

**Focus Ring:**
- Appears **inside** the input field border when dropdown is open
- 2px width, `nova/color/focus` color (#9ef1e4)
- Matches input border radius (8px)

**Dropdown Menu Scrolling:**
- Max height: 372px
- If options exceed max height, vertical scrollbar appears
- Padding maintained (8px around content)
- Options remain full width even with scrollbar

**Z-Index Layering:**
- Dropdown menu appears above other content
- Each option has z-index to maintain stacking order
- Selected/hovered option may appear slightly elevated

### Sizing Behavior
- **Width:** Full width of parent container (fill container)
- **Height:** Auto-adjusts based on content
  - Minimum: 36px input height + label
  - With chips: Expands to accommodate wrapped chips
- **Dropdown Menu:** Matches input width, max 372px height

---

## Reference Components
This component references or includes:
- **Form Label** - Used for the label text above input
- **Text Input** - Base structure for the input field
- **Checkbox** - Used in multi-select mode for option selection

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** Comprehensive dropdown component with single/multi-select modes, filled states, chips, and dropdown menu

---

## Questions or Clarifications
For implementation questions or design clarifications:
- Verify dropdown opening/closing animation behavior with design team
- Confirm maximum number of chips to display before wrapping or truncating
- Check search/filter functionality (not visible in current Figma component)
- Validate error state behavior (not shown in current variants)
- Confirm disabled state styling (not shown in current variants)
- Verify maximum dropdown menu width constraints
