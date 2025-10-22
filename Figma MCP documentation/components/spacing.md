# Spacing

## Overview
The spacing system provides a consistent, predictable scale for margins, padding, gaps, and layout spacing throughout the design system. Based on an 8px grid system with fractional values for tighter spaces, this scale ensures visual rhythm and hierarchy while maintaining flexibility for various layout needs.

## Spacing Philosophy

### Base Unit
- **Base:** 8px (or multiples thereof)
- **Fractions:** Can be used for smaller spaces (2px, 4px)

This approach ensures:
- Consistent visual rhythm across the interface
- Predictable spacing that scales well
- Clear hierarchy between related and unrelated elements
- Flexibility for both tight and spacious layouts

---

## Spacing Scale

### `nova/spacing/slight` - 2px
**Value:** 2px

**Design Token:** `nova/spacing/slight`

**Purpose:** Gaps between icons

**Use Cases:**
- Minimal gaps between closely related icons
- Fine-tuning alignment and positioning
- Tight spacing in dense UI areas

---

### `nova/spacing/next` - 4px
**Value:** 4px

**Design Token:** `nova/spacing/next`

**Purpose:** Gaps between icons

**Use Cases:**
- Small gaps between icon groups
- Internal component spacing
- Compact element separation

---

### `nova/spacing/tight` - 8px
**Value:** 8px

**Design Token:** `nova/spacing/tight`

**Purpose:** Base spacing unit

**Use Cases:**
- Standard internal padding for compact components
- Gap between related elements within a component
- Tight but comfortable spacing

---

### `nova/spacing/close` - 12px
**Value:** 12px

**Design Token:** `nova/spacing/close`

**Purpose:** Close proximity spacing

**Use Cases:**
- Internal component padding
- Spacing between closely related elements
- Comfortable breathing room within components

---

### `nova/spacing/near` - 16px
**Value:** 16px

**Design Token:** `nova/spacing/near`

**Purpose:** Default margins

**Use Cases:**
- Standard padding for most components
- Default margins between elements
- Consistent spacing in forms and layouts
- Base unit for comfortable readability

---

### `nova/spacing/related` - 24px
**Value:** 24px

**Design Token:** `nova/spacing/related`

**Purpose:** More spacious padding

**Use Cases:**
- Generous padding for larger components
- Spacing between related sections
- Comfortable separation while maintaining relationship
- Card and panel padding

---

### `nova/spacing/breathe` - 32px
**Value:** 32px

**Design Token:** `nova/spacing/breathe`

**Purpose:** Create separation

**Use Cases:**
- Clear visual separation between content sections
- Vertical spacing between major content blocks
- Generous padding for emphasis
- Breathing room in spacious layouts

---

### `nova/spacing/separate` - 48px
**Value:** 48px

**Design Token:** `nova/spacing/separate`

**Purpose:** These things are different

**Use Cases:**
- Strong visual separation between unrelated elements
- Major section breaks
- Clear boundaries between distinct content areas
- Emphasize lack of relationship

---

### `nova/spacing/distant` - 64px
**Value:** 64px

**Design Token:** `nova/spacing/distant`

**Purpose:** Sections that do not relate

**Use Cases:**
- Maximum separation between completely unrelated sections
- Large page-level spacing
- Emphasize independence of content areas
- Generous padding for hero sections or major page divisions

---

## Spacing Hierarchy

### Visual Relationship Scale (Closest to Most Distant)

1. **Slight (2px)** - Virtually touching, minimal separation
2. **Next (4px)** - Very close, tightly grouped
3. **Tight (8px)** - Close, clearly related
4. **Close (12px)** - Comfortable proximity, related
5. **Near (16px)** - Default spacing, moderate relationship
6. **Related (24px)** - More space, still related
7. **Breathe (32px)** - Clear separation, distinct but grouped
8. **Separate (48px)** - Strong separation, different things
9. **Distant (64px)** - Maximum separation, unrelated

### Spacing Multipliers (8px Base)
- 2px = Base × 0.25 (fraction)
- 4px = Base × 0.5 (fraction)
- 8px = Base × 1
- 12px = Base × 1.5
- 16px = Base × 2
- 24px = Base × 3
- 32px = Base × 4
- 48px = Base × 6
- 64px = Base × 8

---

## Design Tokens Reference

All spacing values are available as design tokens:

| Token | Value | Multiplier | Purpose |
|-------|-------|------------|---------|
| `nova/spacing/slight` | 2px | 0.25× | Gaps between icons |
| `nova/spacing/next` | 4px | 0.5× | Gaps between icons |
| `nova/spacing/tight` | 8px | 1× | Base spacing |
| `nova/spacing/close` | 12px | 1.5× | Close proximity |
| `nova/spacing/near` | 16px | 2× | Default margins |
| `nova/spacing/related` | 24px | 3× | More spacious padding |
| `nova/spacing/breathe` | 32px | 4× | Create separation |
| `nova/spacing/separate` | 48px | 6× | These things are different |
| `nova/spacing/distant` | 64px | 8× | Sections that do not relate |

---

## Usage Guidelines

### Best Practices

#### Do:
- Use spacing tokens consistently throughout the design
- Follow the visual relationship hierarchy (closer spacing = more related)
- Use the base 8px unit or its multiples for primary spacing
- Use fractional values (2px, 4px) only for icons or fine-tuning
- Consider the semantic meaning of spacing (Near for default, Distant for unrelated)
- Maintain consistent spacing within similar components
- Use larger spacing values to create clear visual hierarchy
- Let spacing communicate relationships between elements

#### Don't:
- Create custom spacing values outside the defined scale
- Use large spacing values (Breathe, Separate, Distant) for internal component spacing
- Use small spacing values (Slight, Next) for major layout divisions
- Mix spacing scales randomly without considering visual relationships
- Ignore the semantic names - they communicate intent
- Apply the same spacing everywhere - variety creates hierarchy
- Use Slight or Next for text content spacing (too tight)

### Choosing the Right Spacing

#### Internal Component Spacing
**Tight (8px) to Close (12px)**
- Internal padding within buttons, inputs, cards
- Gap between icon and label
- Space between form elements within a field

#### Related Elements
**Near (16px) to Related (24px)**
- Default margins between elements
- Spacing between form fields
- Padding within cards or panels
- Gap between related sections

#### Section Separation
**Breathe (32px) to Separate (48px)**
- Vertical spacing between major content sections
- Separation between distinct content blocks
- Clear boundaries between different types of content

#### Major Divisions
**Distant (64px)**
- Page-level spacing
- Hero sections
- Completely unrelated content areas
- Maximum visual separation

### Semantic Meaning

The spacing scale uses semantic naming to communicate intent:

- **Slight/Next:** Almost touching, minimal gap
- **Tight:** Compact but clear
- **Close:** Comfortable proximity
- **Near:** Standard, default spacing
- **Related:** More generous, still connected
- **Breathe:** Room to breathe, distinct but grouped
- **Separate:** Different things, clear boundary
- **Distant:** Completely unrelated, maximum separation

---

## Accessibility Considerations

### Visual Clarity
- Use spacing to create clear focus areas
- Larger spacing helps users with cognitive disabilities parse content
- Consistent spacing aids navigation and comprehension
- Proper spacing improves readability for low-vision users

### Reading Flow
- Use Near (16px) or larger for paragraph spacing
- Separate distinct content sections with Breathe (32px) or more
- Create clear visual groups through consistent spacing

---

## Layout Patterns

### Common Spacing Combinations

#### Compact Components (Buttons, Inputs)
- **Internal padding:** Tight (8px) or Close (12px)
- **Between elements:** Near (16px)

#### Cards and Panels
- **Internal padding:** Near (16px) or Related (24px)
- **Between cards:** Related (24px) or Breathe (32px)

#### Forms
- **Field internal padding:** Tight (8px) or Close (12px)
- **Between fields:** Near (16px)
- **Between sections:** Breathe (32px)

#### Page Layout
- **Content padding:** Near (16px) to Related (24px)
- **Section spacing:** Breathe (32px) to Separate (48px)
- **Major divisions:** Distant (64px)

---

## Implementation Notes

### CSS Variables
When implementing, reference spacing tokens as CSS variables or design system constants:
```
padding: var(--nova-spacing-near);
margin-bottom: var(--nova-spacing-breathe);
gap: var(--nova-spacing-tight);
```

### Consistency
- Always use the defined spacing tokens
- Don't hardcode pixel values
- Maintain the same token for similar spacing needs across components
- Document any deviations from standard spacing patterns

### Stacking
When multiple spacing values affect the same area (e.g., margin + padding):
- Consider the combined visual space
- Avoid excessive stacking that creates unintended gaps
- Use consistent spacing sides (e.g., vertical rhythm with consistent bottom margins)

---

## Visual Reference

Each spacing value creates a progressively larger separation:

| Token | Size | Visual Reference |
|-------|------|------------------|
| Slight | 2px | ▪ |
| Next | 4px | ▪▪ |
| Tight | 8px | ▪▪▪▪ |
| Close | 12px | ▪▪▪▪▪▪ |
| Near | 16px | ▪▪▪▪▪▪▪▪ |
| Related | 24px | ▪▪▪▪▪▪▪▪▪▪▪▪ |
| Breathe | 32px | ▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪ |
| Separate | 48px | ▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪ |
| Distant | 64px | ▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪▪ |

---

## Version History
- **Version 1.0** - Initial spacing system with 9 spacing tokens ranging from 2px (Slight) to 64px (Distant), based on 8px grid with fractional values
