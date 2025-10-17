# Header Top Nav

## Overview

The Header Top Nav is a comprehensive application-level navigation component that provides primary and secondary navigation, branding, search functionality, and global actions. It supports multiple layout configurations and responsive behaviors to accommodate different screen sizes and navigation patterns.

---

## Component Properties

### Variant Properties

#### 1. **Width** (2 options)
- **Large**: Full-width navigation with all items visible, optimized for desktop (≥1280px)
- **Medium**: Condensed navigation with overflow handling, optimized for tablets and smaller screens (640px-1279px)

#### 2. **Legacy** (2 options)
- **off**: Modern layout with horizontal primary navigation integrated in header bar
- **on**: Classic layout with separate rows for branding/actions and primary navigation

#### 3. **Vertical Nav** (2 options)
- **off**: Standard horizontal navigation (default)
- **on**: Vertical navigation mode with hamburger menu toggle (Large width only)

#### 4. **Show Secondary Navigation** (boolean)
- When enabled: Displays sub-navigation row below primary navigation
- When disabled: Only shows primary header navigation bar

#### 5. **Show Header Icons** (boolean)
- When enabled: Displays icon-only action buttons in header actions area
- When disabled: Only shows search and avatar

#### 6. **Show Context** (boolean)
- When enabled: Displays organization/context tag (e.g., "Acer Skyline Health")
- When disabled: Hides context tag

#### 7. **Show Help** (boolean)
- When enabled: Displays help/support icon in global actions
- When disabled: Only shows avatar in global actions

#### 8. **Menu Open** (boolean)
- Indicates whether navigation menu is expanded or collapsed
- Primarily affects visual state, not layout

---

## Visual Specifications by Variant

### Width=Large, Legacy=off, Vertical Nav=off (Default Large Desktop)

**Primary Navigation Bar:**
- Background: `nova/navigation/primary` (#0f4146 - muted teal 800)
- Height: 52px (padding top/bottom: `nova/spacing/tight` 8px)
- Horizontal padding: Left `nova/spacing/close` (12px), Right `nova/spacing/tight` (8px)
- Gap between sections: `nova/spacing/tight` (8px)

**Logo & Branding Section:**
- Logo mark: 20.049px × 19.819px
- Vertical divider: `nova/border/basic` (1px) white line, full height
- Product name: "Risk & Safety", `nova/typography/base/strong` (14px SemiBold, 130% line height), white text
- Context tag (when enabled): White border (`nova/border/basic` 1px), `nova/radii/relaxed` (16px) rounded corners, `nova/typography/supporting/regular` (12px Regular, 120% line height) white text, padding `nova/spacing/tight`/`nova/spacing/close` (8px/12px)

**Primary Nav Items:**
- Active state background: `global/color/pale-green/150` (#e7f4eb)
- Active state text: `global/color/green/900` (#042f22 - darkest green)
- Hover state background: `global/color/muted-teal/700` (#185956)
- Hover state text: White
- Default state text: White
- Padding: `nova/spacing/close` (12px) horizontal, 0px vertical
- Min height: 32px
- Border radius: `nova/radii/component/button` (8px)
- Font: `nova/typography/base/regular` (14px Regular, 130% line height)
- Gap between items: `nova/spacing/slight` (2px)

**Search & Actions:**
- Search box background: `global/color/muted-teal/700` (#185956)
- Search box width: 160px, height: 36px
- Search box border radius: `nova/radii/component/input` (8px)
- Search icon: 20px, white
- Search placeholder text: `nova/color/static/white-60%` (rgba(255,255,255,0.62)), `nova/typography/base/regular` (14px Regular, 130% line height)
- Search padding: Right `nova/spacing/next` (4px)
- Icon buttons: 36px square, `nova/radii/component/button` (8px) border radius
- Global actions container: 36px `nova/radii/full` (36px) rounded pill, teal 700 background, `nova/spacing/next` (4px) internal gap/padding

**Secondary Navigation (when enabled):**
- Background: `global/color/pale-green/150` (#e7f4eb - lightest green)
- Border: `nova/border/basic` (1px) bottom/sides `global/color/pale-green/200` (#d3e4d6)
- Border radius: `nova/radii/component/header` (12px) bottom corners
- Padding: `nova/spacing/tight` (8px) vertical, `nova/spacing/close` (12px) horizontal
- Active sub-nav background: `global/color/muted-teal/800` (#0f4146 - darkest teal)
- Active sub-nav text: `global/color/pale-green/150` (#e7f4eb)
- Hover sub-nav background: `global/color/pale-green/200` (#d3e4d6)
- Default sub-nav text: `global/color/green/900` (#042f22)

### Width=Large, Legacy=on, Vertical Nav=off (Classic Large Desktop)

**Differences from modern layout:**
- Primary navigation in separate row below branding bar
- Branding bar contains: Logo, divider, product name, context tag, spacer, search, icons, avatar
- Navigation row: Full-width horizontal nav with same styling as modern active items
- Secondary navigation appears as third row with same styling

### Width=Medium (Tablet/Mobile)

**Primary Navigation Bar:**
- Similar structure to Large but more compact
- Nav items may overflow with horizontal scroll
- Overflow indicator: Right-pointing chevron icon (20px)
- Search box: 100px width (condensed from 160px)
- Menu button (when Legacy=on): 28px square icon button with chevron

**Secondary Navigation (when enabled):**
- Max visible width: 624px
- Overflow handling with scroll and chevron indicator

### Width=Large, Vertical Nav=on

**Primary Bar:**
- Hamburger menu icon: 36px button with 3-line icon
- Simplified header with: Menu, Logo, Divider, Product Name, Search, Icons, Avatar
- No inline primary navigation (moved to vertical sidebar)

---

## Design Tokens

### Typography

| Token | Value | Usage |
|-------|-------|-------|
| `nova/typography/base/strong` | 14px SemiBold, 130% line height | Product name, emphasized labels |
| `nova/typography/base/regular` | 14px Regular, 130% line height | Navigation items, search placeholder |
| `nova/typography/supporting/regular` | 12px Regular, 120% line height | Context tag, secondary labels |

### Colors

**Header Navigation:**
| Token | Value | Usage |
|-------|-------|-------|
| `nova/navigation/primary` | #0f4146 | Primary header background |
| `global/color/muted-teal/700` | #185956 | Search box, hover states, action buttons |
| `global/color/muted-teal/800` | #0f4146 | Active sub-nav background |
| `global/color/muted-teal/900` | #002d2d | Darkest text on light backgrounds |
| `nova/color/static/white` | #ffffff | Primary text, icons, borders on dark bg |
| `nova/color/static/white-60%` | rgba(255,255,255,0.62) | Search placeholder text |

**Secondary Navigation:**
| Token | Value | Usage |
|-------|-------|-------|
| `global/color/pale-green/150` | #e7f4eb | Secondary nav background, active primary nav |
| `global/color/pale-green/200` | #d3e4d6 | Secondary nav border, hover sub-nav |
| `global/color/green/900` | #042f22 | Text on light green backgrounds |

**Additional:**
| Token | Value | Usage |
|-------|-------|-------|
| `nova/input/color/highlight2` | #148d87 | Search input border (focus state) |
| `nova/tooltip/color/background` | rgba(0,0,0,0.81) | Tooltip backgrounds |
| `nova/tooltip/color/foreground` | #ffffff | Tooltip text |

### Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `nova/spacing/slight` | 2px | Gap between nav items |
| `nova/spacing/next` | 4px | Icon gaps, small padding |
| `nova/spacing/tight` | 8px | Section gaps, small padding |
| `nova/spacing/close` | 12px | Nav item horizontal padding, container padding |
| `nova/spacing/near` | 16px | Logo section gap, major element spacing |

### Borders & Radii

| Token | Value | Usage |
|-------|-------|-------|
| `nova/border/basic` | 1px | Standard borders |
| `nova/radii/component/button` | 8px | Navigation items, action buttons |
| `nova/radii/component/input` | 8px | Search box |
| `nova/radii/component/header` | 12px | Secondary navigation corners |
| `nova/radii/relaxed` | 16px | Context tag |
| `nova/radii/full` | 36px | Global actions pill container |

### Effects

| Effect | Value | Usage |
|--------|-------|-------|
| Tooltip shadow | 0px 2px 4px rgba(0,0,0,0.13) | Tooltip drop shadow |

---

## Layout Specifications

### Structure

```
Header Top Nav
├── Primary Navigation Bar (height: 52px)
│   ├── Logo & Branding Section
│   │   ├── Logo mark (20×20px)
│   │   ├── Divider (1px × full height)
│   │   ├── Product name ("Risk & Safety")
│   │   └── Context tag (optional)
│   ├── Primary Nav Items (when Legacy=off, Vertical Nav=off)
│   │   └── Nav item pills (32px height, 8px radius)
│   └── Actions Section
│       ├── Search input (160px/100px width, 36px height)
│       ├── Icon buttons (optional, 36px square)
│       └── Global actions (Avatar + Help pill)
└── Secondary Navigation (optional, 48px height)
    └── Sub-nav items (32px height, 8px radius)
```

**Alternative Layouts:**

**Legacy=on:** Branding bar + separate navigation row
**Vertical Nav=on:** Hamburger menu + simplified header
**Medium width:** Condensed with overflow indicators

### Dimensions

**Large Width (≥1280px):**
- Primary bar height: 52px
- Nav item height: 32px
- Icon button size: 36px square
- Search box: 160px width
- Logo mark: ~20px square

**Medium Width (640-1279px):**
- Same heights as Large
- Search box: 100px width
- Nav may scroll horizontally
- Overflow chevron: 28px square

### Responsive Behavior

- **Large → Medium:** Search box narrows, nav items may overflow with scroll
- **Legacy=off → Legacy=on:** Primary nav moves to separate row
- **Vertical Nav=on:** Primary nav hidden from header, accessible via hamburger menu
- **Secondary Nav:** Can be toggled independently of other variants

---

## Accessibility

### Keyboard Navigation
- **Tab**: Navigate through logo, nav items, search, action buttons, avatar
- **Enter/Space**: Activate selected nav item or button
- **Arrow keys**: Navigate between nav items within navigation group
- **Escape**: Close menu (when Vertical Nav=on and menu open)
- **/** (forward slash): Focus search input (common shortcut)

### ARIA Attributes
- Navigation container: `role="navigation"`, `aria-label="Main navigation"`
- Active nav item: `aria-current="page"`
- Menu button (Vertical Nav): `aria-expanded="true/false"`, `aria-controls="nav-menu"`
- Search input: `aria-label="Search"`, `role="search"`
- Icon buttons: `aria-label` describing action (e.g., "Notifications", "Help")
- Avatar: `aria-label` with user name or "User menu"

### Screen Reader Considerations
- Product name announced as main heading
- Context tag announced as supplementary info
- Nav items announced with current page indicator
- Icon buttons require descriptive labels
- Search placeholder provides context

### Focus Management
- Visible focus indicators on all interactive elements
- Focus ring: `nova/color/focus` (#9ef1e4 - teal 200)
- Logical tab order: Logo → Context → Nav items → Search → Actions
- Skip link (recommended): "Skip to main content" before header

---

## Usage Guidelines

### When to Use
- Primary application navigation across all major sections
- Persistent branding and context display throughout application
- Global search and actions that need constant accessibility
- Multi-level navigation hierarchies (primary + secondary)

### When Not to Use
- Simple websites with few pages (consider simpler header)
- Mobile-first apps (consider bottom tab navigation instead)
- Dashboards where navigation is secondary to content

### Best Practices
1. **Limit primary nav items:** 5-10 items maximum for optimal usability
2. **Use active states clearly:** Make current location obvious
3. **Context tag:** Only show when user can switch contexts (multi-tenant)
4. **Secondary nav:** Use for sub-sections related to active primary item
5. **Icon buttons:** Limit to 2-3 most important global actions
6. **Search:** Always visible for applications with significant content

### Content Guidelines
- **Nav labels:** Short, action-oriented (e.g., "Reports", "Tasks")
- **Product name:** Keep concise (2-3 words max)
- **Context tag:** Organization/tenant name, 20 characters max
- **Search placeholder:** Descriptive (e.g., "Search files..." not just "Search")

---

## Component Structure

### Navigation Hierarchy

**Level 1 - Primary Navigation:**
- Application-wide sections (Reports, Tasks, Alerts, etc.)
- Persistent across entire app
- Max 10 items recommended

**Level 2 - Secondary Navigation:**
- Sub-sections within active primary item
- Context-specific (changes based on primary selection)
- Examples: Roster Stats, Bank Requests, Daily Staffing

**Level 3 - Tertiary (not in header):**
- Page-level navigation
- Typically in sidebar or breadcrumbs

### Action Zones

**Local Actions (Left to Right):**
1. Logo/Branding (identity, home link)
2. Context selector (when applicable)
3. Primary navigation
4. Search

**Global Actions (Right):**
1. Notifications icon
2. Settings icon
3. Help/Support icon
4. User avatar/menu

---

## Visual Behavior Notes

### Component Architecture
- **Layered z-index:** Primary bar (z-index: 3 for Legacy), Secondary nav (z-index: 2), ensures proper stacking
- **Fixed positioning:** Typically fixed to top of viewport for persistent access
- **Shadow elevation:** Consider subtle shadow (0px 2px 4px rgba(0,0,0,0.1)) to separate from content

### State Transitions
1. **Nav item hover → active:**
   - Background transitions from transparent → hover color → active color
   - Text color inverts for contrast
   - Transition duration: 150ms ease-out (nova/motion/duration/flash)

2. **Search focus:**
   - Border appears/highlights: 1px `nova/input/color/highlight2`
   - Subtle scale or glow effect acceptable
   - Transition: 100ms ease-in (nova/motion/duration/blink)

3. **Menu open/close (Vertical Nav):**
   - Sidebar slides in from left
   - Backdrop fade-in: 300ms
   - Hamburger icon animates to X

### Color Progression
- **Primary nav active states:** White text → Hover teal → Active light green
- **Secondary nav active states:** Green text → Hover pale green → Active dark teal with light green text
- **Depth through color:** Dark teal (primary bar) → Light green (secondary bar) creates visual hierarchy

### Overflow Handling
- **Medium width:** Horizontal scroll with chevron indicator
- **Touch devices:** Swipe to scroll, momentum scrolling enabled
- **Keyboard:** Left/right arrows scroll when nav focused

### Icon Consistency
- All icons: 20px base size
- Consistent optical weight
- 2px stroke width standard
- Aligned to pixel grid for crispness

---

## Related Components

- **[Icon Button](./icon-button.md)** - Used for action buttons in header
- **[Badge](./badge.md)** - May be used for notification counts on icons
- **[Text Input](./text-input.md)** - Search input styling reference
- **[Dropdown](./dropdown.md)** - Context selector implementation

---

## Notes

- This component is highly configurable with 8 boolean/variant properties creating numerous combinations
- Most common configurations:
  - **Desktop default:** Width=Large, Legacy=off, Vertical Nav=off, all shows enabled
  - **Tablet:** Width=Medium, Legacy=on (separate nav row), all shows enabled
  - **Mobile:** Width=Medium, Legacy=on, Vertical Nav=on, reduced shows
- Secondary navigation visibility typically controlled by application state (active section has sub-sections)
- Consider performance: Sticky headers should use `position: sticky` for better scroll performance than `position: fixed` with scroll listeners
- Avatar component not detailed here but should support user menu dropdown
- Context tag may be clickable to switch organizations in multi-tenant applications

---

**Version:** 1.0  
**Last Updated:** 2025-10-17  
**Design System:** Nova Design System
