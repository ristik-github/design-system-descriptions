# Form Label Component

## Overview
The Form Label component is a text element used to identify and describe form input fields. It provides three variants to indicate field requirement status: Default (no indication), Required (with asterisk), and Optional (with "optional" text). The label ensures forms are accessible and user-friendly by clearly communicating what information is expected.

---

## Component Properties

### Variants
The label supports three distinct variants to indicate field requirement status:

#### 1. **Default**
The standard label without any requirement indicator. Used when requirement status is not relevant or is communicated through other means.

- **Content:** Label text only
- **Use case:** When all fields have the same requirement status, or when requirement indication is handled differently

#### 2. **Required**
Indicates that the associated field must be filled out before form submission. Features a red asterisk (*) after the label text.

- **Content:** Label text + red asterisk (*)
- **Asterisk Color:** `nova/color/critical/primary`
- **Asterisk Typography:** `nova/typography/base/strong`
- **Asterisk Font Size:** `global/typography/fontsize/14`
- **Use case:** For mandatory fields that must be completed

#### 3. **Optional**
Indicates that the associated field is not required. Features gray "optional" text after the label.

- **Content:** Label text + "optional" text
- **Optional Text Color:** `nova/color/typography/muted`
- **Optional Text Typography:** `nova/typography/supporting/regular`
- **Optional Text Font Size:** `global/typography/fontsize/12`
- **Use case:** When most fields are required and you want to highlight the optional ones

---

## Design Tokens

### Typography

**Label Text (All Variants):**
- **Font:** `nova/typography/body/regular`
- **Text Color:** `nova/color/typography/base`
- **Font Size:** 16px (embedded in typography token)
- **Line Height:** 1.4 (embedded in typography token)

**Required Asterisk:**
- **Font:** `nova/typography/base/strong`
- **Font Size:** `global/typography/fontsize/14`
- **Text Color:** `nova/color/critical/primary`
- **Line Height:** 0 (for vertical centering)

**Optional Text:**
- **Font:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`
- **Text Color:** `nova/color/typography/muted`
- **Line Height:** 1.2 (embedded in typography token)

### Spacing
- **Gap between label and indicator:** 10px (Required and Optional variants)
- **Internal spacing (slight):** `nova/spacing/slight` (2px, used for fine-tuning)
- **Context spacing (near):** `nova/spacing/near` (16px, for spacing from other elements)

### Colors
- **Label Text:** `nova/color/typography/base`
- **Required Asterisk:** `nova/color/critical/primary`
- **Optional Text:** `nova/color/typography/muted`
- **Background:** `nova/surfaces/color/workspace` (transparent/inherited)

---

## Layout Specifications

### Structure

**Default Variant:**
- Single text element
- No additional indicators
- Minimal structure

**Required Variant:**
- Horizontal flex layout
- Label text on the left
- Asterisk (*) on the right
- 10px gap between elements
- Items aligned horizontally

**Optional Variant:**
- Horizontal flex layout
- Label text on the left
- "optional" text on the right
- 10px gap between elements
- Items aligned horizontally

### Spacing
- **Internal gap (Required & Optional):** 10px between label text and indicator
- **Label height:** 22px (for all variants)
- **Label width:** Varies based on text content (minimum ~90px)

### Visual Properties
- **Text rendering:** Nowrap for label text (prevents wrapping)
- **Whitespace:** Pre (preserves spacing)
- **Display:** Inline-flex for Required and Optional variants
- **Alignment:** Items centered vertically

---

## Accessibility Considerations

### Label Association
- **CRITICAL:** Label must be associated with its input field using:
  - `<label for="input-id">` with matching input `id="input-id"`, OR
  - Wrapping the input: `<label>Label text <input /></label>`
- Clicking the label should focus the associated input field
- Screen readers will announce the label when the input receives focus

### Required Fields
- The asterisk (*) is a visual indicator only
- **Must also include:** `aria-required="true"` on the input element
- Consider adding `required` attribute to the input for HTML5 validation
- Some screen readers may not announce the asterisk, so programmatic indication is essential

### Optional Fields
- The "optional" text provides visual clarity
- If most fields are required, marking optional fields is helpful
- Does not require special ARIA attributes (absence of `aria-required` indicates optional)

### Screen Reader Support
- Screen readers will read the label text
- The asterisk (*) may or may not be announced (depends on screen reader)
- The word "optional" will typically be announced
- Always use `aria-required` for programmatic indication of required fields

### Color and Contrast
- Label text must meet WCAG 2.1 AA contrast requirements (4.5:1 for normal text)
- Red asterisk provides visual reinforcement but should not be the only indicator
- "optional" text has lower contrast (muted color) but is supplementary information

---

## Usage Guidelines

### When to Use Each Variant

**Default:**
- When all fields in the form are required (no need to mark each one)
- When all fields are optional (no need to mark each one)
- When requirement status is communicated at the form level
- In compact forms where space is limited

**Required:**
- When mixing required and optional fields, and required fields are fewer
- When you want to emphasize mandatory fields
- Standard approach in most forms
- Follow platform conventions (e.g., asterisk is universally recognized)

**Optional:**
- When most fields are required and you want to highlight the exceptions
- In forms where users expect most fields to be mandatory
- When you want to reduce visual clutter from multiple asterisks
- Better for accessibility (clearer language than asterisk)

### Best Practices

#### Do:
- Keep label text clear and concise
- Use sentence case (e.g., "Email address" not "Email Address")
- Associate labels with their inputs properly (using `for` attribute)
- Use consistent variant choice throughout a form
- Place labels above inputs for better mobile experience
- Make labels descriptive enough to stand alone
- Use `aria-required` in addition to visual indicators
- Test with screen readers to ensure proper announcement

#### Don't:
- Use labels and placeholders interchangeably
- Make labels too long or verbose
- Mix "Required" and "Optional" variants in the same form
- Use only color to indicate required status (asterisk provides shape)
- Hide labels (even if placeholder seems sufficient)
- Use technical jargon without explanation
- Rely solely on asterisk for accessibility (add `aria-required`)
- Use all caps for labels (reduces readability)

### Label Text Guidelines
- **Be specific:** "Email address" instead of just "Email"
- **Avoid questions:** "Phone number" instead of "What's your phone number?"
- **No colons:** Modern practice omits colons after labels
- **Use context:** "Shipping address" vs. "Billing address" for clarity
- **Avoid redundancy:** Don't repeat "Enter your..." for every field
- **Be concise:** 1-4 words typically
- **Action-oriented:** Make it clear what's expected

---

## Content Structure

### Default Variant
- **Label text:** The descriptive name for the field

### Required Variant
- **Label text:** The descriptive name for the field
- **Asterisk (*):** Visual indicator of requirement
  - Color: Red (`nova/color/critical/primary`)
  - Size: 14px
  - Weight: Semibold
  - Position: Immediately after label text with 10px gap

### Optional Variant
- **Label text:** The descriptive name for the field
- **"optional" text:** Indicator of optionality
  - Color: Muted gray (`nova/color/typography/muted`)
  - Size: 12px
  - Weight: Regular
  - Position: After label text with 10px gap
  - Lowercase

---

## Variant Selection Strategy

### When Most Fields Are Required
Use the **Optional** variant for exceptions:
```
First name
Last name
Email address
Phone number optional
```

**Advantages:**
- Reduces visual clutter (fewer indicators)
- Clearer language ("optional" is more explicit than "*")
- Better accessibility (word is more universally understood)

### When Most Fields Are Optional
Use the **Required** variant for mandatory fields:
```
Email address *
Password *
Company name
Job title
```

**Advantages:**
- Follows established conventions (asterisk is universally recognized)
- Draws attention to critical fields
- Common pattern users expect

### When All Fields Share Status
Use the **Default** variant and communicate status at the form level:
```
All fields are required
---
First name
Last name
Email address
```

**Advantages:**
- Cleanest visual design
- No repeated indicators
- Clear communication upfront

---

## Implementation Notes

### Component API
The label accepts:
- **text:** The label text content (string)
- **variant:** "Default" | "Required" | "Optional" (string)

### Rendering Behavior
- Default: Renders single paragraph with label text
- Required: Renders label text + asterisk in flex container
- Optional: Renders label text + "optional" text in flex container

### Text Truncation
- Label text uses `text-nowrap` to prevent wrapping
- Consider overflow behavior for very long labels
- May need max-width constraint in some layouts

### Internationalization
- Label text should be localizable
- "optional" text should be translated to appropriate language
- Asterisk (*) is generally universal but consider cultural differences
- RTL languages may need layout adjustments

### Form Integration
- Always pair with an input component
- Ensure proper HTML association (for/id or nesting)
- Consider using within a Form Field component for consistent structure
- Maintain consistent spacing between label and input

---

## Related Components
Consider these related components when implementing forms:
- **Form Field:** Composite component that combines Label with Input
- **Text Input:** The input field associated with the label
- **Help Text:** Additional guidance below the input
- **Error Message:** Validation feedback component
- **Field Group:** Container for related form fields

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component set
- **Last Updated:** Form Label component with Default, Required, and Optional variants

---

## Questions or Clarifications
For implementation questions or design clarifications:
- Ensure proper HTML label-input association for accessibility
- Confirm variant choice strategy with UX team for your specific form
- Reference WCAG guidelines for color contrast requirements
- Test with screen readers to verify proper announcement
- Consult design system for form-level requirement indication patterns
