# Title Bar / Page Title

## Overview
The Title Bar / Page Title component displays the primary page heading (and optional subtitle) within layouts that use a workspace or container region. It provides two layout variants aligned to platform context: a standard (desktop) configuration and a mobile configuration. The component focuses on presenting hierarchical page information while optionally accommodating contextual actions or badges via slots.

## Component Properties

### Variants (Mobile)
- **mobile=off** (Desktop / Standard): Full-width horizontal context area with heading and optional subtitle aligned bottom; may include action slots right-aligned (placeholder element present in design context). Minimum width observed: 343px (from design context node min-width setting); actual container symbol width 1272px within frame.
- **mobile=on** (Mobile): Condensed vertical height with slightly increased total height (90px frame symbol vs 50px desktop symbol) to allow stacked or wrapped context; heading and subtitle share a vertical arrangement with tighter horizontal width (320px symbol width). Both variants maintain consistent typography tokens for heading and subtitle.

### Sizes
No explicit size property variants beyond the mobile switch are defined in metadata. Size behavior differs by variant:
- **Desktop (mobile=off):** Symbol height 50px (frame symbol). Horizontal spacing between heading and subtitle uses `nova/spacing/tight` (8px). Context min-width 343px.
- **Mobile (mobile=on):** Symbol height 90px. Vertical gap between contextual elements uses `nova/spacing/next` (4px) plus internal gap of `nova/spacing/tight` (8px) where specified. Width constrained to 320px symbol width.

> Note: Raw heights (50px / 90px) are frame symbol dimensions; no direct height tokens surfaced. Documented as factual measurements with no token found.

### States
No interactive state variants (hover, focus, pressed, disabled) are defined in the metadata for this component set. The component is purely informational. Any focus/interactive visuals would come from embedded interactive child components (e.g., action buttons) rather than the title container itself.

### Slots / Conditional Elements
- **Subtitle:** Controlled by `showSubtitle` boolean (true by default). When present, uses body/base typography token for secondary line.
- **Title Actions / Context Actions / Badge / Back Button / Sidebar Button:** Boolean flags in the design context code show potential conditional areas. Their specific visual tokens are not exposed in the captured variable definitions; this documentation only notes their presence as optional placeholders.
- **Title Bar Action Slot:** Placeholder `titleBarActions` referencing a slot component (node `208:1096`). Slot token styling inherits link tertiary color token for demonstration text.

## Design Tokens

### Typography
- **Page Title Heading:** `nova/typography/heading/1` (Geist SemiBold, 24px, weight 600, line height ~140%) – Used for primary title text.
- **Subtitle / Secondary Text:** `nova/typography/base/regular` (Geist Regular, 14px, weight 400, line height ~130%) – Used for optional subtitle line.
- **Slot Demo Text (tertiary link style):** Uses color token `nova/link/color/tertiary` with font size 12px (raw size) and regular weight. No composite typography token for 12px regular surfaced; recorded as raw value.

### Spacing
- **Horizontal gap between heading and subtitle (desktop):** `nova/spacing/tight` (8px).
- **Mobile variant primary horizontal/element gap:** `nova/spacing/next` (4px) combined with contexts using `nova/spacing/tight` (8px) for grouping.
- **Context wrapper vertical padding (slot wrapper shows px-[16px] py-[8px]):** Horizontal 16px and vertical 8px appear as raw values; corresponding spacing tokens not surfaced (likely `nova/spacing/near` for 16px and `nova/spacing/slight` or similar for 8px if they exist). Documented as raw measurements with no token found.
- **Optional close spacing token:** `nova/spacing/close` (12px) present in variable defs but not explicitly applied within captured code for this component context area; included for reference only if later variants use it.

> Note: Only tokens explicitly appearing in variable definitions are listed. Where spacing appears as pixel values without mapped tokens, they are noted as raw.

### Colors
- **Heading Text Color:** `nova/color/typography/base` (#151d1e).
- **Subtitle Text Color:** `nova/color/typography/muted` (#0000009e) – Muted text for secondary information.
- **Slot Placeholder Text (Tertiary link / action text):** `nova/link/color/tertiary` (#7c6fdc).

No background, border, or container color tokens surfaced for the title bar itself in the provided variable definitions (component likely inherits parent surface/background).

### Border & Radius
No border width, border color, or radius tokens surfaced for this component in the captured data. The component appears as a content container without an explicit border in the provided code and metadata.

### Effects
No shadow, focus ring, or effect tokens are defined in the variable definitions for this component.

## Layout Specifications

### Structure
- **Container (Desktop):** Flex layout, items aligned to end (bottom) to vertically align title and subtitle baseline. Gap between text elements uses `nova/spacing/tight`.
- **Container (Mobile):** Flex layout with `items-center` or `items-end` alignment (per code), includes combined gaps using `nova/spacing/next` (4px) and `nova/spacing/tight` (8px). Height larger (90px symbol) allowing vertical breathing room.
- **Min Width (Desktop Context Group):** 343px (raw value) ensures readable truncation area for title/subtitle.

### Spacing
- Horizontal internal gaps rely on `nova/spacing/tight` (8px).
- Mobile introduces an additional reduction gap `nova/spacing/next` (4px).
- Padding in slot wrapper (16px horizontal / 8px vertical) documented as raw (no tokens surfaced).

### Visual Properties
- Text colors derived from typography color tokens.
- No independent background fill or border defined.

### Dimensions
- **Desktop Symbol Height:** 50px (raw; composed from heading line height plus vertical alignment; no direct token).
- **Mobile Symbol Height:** 90px (raw).
- **Width Behavior:** Fills parent width in desktop frame (symbol width 1272px inside outer frame width 1320px); mobile constrained to 320px symbol width.
- **Sizing Behavior:** Desktop variant designed to fill horizontal space; mobile variant fixed to narrower width. Content text uses overflow handling (ellipsis) preserving Hug contents vertical logic while width fills available horizontal region up to min constraints.

> Calculations for total height rely on typography line heights (heading ~24px * 1.4, subtitle ~14px * 1.3) plus vertical alignment; because explicit padding tokens for the title container are not surfaced, raw heights are recorded.

## Accessibility Considerations

### Semantics
- Heading should be announced as a page-level title (implementation typically maps primary title to a semantic heading level such as <h1>). This is a factual usage pattern for page titles.
- Subtitle provides supplemental descriptive context; should follow heading in reading order.

### ARIA Attributes
- No ARIA state attributes defined within component variants (non-interactive container).
- If interactive action slots are included (buttons, links) they adopt their own ARIA semantics; not documented here since those are separate components.

### Keyboard Navigation
- Component itself is not focusable. Child interactive elements (actions) join tab sequence individually.

### Screen Readers
- Ensure the title text is exposed as the main page heading. Subtitle read immediately after if present.

## Usage Guidelines

### When to Use
- Display a clear page title at the top of a workspace or section.
- Provide optional secondary descriptive line for context.
- Switch to mobile variant when constrained to narrow mobile layout widths.

### Best Practices
#### Do:
- Use `nova/typography/heading/1` strictly for the primary page heading here.
- Keep subtitle concise (uses `nova/typography/base/regular`).
- Preserve truncation behavior for long titles via overflow handling.
#### Don't:
- Replace heading typography with body tokens.
- Introduce interactive behaviors directly on the container.
- Hardcode colors—always reference documented tokens.

> Note: The usage guidance above reflects standard page header patterns; verify against broader design system conventions if uncertain.

## Content Structure
- **Heading Text (required)** – Uses `nova/typography/heading/1`.
- **Subtitle (optional)** – Uses `nova/typography/base/regular` with muted color token.
- **Optional Action/Context Slots** – Placeholder areas for external child components (not visually specified here beyond slot placeholder styling).

## Interactive States
No explicit component-level states; rely on child component states if actions are inserted.

## Visual Behavior Notes
- Text truncates with ellipsis in constrained widths (desktop min-width 343px, mobile width 320px).
- Subtitle visibility toggled by boolean; absence collapses vertical space.
- Slot placeholder demonstrates tertiary link color styling for potential interactive affordances.

### Component Architecture
A flex container grouping heading and optional subtitle, optionally extended by slots for actions or contextual data. Mobile variant increases vertical space for comfortable stacking.

### Key Visual Behaviors
- Consistent typography tokens across variants.
- Mobile variant uses additional small gap token to compress vertical layout.

### Sizing Behavior
- Desktop variant: fills available width (flex grow) with ellipsis handling.
- Mobile variant: fixed narrower symbol width; still uses ellipsis for overflow.

## Reference Components
- Workspace (page-level container) – often hosts this Title Bar component.
- Badge (if showBadge is true) – separate component for status indication.
- Action buttons / Icon button – placed within action slots.

## Related Components
- Section Title (alternative header style inside workspaces).
- Breadcrumb navigation (for hierarchical context – separate component, not embedded).

## Version History
- Initial documentation generated from Figma metadata and design context on 2025-10-17.

## Validation Checklist
- [x] Tokens referenced match variable definitions captured.
- [x] Raw pixel values only used where no tokens surfaced (heights, padding 16px/8px).
- [x] No implementation-specific code or framework examples included.
- [x] No responsive speculation beyond explicit mobile variant.
- [x] No contrast ratios or performance notes.
- [x] Sizing behavior (fill vs fixed) described using factual frame data.
