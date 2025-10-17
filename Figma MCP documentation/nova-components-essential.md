# Nova Design System - Essential Components

**Version:** 1.0  
**Purpose:** Complete specifications for most commonly used components with all variants, states, and hover behaviors.  
**Usage:** Attach this file when building forms, buttons, or interactive elements that need detailed specifications.

**Prerequisites:** Attach `nova-core.md` first for design tokens and patterns.

---

## Table of Contents
1. [Button Component](#button-component)
2. [Text Input Component](#text-input-component)
3. [Form Label Component](#form-label-component)
4. [Typography System Reference](#typography-system-reference)

---

## Button Component

### Overview
Primary interactive component for user actions. Supports multiple variants for different action types, three sizes, and five interactive states.

### Variants

#### Primary (Default)
- **Purpose:** Main call-to-action, primary user actions
- **Background (Default):** `nova/interactive/color/primary` (#0969da)
- **Background (Hover):** `nova/interactive/color/primary-hover` (#0550ae)
- **Background (Pressed):** `nova/interactive/color/primary-pressed` (#033d8b)
- **Text Color:** `nova/color/typography/inverse` (#ffffff)
- **Border:** None

#### Secondary
- **Purpose:** Secondary actions, alternative choices
- **Background (Default):** `nova/surfaces/color/workspace` (#ffffff)
- **Background (Hover):** `nova/surfaces/color/surface-hover` (#f6f8fa)
- **Background (Pressed):** `nova/surfaces/color/workspace border` (#e0e6e6)
- **Text Color:** `nova/color/typography/base` (#151d1e)
- **Border:** 1px solid `nova/surfaces/color/workspace border` (#e0e6e6)
- **Border (Hover):** 1px solid darker shade
- **Border (Pressed):** 1px solid darker shade

#### Destructive
- **Purpose:** Delete, remove, or destructive actions
- **Background (Default):** `nova/interactive/color/destructive` (#d1242f)
- **Background (Hover):** `nova/interactive/color/destructive-hover` (#a20915)
- **Background (Pressed):** `nova/interactive/color/destructive-pressed` (#870714)
- **Text Color:** `nova/color/typography/inverse` (#ffffff)
- **Border:** None

#### Ghost
- **Purpose:** Tertiary actions, cancel buttons, subtle interactions
- **Background (Default):** transparent
- **Background (Hover):** `nova/interactive/color/ghost-hover` (rgba(175,184,193,0.2))
- **Background (Pressed):** Slightly darker transparent overlay
- **Text Color:** `nova/color/typography/base` (#151d1e)
- **Border:** None

### Sizes

#### Small
- **Height:** 28px
- **Padding horizontal:** `nova/spacing/tight` (8px)
- **Padding vertical:** `nova/spacing/next` (4px)
- **Typography:** `nova/typography/instructional/regular` (14px, Regular, 100%)
- **Icon size:** 14px (if present)
- **Gap (icon + text):** `nova/spacing/tight` (8px)

#### Medium (Default)
- **Height:** 32px
- **Padding horizontal:** `nova/spacing/close` (12px)
- **Padding vertical:** `nova/spacing/tight` (8px)
- **Typography:** `nova/typography/instructional/regular` (14px, Regular, 100%)
- **Icon size:** 16px (if present)
- **Gap (icon + text):** `nova/spacing/tight` (8px)

#### Large
- **Height:** 40px
- **Padding horizontal:** `nova/spacing/near` (16px)
- **Padding vertical:** `nova/spacing/close` (12px)
- **Typography:** `nova/typography/instructional/regular` (14px, Regular, 100%)
- **Icon size:** 20px (if present)
- **Gap (icon + text):** `nova/spacing/tight` (8px)

### States

#### Default
- Base colors as documented per variant
- No additional visual effects

#### Hover
- Background color changes to hover variant (see variant sections above)
- Cursor: pointer
- Transition: smooth 150-200ms

#### Pressed / Active
- Background color changes to pressed variant
- Slight visual depression (optional transform: scale(0.98))

#### Focused
- Outline: 2px solid `nova/interactive/color/focus-ring` (#0969da with 20% opacity)
- Outline offset: 2px
- Background remains default state color

#### Disabled
- **Opacity:** 0.5 or 50%
- **Cursor:** not-allowed
- **Background:** Same as default but dimmed
- **Text:** Same as default but dimmed
- **No hover effects**

### Border Radius
- **All variants, all sizes:** `nova/radii/component/button` (6px)

### Typography
- **All variants, all sizes:** `nova/typography/instructional/regular`
  - Font size: 14px
  - Weight: Regular (400)
  - Line height: 100%
  - Font family: Geist

### Layout
- **Display:** inline-flex or flex
- **Align items:** center
- **Justify content:** center
- **Text align:** center
- **Vertical alignment:** middle

### With Icons
- **Icon position:** Before or after text
- **Gap between icon and text:** `nova/spacing/tight` (8px)
- **Icon size:** 14px (Small), 16px (Medium), 20px (Large)
- **Icon color:** Same as text color

### Accessibility
- **Element:** `<button>` tag (semantic HTML)
- **Disabled state:** `disabled` attribute (not just CSS)
- **ARIA label:** If icon-only, include `aria-label="[action]"`
- **Focus visible:** Clear focus ring
- **Keyboard navigation:** Tab to focus, Enter/Space to activate

### Common Combinations

**Primary Action (Default):**
```
Variant: Primary
Size: Medium
State: Default
Text: "Save" or "Submit" or "Create"
```

**Secondary Action:**
```
Variant: Ghost or Secondary
Size: Medium
State: Default
Text: "Cancel" or "Close"
```

**Destructive Action:**
```
Variant: Destructive
Size: Medium
State: Default
Text: "Delete" or "Remove"
```

---

## Text Input Component

### Overview
Standard text input field for single-line text entry. Supports multiple states and optional icons/indicators.

### Variants / States

#### Default
- **Background:** `nova/surfaces/color/workspace` (#ffffff)
- **Border:** 1px solid `nova/surfaces/color/workspace border` (#e0e6e6)
- **Text color:** `nova/color/typography/base` (#151d1e)
- **Placeholder color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **No additional visual effects**

#### Filled (Has Value)
- **Same as Default**
- Text appears in base color
- Placeholder hidden

#### Focused
- **Background:** `nova/surfaces/color/workspace` (#ffffff)
- **Border:** 2px solid `nova/interactive/color/primary` (#0969da)
- **Outline ring:** 2px solid `nova/interactive/color/focus-ring` (rgba(9,105,218,0.2))
- **Outline offset:** 2px
- **Text color:** `nova/color/typography/base` (#151d1e)

#### Hover (when not focused)
- **Border:** 1px solid slightly darker shade of workspace border
- **Background:** `nova/surfaces/color/workspace` (#ffffff)
- **Cursor:** text

#### Error
- **Background:** `nova/surfaces/color/workspace` (#ffffff)
- **Border:** 2px solid `nova/interactive/color/destructive` (#d1242f)
- **Text color:** `nova/color/typography/base` (#151d1e)
- **Error message below:** `nova/typography/supporting/regular` (12px), destructive color

#### Disabled
- **Background:** `nova/surfaces/color/surface-hover` (#f6f8fa)
- **Border:** 1px solid `nova/surfaces/color/workspace border` (#e0e6e6)
- **Text color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Cursor:** not-allowed
- **Opacity:** 0.6

### Dimensions
- **Height:** 32px
- **Padding horizontal:** `nova/spacing/tight` (8px)
- **Padding vertical:** Calculated to center text (typically ~6px)
- **Border width:** 1px (default), 2px (focused/error)

### Typography
- **Text:** `nova/typography/base/regular`
  - Font size: 14px
  - Weight: Regular (400)
  - Line height: 130%
  - Font family: Geist
- **Placeholder:** Same as text but with muted color

### Border Radius
- **All states:** `nova/radii/component/input` (8px)

### With Icons

#### Leading Icon (Left)
- **Icon position:** Before text
- **Icon size:** 16px
- **Icon color:** `nova/color/typography/muted` (muted) or base (active)
- **Padding left:** `nova/spacing/tight` (8px) for icon, additional `nova/spacing/tight` (8px) for text
- **Total left padding:** ~28px (8px + 16px icon + 4px gap)

#### Trailing Icon (Right)
- **Icon position:** After text
- **Icon size:** 16px
- **Icon color:** `nova/color/typography/muted` (muted) or base (active)
- **Padding right:** Same as leading icon
- **Common uses:** Clear button (X), search icon, validation checkmark

### Accessibility
- **Element:** `<input type="text">` (semantic HTML)
- **Associated label:** Use `<label>` with `for` attribute matching input `id`
- **Placeholder:** Never rely solely on placeholder for label
- **ARIA attributes:**
  - `aria-label` if no visible label
  - `aria-describedby` for helper text or error messages
  - `aria-invalid="true"` for error state
  - `aria-required="true"` for required fields
- **Keyboard navigation:** Tab to focus, type to enter text
- **Focus visible:** Clear focus ring

### Error Messages
- **Position:** Below input field
- **Typography:** `nova/typography/supporting/regular` (12px)
- **Color:** `nova/interactive/color/destructive` (#d1242f)
- **Gap from input:** `nova/spacing/next` (4px)
- **ARIA:** Connect with `aria-describedby`

### Helper Text
- **Position:** Below input field (same as error)
- **Typography:** `nova/typography/supporting/regular` (12px)
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Gap from input:** `nova/spacing/next` (4px)

### Common Patterns

**Standard Text Input:**
```
State: Default
Height: 32px
Placeholder: "Enter text..."
Border: 1px solid workspace border
```

**Required Field with Error:**
```
State: Error
Border: 2px solid destructive
Error message below: "This field is required"
ARIA: aria-invalid="true" aria-required="true"
```

**Search Input:**
```
Leading icon: Search icon (16px, muted)
Placeholder: "Search..."
Trailing icon: Clear button (X) when filled
```

---

## Form Label Component

### Overview
Label component for form inputs with support for required/optional indicators. Always pair with form input fields.

### Structure

#### Label Text
- **Typography:** `nova/typography/body/regular`
  - Font size: 16px
  - Weight: Regular (400)
  - Line height: 140%
  - Font family: Geist
- **Color:** `nova/color/typography/base` (#151d1e)

#### Required Indicator (Asterisk)
- **Typography:** `nova/typography/base/strong`
  - Font size: 14px
  - Weight: SemiBold (600)
  - Line height: 130%
- **Color:** `nova/interactive/color/destructive` (#d1242f) - RED
- **Symbol:** * (asterisk)
- **Position:** Immediately after label text
- **Gap from label:** `nova/spacing/next` (4px)

#### Optional Indicator
- **Typography:** `nova/typography/supporting/regular`
  - Font size: 12px
  - Weight: Regular (400)
  - Line height: 120%
- **Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Text:** "(optional)"
- **Position:** After label text
- **Gap from label:** `nova/spacing/next` (4px)

### Layout
- **Display:** block or flex
- **Margin bottom:** `nova/spacing/next` (4px) - gap between label and input
- **Alignment:** Left-aligned

### Variants

#### Required Field (Default)
```
[Label Text]*
└─ Label text (16px, Regular, base color)
└─ Asterisk (14px, SemiBold, RED)
└─ Gap: 4px

Example: "Email Address*"
```

#### Optional Field
```
[Label Text] (optional)
└─ Label text (16px, Regular, base color)
└─ "(optional)" (12px, Regular, muted)
└─ Gap: 4px

Example: "Phone Number (optional)"
```

#### Plain Label (No Indicator)
```
[Label Text]
└─ Label text only (16px, Regular, base color)

Example: "Username" (when context is clear)
```

### Accessibility
- **Element:** `<label>` tag (semantic HTML)
- **For attribute:** Must match input's `id` attribute
  ```html
  <label for="email">Email Address*</label>
  <input id="email" type="text" required />
  ```
- **Required fields:** Include `required` attribute on input
- **Screen reader:** Reads label text + indicator

### Spacing with Input

**Vertical spacing:**
```
[Label]
  ↓ 4px gap (nova/spacing/next)
[Input]
  ↓ 12px gap (nova/spacing/close)
[Next Label]
```

**Complete form row:**
```
Form Label (16px, Regular)
  ↓ 4px
Text Input (32px height)
  ↓ 4px (if error/helper text)
Error/Helper Text (12px, Supporting)
  ↓ 12px
Next Form Row
```

### Common Patterns

**Required Text Input:**
```html
<label for="username">Username*</label>
<input id="username" type="text" required aria-required="true" />
```

**Optional Text Input:**
```html
<label for="nickname">Nickname <span>(optional)</span></label>
<input id="nickname" type="text" />
```

**With Error:**
```html
<label for="email">Email Address*</label>
<input id="email" type="email" required aria-invalid="true" aria-describedby="email-error" />
<span id="email-error" style="color: #d1242f; font-size: 12px;">Please enter a valid email</span>
```

---

## Typography System Reference

### Complete Typography Scale

For detailed usage, see `typography.md`. Quick reference:

| Style | Size | Weight | Line Height | Primary Use |
|-------|------|--------|-------------|-------------|
| Title | 30px | SemiBold (600) | 100% | Major page headings |
| Heading 1 | 24px | SemiBold (600) | 140% | Page titles, H1 |
| Heading 2 | 20px | SemiBold (600) | 140% | Section headers, H2 |
| Heading 3 | 18px | SemiBold (600) | 140% | Subsection headers, H3 |
| Body Regular | 16px | Regular (400) | 140% | Body text, form labels |
| Body Strong | 16px | SemiBold (600) | 140% | Emphasized body text |
| Base Regular | 14px | Regular (400) | 130% | UI text, input values |
| Base Strong | 14px | SemiBold (600) | 130% | Emphasized UI text |
| Supporting Regular | 12px | Regular (400) | 120% | Helper text, captions |
| Supporting Strong | 12px | SemiBold (600) | 120% | Emphasized helper |
| Instructional Regular | 14px | Regular (400) | 100% | Buttons, badges |

### Typography Usage in Components

**Buttons:** `nova/typography/instructional/regular` (14px, Regular, 100%)  
**Text Inputs:** `nova/typography/base/regular` (14px, Regular, 130%)  
**Form Labels:** `nova/typography/body/regular` (16px, Regular, 140%)  
**Error Messages:** `nova/typography/supporting/regular` (12px, Regular, 120%)  
**Helper Text:** `nova/typography/supporting/regular` (12px, Regular, 120%)  
**Page Titles:** `nova/typography/heading/1` (24px, SemiBold, 140%)  
**Section Headers:** `nova/typography/heading/2` or `heading/3` (20px or 18px)  
**Body Content:** `nova/typography/body/regular` (16px, Regular, 140%)

### Font Families
- **Primary:** Geist (sans-serif)
- **Fallback:** Roboto, system-ui, -apple-system, sans-serif

---

## Complete Example: Login Form

Here's how all three components work together:

```html
<form>
  <!-- Email Field (Required) -->
  <div style="margin-bottom: 12px;">
    <label for="email" style="font-size: 16px; font-weight: 400; color: #151d1e;">
      Email Address<span style="color: #d1242f; font-weight: 600;">*</span>
    </label>
    <input 
      id="email" 
      type="email" 
      required
      aria-required="true"
      placeholder="Enter your email"
      style="
        width: 100%;
        height: 32px;
        margin-top: 4px;
        padding: 0 8px;
        font-size: 14px;
        border: 1px solid #e0e6e6;
        border-radius: 8px;
        background: #ffffff;
      "
    />
  </div>

  <!-- Password Field (Required) -->
  <div style="margin-bottom: 12px;">
    <label for="password" style="font-size: 16px; font-weight: 400; color: #151d1e;">
      Password<span style="color: #d1242f; font-weight: 600;">*</span>
    </label>
    <input 
      id="password" 
      type="password" 
      required
      aria-required="true"
      placeholder="Enter your password"
      style="
        width: 100%;
        height: 32px;
        margin-top: 4px;
        padding: 0 8px;
        font-size: 14px;
        border: 1px solid #e0e6e6;
        border-radius: 8px;
        background: #ffffff;
      "
    />
  </div>

  <!-- Remember Me (Optional) -->
  <div style="margin-bottom: 16px;">
    <label for="remember" style="font-size: 16px; font-weight: 400; color: #151d1e;">
      Remember me <span style="font-size: 12px; color: rgba(0,0,0,0.62);">(optional)</span>
    </label>
    <input 
      id="remember" 
      type="checkbox" 
      style="margin-top: 4px;"
    />
  </div>

  <!-- Buttons -->
  <div style="display: flex; gap: 8px;">
    <button 
      type="submit"
      style="
        height: 32px;
        padding: 0 12px;
        font-size: 14px;
        font-weight: 400;
        background: #0969da;
        color: #ffffff;
        border: none;
        border-radius: 6px;
        cursor: pointer;
      "
    >
      Log In
    </button>
    <button 
      type="button"
      style="
        height: 32px;
        padding: 0 12px;
        font-size: 14px;
        font-weight: 400;
        background: transparent;
        color: #151d1e;
        border: none;
        border-radius: 6px;
        cursor: pointer;
      "
    >
      Cancel
    </button>
  </div>
</form>
```

### Form Spacing Summary
- **Between label and input:** 4px (`nova/spacing/next`)
- **Between form rows:** 12px (`nova/spacing/close`)
- **Between buttons:** 8px (`nova/spacing/tight`)
- **Before button row:** 16px (`nova/spacing/near`)

---

## Version History
- **Version 1.0** - Initial essential components reference with Button, Text Input, and Form Label complete specifications including all hover states and variants
