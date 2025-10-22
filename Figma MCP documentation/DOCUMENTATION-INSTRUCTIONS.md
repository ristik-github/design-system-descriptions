# Component Documentation Generation Instructions

## Overview
This document provides step-by-step instructions for creating comprehensive Markdown documentation for Figma components. The documentation is designed to be framework-agnostic and usable by both developers and AI models for implementation.

---

## Documentation Philosophy

### Core Principles
1. **Token-Based:** Use design token names only, never hardcoded values
2. **Framework-Agnostic:** Describe the component's visual design, not specific code implementations
3. **Comprehensive:** Cover all variants, states, and visual specifications
4. **Accessible:** Include accessibility considerations (ARIA attributes, screen readers)
5. **Visual-Focused:** Emphasize what you can see and extract from Figma
6. **Clear:** Written for both human developers and AI models

### What to Document
- Component purpose and overview
- All variants and their use cases
- All interactive states (visual specifications)
- Design tokens (spacing, colors, typography, borders, etc.)
- Size variations and their specific properties
- Layout and structural specifications (flex, alignment, dimensions)
- Sizing behavior (full width, hug contents, fixed)
- Visual accessibility (focus states, contrast from design tokens)
- ARIA attributes for screen readers
- Usage guidelines and best practices
- Visual behaviors specific to the component

### What NOT to Document

❌ **NEVER Include These Sections:**

1. **Implementation Notes / Implementation Details**
   - ❌ NO: "CSS Variables", "Border Inheritance", "Content Slot implementation"
   - ❌ NO: "When implementing, reference spacing tokens as CSS variables"
   - ❌ NO: Framework-specific implementation guidance
   - ✅ YES: Only document what is VISIBLE in Figma

2. **Responsive Behavior / Mobile Considerations**
   - ❌ NO: "Consider reducing spacing on mobile", "Stack elements on small screens"
   - ❌ NO: "May need to hide elements on narrow viewports"
   - ❌ NO: Any mention of breakpoints, media queries, or viewport sizes
   - ✅ YES: Only if explicit mobile/tablet/desktop variants exist in Figma

3. **Hardcoded Values**
   - ❌ NO: "52px height" - Use token name or calculation
   - ❌ NO: "16px padding" - Use `nova/spacing/near` (16px)
   - ❌ NO: "#ffffff" - Use `nova/surfaces/color/workspace` (#ffffff)
   - ✅ YES: Token name first, value in parentheses

4. **Code Examples**
   - ❌ NO: React, Vue, Angular, or any framework code
   - ❌ NO: CSS, HTML, or JavaScript snippets
   - ❌ NO: "Use rounded-[inherit] to maintain corners"

5. **Performance / Optimization**
   - ❌ NO: Performance tips
   - ❌ NO: Build instructions
   - ❌ NO: State management patterns

6. **Implementation Logic**
   - ❌ NO: Validation logic
   - ❌ NO: Error handling code
   - ❌ NO: Hooks, stores, or state management

7. **Multi-Component Patterns**
   - ❌ NO: How to combine multiple components
   - ❌ NO: Layout patterns beyond single component

8. **Color Contrast / WCAG Compliance**
   - ❌ NO: "Title text (#151d1e on #ffffff) meets WCAG AA standards"
   - ❌ NO: "Badge text should be verified for contrast"
   - ❌ NO: Any mention of contrast ratios or accessibility compliance
   - ✅ YES: Color contrast is inherent in Figma component design - no need to document

9. **Reference / Node IDs & Assets**
   - ❌ NO: "Reference / Node IDs & Assets (from exported design context)"
   - ❌ NO: "Component frame name: 'Title Bar / Section Title'"
   - ❌ NO: "Example node IDs (useful when cross-referencing the Figma source)"
   - ❌ NO: "Variant=wide, Hierarchy=SH1, Mobile=off → `2058:8795`"
   - ❌ NO: "Image assets referenced in the design export"
   - ❌ NO: Data-node-id attributes or internal element mappings
   - ✅ YES: Node IDs are internal Figma metadata - not needed in documentation

10. **Usage Guidance Notes / Advisory Sections**
    - ❌ NO: "Note: The following guidance is interpretative and should be verified against product conventions"
    - ❌ NO: Sections labeled as "advisory" or "interpretative"
    - ✅ YES: If you cannot provide factual guidance, omit it entirely

**Summary - Document ONLY:**
- What you can SEE in Figma
- Design token names (with values in parentheses)
- Visual specifications (sizes, colors, spacing using tokens)
- Variants that EXIST in Figma metadata
- Layout structure visible in the design
- Accessibility attributes (ARIA) that are standard (NOT color contrast)
- Usage guidelines (only if based on facts from existing component docs)

### CRITICAL: Interpretations vs. Facts

**Facts (Always Document):**
- What is EXPLICITLY in the Figma design
- Design token names and values from `get_variable_defs`
- Specifications: sizes, colors, spacing, typography from the design
- Visual structure and layout from screenshots and code
- Variant combinations that exist in metadata

**Interpretations (Handle with Extreme Care):**
- **Use Cases** for components or typography styles
- **When to Use** guidance
- **Best Practices** (Do's and Don'ts)

**Rules for Interpretations:**

1. **Cross-Reference Existing Documentation First**
   - Before adding interpretations, search existing `.md` files in the workspace
   - Check if components already document their typography/token usage
   - Example: If documenting typography, check button.md, form-label.md, text-input.md to see which styles they actually use
   - Build use cases from ACTUAL component documentation, not assumptions

2. **Mark Interpretations Clearly**
   - If you cannot find factual references, mark sections as:
     ```markdown
     > **Note:** The following use cases are suggested interpretations and should be verified against actual component implementations.
     ```

3. **Avoid Conflicting Information**
   - NEVER add interpretation that could contradict actual implementation
   - Example: Don't say "Base typography is used for form labels" if form-label.md shows it uses Body typography
   - When in doubt, omit the interpretation entirely

4. **Prefer Omission Over Incorrect Information**
   - It's better to have incomplete documentation than incorrect documentation
   - AI agents will make errors based on incorrect documentation
   - Developers will waste time debugging conflicts

5. **Use Existing Documentation as Source of Truth**
   - If button.md says buttons use `nova/typography/instructional/regular`, that's a FACT for typography use cases
   - If form-label.md says labels use `nova/typography/body/regular`, that's a FACT for typography use cases
   - Build comprehensive use cases by aggregating these FACTS

**Example of CORRECT Approach:**
```markdown
### Base Regular

**Design Token:** `nova/typography/base/regular`

**Specifications:**
- Size: 14px
- Line Height: 130% (1.3)
- Weight: Regular (400)

**Known Uses (from component documentation):**
- Text Input: Input field text (ref: text-input.md)
- Form Label: Required asterisk (Base Strong variant) (ref: form-label.md)
```

**Example of INCORRECT Approach:**
```markdown
**Use Cases:**
- Form labels ❌ (Wrong - labels use Body, not Base)
- Button text ❌ (Wrong - buttons use Instructional)
```

---

## Step-by-Step Process

### Step 1: Select the Component in Figma

**Action:** Select the master component (component set) in Figma, not an instance.

**Why:** The master component provides access to all variants, states, and design tokens.

**Tip:** If you initially select an instance and don't see all variants/tokens, switch to the master component.

---

### Step 2: Extract Component Information

**Use these Figma MCP tools:**

1. **`mcp_figma_get_design_context`**
   - Gets the component structure and code representation
   - Shows variant properties and their values
   - Provides initial token information

2. **`mcp_figma_get_screenshot`**
   - Visual reference of the component
   - Helps understand the layout and appearance

3. **`mcp_figma_get_variable_defs`**
   - **CRITICAL:** Extracts all design token names and their values
   - This is where you get color tokens, spacing tokens, etc.

4. **`mcp_figma_get_metadata`**
   - Shows all variant combinations
   - Lists all available states and options
   - Provides component hierarchy

**Parameters to use:**
```
clientFrameworks: "documentation"
clientLanguages: "markdown"
```

---

### Step 3: Analyze Variants and Properties

**From the metadata/design context, identify:**

1. **Variant Properties:** What are the main variant axes?
   - Examples: Variant (Primary/Secondary/Tertiary), State, Size, Color, etc.

2. **Property Values:** What values does each property have?
   - Example: Size = Small | Large
   - Example: State = Default | Hover | Focus | Pressed | Loading | Disabled

3. **Available Combinations:** Which combinations are actually implemented?
   - Not all combinations may exist (e.g., some colors only for certain variants)

---

### Step 4: Deep Dive into Size Variants

**IMPORTANT:** Always check if different sizes use different design tokens!

**Action:** Call `mcp_figma_get_design_context` and `mcp_figma_get_variable_defs` for individual size variants.

**Example:**
- Get Small variant (e.g., node ID for Small size)
- Get Large variant (e.g., node ID for Large size)
- Compare the tokens used (especially padding, spacing)

**Common Findings:**
- Different sizes often use different padding tokens
- Height/width differences may come from different padding, not just scaling
- Internal spacing might remain constant while padding changes

---

### Step 5: Extract and Organize Design Tokens

**CRITICAL:** Always use the design tokens that are ACTUALLY APPLIED in Figma, not approximations or hardcoded values!

**NEVER HALLUCINATE TOKENS! If a token is not in `get_variable_defs`, DO NOT make it up!**

**How to verify tokens are being used:**
1. Check `get_variable_defs` output - this shows ALL tokens actually used by the component
2. **ONLY use tokens that appear in the `get_variable_defs` output**
3. Cross-reference with the generated code - look for `var(--token-name)` in class names
4. When documenting measurements (padding, radius, borders), ALWAYS check if a token exists for that value
5. **If you cannot find the appropriate token, ask the user or leave it as a measurement with a note that no token was found**

**Common Typography Token Mistakes:**
- ❌ WRONG: `global/typography/fontsize/14` as a typography token (this is just a size value)
- ✅ CORRECT: `nova/typography/base/regular` (this is the composite typography token with family, size, weight, line height)
- ❌ WRONG: "14px SemiBold" without a token reference
- ✅ CORRECT: `nova/typography/base/strong` (14px SemiBold, 130% line height)

**Token Verification Checklist:**
- [ ] Every token reference exists in `get_variable_defs` output
- [ ] Typography uses composite tokens (e.g., `nova/typography/base/regular`), not size-only tokens
- [ ] If a token doesn't exist, document the raw value with a note: "No token found, raw value used"
- [ ] No made-up token names or assumed token structures

**Group tokens by category:**

1. **Typography Tokens**
   - Font family and style tokens
   - Font size tokens (e.g., `global/typography/fontsize/14`)
   - Line height (often embedded in composite font tokens)
   - **Use the actual token names from Figma**

2. **Spacing Tokens**
   - Padding (may differ by size) - e.g., `nova/spacing/close`, `nova/spacing/tight`
   - Margins
   - Internal gaps - e.g., `nova/spacing/slight`, `nova/spacing/next`
   - **Document per-size differences explicitly**
   - **ALWAYS check if padding/gap values have corresponding tokens**

3. **Color Tokens**
   - Background colors
   - Text/foreground colors
   - Border colors
   - State-specific colors (hover, pressed, focus, disabled)
   - Icon colors
   - Accent colors

4. **Border & Radius Tokens**
   - Border radius - e.g., `nova/radii/component/button`, `nova/radii/component/input`
   - Border width - e.g., `nova/border/basic`, `nova/border/slight`
   - **Don't use "8px" when `nova/radii/component/button` exists**
   - **Don't use "1px" when `nova/border/basic` exists**

5. **Effect Tokens**
   - Shadows
   - Opacity
   - Focus indicators

**Token Documentation Format:**
- **ALWAYS use token NAME with value in parentheses:** `nova/spacing/close` (12px)
- Specify which variant/state/size uses which token
- Example: "Padding: `nova/spacing/close` (12px) horizontal"
- Example: "Border radius: `nova/radii/component/button` (8px)"
- **Never write "8px border radius" when you should write "`nova/radii/component/button` (8px)"**

**CRITICAL: Dimensions and Measurements**

When documenting dimensions (height, width, etc.):

❌ **WRONG:**
- "Height: 52px" (hardcoded value)
- "Height: Auto (typically ~18px with padding)" (calculated height that's redundant)
- "Padding: 16px on all sides" (hardcoded value)
- "Border: 1px solid" (hardcoded value)

✅ **CORRECT:**
- "Width: Hug contents" (for auto-layout components)
- "Height: Hug contents" (for auto-layout components)
- "Padding: `nova/spacing/near` (16px) on all sides"
- "Border: `nova/border/basic` (1px) solid"

**IMPORTANT: Hug Contents vs Calculated Heights**

❌ **DO NOT document calculated heights when components use auto-layout/hug contents:**
- "Height: ~18px (2px padding + 14px line height + 2px padding)" - WRONG, redundant
- "Total height: ~52px" - WRONG if it's derived from padding + content

✅ **INSTEAD, document the actual properties:**
- "Height: Hug contents" - The component automatically sizes to its content
- "Width: Hug contents" - The component automatically sizes to its content
- Then document the properties that determine the size:
  - Padding (with tokens)
  - Typography (with tokens)
  - Content

**Why This Matters:**
- Height/width are **derived** from padding, typography, and content when using auto-layout
- Documenting derived values is redundant and confusing
- It creates maintenance issues - if padding changes, calculated heights become wrong
- Only document the **actual properties** that Figma shows (padding, typography, etc.)

**When Dimensions Don't Have Tokens:**
- If a dimension is calculated (e.g., padding + content), DON'T document the calculation - just document "Hug contents"
- If it's a FIXED dimension (not hug contents), document the raw value with note: "No token found for this dimension"
- Example: "Fixed height: 28px (no token found)"
- Don't make up dimensions - only document what's visible in Figma

**Examples of Correct Dimension Documentation:**

```markdown
### Dimensions

**Title Bar:**
- Width: Full width of container
- Height: Hug contents
- Padding: `nova/spacing/close` (12px) top and bottom
- Sizing behavior: Full width, height adapts to content

**Badge:**
- Width: Hug contents
- Height: Hug contents
- Padding vertical: `nova/spacing/next` (4px)
- Padding horizontal: `nova/spacing/tight` (8px)
- Sizing behavior: Adapts to content in both dimensions

**Fixed Size Component:**
- Width: 200px (fixed)
- Height: 48px (fixed, no token found)
- Padding: `nova/spacing/tight` (8px)
```

---

### Step 6: Structure the Documentation

**Use this standard structure:**

```markdown
# [Component Name]

## Overview
[Brief description of purpose and usage]

## Component Properties

### Variants
[Describe each variant and its purpose]

### Sizes
[List all sizes with their specifications]
- Include dimensions
- Include padding tokens PER SIZE
- Include use cases

### States
[Describe all interactive states: Default, Hover, Focus, Pressed, Loading, Disabled, etc.]
- Document visual specifications for each state
- Include state-specific design tokens

### [Other Properties]
[Additional properties like filled conditions, optional features, etc.]

## Design Tokens

### Typography
[List all typography tokens with usage context]

### Spacing
[List spacing tokens, SEPARATED BY SIZE if they differ]

### Colors
[List all color tokens, organized by variant and state]

### Border & Radius
[List border and radius tokens]

## Layout Specifications

### Structure
[Describe the layout structure - flex direction, alignment, etc.]

### Spacing
[Vertical and horizontal spacing details]

### Visual Properties
[Border radius, border width, backgrounds, etc.]

### Dimensions
[Height, width, and sizing behavior]
- **Sizing behavior:** Full width, hug contents, or fixed
- Component and sub-component dimensions

## Accessibility Considerations

### Label Association
[How labels connect to inputs]

### Keyboard Navigation
[Tab order, keyboard interactions]

### Screen Readers
[Descriptive text requirements, ARIA attributes]

### ARIA Attributes
[Specific ARIA attributes needed for each state/variant]
- Required fields: aria-required
- Error states: aria-invalid, aria-errormessage
- Disabled: disabled attribute
- etc.

## Usage Guidelines

### When to Use
[Describe appropriate use cases for the component and its variants]

### Best Practices
#### Do:
[List of recommended practices]

#### Don't:
[List of anti-patterns]

### [Content Guidelines]
[If applicable: Label writing, placeholder text, etc.]

## Content Structure
[Describe what content/elements make up the component]

## Interactive States
[Detailed visual behavior of each state]

## Visual Behavior Notes
[Component-specific visual behaviors that need clarification]

### Component Architecture
[How the component is visually composed]

### Key Visual Behaviors
[Special behaviors like icon display, state transitions, etc.]

### Sizing Behavior
[Full width vs hug contents, responsive behavior if Figma variants exist]

## Reference Components
[For composite components: list child components]

## Related Components
[ONLY list alternative input types or direct child components]

## Version History
- **Version 1.0** - Initial [component name] component with [list key variant properties and their options]

**Format Rules:**
- Always starts with "Version 1.0" for new documentation
- Brief one-line summary of the component and its variant properties
- List variant properties with their possible values in parentheses
- Example: "Initial workspace component with Padding (on/off) and showTitle (true/false) variants"
- ❌ NO: Verbose explanations, implementation notes, or usage details
- ❌ NO: Multiple version entries unless updating existing documentation
- ❌ NO: "Documentation created from Figma design context" or similar meta-commentary
```

---

### Step 7: Special Considerations

#### Color Tokens
- If color tokens aren't showing in `get_variable_defs`, the component might not have them properly applied
- Try selecting different variants or the master component
- Document missing tokens as placeholders following the naming pattern

#### State Colors
- Each state (default, hover, pressed, focus, disabled) may have different color tokens
- Document the progression: default → hover → pressed
- Focus state often has a separate indicator token

#### **CRITICAL: Verify State Visual Differences**
**Common Error:** Assuming states look the same when they actually have different colors/styles.

**Prevention Steps:**
1. **Always examine the screenshot carefully** - Look for subtle color differences between states
2. **Check available color tokens** - Use `get_variable_defs` to see all available color shades (e.g., `dark-blue/10`, `dark-blue/50`, `dark-blue/100`)
3. **Compare state structures** - Look at the generated code for each state, even if visually subtle
4. **Document ALL visual differences** - Don't assume "same as Default" without verification
5. **Look for progressive patterns** - Interactive states often darken/lighten progressively (Default → Hover → Pressed)

**What to Check for Each State:**
- **Background color** - Most common difference (often uses numbered token variants like `/10`, `/50`, `/100`)
- **Border color** - May change in some states
- **Text color** - May change for contrast or emphasis
- **Opacity** - May be applied in disabled/loading states
- **Additional overlays** - Hover/pressed may add alpha overlays
- **Focus rings** - Additional visual elements in focus state

**Example Pattern:**
- Default: `global/color/dark-blue/10` (lightest)
- Hover: `global/color/dark-blue/50` (medium)
- Pressed: `global/color/dark-blue/100` (darkest)

**If Figma's code generation is incomplete:**
- Cross-reference with the screenshot
- Check token definitions for numbered variants
- Use logical progression based on available tokens
- Document assumptions clearly and verify with design team if uncertain

#### Size-Specific Tokens
- **CRITICAL:** Always check if padding/spacing differs by size
- Document this clearly in:
  1. The "Sizes" section under Component Properties
  2. The "Design Tokens > Spacing" section
  3. The "Layout Specifications > Dimensions" section

#### Complex/Composite Components
- For components with child components (like Form Field = Label + Input), document as **one unified component**
- List child components in "Reference Components" section
- Include all child component specifications inline (variants, states, etc.)
- Make it clear this should be implemented as one cohesive component

#### Sizing Behavior
- **ALWAYS document:** Whether component is full width, hug contents, or fixed
- Check Figma's layout settings (Auto layout, Fixed, Fill container, Hug contents)
- Document for both the component and sub-components (e.g., label row vs input row)

#### Responsive/Breakpoint Variants
- **ONLY document responsive behavior if:**
  - Explicit mobile/desktop/tablet variants exist in Figma
  - Component has breakpoint-specific designs
- **Do NOT assume or speculate** about mobile behavior
- If no variants exist, omit responsive sections

#### Visual Behaviors
- Document component-specific visual quirks (e.g., "readonly shows hyphen instead of placeholder")
- Note state-dependent behaviors (e.g., "icon hidden in readonly state")
- Clarify transitions that might not be obvious from static designs

---

## Validation Checklist

Before finalizing documentation, verify:

- [ ] All design tokens use token NAMES, not values
- [ ] Size variants document their specific padding/spacing tokens
- [ ] All interactive states are documented with visual specifications
- [ ] **CRITICAL: Each state's visual differences are verified** (especially background colors)
- [ ] Screenshot examined for subtle color differences between states
- [ ] Token definitions checked for numbered variants (e.g., `/10`, `/50`, `/100`)
- [ ] No assumptions of "same as Default" without visual verification
- [ ] Color tokens cover all states (default, hover, pressed, focus, disabled)
- [ ] Accessibility section includes ARIA attributes for all relevant states
- [ ] Usage guidelines include Do's and Don'ts
- [ ] No code examples in specific frameworks
- [ ] No performance optimization tips or implementation logic
- [ ] No mobile/responsive assumptions (only if Figma variants exist)
- [ ] Sizing behavior documented (full width, hug contents, or fixed)
- [ ] Documentation is clear enough for AI model implementation
- [ ] Reference components listed (for composite components)
- [ ] Related components section ONLY includes direct child/alternative components
- [ ] No patterns or usage beyond the single component
- [ ] Visual behaviors specific to the component are documented
- [ ] Component screenshot is referenced or included

---

## Common Patterns

### Button-Like Components
- Usually have: Size, State, Variant properties
- Padding typically differs by size
- Focus state has a separate indicator (focus ring)
- Document all state color progressions

### Icon Components
- Usually have: Size, State variants
- Icon size may be constant while container size changes
- Padding may be constant or vary by size
- Document selection states if applicable

### Form Components
- Usually have: Size, State, Validation states
- May be composite (Label + Input)
- **Document as unified components** with all child specs inline
- Focus state is critical for accessibility
- Document ARIA attributes for required, error, disabled states

### Composite Components
- Document as **one unified component** from implementation perspective
- Include all child component specifications inline
- List child components in "Reference Components" section
- Clarify which properties come from which child component
- Note visual behaviors specific to the composition (e.g., showIcon differences)

---

## Token Naming Conventions

Common token naming patterns you'll encounter:

### Spacing
- `nova/spacing/[name]` - e.g., `nova/spacing/tight`, `nova/spacing/close`
- `semantic/spacing/[name]` - e.g., `semantic/spacing/next`

### Colors
- `nova/button/[variant]/[color]/color/[state]` - Component-specific colors
- `nova/color/[semantic]/[level]` - Semantic colors (success, error, warning, etc.)
- `global/color/[name]/[value]` - Global color palette

### Typography
- `nova/typography/[category]/[style]` - e.g., `nova/typography/instructional/regular`
- `global/typography/fontsize/[size]` - Font size tokens

### Radii
- `nova/radii/component/[component]` - Component-specific radius
- `semantic/radii/[name]` - Semantic radius values

### Effects
- `nova/color/focus` - Focus indicators
- `nova/color/skeleton/[level]` - Loading/disabled states

---

## Example Workflow

1. Select master component in Figma
2. Run `get_design_context`, `get_screenshot`, `get_variable_defs`, `get_metadata`
3. Identify all variants from metadata (size, state, variant type, etc.)
4. For each SIZE variant, run `get_design_context` and `get_variable_defs` on specific nodes
5. Compare tokens across sizes (especially padding)
6. **CRITICAL: Examine screenshot carefully for state visual differences** (especially background colors)
7. **Check `get_variable_defs` for numbered color variants** (e.g., `dark-blue/10`, `/50`, `/100`)
8. **Compare generated code structure for each state** - don't assume states are identical
9. Check layout settings in Figma (full width, hug contents, fixed)
10. Organize tokens by category (Typography, Colors, Spacing, Borders & Radii)
11. **Document each state's specific visual properties** (background, border, text colors)
12. **Note color progressions** (Default → Hover → Pressed transitions)
13. Write documentation following the standard structure
14. Document size-specific spacing in multiple sections
15. Document sizing behavior (full width vs hug contents)
16. Include visual behavior notes for component-specific quirks
17. Document ARIA attributes for accessibility
18. Add usage guidelines (When to Use, Do's and Don'ts)
19. For composite components, document as unified with child component references
20. Review against validation checklist

---

## File Naming Convention

- Use lowercase with hyphens: `button.md`, `icon-button.md`, `text-input.md`
- Match the component name in Figma when possible
- Be consistent within the project

---

## Tips for AI Models

When using this documentation to implement components:

1. Always reference the design token file for actual values
2. Convert the documented structure to your target framework
3. Implement all states, not just the default
4. Follow the accessibility guidelines and ARIA attributes
5. Use the usage guidelines to understand context
6. Pay attention to size-specific token differences
7. Don't hardcode values - always use design tokens
8. Respect the sizing behavior (full width vs hug contents)
9. For composite components, implement as one unified component
10. Focus on visual accuracy - match the Figma design exactly

---

## Troubleshooting

### Issue: Color tokens not appearing
**Solution:** Select the master component set, not an instance. Try `get_variable_defs` on the master component node.

### Issue: Can't see all variants
**Solution:** Use `get_metadata` to list all variants, then call `get_design_context` on specific variant node IDs.

### Issue: Padding seems wrong
**Solution:** Check individual size variants - they may use different spacing tokens.

### Issue: States are unclear
**Solution:** Look at the variant names in metadata - they usually follow pattern: "Variant=X, State=Y, Size=Z"

---

## Summary

**Key Principles:**
1. Token names, never values
2. Check size-specific differences
3. Framework-agnostic, visual-focused descriptions
4. Comprehensive coverage of all states and variants
5. Document sizing behavior (full width, hug contents, fixed)
6. Visual accessibility and ARIA attributes
7. No implementation logic or performance tips
8. No mobile assumptions unless Figma variants exist
9. Composite components documented as unified implementations
10. Usage guidelines for context, not multi-component patterns
11. **NO Reference/Node IDs sections** - Internal Figma metadata not needed
12. **NO advisory/interpretative disclaimers** - Only facts or omit entirely
13. **Simple Version History** - One-line summary with variant properties

**Essential Steps:**
1. Select master component
2. Extract all variant information
3. Deep dive into size variants
4. Check layout/sizing behavior in Figma
5. Organize and document tokens
6. Follow standard structure
7. Document visual behaviors and quirks
8. Include ARIA attributes (NOT color contrast)
9. Validate completeness against checklist
10. End with concise Version History (Version 1.0 format)

**Result:** Documentation that enables any developer or AI model to implement the component correctly in any technology stack by referencing the design tokens and visual specifications extracted from Figma.
