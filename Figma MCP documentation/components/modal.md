# Modal

## Overview
A Modal is an overlay component that displays content above the main page interface, requiring user interaction or acknowledgment before returning to the primary content. The Modal component includes a header with a title and optional close button, along with a content area for custom content. It supports both modal and dialog variants with different sizing options, and can be configured with or without content padding.

## Component Properties

### Variants
The Modal component has two primary variants:

- **Modal:** A full-width modal overlay (720px width) for primary content display and user interactions
- **Dialog:** A narrower dialog overlay (288px width) for confirmations, alerts, or simple user prompts

### Padding Options
The Modal supports two padding configurations:

- **On:** Content area includes padding of `nova/spacing/near` (16px) around the content slot
- **Off:** Content area has no padding, allowing content to extend to the edges

### Header Components

#### Closeable
The header can optionally display a close button (Icon Button component) in the top-right corner:
- **Closeable = true:** Displays the close icon button
- **Closeable = false:** No close button is shown

#### Subtitle Display
The header supports an optional subtitle display:
- **showSubtitle = true:** Displays a subtitle below the title
- **showSubtitle = false:** Only the title is shown

#### Actions
The header supports optional action elements:
- **showActions = true:** Displays additional action elements in the header
- **showActions = false:** No additional actions shown

### Footer Display
The Modal supports an optional footer section:
- **showFooter = true:** Displays a footer area at the bottom
- **showFooter = false:** No footer is shown

## Design Tokens

### Typography
- **Title:** `nova/typography/heading/3` (Geist SemiBold, 18px, 600 weight, 140% line height) - Used for the modal title
- **Slot Content:** Font family: Roboto Regular, 12px - Used for placeholder/slot content text

### Spacing
- **Header padding horizontal:** `nova/spacing/near` (16px)
- **Header padding vertical:** `nova/spacing/close` (12px)
- **Header gap (title to actions):** `nova/spacing/close` (12px)
- **Title internal gap:** `nova/spacing/slight` (2px) - Between title and subtitle
- **Actions gap:** `nova/spacing/tight` (8px) - Between action elements
- **Content wrapper padding (when Padding=on):** `nova/spacing/near` (16px)
- **Icon button padding:** 6px

### Colors
- **Title text:** `nova/color/typography/base` (#151d1e)
- **Header border:** `nova/surfaces/color/workspace border` (#e0e6e6)
- **Modal background:** `nova/drawer/color/background` (#ffffff)
- **Slot content text:** `nova/link/color/tertiary` (#7c6fdc)

### Border & Radius
- **Header border bottom width:** `nova/border/basic` (1px)
- **Icon button border radius:** `nova/radii/component/button` (8px)
- **Modal border radius:** `nova/radii/component/modal` (8px)

## Layout Specifications

### Structure
The Modal component follows a vertical flex layout with the following structure:
- **Root container:** Flex column, full width and height
- **Header:** Fixed height (56px for Modal variant, 60px for Dialog variant), full width, border bottom
- **Content wrapper:** Grows to fill remaining space, flex column layout
  - Minimum height: 80px
  - Contains slot component for custom content
- **Footer (optional):** Fixed at bottom when enabled

### Header Layout
- **Container:** Horizontal flex, items centered
- **Title section:** Grows to fill available space (flex-grow: 1), flex column
  - Title text: 640px width, 22px height (Dialog variant)
- **Actions section:** Fixed width based on content, horizontal flex
  - Close button (when closeable): 36px × 36px

### Content Wrapper Layout
- **Flex column:** Grows to fill remaining vertical space
- **Full width:** Stretches to container width
- **Minimum dimensions:** 80px height minimum

### Dimensions

#### Modal Variant (Variant=Modal)
- **Width:** 720px
- **Header height:** 56px
- **Content minimum height:** 80px
- **Overall minimum height:** 136px (header + content minimum)

#### Dialog Variant (Variant=Dialog)
- **Width:** 288px
- **Header height:** 60px
- **Content minimum height:** 80px
- **Overall minimum height:** 140px (header + content minimum)

#### Icon Button (Close)
- **Size:** 36px × 36px
- **Icon size:** 20px × 20px
- **Padding:** 6px

### Sizing Behavior
- **Width:** Fixed - Modal variant is 720px, Dialog variant is 288px
- **Height:** Flexible - Grows with content, minimum 136px (Modal) or 140px (Dialog)
- **Content area:** Grows to fill available space between header and footer

## Accessibility Considerations

### Keyboard Navigation
- **Focus trap:** Focus should be trapped within the modal when open
- **Tab order:** Should follow natural DOM order: close button → content → footer actions
- **Escape key:** Should close the modal (when closeable)
- **Close button:** Should be keyboard accessible when present

### Screen Readers
- **Modal title:** Should be announced as the dialog title
- **Content area:** Should be properly labeled and associated with the modal
- **Close button:** Should have descriptive label (e.g., "Close modal" or "Close dialog")

### ARIA Attributes
- **role="dialog"** or **role="alertdialog"** - On the root modal container
- **aria-modal="true"** - Indicates content beneath is inert
- **aria-labelledby** - References the title element ID
- **aria-describedby** - References the content area if applicable
- **Close button:** aria-label="Close" or similar descriptive text

### Focus Management
- **Initial focus:** Should move to the modal when opened (typically to close button or first focusable element)
- **Focus return:** Should return focus to the triggering element when closed
- **Focus visible:** Close button should show clear focus indicator

## Usage Guidelines

### When to Use

#### Modal Variant (720px)
- **Complex forms:** Multi-step forms or forms with multiple fields
- **Detailed content:** Content that requires more space for readability
- **Rich interactions:** Components with multiple interactive elements
- **Data tables:** Displaying tabular data within an overlay
- **Settings panels:** Application settings or preferences

#### Dialog Variant (288px)
- **Confirmations:** Simple yes/no or confirm/cancel prompts
- **Alerts:** Important messages requiring acknowledgment
- **Simple forms:** Single field inputs or basic selections
- **Quick actions:** Compact action menus or options
- **Status messages:** Success, error, or warning notifications

### Best Practices

#### Do:
- Use the Modal variant for complex, content-rich overlays
- Use the Dialog variant for simple confirmations and alerts
- Include a clear, descriptive title that explains the modal's purpose
- Provide a way to close the modal (close button, cancel action, or ESC key)
- Use Padding=on for most content to maintain consistent spacing
- Ensure the modal is centered on the viewport
- Disable background interaction when modal is open
- Limit the number of simultaneous modals (avoid stacking multiple modals)
- Use appropriate variant width for the content being displayed

#### Don't:
- Don't use modals for non-critical information that doesn't require immediate attention
- Don't create modals that are taller than the viewport without scroll capability
- Don't remove the close button unless there's a specific interaction requirement (critical confirmations)
- Don't use Padding=off unless the content needs to extend to edges (e.g., images, maps)
- Don't use the Modal variant (720px) for simple confirmations - use Dialog instead
- Don't overload modals with too much content - consider alternative layouts
- Don't auto-close modals without user action (unless timeout is clearly communicated)

### Content Guidelines

#### Title
- Keep titles concise (1-5 words)
- Use sentence case
- Clearly describe the modal's purpose
- Avoid generic titles like "Modal" or "Dialog"

#### Content
- Keep content focused on a single task or message
- Use clear, action-oriented language
- Break up long content with headings and spacing
- Ensure adequate contrast for readability

## Content Structure

The Modal consists of the following content elements:

1. **Header (Header - Modal Drawer component)**
   - Title text (required)
   - Optional subtitle
   - Optional close button (Icon Button)
   - Optional action elements

2. **Content Wrapper**
   - Slot component for custom content insertion
   - Flexible height based on content
   - Optional padding (16px when Padding=on)

3. **Footer (optional, not shown in variants)**
   - Action buttons or additional controls
   - Typically contains primary and secondary actions

## Visual Behavior Notes

### Component Architecture
The Modal is a composite component consisting of:
- **Header - Modal Drawer:** Reusable header component with title, actions, and close button
- **Content Wrapper:** Container for custom content with optional padding
- **Slot Component:** Placeholder for injected content

### Key Visual Behaviors

#### Header Variations
- **Title section** grows to fill available horizontal space
- **Actions section** is fixed width based on content
- **Close button** appears/disappears based on `closeable` property
- **Border bottom** provides visual separation from content

#### Content Area
- **Padding=on:** Content is inset by 16px on all sides for comfortable spacing
- **Padding=off:** Content extends to edges, useful for full-width components (images, tables, etc.)
- **Growth behavior:** Content area expands vertically to accommodate content
- **Minimum height:** 80px ensures usable space even with minimal content

#### Width Differences
- **Modal (720px):** Provides substantial horizontal space for complex layouts
- **Dialog (288px):** Compact width for focused interactions, approximately 40% of Modal width

### Sizing Behavior
- **Width:** Fixed based on variant (not responsive within variants)
- **Height:** Dynamic - grows with content, respects minimum height
- **Overlay:** Should typically be centered on the viewport
- **Background:** Should include a semi-transparent backdrop to dim underlying content

## Reference Components

This Modal component uses the following child components:

1. **Header - Modal Drawer**
   - Provides title, subtitle, actions, and close button functionality
   - Handles header layout and spacing
   - Configurable via props: title, subtitle, showActions, closeable, showSubtitle

2. **Icon Button**
   - Used for the close button in the header
   - 36px × 36px clickable area
   - Contains 20px × 20px icon (typically 'X' or close icon)

3. **Slot Component**
   - Placeholder representing custom content injection area
   - Shows "Slot component" or "Modal content" text in design
   - Should be replaced with actual modal content during implementation

## Related Components

- **Header - Modal Drawer:** The header component used within this modal
- **Icon Button:** Used for the close action in the modal header
- **Dialog (variant):** An alternative size variant for simpler interactions

## Variant Combinations

The Modal component supports the following variant combinations:

1. **Variant=Modal, Padding=on** (default)
   - Width: 720px, Height: 56px header + content
   - Content padding: 16px on all sides

2. **Variant=Dialog, Padding=on**
   - Width: 288px, Height: 60px header + content
   - Content padding: 16px on all sides

3. **Variant=Variant4, Padding=off** (Modal width, no padding)
   - Width: 720px, Height: 56px header + content
   - Content extends to edges (no padding)

4. **Variant=Variant3, Padding=off** (Dialog width, no padding)
   - Width: 288px, Height: 60px header + content
   - Content extends to edges (no padding)

## Implementation Notes

### Focus Trap
When implementing the modal, ensure that keyboard focus is trapped within the modal while it's open. Users should not be able to tab to elements behind the modal.

### Background Overlay
Although not shown in the component itself, modals should typically be displayed over a semi-transparent backdrop that:
- Dims the underlying content
- Prevents interaction with background elements
- Can optionally close the modal when clicked (if closeable)

### Animation
Consider adding entrance/exit animations:
- Fade in/out for the backdrop
- Scale or slide animation for the modal itself
- Keep animations subtle and quick (200-300ms)

### Responsive Behavior
The documented variants show fixed widths (720px and 288px). Consider:
- Maximum width constraints for smaller viewports
- Margin around the modal on mobile devices
- Potentially different padding values for mobile

### Content Scrolling
If content exceeds the available viewport height:
- The content area should become scrollable
- The header should remain fixed at the top
- The footer (if present) should remain fixed at the bottom

## Version History
- **Version 1.0** - Initial component design with Modal and Dialog variants, optional padding configurations
