# Text Input Component

## Overview
The Text Input component (Form / Input) is a versatile input field that allows users to enter text data. It supports multiple interactive states, provides visual feedback during user interaction, and includes optional features like icons and clear buttons. The component handles both empty (placeholder) and filled states, making it suitable for various form scenarios.

---

## Component Properties

### States
The input supports seven distinct states to provide appropriate visual feedback:

#### 1. **Default**
The initial resting state when the input is not being interacted with.

#### 2. **Hover**
The state when the user's cursor is positioned over the input field, indicating interactivity.

#### 3. **Focus**
The state when the input field is actively selected and ready for user input. Features a prominent focus indicator ring.

#### 4. **Error**
The state when validation has failed or the input contains invalid data. Provides visual indication of an error condition.

#### 5. **Focus (Error)**
The combined state when an input with an error receives focus. Shows both error indication and focus ring.

#### 6. **Disabled**
The state when the input is not interactive. The field cannot receive focus or accept input.

#### 7. **Readonly**
The state when the field displays data but does not allow editing. Users can see the content but cannot modify it.

---

### Filled Status

#### Filled Off (Empty)
- Input displays placeholder text
- Placeholder uses muted color: `nova/input/color/placeholder`
- Indicates the field is empty and awaiting input

#### Filled On (Has Content)
- Input displays user-entered text
- Text uses base color: `nova/color/typography/base`
- Indicates the field contains data

---

### Optional Features

#### Show Icon
Controls whether an icon is displayed within the input field (typically on the right side).

**Property:** `showIcon` (boolean)
**Default:** `true`

**Note:** When used within Form Field component, this is typically set to `false`.

**Icon Types:**
- Dropdown indicator (expand more icon) - default
- Custom icons can be swapped via the `icon` property

#### Show Clear Button
Controls whether a clear/close button is displayed to quickly empty the input field.

**Property:** `showClearButton` (boolean)
**Default:** `false`

#### Input Value
The text content displayed in the input field (placeholder or actual value).

**Property:** `inputValue` (string)
**Default:** `"Lorem Ipsum"`

---

## Design Tokens

### Typography
- **Font:** `nova/typography/base/regular`
- **Font Size:** `global/typography/fontsize/14`
- **Line Height:** 1.3 (embedded in typography token)

### Colors

**Text:**
- **Filled text:** `nova/color/typography/base`
- **Placeholder text:** `nova/input/color/placeholder`
- **Disabled text:** `nova/color/typography/muted`

**Background & Border:**
- **Background:** `nova/input/color/background`
- **Border (default):** `nova/input/color/accent`
- **Border (error):** `nova/color/critical/primary`
- **Border (workspace):** `nova/surfaces/color/workspace border`
- **Disabled background:** `nova/input/color/disabled`

**Focus:**
- **Focus ring:** `nova/color/focus`
- **Focus border width:** 2px

**Icons:**
- **Default icon color:** `nova/input/color/secondary`
- **Disabled icon color:** `nova/color/skeleton/secondary`

### Spacing
- **Internal padding:** `nova/spacing/tight` (8px)
- **Gap to icon:** `nova/spacing/next` (4px)
- **Vertical spacing:** `nova/spacing/near` (16px, for spacing from other elements)

### Border & Radius
- **Border Radius:** `nova/radii/component/input`
- **Border Width (default):** `nova/border/basic`
- **Focus Border Width:** 2px

---

## State-Specific Styling

### Default State
- Border: `nova/input/color/accent`
- Background: `nova/input/color/background`
- Text color (empty): `nova/input/color/placeholder`
- Text color (filled): `nova/color/typography/base`

### Hover State
- Visual feedback to indicate interactivity
- Border may be slightly emphasized (implementation-specific)
- Maintains placeholder or filled text styling

### Focus State
- **Focus ring:** 2px border using `nova/color/focus`
- Ring positioned at the input boundary
- Border radius: `nova/radii/component/input`
- Clear visual indication of active field
- Maintains placeholder or filled text styling

### Error State
- Border color: `nova/color/critical/primary`
- Indicates validation failure
- Should be accompanied by error message (external to component)
- Maintains placeholder or filled text styling

### Focus (Error) State
- Combines error border with focus ring
- Border color: `nova/color/critical/primary`
- Focus ring: `nova/color/focus` (2px)
- Both visual indicators present simultaneously

### Disabled State
- Background: `nova/input/color/disabled`
- Text color: `nova/color/typography/muted`
- Icon color: `nova/color/skeleton/secondary` (grayed out)
- Cursor indicates non-interactive state
- Input does not respond to user interactions

### Readonly State
- **Empty (Filled=off):** Displays hyphen "-" as placeholder
- **Filled (Filled=on):** Displays actual content
- Input shows data but is not editable
- No icon displayed in readonly state
- May have distinct visual styling to indicate read-only nature

---

## Layout Specifications

### Structure
- Horizontal flex layout
- Content aligned and spaced appropriately
- Icon positioned on the right (when `showIcon=true`)

### Sizing
- **Height:** 36px (standard)
- **Width:** Flexible (stretches to container width, minimum ~150px)
- **Padding:** `nova/spacing/tight` (8px on all sides)

### Icon Specifications
- **Icon size:** 20x20px
- **Icon position:** Right side of input
- **Gap to text:** Internal flexbox spacing

### Visual Properties
- **Border radius:** `nova/radii/component/input`
- **Border width:** `nova/border/basic` (default), 2px (focus)
- **Background:** `nova/input/color/background`
- **Text overflow:** Ellipsis (text truncates with "..." if too long)
- **Text wrapping:** Nowrap (single line)
- **Overflow:** Hidden

---

## Accessibility Considerations

### Keyboard Navigation
- Input must be focusable via Tab key
- Focus state must be clearly visible (2px focus ring)
- Enter key may submit form (standard behavior)
- Escape key should clear focus (standard behavior)
- Text can be selected and edited with standard keyboard shortcuts

### Screen Readers
- Input must have associated label (via Form Label component or aria-label)
- Placeholder text should not replace the label
- Error states should use `aria-invalid="true"` and `aria-describedby` to reference error message
- Disabled state should use `disabled` attribute
- Readonly state should use `readonly` attribute
- Clear button (if shown) should have accessible label

### Visual Accessibility
- Focus ring must meet WCAG 2.1 contrast requirements
- Placeholder text meets minimum contrast (though should not be sole indicator)
- Error states should not rely solely on color (border + message)
- Disabled state should be clearly distinguishable
- Text color must meet WCAG 2.1 AA contrast standards (4.5:1)

### Focus Indicators
- Focus ring is 2px wide using `nova/color/focus`
- Ring appears outside the input border
- Highly visible against various backgrounds
- Maintains border radius of input

---

## Usage Guidelines

### When to Use

**Text Input:**
- For single-line text entry (names, emails, URLs, etc.)
- When collecting alphanumeric data
- For search fields
- For form data entry

**With Icon:**
- For dropdown/select-like inputs (expand more icon)
- For inputs with associated actions (search icon, date picker icon)
- When visual indicator helps clarify input purpose

**Without Icon (`showIcon=false`):**
- For simple text fields (names, addresses, etc.)
- When used within Form Field component
- When icon would add unnecessary visual clutter

**Readonly State:**
- To display data that should not be edited
- In form review/confirmation screens
- When showing calculated or derived values

### Best Practices

#### Do:
- Always pair with a Form Label for accessibility
- Provide clear placeholder examples (format hints)
- Use appropriate input types (email, tel, url, etc.) when available
- Show error states with accompanying error messages
- Clear error states when user corrects the input
- Use readonly for non-editable data
- Provide sufficient padding for readability
- Ensure focus state is highly visible

#### Don't:
- Use placeholder text as the only label
- Make placeholders too long or verbose
- Disable inputs unless absolutely necessary
- Use error state without explaining what's wrong
- Rely solely on color for error indication
- Nest inputs or create overly complex input structures
- Use tiny fonts or insufficient contrast
- Ignore keyboard navigation

### Input Type Considerations
The Text Input component can be adapted for various data types:
- **Text:** General text entry (default)
- **Email:** Email address with validation
- **Tel:** Telephone numbers
- **URL:** Web addresses
- **Number:** Numeric input (may need custom validation)
- **Date:** Date selection (may integrate with date picker)
- **Password:** Masked text entry

---

## Placeholder Guidelines
- **Show format:** "MM/DD/YYYY" for dates, "john@example.com" for email
- **Be realistic:** Use believable example data
- **Be concise:** Keep placeholders short
- **Don't replace labels:** Placeholders disappear when typing
- **Provide hints:** "Search by name or ID" instead of just "Search"

---

## Error Handling

### Error Display Pattern
1. Input shows Error state (red border)
2. Error message appears below the input
3. Focus (Error) state when user returns to fix the error
4. Error clears when input becomes valid

### Error Message Association
- Use `aria-describedby` to link input with error message
- Set `aria-invalid="true"` on the input element
- Error message should explain what's wrong and how to fix it
- Error should clear immediately when input becomes valid (or on blur)

---

## Implementation Notes

### State Management
Implementations should handle:
- Input value state
- Focus/blur events
- Validation and error states
- Disabled/readonly states
- Icon visibility toggle
- Clear button functionality

### Value Handling
- Track whether input has content (filled on/off)
- Manage placeholder vs. actual value display
- Handle value changes and updates
- Clear functionality (if clear button is shown)

### Icon Swapping
- Default icon is "expand more" (dropdown indicator)
- Support swapping with custom icons via `icon` property
- Icon size is fixed at 20x20px
- Icon should change color in disabled state

### Focus Management
- Focus ring appears on focus
- Focus ring should be visible over all backgrounds
- Focus persists until blur event
- Focus + Error state combines both visual indicators

### Readonly Behavior
- Readonly fields display content but don't allow editing
- Empty readonly fields show "-" as placeholder
- Filled readonly fields show actual content
- No icon is displayed in readonly state
- Cursor may indicate non-editable nature

### Integration with Form Field
When used within Form Field component:
- `showIcon` is typically set to `false`
- Label is provided by Form Label component
- Help text and validation appear external to input
- Consistent spacing maintained by Form Field wrapper

---

## Related Components
Consider these related components when implementing input functionality:
- **Form Field:** Wrapper component that combines Label, Input, Help Text, etc.
- **Form Label:** The label component associated with the input
- **Textarea:** For multi-line text input
- **Select/Dropdown:** For choosing from predefined options (may use similar visual styling)
- **Date Picker:** For date selection (may use Text Input as trigger)
- **Error Message:** Validation feedback component

---

## Common Patterns

### Basic Input with Label
```
Form Field
├── Form Label (Default variant)
└── Text Input (showIcon=false, state=Default)
```

### Required Field
```
Form Field
├── Form Label (Required variant with *)
└── Text Input (showIcon=false, state=Default)
```

### Error State
```
Form Field
├── Form Label (Required variant with *)
├── Text Input (showIcon=false, state=Error)
└── Error Message ("Email address is required")
```

### Readonly Display
```
Form Field
├── Form Label (Default variant)
└── Text Input (state=Readonly, filled=on)
```

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** Text Input component with all states, filled conditions, and optional features

---

## Questions or Clarifications
For implementation questions or design clarifications:
- Refer to Form Field documentation for integration patterns
- Consult design system for validation error message patterns
- Reference HTML5 input types for additional input variations
- Test with screen readers to ensure proper accessibility
- Verify focus indicators meet WCAG contrast requirements
