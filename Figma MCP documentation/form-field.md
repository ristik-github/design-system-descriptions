# Form Field Component

## Overview
The Form Field component is a complete, unified form input element that combines a label with an input field to create accessible, consistent form controls. It is designed as a single, cohesive component from an implementation perspective, though it incorporates label variants and input states as configurable properties. The component supports different input types (text, number, date, email, etc.) and includes optional features such as help text, badges, and tooltips.

**Implementation Approach:** While built from modular pieces in Figma (Label + Input), this component should be implemented as **one unified component** with configurable properties for label variants, input states, and optional features.

**Use Cases:** Text input, email input, password input, number input, date input, telephone input, URL input, and other single-line data entry fields.

---

## Component Properties

### Label Variants
The label portion of the form field supports three visual variants to indicate field requirement status:

#### Default
Plain label text without any requirement indicator.

**Visual Specifications:**
- **Typography:** `nova/typography/body/regular`
- **Text Color:** `nova/color/typography/base`
- **Content:** Label text only

**Use When:**
- All fields in the form have the same requirement status
- Requirement is communicated at the form level
- In compact forms where indicators would add clutter

#### Required
Label with a red asterisk (*) indicator to denote mandatory fields.

**Visual Specifications:**
- **Label Typography:** `nova/typography/body/regular`
- **Label Text Color:** `nova/color/typography/base`
- **Asterisk Typography:** `nova/typography/base/strong`
- **Asterisk Font Size:** `global/typography/fontsize/14`
- **Asterisk Color:** `nova/color/critical/primary`
- **Gap between label and asterisk:** 10px
- **Content:** Label text + red asterisk (*)

**Use When:**
- Mixing required and optional fields (when required fields are fewer)
- Want to emphasize mandatory data collection
- Following standard form conventions

**Accessibility:**
- Must also include `aria-required="true"` on input element
- Asterisk is visual only; screen reader support requires programmatic indication

#### Optional
Label with gray "optional" text to denote non-mandatory fields.

**Visual Specifications:**
- **Label Typography:** `nova/typography/body/regular`
- **Label Text Color:** `nova/color/typography/base`
- **"Optional" Typography:** `nova/typography/supporting/regular`
- **"Optional" Font Size:** `global/typography/fontsize/12`
- **"Optional" Text Color:** `nova/color/typography/muted`
- **Gap between label and "optional":** 10px
- **Content:** Label text + "optional" (lowercase, gray)

**Use When:**
- Most fields are required and you want to highlight exceptions
- Better accessibility (clearer language than asterisk)
- Reducing visual clutter from multiple asterisks

---

### Input States
The input portion of the form field supports seven interactive states:

#### Default
The initial resting state when not being interacted with.

**Visual Specifications:**
- **Background:** `nova/input/color/background`
- **Border:** `nova/input/color/accent`
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/input`
- **Padding:** `nova/spacing/tight` (8px all sides)
- **Text (empty):** Placeholder using `nova/input/color/placeholder`
- **Text (filled):** User content using `nova/color/typography/base`
- **Typography:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14`

#### Hover
The state when cursor is over the input field.

**Visual Specifications:**
- Same as Default state
- May include subtle visual feedback (implementation-specific)
- Indicates interactivity to user

#### Focus
The state when input is actively selected and ready for input.

**Visual Specifications:**
- **All Default state properties, plus:**
- **Focus Ring:** 2px border using `nova/color/focus`
- **Focus Ring Position:** Outside the input border
- **Border Radius:** `nova/radii/component/input` (matches input)
- Highly visible indication of active field

#### Error
The state when validation has failed or input is invalid.

**Visual Specifications:**
- **All Default state properties, except:**
- **Border Color:** `nova/color/critical/primary` (red border)
- Should be accompanied by error message below the input
- Indicates validation failure

#### Focus (Error)
The combined state when an errored input receives focus.

**Visual Specifications:**
- **Border Color:** `nova/color/critical/primary`
- **Focus Ring:** 2px border using `nova/color/focus`
- Both error border and focus ring visible simultaneously

#### Disabled
The state when input is not interactive.

**Visual Specifications:**
- **Background:** `nova/input/color/disabled`
- **Border:** `nova/input/color/accent` (or muted variant)
- **Text Color:** `nova/color/typography/muted`
- **Icon Color (if shown):** `nova/color/skeleton/secondary`
- **Cursor:** Indicates non-interactive state
- Input does not accept focus or input

#### Readonly
The state when field displays data but doesn't allow editing.

**Visual Specifications:**
- **Empty state:** Displays hyphen "-" using `nova/input/color/placeholder`
- **Filled state:** Displays content using `nova/color/typography/base`
- **No icon displayed**
- May have distinct styling to indicate read-only nature
- Field cannot be edited but may show focus states

---

### Filled Conditions

#### Filled Off (Empty)
- Input is empty and shows placeholder text
- **Placeholder Color:** `nova/input/color/placeholder`
- **Placeholder Text:** Example or format hint (e.g., "john@example.com", "MM/DD/YYYY")

#### Filled On (Has Content)
- Input contains user-entered data
- **Text Color:** `nova/color/typography/base`
- Placeholder is hidden
- Content is visible and editable (unless readonly/disabled)

---

### Optional Features

#### Show Icon
Controls whether an icon is displayed within the input field (typically on the right side).

**Property:** `showIcon` (boolean)
**Default:** `false` (in Form Field context)

**Note:** The Form Field sets `showIcon` to `false` by default. This is appropriate for standard text inputs. For dropdown/select fields, use the Select component instead.

**When to Enable:**
- Custom icon indicators (search icon, calendar icon, etc.)
- Specialized input types requiring visual cues

**Icon Specifications:**
- **Size:** 20x20px
- **Position:** Right side of input
- **Default icon color:** `nova/input/color/secondary`
- **Disabled icon color:** `nova/color/skeleton/secondary`

#### Show Clear Button
Displays a clear/close button to quickly empty the input.

**Property:** `showClearButton` (boolean)
**Default:** `false`

**When to Enable:**
- Search fields
- Filters
- Fields where quick clearing is beneficial

#### Show Help Text
Displays additional guidance below the input field.

**Property:** `showHelpText` (boolean)
**Default:** `false`

**Use For:**
- Format requirements (e.g., "Password must be at least 8 characters")
- Examples of valid input
- Important context users need before filling

#### Show Badge
Displays a visual indicator near the label.

**Property:** `showBadge` (boolean)
**Default:** `false`

**Use For:**
- Alternative required field indication
- "New" or "Updated" field markers
- Special status indicators

#### Show Tooltip
Displays an interactive tooltip with additional information.

**Property:** `showTooltip` (boolean)
**Default:** `false`

**Use For:**
- Detailed explanations that would clutter the UI
- Extended help that's not always needed
- Technical details or jargon explanations

---

### Input Type
The type of data being collected, which may affect validation and input behavior.

**Property:** `inputType` (string or component reference)
**Supported Types:**
- `text` - General text (default)
- `email` - Email addresses
- `password` - Masked password entry
- `tel` - Telephone numbers
- `url` - Web addresses
- `number` - Numeric values
- `date` - Date selection (may integrate with date picker)
- Custom input components as needed

**Note:** For dropdown/select inputs, use the dedicated Select component instead of Form Field with `showIcon=true`.

---

## Design Tokens

This section consolidates all design tokens used across both the label and input portions of the unified Form Field component.

### Typography

#### Label Typography
**Base Label Text:**
- **Token:** `nova/typography/body/regular`
- **Usage:** All label variants (Default, Required, Optional)

**Required Indicator (Asterisk):**
- **Token:** `nova/typography/base/strong`
- **Font Size:** `global/typography/fontsize/14`
- **Usage:** Asterisk (*) in Required variant

**Optional Indicator:**
- **Token:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`
- **Usage:** "optional" text in Optional variant

#### Input Typography
**Input Text:**
- **Token:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14`
- **Usage:** User-entered content and placeholder text

---

### Colors

#### Label Colors
**Label Text:**
- **Token:** `nova/color/typography/base`
- **Usage:** Label text in all variants

**Required Asterisk:**
- **Token:** `nova/color/critical/primary`
- **Usage:** Red asterisk in Required variant

**Optional Text:**
- **Token:** `nova/color/typography/muted`
- **Usage:** Gray "optional" text in Optional variant

#### Input Colors

**Background:**
- **Token:** `nova/input/color/background`
- **Usage:** Input field background (all non-disabled states)

**Disabled Background:**
- **Token:** `nova/input/color/disabled`
- **Usage:** Input field background when disabled

**Border - Default:**
- **Token:** `nova/input/color/accent`
- **Usage:** Border in Default, Hover, Focus, Disabled, Readonly states

**Border - Error:**
- **Token:** `nova/color/critical/primary`
- **Usage:** Border in Error and Focus (Error) states

**Focus Ring:**
- **Token:** `nova/color/focus`
- **Usage:** 2px focus ring in Focus and Focus (Error) states

**Text - Placeholder:**
- **Token:** `nova/input/color/placeholder`
- **Usage:** Placeholder text when empty, hyphen in readonly empty state

**Text - Filled:**
- **Token:** `nova/color/typography/base`
- **Usage:** User-entered content

**Text - Disabled:**
- **Token:** `nova/color/typography/muted`
- **Usage:** Text when input is disabled

**Icon - Default:**
- **Token:** `nova/input/color/secondary`
- **Usage:** Icons when input is not disabled (if showIcon=true)

**Icon - Disabled:**
- **Token:** `nova/color/skeleton/secondary`
- **Usage:** Icons when input is disabled (if showIcon=true)

---

### Spacing

**Gap between Label and Input:**
- **Token:** `nova/spacing/tight`
- **Value Context:** 8px (vertical spacing)

**Gap between Label and Indicators:**
- **Value:** 10px (horizontal spacing)
- **Usage:** Space between label text and asterisk (*) or "optional" text

**Input Padding:**
- **Token:** `nova/spacing/tight`
- **Value Context:** 8px all sides

---

### Borders & Radii

**Border Width:**
- **Token:** `nova/border/basic`
- **Usage:** Input border in all states

**Border Radius:**
- **Token:** `nova/radii/component/input`
- **Usage:** Input corners and focus ring corners

**Focus Ring Width:**
- **Value:** 2px
- **Usage:** Focus ring border width

---

## Layout Specifications

### Structure
The form field uses a vertical flex layout with two main rows:

1. **Label row:** 
   - Contains the label text and optional requirement indicator (asterisk or "optional" text)
   - Horizontal layout with 10px gap between label and indicator
   - Label text is left-aligned
   
2. **Input field row:** 
   - Full-width input positioned below the label
   - 8px gap from the label row (`nova/spacing/tight`)
   - Stretches to fill available width

### Spacing
**Vertical spacing:**
- **Gap between label and input:** `nova/spacing/tight` (8px)

**Horizontal spacing:**
- **Gap in label row:** 10px (between label text and asterisk or "optional" text)

**Input padding:**
- **All sides:** `nova/spacing/tight` (8px)

### Visual Properties
**Input field:**
- **Border radius:** `nova/radii/component/input`
- **Border width:** `nova/border/basic`
- **Background:** `nova/input/color/background`

**Focus ring (when focused):**
- **Width:** 2px
- **Position:** Outside the input border
- **Radius:** `nova/radii/component/input` (matches input corners)

**Layout container:**
- **Direction:** Column (vertical)
- **Alignment:** Stretch to fill width
- **Gap:** `nova/spacing/tight` (8px between label and input)

### Dimensions
**Input height:**
- Determined by padding (`nova/spacing/tight` top and bottom) + text height

**Input width:**
- Fills available container width
- Minimum recommended: 200px
- Maximum recommended: 600px (for readability)

**Icon (if showIcon=true):**
- **Size:** 20x20px
- **Position:** Right side of input, inside padding

---

## Accessibility Considerations

### Label Association
- The label must be properly associated with the input field using `for` and `id` attributes or proper nesting
- This ensures screen readers can announce the label when the input receives focus
- Clicking the label should focus the associated input

### Keyboard Navigation
- Input field must be focusable via keyboard (Tab key)
- Focus state should be clearly visible
- Enter key should submit the form (if applicable)
- Escape key should clear focus (standard behavior)

### Screen Readers
- Label text should be descriptive and clear
- Placeholder text should not replace the label
- Help text should be associated with the input using `aria-describedby`
- Required fields should use `aria-required="true"`
- Error states should use `aria-invalid` and `aria-errormessage`

### Visual Accessibility
- Label text must meet WCAG 2.1 AA contrast requirements
- Placeholder text meets minimum contrast (though should not be relied upon)
- Focus indicators must be clearly visible
- Don't rely solely on color to indicate required or error states

### Required Fields
- If using a badge to indicate required fields, also use `aria-required`
- Provide clear visual and programmatic indication
- Consider using asterisk (*) or "Required" text in addition to visual badges

---

## Usage Guidelines

### When to Use

**Form Fields:**
- For collecting user input in forms
- When you need a consistent label-input pairing
- For creating accessible and structured forms
- Any time user data entry is required

**Help Text:**
- To provide additional context about expected input format
- To give examples of valid input
- To explain why the information is needed
- To clarify complex or uncommon fields

**Badges:**
- To indicate required fields
- To mark new or updated fields
- To denote special field types or statuses
- To provide quick visual scanning cues

**Tooltips:**
- For detailed explanations that would clutter the UI if always visible
- For providing examples or formatting rules
- For explaining technical terms or jargon
- When help text would be too lengthy

### Best Practices

#### Do:
- Always provide a clear, descriptive label
- Use placeholder text for examples, not as a replacement for labels
- Keep labels concise and action-oriented
- Associate labels with inputs properly for accessibility
- Use help text for important formatting requirements
- Indicate required fields clearly
- Maintain consistent spacing and alignment throughout forms
- Group related form fields together

#### Don't:
- Use placeholder text as the only label (it disappears on input)
- Make labels too long or verbose
- Use technical jargon without explanation
- Forget to indicate required fields
- Over-use tooltips for basic information
- Hide critical information in tooltips
- Use inconsistent label positioning across a form
- Stack too many form fields without visual grouping

### Label Writing Guidelines
- **Be specific:** "Email address" instead of "Email"
- **Use sentence case:** "First name" not "First Name"
- **Avoid redundancy:** Don't repeat "Enter your..." for every field
- **Be concise:** Keep labels short (1-3 words typically)
- **Action-oriented:** Make it clear what data is expected

### Placeholder Text Guidelines
- **Provide examples:** "john@example.com" instead of "Enter email"
- **Show format:** "MM/DD/YYYY" for date fields
- **Don't replace labels:** Placeholders disappear when typing
- **Keep it brief:** Short examples work best
- **Use real examples:** Realistic data helps users understand

---

## Content Structure

The form field consists of:

1. **Label (Required)**
   - Descriptive text identifying the input field
   - Should be present for all form fields
   - Positioned above the input

2. **Input Field (Required)**
   - The actual input area where users enter data
   - Includes placeholder text for guidance
   - Full-width within the container

3. **Help Text (Optional)**
   - Additional guidance or formatting instructions
   - Positioned below the input field (typically)
   - Should be concise and helpful

4. **Badge (Optional)**
   - Visual indicator for field status or requirements
   - Positioned near the label
   - Should be small and non-intrusive

5. **Tooltip (Optional)**
   - Detailed information available on hover/focus
   - Provides extended explanations without cluttering UI
   - Should contain supplementary, not critical information

---

## Interactive States

The Form Field component combines label presentation with input interaction states. The label remains static while the input transitions through various states based on user interaction and validation.

### Default
The initial resting state before any user interaction.

**Label:**
- Displays according to selected variant (Default/Required/Optional)
- Static appearance throughout all input states

**Input:**
- Background: `nova/input/color/background`
- Border: `nova/input/color/accent`
- Shows placeholder text in `nova/input/color/placeholder`
- No content entered

### Hover
When the cursor is positioned over the input field.

**Label:**
- No visual change

**Input:**
- Same visual appearance as Default
- Cursor changes to text input cursor
- May include subtle visual feedback (implementation-specific)

### Focused
When the input field is actively selected (clicked or tabbed into).

**Label:**
- No visual change

**Input:**
- All Default state visuals, plus:
- **Focus ring:** 2px border using `nova/color/focus`, positioned outside input border
- Cursor actively blinking in input field
- Ready to receive text input
- Placeholder text visible until typing begins

### Filled
When user has entered content into the field.

**Label:**
- No visual change

**Input:**
- Placeholder text is hidden
- User content displays in `nova/color/typography/base`
- All other properties same as Default/Focused state

### Error
When validation has failed or input is invalid.

**Label:**
- No visual change (label text remains same)
- Error message typically displays below input

**Input:**
- All Default state properties, except:
- **Border color:** `nova/color/critical/primary` (red border)
- Should be accompanied by error message component below input
- Clearly indicates validation failure

### Focus (Error)
When an invalid field receives focus.

**Label:**
- No visual change

**Input:**
- **Border color:** `nova/color/critical/primary` (red)
- **Focus ring:** 2px border using `nova/color/focus`
- Both error border and focus ring visible simultaneously
- User can correct the error while focus ring shows field is active

### Disabled
When the field is not interactive.

**Label:**
- May appear muted (implementation choice)
- Indicates field is not available for input

**Input:**
- **Background:** `nova/input/color/disabled`
- **Border:** `nova/input/color/accent` (or muted variant)
- **Text color:** `nova/color/typography/muted`
- **Icon color (if shown):** `nova/color/skeleton/secondary`
- Cannot receive focus or accept input
- Cursor indicates non-interactive state

### Readonly
When the field displays data but doesn't allow editing.

**Label:**
- Normal appearance
- Field is visible but not editable

**Input:**
- **Empty state:** Shows hyphen "-" in `nova/input/color/placeholder`
- **Filled state:** Shows content in `nova/color/typography/base`
- **No icon displayed** (even if showIcon=true in other states)
- May show focus states but content cannot be modified
- Distinct from Disabled (appears more "active" but non-editable)

---

### State Combinations

The component supports various combinations of states:

**Common Combinations:**
- **Default + Empty:** Initial state, placeholder visible
- **Default + Filled:** User has entered valid data
- **Focus + Empty:** User clicked in, placeholder still visible
- **Focus + Filled:** User is editing existing content
- **Error + Empty:** Required field left blank
- **Error + Filled:** Invalid data entered (e.g., malformed email)
- **Focus + Error + Filled:** User correcting invalid data
- **Disabled + Empty:** Field not available, no data
- **Disabled + Filled:** Field not available, showing existing data
- **Readonly + Empty:** Data not provided, field not editable
- **Readonly + Filled:** Data displayed, field not editable

**Label Variant Independence:**
All input states can combine with any label variant:
- **Required variant** with any input state
- **Optional variant** with any input state
- **Default variant** with any input state

---

## Visual Behavior Notes

### Component Architecture
The Form Field should be implemented as **one unified component** with configurable properties for label variants, input states, and optional features.

**Visual Composition:**
- Label row (with optional requirement indicator: asterisk or "optional" text)
- Input field row
- Optional elements (help text, badge, tooltip) as separate configurable parts

### Key Visual Behaviors

**showIcon Property:**
- Form Field sets `showIcon=false` by default (standard text inputs)
- For select/dropdown inputs, use the dedicated Select component instead
- When enabled, icon appears on right side of input (20x20px)

**Readonly Empty State:**
- Displays hyphen "-" instead of placeholder text
- Uses `nova/input/color/placeholder` for the hyphen
- No icon is displayed (even if showIcon=true in other states)

**Error State Visual:**
- Border color changes to `nova/color/critical/primary`
- Error message should display below the input
- Both error border and focus ring visible when focused

**State Transitions:**
- Label remains static across all input states
- Input transitions between states affect border color, background, and focus ring
- Filled state hides placeholder and shows user content

### Sizing Behavior
- **Width:** Component fills available container width (full width)
- **Height:** Determined by padding tokens (`nova/spacing/tight`) + content height
- **Label row:** Horizontal layout, hugs content
- **Input row:** Full width of container

### Input Type Flexibility
**Supported for Form Field:**
- Text-based inputs: `text`, `email`, `password`, `tel`, `url`
- Numeric inputs: `number`
- Date/time inputs: `date` (may integrate with date picker component)

**NOT for Form Field:**
- Select/Dropdown - Use dedicated Select component
- Textarea - May require Form Field variant or separate component
- Checkbox/Radio - Separate components with different interaction patterns

---

## Accessibility Considerations

### Label Association
- The label must be properly associated with the input field using `for` and `id` attributes or proper nesting
- This ensures screen readers can announce the label when the input receives focus
- Clicking the label should focus the associated input

### Keyboard Navigation
- Input field must be focusable via keyboard (Tab key)
- Focus state should be clearly visible with focus ring (`nova/color/focus`)
- Enter key should submit the form (if applicable)

### Screen Readers
- Label text should be descriptive and clear
- Placeholder text should not replace the label
- Help text should be associated with the input using `aria-describedby`
- Required fields should use `aria-required="true"`
- Error states should use `aria-invalid="true"` and `aria-errormessage`

### ARIA Attributes

**Required variant:**
- Use `aria-required="true"` on input for screen readers
- Visual asterisk plus programmatic indication required

**Error state:**
- `aria-invalid="true"` when error exists
- `aria-describedby="error-id"` pointing to error message element
- Error message should have `role="alert"` for immediate announcement

**Disabled state:**
- `disabled` attribute on input
- Not in tab order

**Readonly state:**
- `readonly` attribute on input
- May remain in tab order (implementation choice)

---

## Reference Components

The Form Field unified component incorporates design specifications from:

- **`form-label.md`** - Label variants (Default, Required, Optional) and typography specifications
- **`text-input.md`** - Input states, filled conditions, showIcon behavior, and color tokens

These standalone component docs remain valid for:
- Understanding individual component behavior in isolation
- Using Label or Input components separately outside Form Field context
- Reference during Form Field implementation

## Related Components

### Reference Documentation

**Components that inform Form Field design:**
- **Form Label** (see `form-label.md`) - Standalone label component with 3 variants
  - Provides specifications for label typography, colors, and requirement indicators
  - Can be used independently outside Form Field context
  - Form Field incorporates these variants as properties

- **Text Input** (see `text-input.md`) - Standalone input component with 7 states
  - Provides specifications for input states, colors, and filled conditions
  - Can be used independently
  - Form Field incorporates these states with `showIcon=false`

**Relationship:**
Form Field is a **unified implementation** that combines specifications from both Form Label and Text Input into one cohesive component. The standalone components remain valid for independent usage and as reference documentation.

---

### Alternative Input Types

**Other input components (not yet documented):**
- **Number Input** - For numeric data entry with increment/decrement controls
- **Date Picker Input** - For date selection with calendar interface
- **Textarea** - For multi-line text input (may require Form Field variant)

**These may be documented later and can replace the input portion of Form Field via `inputType` property.**


---

## Version History
- **Current Version:** Design system tokens extracted from Figma component
- **Last Updated:** Form field composite component with label, input, and optional features

---

## Questions or Clarifications
For implementation questions or design clarifications:
- Refer to individual Input component documentation for input-specific states
- Consult the design system for validation error patterns
- Check with the design team for help text and badge styling details
- Reference accessibility guidelines for proper form field implementation
