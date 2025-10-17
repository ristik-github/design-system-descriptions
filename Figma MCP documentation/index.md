# Nova Design System - Component Documentation Index

## Overview
This index provides a comprehensive map of all documented components in the Nova design system. Each component has detailed specifications including design tokens, variants, states, and accessibility guidelines.

## Design Tokens
**File:** `design-tokens.json` or `DESIGN-TOKENS.md`
- Complete token reference for spacing, typography, colors, and radii
- Use this file for token value lookups during implementation

## Foundation

### Typography System
**File:** `typography.md`
- 11 typography styles (Title through Instructional)
- Font families: Geist (primary), Roboto (fallback)
- Line heights, weights, and sizes
- Known component usage references

### Spacing System
**File:** `spacing.md`
- 9 spacing tokens (2px - 64px)
- 8px base grid system
- Token names: Slight, Next, Tight, Close, Near, Related, Breathe, Separate, Distant

## Layout Components

### Workspace
**File:** `workspace.md`
- Container component for content display
- **Variants:** Padding (on/off), showTitle (true/false)
- Includes title bar with heading, metadata, badge, and buttons
- Uses child components: Title Bar/Section Title, Badge

### Title Bar / Page Title
**File:** `title-bar-page-title.md`
- Page-level header component
- **Variants:** Mobile (on/off), showSubtitle (true/false), showTitleBarAction (true/false)
- Typography: Heading 1 (24px) for title, Base Regular (14px) for subtitle
- Supports desktop and mobile layouts

### Title Bar / Section Title
**File:** `title-bar-section-title.md`
- Section header component with hierarchy levels
- **Variants:** Variant (wide), Hierarchy (SH1/SH2/SH3), Mobile (on/off), showSubtitle (true/false)
- SH1: Heading 3 (18px), SH2/SH3: Body Strong (16px)
- SH3 includes decorative line separator
- Mobile=on for SH3 stacks vertically with 260px max-width

## Navigation Components

### Header Top Nav
**File:** `header-top-nav.md`
- Top-level navigation header
- (Check file for specific variants and properties)

### Vertical Navigation
**File:** `vertical-navigation.md`
- Side navigation component
- (Check file for specific variants and properties)

## Form Components

### Button
**File:** `button.md`
- Primary interactive component
- **Variants:** Multiple variants including size and state options
- States: Default, Hover, Pressed, Focus, Disabled
- (Check file for complete variant matrix)

### Icon Button
**File:** `icon-button.md`
- Button with icon-only display
- **Variants:** Size and state variations
- (Check file for specific specifications)

### Form Field
**File:** `form-field.md`
- Generic form field wrapper/container
- (Check file for specific variants and properties)

### Form Label
**File:** `form-label.md`
- Label component for form inputs
- Typography: Body Regular
- (Check file for complete specifications)

### Text Input
**File:** `text-input.md`
- Text input field component
- **Variants:** States and size variations
- (Check file for specific specifications)

### Form File Upload
**File:** `form-file-upload.md`
- File upload input component
- (Check file for specific variants and properties)

### Dropdown
**File:** `dropdown.md`
- Select/dropdown input component
- (Check file for specific variants and properties)

## UI Components

### Badge
**File:** `badge.md` (if exists, or referenced in workspace.md)
- Status indicator component
- Used in Workspace title bar
- (Check workspace.md or dedicated badge.md for specifications)

### Modal
**File:** `modal.md`
- Overlay dialog component
- (Check file for specific variants and properties)

## HTML/CSS Output Examples

**Directory:** `html-css-output/`
- Contains static HTML/CSS implementations of components
- Files: `badge.html`, `badge.css`, `button.html`, `button.css`
- Use as reference for implementation patterns

## How to Use This Index

### For Implementation:
1. **Locate the component** you need in the index above
2. **Open the referenced .md file** for complete specifications
3. **Reference design-tokens.json** for exact token values
4. **Follow the documented variants** and states
5. **Use token names** (not hardcoded values) in your implementation

### For Lovable/AI Agents:
When requesting component creation, reference specific files:

```
Example prompts:
- "Using button.md, create a Primary Medium button"
- "Using workspace.md and title-bar-section-title.md, create a Workspace with SH1 title"
- "Reference typography.md to implement the Heading 1 style"
- "Use spacing.md tokens to add padding of nova/spacing/near"
```

### Component Dependencies:
Some components use other components as children:

- **Workspace** → uses Title Bar/Section Title, Badge
- **Title Bar components** → may use Icon Button, Badge
- **Form Field** → may use Form Label, Text Input

When implementing composite components, reference all dependent component documentation.

## Documentation Standards

All component documentation follows these standards:
- **Token-based:** All values reference design tokens
- **Framework-agnostic:** Visual specifications only, no implementation code
- **Variant-complete:** All Figma variants documented
- **State-complete:** All interactive states documented
- **Accessibility:** ARIA attributes and semantic guidelines included

## Version Information

All components are currently at **Version 1.0** unless otherwise noted in individual files.

---

## Quick Reference Table

| Component | File | Key Variants | Primary Use Case |
|-----------|------|--------------|------------------|
| Workspace | `workspace.md` | Padding, showTitle | Content containers |
| Title Bar/Page Title | `title-bar-page-title.md` | Mobile, showSubtitle | Page headers |
| Title Bar/Section Title | `title-bar-section-title.md` | Hierarchy (SH1/SH2/SH3), Mobile | Section headers |
| Button | `button.md` | Type, Size, State | Primary interactions |
| Icon Button | `icon-button.md` | Size, State | Icon-only actions |
| Text Input | `text-input.md` | State, Size | Text entry |
| Form Label | `form-label.md` | - | Input labels |
| Dropdown | `dropdown.md` | State | Selection inputs |
| Badge | Referenced in workspace.md | Color variants | Status indicators |
| Modal | `modal.md` | - | Overlays/dialogs |

## Getting Started

**New to this documentation?**
1. Start with `DESIGN-TOKENS.md` to understand the token system
2. Review `typography.md` and `spacing.md` for foundation
3. Choose a component from the table above
4. Open the specific .md file for detailed specifications
5. Implement using the documented tokens and variants

**For AI/Lovable:**
Attach this `index.md` file along with specific component files to help the AI locate and understand the component structure and relationships.
