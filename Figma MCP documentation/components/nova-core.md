# Nova Design System - Core Reference

**Version:** 1.0  
**Purpose:** Essential design system specifications for AI agents to automatically apply Nova design patterns.  
**Usage:** Attach this file at the start of every Lovable conversation for consistent Nova design implementation.

---

## 🎯 AI Agent Instructions

**When processing user requests:**
1. **Always use Nova design tokens** - Never hardcode colors, spacing, or typography
2. **Apply documented components** - Use Button, Text Input, Form Label, etc. with their specifications
3. **Follow default choices** - Unless user specifies otherwise, use the defaults listed below
4. **Maintain consistency** - Same components for similar purposes across the interface
5. **Include accessibility** - ARIA attributes, semantic HTML, keyboard navigation
6. **Natural language friendly** - User doesn't need to specify design details

**When user says things like:**
- "Create a dashboard" → Use Workspace with Title Bar, proper sections with spacing
- "Add a login form" → Use Form Labels (with required indicators) + Text Inputs + Primary Button
- "Show a confirmation" → Use Modal (Dialog variant) with Destructive + Ghost buttons
- "Add a button" → Use Button component, Primary variant, Medium size

---

## 🎨 Complete Design Tokens Reference

### Typography Tokens

**Token Format:** `nova/typography/[style]/[weight]`

| Token | Size | Weight | Line Height | Use Cases |
|-------|------|--------|-------------|-----------|
| `nova/typography/title` | 30px | SemiBold (600) | 100% | Major page headings |
| `nova/typography/heading/1` | 24px | SemiBold (600) | 140% | Page titles |
| `nova/typography/heading/2` | 20px | SemiBold (600) | 140% | Section headers |
| `nova/typography/heading/3` | 18px | SemiBold (600) | 140% | Subsection headers |
| `nova/typography/body/regular` | 16px | Regular (400) | 140% | Body text, form labels |
| `nova/typography/body/strong` | 16px | SemiBold (600) | 140% | Emphasized body text |
| `nova/typography/base/regular` | 14px | Regular (400) | 130% | UI text, input values |
| `nova/typography/base/strong` | 14px | SemiBold (600) | 130% | Emphasized UI text |
| `nova/typography/supporting/regular` | 12px | Regular (400) | 120% | Helper text, captions |
| `nova/typography/supporting/strong` | 12px | SemiBold (600) | 120% | Emphasized helper text |
| `nova/typography/instructional/regular` | 14px | Regular (400) | 100% | Buttons, badges, tags |

**Font Family:** Geist (primary), Roboto (fallback)

### Spacing Tokens

**Base System:** 8px grid with fractional values for tight spaces

| Token | Value | Common Uses |
|-------|-------|-------------|
| `nova/spacing/slight` | 2px | Minimal gaps, fine adjustments |
| `nova/spacing/next` | 4px | Icon spacing, very tight gaps, badge padding |
| `nova/spacing/tight` | 8px | Standard component gaps, button padding |
| `nova/spacing/close` | 12px | Related elements, form row spacing |
| `nova/spacing/near` | 16px | Default padding/margins, comfortable spacing |
| `nova/spacing/moderate` | 24px | Section spacing, card padding |
| `nova/spacing/far` | 32px | Large section separation |
| `nova/spacing/remote` | 48px | Major page sections |
| `nova/spacing/distant` | 64px | Page-level separations |

**Default Choices:**
- Component internal padding: `nova/spacing/tight` (8px) or `nova/spacing/close` (12px)
- Container padding: `nova/spacing/near` (16px)
- Between form rows: `nova/spacing/close` (12px)
- Between sections: `nova/spacing/moderate` (24px) or `nova/spacing/far` (32px)
- Between buttons: `nova/spacing/tight` (8px)

### Color Tokens

#### Typography Colors
```
nova/color/typography/base (#151d1e)
  → Main text color for all primary content

nova/color/typography/muted (rgba(0,0,0,0.62))
  → Secondary text, subtitles, helper text, optional indicators

nova/color/typography/link (#0969da)
  → Links and interactive text

nova/color/typography/inverse (#ffffff)
  → Text on dark/colored backgrounds (e.g., primary button text)
```

#### Surface Colors
```
nova/surfaces/color/workspace (#ffffff)
  → Main backgrounds, cards, modals, input backgrounds

nova/surfaces/color/background (#f5f7fa)
  → Page background, subtle contrast areas

nova/surfaces/color/workspace border (#e0e6e6)
  → Borders, dividers, separators, input borders

nova/surfaces/color/surface-hover (#f6f8fa)
  → Hover states for surfaces, subtle background changes
```

#### Interactive Colors - Primary
```
nova/interactive/color/primary (#0969da)
  → Primary buttons (default state), primary actions, links

nova/interactive/color/primary-hover (#0550ae)
  → Primary button hover state, darker shade

nova/interactive/color/primary-pressed (#033d8b)
  → Primary button pressed/active state, darkest shade
```

#### Interactive Colors - Destructive
```
nova/interactive/color/destructive (#d1242f)
  → Destructive actions (delete, remove), error states

nova/interactive/color/destructive-hover (#a20915)
  → Destructive button hover state

nova/interactive/color/destructive-pressed (#870714)
  → Destructive button pressed state
```

#### Interactive Colors - Neutral
```
nova/color/neutral/secondary (#f6fafa)
  → Badge backgrounds, subtle UI elements

nova/color/neutral/primary (#889192)
  → Badge borders, muted borders

nova/color/neutral/dark (#333b3b)
  → Badge text, strong muted text

nova/interactive/color/ghost-hover (rgba(175,184,193,0.2))
  → Ghost button hover background, subtle hover effects
```

#### Focus & Selection
```
nova/interactive/color/focus-ring (#0969da with 20% opacity)
  → Focus indicators around interactive elements
```

### Border Radius Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `nova/radii/component/badge` | 4px | Badges, small tags |
| `nova/radii/component/button` | 6px | Buttons, similar small components |
| `nova/radii/component/input` | 8px | Text inputs, form fields |
| `nova/radii/component/modal` | 12px | Modals, cards, workspaces, larger containers |
| `nova/radii/component/workspace` | 12px | Workspace containers |

---

## 📦 Component Quick Reference

### Available Components

| Component | File Reference | Default Configuration | Common Use Cases |
|-----------|---------------|----------------------|------------------|
| **Button** | `button.md` or `nova-components-essential.md` | Primary, Medium, Default | Primary actions, form submissions |
| **Text Input** | `text-input.md` or `nova-components-essential.md` | Default state, 32px height | Form fields, search, data entry |
| **Form Label** | `form-label.md` or `nova-components-essential.md` | Body Regular typography | Input labels with required/optional |
| **Workspace** | `workspace.md` | Padding=on, showTitle=true | Page containers, content sections |
| **Title Bar / Page Title** | `title-bar-page-title.md` | Mobile=off, showSubtitle=true | Main page titles with context |
| **Title Bar / Section Title** | `title-bar-section-title.md` | Hierarchy=SH1, Mobile=off | Section headers with hierarchy |
| **Modal** | `modal.md` | Modal variant (720px), Padding=on | Dialogs, confirmations |
| **Badge** | Referenced in workspace.md | Neutral variant | Status indicators |
| **Icon Button** | `icon-button.md` | Medium size | Icon-only actions |
| **Dropdown** | `dropdown.md` | Default state | Selection inputs |

### Component Default Choices

**When user doesn't specify details:**

- **"Add a button"** → Primary variant, Medium size (32px), Default state
- **"Add a form"** → Form Labels (Body Regular) + Text Inputs (32px height) with `nova/spacing/close` (12px) between rows
- **"Create a page"** → Workspace (padding=on, showTitle=true) with Title Bar / Page Title
- **"Add a title"** → Title Bar / Section Title (SH1 hierarchy, 18px)
- **"Add a section header"** → Title Bar / Section Title (SH2 hierarchy, 16px)
- **"Show a dialog"** → Modal (Modal variant 720px, padding=on)
- **"Show a confirmation"** → Modal (Dialog variant 288px) with Destructive + Ghost buttons
- **"Add an input"** → Text Input (32px height) with Form Label (required indicator)

---

## 🎭 Common Layout Patterns

### Standard Page Layout
```
Page Background: nova/surfaces/color/background (#f5f7fa)
└─ Workspace Container
    ├─ Padding: nova/spacing/near (16px)
    ├─ Background: nova/surfaces/color/workspace (#ffffff)
    ├─ Border radius: nova/radii/component/workspace (12px)
    │
    ├─ Title Bar / Page Title (optional, at top)
    │   ├─ Title: nova/typography/heading/1 (24px)
    │   ├─ Subtitle: nova/typography/base/regular (14px, muted)
    │   └─ Actions: Button(s)
    │
    └─ Content Area
        ├─ Section 1
        │   ├─ Title Bar / Section Title (SH2, 16px)
        │   └─ Content with nova/spacing/moderate (24px) padding
        │
        └─ Section 2
            ├─ Title Bar / Section Title (SH2, 16px)
            └─ Content

Spacing between sections: nova/spacing/moderate (24px) or nova/spacing/far (32px)
```

### Form Layout Pattern
```
Workspace or Modal
└─ Form Container
    ├─ Title: Title Bar / Section Title (SH2 or SH3)
    │
    ├─ Form Row 1
    │   ├─ Form Label (required=true)
    │   │   ├─ Text: nova/typography/body/regular (16px)
    │   │   └─ Asterisk: nova/typography/base/strong (14px, RED)
    │   └─ Text Input (height: 32px)
    │
    ├─ Gap: nova/spacing/close (12px)
    │
    ├─ Form Row 2
    │   ├─ Form Label (optional=true)
    │   │   ├─ Text: nova/typography/body/regular (16px)
    │   │   └─ "(optional)": nova/typography/supporting/regular (12px, muted)
    │   └─ Text Input (height: 32px)
    │
    ├─ Gap: nova/spacing/close (12px)
    │
    └─ Action Buttons
        ├─ Button (Primary, Medium) - "Submit"
        └─ Button (Ghost, Medium) - "Cancel"
        
        Gap between buttons: nova/spacing/tight (8px)
```

### Modal Dialog Pattern
```
Modal Overlay: rgba(0, 0, 0, 0.5)
└─ Modal Container
    ├─ Width: 720px (Modal) or 288px (Dialog)
    ├─ Border radius: nova/radii/component/modal (12px)
    ├─ Background: nova/surfaces/color/workspace (#ffffff)
    ├─ Padding: nova/spacing/near (16px)
    │
    ├─ Header
    │   ├─ Title Bar / Section Title (SH3, 16px)
    │   └─ Close Button (Icon Button)
    │
    ├─ Gap: nova/spacing/near (16px)
    │
    ├─ Content Area
    │   └─ Body text: nova/typography/body/regular (16px)
    │
    ├─ Gap: nova/spacing/near (16px)
    │
    └─ Footer / Action Buttons
        ├─ Button (Destructive, Medium) - "Delete" / "Confirm"
        └─ Button (Ghost, Medium) - "Cancel"
```

### Card / Content Block Pattern
```
Card Container
├─ Background: nova/surfaces/color/workspace (#ffffff)
├─ Border: 1px solid nova/surfaces/color/workspace border (#e0e6e6)
├─ Border radius: nova/radii/component/modal (12px)
├─ Padding: nova/spacing/near (16px)
│
├─ Header (optional)
│   └─ Title Bar / Section Title (SH3, 16px)
│
├─ Gap: nova/spacing/close (12px)
│
└─ Content
    ├─ Body text: nova/typography/body/regular (16px)
    └─ Supporting text: nova/typography/supporting/regular (12px, muted)
```

---

## ✅ Implementation Checklist

When building any component or layout:

### Typography
- [ ] Uses appropriate `nova/typography/*` token for text style
- [ ] Never hardcodes font sizes (use 30/24/20/18/16/14/12px scale)
- [ ] Applies correct line heights (100%/120%/130%/140%)
- [ ] Uses Geist font family

### Spacing
- [ ] All padding/margins use `nova/spacing/*` tokens
- [ ] Follows 8px base grid system (8, 16, 24, 32, etc.)
- [ ] Uses appropriate spacing scale (slight/next/tight/close/near/moderate/far/remote/distant)
- [ ] Consistent spacing between similar elements

### Colors
- [ ] Uses `nova/color/*` or `nova/interactive/color/*` tokens
- [ ] Never hardcodes hex colors directly
- [ ] Appropriate contrast for accessibility
- [ ] Correct color for element purpose (primary for main actions, destructive for delete, etc.)

### Components
- [ ] Uses documented component variants (Primary/Secondary/Ghost for buttons)
- [ ] Includes all required props/states
- [ ] Follows documented component structure
- [ ] Maintains consistent component usage

### Accessibility
- [ ] Semantic HTML elements (button, input, label, etc.)
- [ ] ARIA labels where needed
- [ ] Keyboard navigation support
- [ ] Focus indicators visible
- [ ] Form labels associated with inputs
- [ ] Required fields marked clearly

### Borders & Radius
- [ ] Uses `nova/radii/component/*` tokens for border radius
- [ ] Consistent radius for similar components (buttons: 6px, inputs: 8px, containers: 12px)
- [ ] Border colors use `nova/surfaces/color/workspace border` token

---

## 🚫 Common Mistakes to Avoid

### ❌ Don't Do This:
```css
/* Hardcoded color */
background-color: #0969da;

/* Arbitrary spacing */
margin: 15px;
padding: 20px;

/* Random font size */
font-size: 17px;

/* Mixed spacing units */
margin: 12px 16px 14px 8px;

/* Hardcoded border radius */
border-radius: 10px;
```

### ✅ Do This Instead:
```css
/* Use color token */
background-color: var(--nova-interactive-color-primary);

/* Use spacing tokens */
margin: var(--nova-spacing-near); /* 16px */
padding: var(--nova-spacing-near); /* 16px */

/* Use typography scale */
font-size: var(--nova-typography-heading-3-size); /* 18px */

/* Consistent spacing with tokens */
margin: var(--nova-spacing-close) var(--nova-spacing-near); /* 12px 16px */

/* Use radius token */
border-radius: var(--nova-radii-component-input); /* 8px */
```

---

## 🎯 Quick Decision Guide for AI

### When User Says → AI Should Do

| User Request | Component Choice | Key Settings |
|--------------|-----------------|--------------|
| "Create a dashboard" | Workspace + Title Bar / Page Title + Sections | Padding=on, showTitle=true, SH2 for sections |
| "Add a form" | Form Labels + Text Inputs + Buttons | Required indicators, 12px row gaps |
| "Add a button" | Button component | Primary, Medium, Default |
| "Show confirmation" | Modal | Dialog variant (288px), Destructive + Ghost buttons |
| "Add a title" | Title Bar / Section Title | SH1 (18px) |
| "Add a section" | Title Bar / Section Title | SH2 (16px) |
| "Add input field" | Form Label + Text Input | Required by default, 32px height |
| "Show error message" | Text with destructive color | Supporting Regular (12px), destructive color |
| "Add status badge" | Badge component | Neutral variant, 4px radius |

---

## 📚 Additional Documentation

**For detailed component specifications**, refer to:
- `nova-components-essential.md` - Button, Text Input, Form Label with full specs
- Individual component files - workspace.md, modal.md, etc.

**This file provides:**
- ✅ All design tokens
- ✅ Quick component reference
- ✅ Default choices
- ✅ Common patterns
- ✅ AI guidance

**You still need for details:**
- Specific component variants and states
- Exact component measurements
- Component property combinations

---

## Version History
- **Version 1.0** - Initial core reference with complete tokens, patterns, and AI guidance
