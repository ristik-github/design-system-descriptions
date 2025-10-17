# Nova Design System - Design Tokens Reference

This document serves as a comprehensive reference for all design tokens used in the Nova design system. Tokens are organized by category and include both the token name and its resolved value where available.

> **Note:** Always use token names in component implementations, never hardcoded values. This ensures consistency and makes updates easier.

---

## Table of Contents
1. [Colors](#colors)
2. [Typography](#typography)
3. [Spacing](#spacing)
4. [Border & Radii](#borders--radii)
5. [Effects](#effects)

---

## Colors

### Base Typography Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/color/typography/base` | #151d1e | Primary text color for labels, content, body text |
| `nova/color/typography/muted` | #0000009e (rgba(0,0,0,0.62)) | Secondary/muted text (optional labels, helper text, disabled text) |

---

### Input Component Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/input/color/background` | #ffffff | Input field background, dropdown background, checkbox background |
| `nova/input/color/disabled` | - | Input background when disabled |
| `nova/input/color/accent` | #c1cacb | Default border color for inputs, checkboxes |
| `nova/input/color/secondary` | #889192 | Border color when focused, neutral chip borders |
| `nova/input/color/placeholder` | #6e7778 | Placeholder text color |
| `nova/input/color/highlight1` | #185956 | Checkbox background when checked (multi-select) |

---

### Button Colors

#### Primary Variant

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/button/primary/default/color/primary` | - | Background (default state) |
| `nova/button/primary/default/color/secondary` | - | Background (hover state) |
| `nova/button/primary/default/color/tertiary` | - | Background (pressed state) |
| `nova/button/primary/default/color/neutral` | - | Text color |
| `nova/button/primary/destructive/color/primary` | - | Destructive background (default) |
| `nova/button/primary/destructive/color/secondary` | - | Destructive background (hover) |
| `nova/button/primary/destructive/color/tertiary` | - | Destructive background (pressed) |
| `nova/button/primary/destructive/color/neutral` | - | Destructive text color |

#### Secondary Variant

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/button/secondary/default/color/primary` | #1f4cb3 | Text/border color (default state) |
| `nova/button/secondary/default/color/secondary` | - | Text/border color (hover/pressed states) |
| `nova/button/secondary/default/color/tertiary` | - | Background color for hover/pressed overlays |
| `nova/button/secondary/destructive/color/primary` | - | Destructive text/border (default) |
| `nova/button/secondary/destructive/color/secondary` | - | Destructive text/border (hover/pressed) |
| `nova/button/secondary/destructive/color/tertiary` | - | Destructive background overlay |

#### Tertiary Variant

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/button/tertiary/default/color/neutral` | - | Background (default state) |
| `nova/button/tertiary/default/color/tertiary` | - | Background (hover state) |
| `nova/button/tertiary/default/color/primary` | - | Text color (default state) |
| `nova/button/tertiary/default/color/secondary` | - | Text color (hover state) |
| `nova/button/tertiary/destructive/color/neutral` | - | Destructive background (default) |
| `nova/button/tertiary/destructive/color/tertiary` | - | Destructive background (hover) |
| `nova/button/tertiary/destructive/color/primary` | - | Destructive text (default) |
| `nova/button/tertiary/destructive/color/secondary` | - | Destructive text (hover) |

---

### Icon Button Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/icon-button/color/border-muted` | - | Border color in Subtle Off variant |
| `global/color/alpha-dark-blue/400` | - | Hover state background overlay |
| `global/color/alpha-dark-blue/500` | - | Pressed state background overlay |
| `global/color/dark-blue/700` | - | Active/selected state solid background |

---

### Semantic Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/color/critical/primary` | #d52020 | Error states, required asterisks, error messages |
| `nova/color/success/primary` | - | Success states |
| `nova/color/success/quaternary` | - | Success background states |
| `nova/color/success/dark` | - | Success dark accent |
| `nova/color/warning/primary` | - | Warning states |
| `nova/color/warning/quaternary` | - | Warning background states |
| `nova/color/warning/dark` | - | Warning dark accent |
| `nova/color/informative/primary` | #41bacf | Informative states |
| `nova/color/informative/secondary` | #eaf9fb | Informative backgrounds |
| `nova/color/informative/quaternary` | - | Informative background states |
| `nova/color/informative/dark` | #112e3b | Informative dark accent |
| `nova/color/feature/primary` | - | Feature highlight states |
| `nova/color/feature/quaternary` | - | Feature background states |
| `nova/color/feature/dark` | - | Feature dark accent |

---

### Neutral Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/color/neutral/primary` | #889192 | Neutral borders (chips) |
| `nova/color/neutral/secondary` | #f6fafa | Neutral backgrounds (chips) |
| `nova/color/neutral/quaternary` | - | Neutral background states (buttons) |
| `nova/color/neutral/dark` | - | Neutral dark accent |

---

### Link/Option Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/link-option/color/neutral` | #151d1e | Dropdown option text (default) |
| `nova/link-option/color/accent` | #e9f7f5 | Dropdown option background (hover/first item) |
| `nova/link-option/color/secondary` | #148d87 | Dropdown option background (selected in multi-select) |

---

### Global Color Palette

| Token Name | Value | Usage |
|------------|-------|-------|
| `global/color/dark-blue/10` | #f5f7fa | Lightest blue (file upload default, form field backgrounds) |
| `global/color/dark-blue/50` | #e6f3ff | Medium blue (file upload hover/focus) |
| `global/color/dark-blue/100` | #dbedfe | Darker blue (file upload pressed) |

---

### Static Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/color/static/white` | #ffffff | White text on dark backgrounds (selected dropdown options) |
| `nova/color/static/white 60%` | #ffffff9e (rgba(255,255,255,0.62)) | Semi-transparent white |

---

### Focus & Skeleton Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/color/focus` | #9ef1e4 | Focus rings, focus indicators |
| `nova/color/skeleton/primary` | - | Loading states, disabled backgrounds |
| `nova/color/skeleton/secondary` | - | Disabled icons, disabled text |

---

### Surface Colors

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/surfaces/color/workspace` | - | Workspace/page background (transparent/inherited) |

---

## Typography

### Typography Tokens (Composite)

These tokens include font family, size, weight, and line height as a composite value.

| Token Name | Font | Size | Weight | Line Height | Usage |
|------------|------|------|--------|-------------|-------|
| `nova/typography/body/regular` | Geist | 16px | 400 | 1.4 | Form labels, body text |
| `nova/typography/base/regular` | Geist | 14px | 400 | 1.3 | Input text, button text, dropdown options |
| `nova/typography/base/strong` | Geist | 14px | - | 0 | Required asterisks (vertically centered) |
| `nova/typography/instructional/regular` | Geist | 14px | 400 | 1.2 | Button labels, instructional text, file upload labels |
| `nova/typography/supporting/regular` | Geist | 12px | 400 | 1.2 | Helper text, optional labels, supporting text, error messages, badge text |

---

### Font Size Tokens

| Token Name | Value | Usage |
|------------|-------|-------|
| `global/typography/fontsize/12` | 12px | Small text (helper text, badges, chip text) |
| `global/typography/fontsize/14` | 14px | Base text size (inputs, buttons, options) |
| `global/typography/fontsize/16` | 16px | Larger text (labels) |

---

### Font Family

**Primary Font:** Geist
- Regular weight: 400
- Used across all text elements

---

## Spacing

### Named Spacing Tokens

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/spacing/slight` | 2px | Fine-tuning, minor adjustments |
| `nova/spacing/next` | 4px | Tight spacing (gaps between elements, chip internal gaps, option gaps, button internal spacing small) |
| `nova/spacing/tight` | 8px | Standard padding (input padding, button padding, dropdown padding, label gaps, file upload padding) |
| `nova/spacing/close` | 12px | Medium spacing (large button horizontal padding) |
| `nova/spacing/near` | 16px | Larger spacing (context spacing between components) |
| `nova/spacing/breathe` | 32px | Large spacing (dropdown chip container padding right) |

---

### Common Spacing Patterns

**Input Field Padding:**
- All sides: `nova/spacing/tight` (8px)

**Button Padding:**
- Small: Horizontal `nova/spacing/tight` (8px), Vertical `nova/spacing/next` (4px)
- Large: Horizontal `nova/spacing/close` (12px), Vertical `nova/spacing/tight` (8px)
- Internal gap: `nova/spacing/next` (4px)

**Dropdown Padding:**
- Input: `nova/spacing/tight` (8px all sides)
- Menu: `nova/spacing/tight` (8px)
- Options: `nova/spacing/tight` (8px all sides)
- Option gap: `nova/spacing/next` (4px)

**Form Field Gaps:**
- Label to input: `nova/spacing/tight` (8px)
- Label to indicator: 10px
- Error message gap: `nova/spacing/tight` (8px)

**Icon Gaps:**
- Icon to text: `nova/spacing/tight` (8px) or `nova/spacing/next` (4px)

**Chip Spacing:**
- Between chips: 6px
- Internal gap (text to icon): `nova/spacing/next` (4px)
- Padding left: `nova/spacing/tight` (8px)
- Padding right: `nova/spacing/next` (4px)
- Padding vertical: 4px

---

## Borders & Radii

### Border Width Tokens

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/border/basic` | 1px | Standard border width (buttons, inputs, checkboxes, chips) |

**Focus Border Width:** 2px (used for focus rings)

---

### Border Radius Tokens

| Token Name | Value | Usage |
|------------|-------|-------|
| `nova/radii/component/button` | 8px | Button corners, input fields, file upload areas, focus rings |
| `nova/radii/component/input` | 8px | Input field corners, dropdown input |
| `nova/radii/component/badge` | 4px | Badge corners |
| `nova/radii/component/checkbox` | 4px | Checkbox corners |
| `nova/radii/softened` | 8px | Dropdown menu corners |

**Dropdown Option Border Radius:** `nova/spacing/next` (4px) - for hover/selected backgrounds

**Chip Border Radius:** 4px

---

## Effects

### Shadows

**Dropdown Menu Shadow:**
- Value: `0px 8px 24px 0px rgba(0,0,0,0.13)`
- Usage: Elevation shadow for dropdown menus

---

### Opacity

**Loading State Opacity:**
- Value: 20% (0.2)
- Usage: Dimming text during file upload loading

---

### Focus Ring

**Standard Focus Ring:**
- Width: 2px
- Color: `nova/color/focus` (#9ef1e4)
- Position: Typically -2px offset (outside component border) or inset 0
- Matches component border radius

---

## Token Naming Conventions

Understanding token naming patterns helps predict and locate the right tokens:

### Spacing Pattern
```
nova/spacing/[name]
```
Examples: `nova/spacing/tight`, `nova/spacing/close`, `nova/spacing/near`

### Color Pattern
```
nova/[component]/[variant]/[color]/color/[state]
nova/color/[semantic]/[level]
global/color/[name]/[value]
```
Examples:
- `nova/button/primary/default/color/primary`
- `nova/color/critical/primary`
- `global/color/dark-blue/10`

### Typography Pattern
```
nova/typography/[category]/[style]
global/typography/fontsize/[size]
```
Examples:
- `nova/typography/instructional/regular`
- `global/typography/fontsize/14`

### Radii Pattern
```
nova/radii/component/[component]
```
Examples:
- `nova/radii/component/button`
- `nova/radii/component/input`
- `nova/radii/component/checkbox`

### Component-Specific Pattern
```
nova/[component]/color/[property]
```
Examples:
- `nova/input/color/background`
- `nova/input/color/placeholder`
- `nova/icon-button/color/border-muted`

---

## Usage Guidelines

### When Using Tokens

1. **Always use token names** in component specifications and implementations
2. **Never hardcode values** - even if you know the value, reference the token
3. **Check for variant-specific tokens** - Many components have state-specific tokens (default, hover, pressed, etc.)
4. **Reference size-specific tokens** - Some components have different padding/spacing by size
5. **Use semantic tokens** when available - Prefer `nova/color/critical/primary` over hardcoded red

### Token Updates

When tokens are updated in the design system:
- Token values change automatically across all implementations
- No need to update individual component code
- Ensures consistency across the entire application

### Missing Tokens

If a token is marked with `-` (no value documented):
- The token exists in Figma but value wasn't extracted
- Check Figma directly or with design team
- Token name is still correct for implementation reference

---

## Component Token Summary

Quick reference for which components use which token categories:

| Component | Typography | Colors | Spacing | Borders | Effects |
|-----------|-----------|--------|---------|---------|---------|
| Button | ✓ | ✓ | ✓ | ✓ | - |
| Icon Button | - | ✓ | ✓ | ✓ | - |
| Badge | ✓ | ✓ | ✓ | ✓ | - |
| Form Label | ✓ | ✓ | ✓ | - | - |
| Form Field | ✓ | ✓ | ✓ | ✓ | - |
| Text Input | ✓ | ✓ | ✓ | ✓ | - |
| Form File Upload | ✓ | ✓ | ✓ | ✓ | - |
| Dropdown | ✓ | ✓ | ✓ | ✓ | ✓ (shadow) |

---

## Version History

- **Current Version:** Compiled from Figma component extractions
- **Last Updated:** Comprehensive token reference with values from all documented components
- **Source:** Nova design system in Figma

---

## Notes

- This file is a living document and should be updated as new components are documented
- Token values marked with `-` need verification from Figma
- Some tokens are composite (e.g., typography includes family, size, weight, line height)
- Always verify token usage in context of specific component states and variants
- When in doubt, refer to individual component documentation for specific token applications

---

## Related Documentation

- [Documentation Instructions](./DOCUMENTATION-INSTRUCTIONS.md) - Guidelines for documenting components
- [Button Component](./button.md) - Button implementation details
- [Dropdown Component](./dropdown.md) - Dropdown implementation details
- [Form Field Component](./form-field.md) - Form field implementation details
- All other component documentation files in this directory
