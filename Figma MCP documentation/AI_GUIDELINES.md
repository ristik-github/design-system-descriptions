# AI Implementation Guidelines

## MANDATORY WORKFLOW - READ THIS FIRST

**BEFORE implementing ANY feature or component, you MUST complete this checklist:**

### Pre-Implementation Checklist (REQUIRED)

1. **☑️ Understand user intent and map to components**
   - What is the user trying to accomplish?
   - Which Nova components are needed?
   - What variants/states are appropriate for this context?
   - What is the hierarchy and importance of actions?
2. **☑️ Read AI_GUIDELINES.md** - You are reading it now
3. \*\*☑️ Check if component exists in docs/
   - If YES → Read the component's .md file completely
   - If NO → STOP and ask user if you should create a new component
4. **☑️ Read docs/design-tokens.json** for ALL tokens you will use
5. **☑️ Verify all colors are in HSL format** - NEVER use hex or Tailwind generic classes
6. **☑️ Check docs/DESIGN-TOKENS.md** for token usage guidelines

### Absolute Rules (NEVER BREAK THESE)

❌ **NEVER** use generic Tailwind classes like `bg-teal-700`, `text-white`, `hover:bg-gray-200`  
✅ **ALWAYS** use design tokens: `hsl(var(--muted-teal-700))` or CSS variable classes

❌ **NEVER** make up color values or tokens  
✅ **ALWAYS** use exact values from design-tokens.json

❌ **NEVER** assume a variant exists  
✅ **ALWAYS** verify in the component's .md file

❌ **NEVER** add "helpful" undocumented features  
✅ **ALWAYS** implement only what's documented

### Implementation Flow

```
User Request (in natural language)
    ↓
UNDERSTAND USER INTENT
  ├─ What is the user trying to accomplish?
  ├─ Map keywords to component types
  ├─ Identify action hierarchy (primary/secondary/destructive)
  └─ Determine if any components are missing from docs
    ↓
Read AI_GUIDELINES.md (this file)
    ↓
Does component exist in docs/?
    ↓
YES → Read component.md + design-tokens.json
    ↓
NO → ASK USER before creating
    ↓
Verify all tokens exist in design-tokens.json
    ↓
Convert all colors to HSL format
    ↓
Implement using ONLY documented features
    ↓
Verify implementation matches documentation
```

## Natural Language Component Mapping (For Non-Technical Users)

**This section enables you to translate non-technical user requests into specific Nova component implementations.**

### Button Intent Mapping

When users describe button actions, map them to NovaButton specifications:

| User Says | Component | Variant | Size | Color | Notes |
|-----------|-----------|---------|------|-------|-------|
| "save", "submit", "continue", "next", "confirm" | NovaButton | primary | large | default | Main action |
| "cancel", "back", "close" (in forms) | NovaButton | secondary | large | default | Supporting action |
| "delete", "remove", "clear data" | NovaButton | primary | large | destructive | Permanent action |
| "edit icon", "settings icon", "more options" | IconButton | varies | 24px | default | Toolbar actions |
| "close" (in modals/alerts) | IconButton | tertiary | 24px | default | Dismiss action |

### Form Field Intent Mapping

**When user says:** "create a form with [fields], [X] is required"

**Rules:**
- Use NovaFormField for each field
- Fields marked as "required", "mandatory", "must have" → `labelVariant="required"`
- Fields marked as "optional" → `labelVariant="optional"`
- If most fields are required and some optional → mark optional ones explicitly
- If most fields are optional and some required → mark required ones explicitly
- If all same status → use `labelVariant="default"` and communicate at form level

**Field type mapping:**
- "email field", "email address" → NovaFormField with `inputType="email"`
- "password field" → NovaFormField with `inputType="password"`
- "text field", "name field", "message field" → NovaFormField with `inputType="text"`
- "dropdown", "select", "choose from list" → Select component (NOT FormField)
- "checkbox", "agree to terms" → Checkbox component
- "upload file", "attach document" → File upload component

### Layout Intent Mapping

Map layout requests to structural components:

| User Says | Component | Notes |
|-----------|-----------|-------|
| "create a section", "add content area", "page for..." | Workspace | Main content container |
| "add a title", "page header", "main heading" | NovaPageTitle | Top-level title |
| "section title", "subsection header" | Title Bar Section Title | Content section headers |
| "sidebar menu", "side navigation" | VerticalNav | Left navigation |
| "top menu", "header navigation" | Header | Top navigation bar |
| "popup", "dialog", "confirmation message" | Modal | Overlay content |
| "card", "tile", "item card", "finding card", "record summary" | NovaTileCard | Display grouped information in a structured format |
| "label", "tag", "status", "count", "badge", "indicator" | NovaBadge | Visual indicator for categorization, counts, and status |

### Action Context Rules

**Primary Action (primary variant):**
- The main thing the user came to do
- Examples: "Save" in a form, "Create Account", "Submit Order", "Confirm Payment"
- **Only ONE primary action per screen/section**

**Secondary Action (secondary variant):**
- Supporting actions, alternatives
- Examples: "Cancel", "Back", "Save as Draft"
- Can have multiple secondary actions

**Tertiary Action (tertiary variant):**
- Low-priority, subtle actions
- Examples: "Skip", "Learn More", "Help"
- Minimal visual weight

**Destructive Action (destructive color):**
- Permanent, dangerous, data-loss actions
- Examples: "Delete Account", "Remove Item", "Clear All Data"
- **ALWAYS require confirmation dialog**

### Common Pattern Compositions

**Pattern: Basic Form**
```
User says: "Create a contact form with name, email, and message. Name and email are required."

AI interprets:
- Container: Workspace
- Title: NovaPageTitle ("Contact Us")
- Field 1: NovaFormField (label="Name", labelVariant="required", inputType="text")
- Field 2: NovaFormField (label="Email", labelVariant="required", inputType="email")
- Field 3: NovaFormField (label="Message", labelVariant="optional", inputType="text")
- Action: NovaButton (variant="primary", size="large", text="Send Message")
```

**Pattern: Confirmation Dialog**
```
User says: "Ask for confirmation before deleting"

AI interprets:
- Container: Modal
- Title: "Confirm Deletion" or similar
- Description: Explain consequence ("This action cannot be undone")
- Primary Action: NovaButton (variant="primary", color="destructive", text="Delete")
- Secondary Action: NovaButton (variant="secondary", text="Cancel")
```

**Pattern: List with Actions**
```
User says: "Show a list of items with edit and delete buttons"

AI interprets:
- Container: Workspace
- Title: NovaPageTitle or Title Bar
- List items with:
  - Edit: IconButton (pencil icon) or NovaButton (variant="secondary", size="small")
  - Delete: IconButton (trash icon) or NovaButton (variant="secondary", color="destructive", size="small")
```

### Intent Recognition Keywords

**Creation/Addition Intent:**
- Keywords: "create", "add", "new", "build", "make"
- Action: Determine what needs to be created, select appropriate components
- Usually needs: primary button for "Create" action

**Modification Intent:**
- Keywords: "edit", "update", "change", "modify"
- Action: Identify what element needs modification
- Usually needs: secondary button or icon button for "Edit" action

**Deletion Intent:**
- Keywords: "delete", "remove", "clear", "erase"
- Action: ALWAYS use destructive styling + confirmation
- Always needs: destructive button + confirmation modal

**Navigation Intent:**
- Keywords: "go to", "navigate", "show", "view"
- Action: Determine if top nav (Header) or side nav (VerticalNav)
- May need: links or navigation buttons

**Submission Intent:**
- Keywords: "submit", "send", "save", "post"
- Action: Form submission, use primary button
- Usually needs: form fields + primary submit button

### Hierarchical Decision Making

**When user describes multiple actions:**

1. Identify the PRIMARY goal (what user came to do) → primary variant
2. Identify supporting actions (alternatives, cancellation) → secondary variant
3. Identify low-priority actions (help, info) → tertiary variant
4. Check if any action is destructive → add destructive color
5. Determine if action needs confirmation → add Modal

**Example:**
```
User says: "Create a profile page with save and cancel buttons, and a delete account option"

AI interprets:
- "save" → primary action (main goal)
- "cancel" → secondary action (alternative)
- "delete account" → primary destructive action WITH confirmation modal
```

### Examples of Natural Language Processing

**Example 1: Simple Login Form**
```
User: "I need a login form"

AI Process:
1. Intent: User needs authentication → form with email/password
2. Components needed:
   - Workspace (container)
   - NovaPageTitle ("Login" or "Sign In")
   - NovaFormField (label="Email", labelVariant="required", inputType="email")
   - NovaFormField (label="Password", labelVariant="required", inputType="password")
   - NovaButton (variant="primary", size="large", text="Sign In")
   - NovaButton (variant="tertiary", size="large", text="Forgot Password?")
3. Check design-tokens.json for all spacing, colors, typography
4. Implement using exact tokens in HSL format
```

**Example 2: Confirmation Dialog**
```
User: "Add a popup to confirm when someone deletes their account"

AI Process:
1. Intent: Destructive action needs confirmation
2. Components needed:
   - Modal component
   - Title: "Delete Account?"
   - Description: "This action cannot be undone. All your data will be permanently deleted."
   - NovaButton (variant="primary", color="destructive", text="Delete Account")
   - NovaButton (variant="secondary", text="Cancel")
3. Triggered by a destructive button in settings
4. Check design-tokens.json for modal, button, and text styling
5. Implement using exact tokens
```

**Example 3: Complex Registration Form**
```
User: "Create a registration form with name, email, password, and optional phone number. Email and password are required."

AI Process:
1. Intent: User registration → form with mixed required/optional fields
2. Most fields are required, one is optional → mark optional one explicitly
3. Components needed:
   - Workspace
   - NovaPageTitle ("Create Account")
   - NovaFormField (label="Name", labelVariant="required", inputType="text")
   - NovaFormField (label="Email", labelVariant="required", inputType="email")
   - NovaFormField (label="Password", labelVariant="required", inputType="password")
   - NovaFormField (label="Phone Number", labelVariant="optional", inputType="tel")
   - NovaButton (variant="primary", size="large", text="Create Account")
4. Check design-tokens.json for all tokens
5. Implement using exact HSL values
```

**Example 4: Dashboard with Item Actions**
```
User: "Create a dashboard showing user projects. Each project should have edit and delete options."

AI Process:
1. Intent: Display list with item-level actions
2. Components needed:
   - Workspace
   - NovaPageTitle ("My Projects")
   - List/grid of project items
   - For each item:
     - IconButton (edit icon, 24px) OR NovaButton (variant="secondary", size="small", text="Edit")
     - IconButton (trash icon, 24px, destructive) OR NovaButton (variant="secondary", color="destructive", size="small", text="Delete")
3. Delete action needs confirmation → add Modal for deletion
4. Check design-tokens.json for layout, spacing, colors
5. Implement using exact tokens
```

### Ambiguity Resolution

**If unclear about field requirements:**
- ASK: "Which fields should be required?"
- Don't assume - let user specify

**If unclear about button importance:**
- ASK: "What is the main action you want users to take?"
- Use this to determine primary vs secondary variants

**If unclear about destructiveness:**
- ASK: "Does this action permanently delete data or can it be undone?"
- Determines if destructive styling is needed

**If user just says "add a button":**
- ASK: "What action should this button perform?"
- This determines variant, size, and potentially color

## Critical Rules for Component Development

### CRITICAL: Creating New Components

**If a feature requires a component that does NOT exist in the documentation:**

1. **DO NOT immediately create the component**
2. **STOP and explain to the user:**
   - What component needs to be created
   - Why it's needed for their requested feature
   - What functionality it would provide
   - How it differs from existing components
3. **WAIT for explicit user confirmation** before proceeding
4. **Once confirmed**, create the component following Nova Design System standards
5. **Document the new component** in a new `.md` file in `docs/`

**This applies to NEW COMPONENTS, not new variants of existing components.**

### Documentation is the Source of Truth

**ALL Nova components MUST strictly follow their documentation in the `docs/` folder.**

1. **Before implementing or modifying any Nova component:**
   - Read the component's `.md` file in `docs/` (e.g., `docs/button.md`)
   - Check `docs/design-tokens.json` for exact token values
   - Verify all variants, states, and props against the documentation

2. **Only implement what is documented:**
   - If a variant is not in the docs, do NOT implement it
   - If a state is not documented, do NOT add it
   - If a prop is not specified, do NOT create it

3. **Never assume or extrapolate:**
   - Do not add "helpful" variants that seem logical but aren't documented
   - Do not create additional states or color options
   - Do not infer patterns from other components

### Nova Component Standards

- Nova components follow the exact specifications in `docs/nova-components-essential.md`
- All design tokens are defined in `docs/design-tokens.json` and `docs/DESIGN-TOKENS.md`
- Typography, spacing, colors, and other tokens MUST match the documentation exactly

### Design Token Usage Rules

**CRITICAL: All colors MUST be in HSL format**

1. **Read design-tokens.json first** - Find the exact hex value
2. **Convert to HSL** - Use the HSL equivalent (or look it up if provided)
3. **Add to index.css** - Create CSS variable if it doesn't exist
4. **Use in components** - Reference via `hsl(var(--token-name))`

**Example Workflow:**

```
Documentation says: global/color/muted-teal/700 (#185956)
    ↓
Check design-tokens.json: "muted-teal": { "700": "#185956" }
    ↓
Convert to HSL: 177 57% 22%
    ↓
Add to index.css: --muted-teal-700: 177 57% 22%;
    ↓
Use in component: style={{ background: "hsl(var(--muted-teal-700))" }}
```

**Common Mistakes to AVOID:**

- ❌ Using `className="bg-teal-700"` - This is NOT the right token
- ❌ Using `className="text-white"` - Use semantic tokens instead
- ❌ Using hex values directly: `color: "#185956"` - Must be HSL
- ❌ Making up token names: `--custom-blue` - Must exist in design-tokens.json

**Correct Approach:**

- ✅ Check design-tokens.json for exact value
- ✅ Add to index.css as HSL if missing
- ✅ Reference via CSS variable: `hsl(var(--token-name))`
- ✅ Use semantic classes when available: `bg-nav-background`

### When Updating Components

1. Read the relevant documentation file FIRST
2. Compare current implementation against the documentation
3. Remove any undocumented features
4. Add any missing documented features
5. Ensure all variants and states match exactly

### Example Files to Always Check

- `docs/button.md` - Button component specification
- `docs/tile-card.md` - Tile (Card) component specification
- `docs/badge.md` - Badge component specification
- `docs/design-tokens.json` - All design tokens
- `docs/DESIGN-TOKENS.md` - Token reference guide
- `docs/index.md` - Component index and overview

## Why This Matters

This project is used by multiple people who rely on consistent, documented behavior. Undocumented features create confusion and maintenance issues. Always prioritize documentation accuracy over assumed helpfulness.

## Quick Reference: Token Sources

**Always check these files in this order:**

1. **AI_GUIDELINES.md** (this file) - Workflow and rules
2. **docs/[component-name].md** - Component-specific documentation
3. **docs/design-tokens.json** - All token values (colors, spacing, etc.)
4. **docs/DESIGN-TOKENS.md** - Token usage guidelines
5. **src/index.css** - Currently implemented CSS variables

## Enforcement Checklist

Before submitting any code changes, verify:

- [ ] I read the component's .md documentation file
- [ ] I checked design-tokens.json for all tokens used
- [ ] All colors are in HSL format
- [ ] All tokens exist in index.css or I added them
- [ ] I only implemented documented features
- [ ] I did NOT add undocumented variants or props
- [ ] I did NOT use generic Tailwind classes for colors
- [ ] I did NOT make up token values

**If you cannot check all boxes, DO NOT implement the feature. Ask the user for clarification first.**
