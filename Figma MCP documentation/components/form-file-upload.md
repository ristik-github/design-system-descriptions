# Form File Upload Component

## Overview
The Form File Upload component is a drag-and-drop file upload area that allows users to select files either by clicking or dragging files into the designated zone. It provides visual feedback through multiple states and includes helper text to guide users on acceptable file types and size limits.

**Use Cases:** File uploads in forms, document submissions, attachment uploads, profile picture uploads, any scenario requiring users to upload files to the application.

---

## Component Properties

### States
The component supports six interactive states:

#### Default
The initial resting state when the upload area is ready to accept files.

**Visual Specifications:**
- **Background:** `global/color/dark-blue/10` (#f5f7fa)
- **Border:** 1px dashed using `nova/button/secondary/default/color/primary` (#1f4cb3)
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/button` (8px)
- **Padding:** `nova/spacing/tight` (8px)
- **Label Typography:** `nova/typography/instructional/regular`
- **Label Font Size:** `global/typography/fontsize/14`
- **Label Color:** `nova/button/secondary/default/color/primary`
- **Helper Text Typography:** `nova/typography/supporting/regular`
- **Helper Text Font Size:** `global/typography/fontsize/12`
- **Helper Text Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Gap between label and helper text:** `nova/spacing/next` (4px)

**Use When:**
- Component is ready to accept interaction
- User has not yet interacted with the upload area

**Behavior:**
- Lightest background color indicating neutral/ready state

#### Hover
The state when cursor is positioned over the upload area.

**Visual Specifications:**
- **Background:** `global/color/dark-blue/50` (#e6f3ff) - darker than Default
- **Border:** 1px dashed using `nova/button/secondary/default/color/primary` (#1f4cb3)
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/button` (8px)
- **Padding:** `nova/spacing/tight` (8px)
- **Label Typography:** `nova/typography/instructional/regular`
- **Label Font Size:** `global/typography/fontsize/14`
- **Label Color:** `nova/button/secondary/default/color/primary`
- **Helper Text Typography:** `nova/typography/supporting/regular`
- **Helper Text Font Size:** `global/typography/fontsize/12`
- **Helper Text Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Gap between label and helper text:** `nova/spacing/next` (4px)
- **Cursor:** Pointer

**Use When:**
- User's cursor is positioned over the upload area
- Indicates the area is interactive

**Behavior:**
- Background color darkens to provide visual feedback
- Cursor changes to pointer to indicate clickability

#### Focus
The state when the upload area is actively focused (via keyboard or click).

**Visual Specifications:**
- **Background:** `global/color/dark-blue/50` (#e6f3ff) - same as Hover
- **Border:** 1px dashed using `nova/button/secondary/default/color/primary` (#1f4cb3)
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/button` (8px)
- **Padding:** `nova/spacing/tight` (8px)
- **Label Typography:** `nova/typography/instructional/regular`
- **Label Font Size:** `global/typography/fontsize/14`
- **Label Color:** `nova/button/secondary/default/color/primary`
- **Helper Text Typography:** `nova/typography/supporting/regular`
- **Helper Text Font Size:** `global/typography/fontsize/12`
- **Helper Text Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Gap between label and helper text:** `nova/spacing/next` (4px)
- **Focus Ring:** 2px border using `nova/color/focus` (#9ef1e4)
- **Focus Ring Position:** Outside the component border (-2px inset)
- **Focus Ring Radius:** `nova/radii/component/button` (8px, matches component)

**Use When:**
- Upload area receives keyboard focus (Tab key)
- User clicks on the upload area

**Behavior:**
- Focus ring appears outside the dashed border
- Background color same as Hover state
- Keyboard accessible (Enter/Space triggers file dialog)

#### Pressed
The state when the upload area is being actively clicked or files are being dragged over it.

**Visual Specifications:**
- **Background:** `global/color/dark-blue/100` (#dbedfe) - darkest interactive state
- **Border:** 1px dashed using `nova/button/secondary/default/color/primary` (#1f4cb3)
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/button` (8px)
- **Padding:** `nova/spacing/tight` (8px)
- **Label Typography:** `nova/typography/instructional/regular`
- **Label Font Size:** `global/typography/fontsize/14`
- **Label Color:** `nova/button/secondary/default/color/primary`
- **Helper Text Typography:** `nova/typography/supporting/regular`
- **Helper Text Font Size:** `global/typography/fontsize/12`
- **Helper Text Color:** `nova/color/typography/muted` (rgba(0,0,0,0.62))
- **Gap between label and helper text:** `nova/spacing/next` (4px)

**Use When:**
- User is actively clicking the upload area
- Files are being dragged over the drop zone

**Behavior:**
- Background color darkens to darkest shade to indicate active press
- Provides clear visual feedback for click/drag interaction

#### Error
The state when file validation fails (wrong file type, size exceeded, etc.).

**Visual Specifications:**
- **Background:** `global/color/dark-blue/10` (#f5f7fa)
- **Border:** 1px dashed using `nova/button/secondary/default/color/primary` (#1f4cb3)
- **Border Width:** `nova/border/basic`
- **Border Radius:** `nova/radii/component/button` (8px)
- **Padding:** `nova/spacing/tight` (8px)
- **Label and Helper Text:** Same as Default state
- **Error Message:**
  - **Typography:** `nova/typography/supporting/regular`
  - **Font Size:** `global/typography/fontsize/12`
  - **Color:** `nova/color/critical/primary` (#d52020)
  - **Icon:** Warning icon (12x12px) in `nova/color/critical/primary`
  - **Gap between icon and text:** `nova/spacing/tight` (8px)
  - **Position:** Below the upload area
  - **Alignment:** Right-aligned

**Error Message Example:** "Invalid file, please upload a different one."

#### Loading
The state when a file is being uploaded or processed.

**Visual Specifications:**
- **Background:** Same as Default
- **Border:** Same as Default
- **Label and Helper Text:**
  - **Opacity:** 20% (0.2)
  - All other properties same as Default
- **Loading Indicator:**
  - Animated spinner centered over the upload area
  - **Size:** 79x84px
  - **Position:** Centered (absolute positioning with 50% transform)
  - Overlays the dimmed label and helper text

---

### Optional Features

#### Show Helper Text
Controls whether the helper text is displayed below the main label.

**Property:** `showHelperText` (boolean)
**Default:** `true`

**Helper Text Purpose:**
- Provide file size limits (e.g., "Up to 8mb")
- Specify accepted file types (e.g., "only PDF, DOC or DOCX files")
- Give users guidance before attempting to upload

**When to Hide:**
- When file requirements are obvious or communicated elsewhere
- In compact layouts where space is limited
- When helper text would be redundant

---

## Design Tokens

### Typography

**Label Text:**
- **Token:** `nova/typography/instructional/regular`
- **Font Size:** `global/typography/fontsize/14`
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Line Height:** 1.2
- **Usage:** Main upload instruction text

**Helper Text:**
- **Token:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`
- **Font Family:** Geist
- **Font Weight:** 400 (Regular)
- **Line Height:** 1.2
- **Usage:** File requirements and guidance text

**Error Message:**
- **Token:** `nova/typography/supporting/regular`
- **Font Size:** `global/typography/fontsize/12`
- **Usage:** Error validation message

---

### Colors

**Background (Default State):**
- **Token:** `global/color/dark-blue/10`
- **Value:** #f5f7fa
- **Usage:** Upload area background in Default, Error, and Loading states

**Background (Hover State):**
- **Token:** `global/color/dark-blue/50`
- **Value:** #e6f3ff
- **Usage:** Upload area background in Hover and Focus states

**Background (Pressed State):**
- **Token:** `global/color/dark-blue/100`
- **Value:** #dbedfe
- **Usage:** Upload area background in Pressed state (darkest interactive state)

**Border (Default, Hover, Focus, Pressed, Error):**
- **Token:** `nova/button/secondary/default/color/primary`
- **Value:** #1f4cb3
- **Usage:** Dashed border in all states

**Focus Ring:**
- **Token:** `nova/color/focus`
- **Value:** #9ef1e4
- **Usage:** Focus indicator border

**Label Text:**
- **Token:** `nova/button/secondary/default/color/primary`
- **Value:** #1f4cb3
- **Usage:** Main instruction text color

**Helper Text:**
- **Token:** `nova/color/typography/muted`
- **Value:** rgba(0,0,0,0.62)
- **Usage:** Supporting guidance text

**Error Message:**
- **Token:** `nova/color/critical/primary`
- **Value:** #d52020
- **Usage:** Error text and icon color

**Loading State Opacity:**
- **Value:** 20% (0.2)
- **Usage:** Dimming label and helper text during upload

---

### Spacing

**Internal Padding:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px (all sides)
- **Usage:** Padding inside the upload area

**Gap between Label and Helper Text:**
- **Token:** `nova/spacing/next`
- **Value:** 4px
- **Usage:** Vertical spacing between main label and helper text

**Gap in Error Message:**
- **Token:** `nova/spacing/tight`
- **Value:** 8px
- **Usage:** Horizontal gap between error icon and error text

**Error Message Icon Padding:**
- **Value:** 1px (vertical padding)
- **Usage:** Vertical padding around error icon

---

### Borders & Radii

**Border Width:**
- **Token:** `nova/border/basic`
- **Value:** 1px
- **Usage:** Dashed border width

**Border Style:**
- **Value:** Dashed
- **Usage:** All states use dashed border style

**Border Radius:**
- **Token:** `nova/radii/component/button`
- **Value:** 8px
- **Usage:** Component corners

**Focus Ring Width:**
- **Value:** 2px
- **Usage:** Focus indicator border width

**Focus Ring Offset:**
- **Value:** -2px (inset)
- **Usage:** Focus ring positioned outside component border

---

## Layout Specifications

### Structure
The component uses a vertical flex layout:

1. **Upload Area (Main Container):**
   - Dashed border container
   - Vertical flex layout (column)
   - Centers content both horizontally and vertically
   
2. **Content (Inside Upload Area):**
   - **Label text** (top)
   - **Helper text** (bottom, optional)
   - **Gap:** `nova/spacing/next` (4px) between label and helper text

3. **Error Message Row (Below Upload Area, Error State Only):**
   - Horizontal flex layout
   - Right-aligned
   - **Icon** (12x12px warning icon)
   - **Error text**
   - **Gap:** `nova/spacing/tight` (8px) between icon and text

4. **Loading Indicator (Loading State Only):**
   - Absolutely positioned, centered
   - Overlays dimmed content

### Spacing

**Internal Padding:**
- **All sides:** `nova/spacing/tight` (8px)

**Content Gap:**
- **Between label and helper text:** `nova/spacing/next` (4px)

**Error Message Gap:**
- **Between icon and text:** `nova/spacing/tight` (8px)
- **Icon vertical padding:** 1px

### Visual Properties

**Upload Area:**
- **Background:** `global/color/dark-blue/10`
- **Border:** 1px dashed `nova/button/secondary/default/color/primary`
- **Border Radius:** `nova/radii/component/button` (8px)

**Focus Ring (Focus State):**
- **Width:** 2px
- **Color:** `nova/color/focus`
- **Position:** -2px inset (outside border)
- **Radius:** 8px (matches component)

**Layout Container:**
- **Direction:** Column (vertical)
- **Alignment:** Center (both horizontal and vertical)
- **Text Alignment:** Center

### Dimensions

**Component Width:**
- Full width of container (fills available space)

**Component Height:**
- Determined by padding + content height
- Flexible based on content (label + optional helper text)

**Minimum Dimensions:**
- Should accommodate label text + helper text + padding
- Typically ranges from 80-120px height depending on content

**Error Icon:**
- **Size:** 12x12px

**Loading Spinner:**
- **Size:** 79x84px (width x height)

---

## Accessibility Considerations

### Keyboard Navigation
- Upload area must be focusable via keyboard (Tab key)
- Focus state should be clearly visible with focus ring (`nova/color/focus`)
- Enter or Space key should trigger file selection dialog

### Screen Readers
- Label text should clearly describe the upload action
- Helper text should be associated with the upload area using `aria-describedby`
- Error messages should be announced when they appear
- Loading state should announce upload progress

### ARIA Attributes

**Upload Area:**
- Use `role="button"` or appropriate interactive role
- `aria-label` should describe the upload action if label is not sufficient
- `aria-describedby` should reference helper text element

**Error State:**
- `aria-invalid="true"` when error exists
- `aria-errormessage` pointing to error message element
- Error message should have `role="alert"` for immediate announcement

**Loading State:**
- `aria-busy="true"` during upload
- `aria-live="polite"` region for upload progress updates

---

## Usage Guidelines

### When to Use

**File Upload Scenarios:**
- Document submissions (resumes, reports, PDFs)
- Image uploads (profile pictures, photos, attachments)
- Any form requiring file attachments
- Multi-file upload scenarios

**Helper Text:**
- Always show when file type or size restrictions exist
- Provide clear guidance on acceptable formats
- Specify file size limits
- Indicate if multiple files are allowed

**Error State:**
- File type not allowed (e.g., .exe when only images accepted)
- File size exceeds limit
- File upload failed due to network or server error
- Corrupted or invalid file

**Loading State:**
- During file upload process
- While file is being validated server-side
- When processing large files that take time

### Best Practices

#### Do:
- Provide clear, actionable label text (e.g., "Click or drag here to upload a file")
- Always include helper text with file requirements
- Show error messages that explain what went wrong and how to fix it
- Use loading state for uploads that take more than 1-2 seconds
- Make the entire area clickable and draggable
- Provide visual feedback for all states (hover, focus, pressed)
- Use appropriate file type validation before upload
- Display file name after successful selection

#### Don't:
- Use vague labels like "Upload" or "Drop file"
- Hide file size or type restrictions
- Forget to show loading state for slow uploads
- Use cryptic error messages
- Make only part of the area clickable
- Allow files that will fail validation
- Forget to clear error state after successful retry

### Content Guidelines

**Label Text:**
- **Be clear:** "Click or drag here to upload a file"
- **Action-oriented:** Use verbs like "Click", "Drag", "Drop"
- **Specific:** Indicate what will be uploaded if context-specific

**Helper Text:**
- **File size limit:** "Up to 8mb" or "Maximum 10MB"
- **File types:** "only PDF, DOC or DOCX files" or "JPG, PNG, or GIF"
- **Quantity:** "Up to 5 files" if multiple allowed
- **Keep it concise:** One line if possible

**Error Messages:**
- **Be specific:** "File size exceeds 8mb limit" not "Invalid file"
- **Provide solution:** "please upload a different one" or "reduce file size and try again"
- **Friendly tone:** Avoid technical jargon

---

## Content Structure

The component consists of:

1. **Upload Area (Required)**
   - Dashed border container
   - Houses label and optional helper text
   - Clickable and accepts drag-and-drop

2. **Label Text (Required)**
   - Primary instruction for the user
   - Describes the upload action
   - Always visible (except at 20% opacity in loading state)

3. **Helper Text (Optional)**
   - File requirements and restrictions
   - Positioned below label text
   - Can be hidden via `showHelperText` property

4. **Error Message (Conditional)**
   - Appears below upload area when error occurs
   - Includes warning icon + descriptive text
   - Right-aligned

5. **Loading Indicator (Conditional)**
   - Animated spinner during upload
   - Centered over dimmed upload area
   - Replaces interactivity temporarily

---

## Interactive States

### Default
The initial ready state.

**Visual:**
- Background: `global/color/dark-blue/10` (#f5f7fa - lightest)
- Border: 1px dashed `nova/button/secondary/default/color/primary`
- Label text visible in `nova/button/secondary/default/color/primary`
- Helper text visible in `nova/color/typography/muted` (if enabled)

**Behavior:**
- Ready to accept click or drag interaction
- Neutral/ready state with lightest background

### Hover
When cursor is over the upload area.

**Visual:**
- Background: `global/color/dark-blue/50` (#e6f3ff - darker than Default)
- Border: 1px dashed `nova/button/secondary/default/color/primary`
- Label text visible in `nova/button/secondary/default/color/primary`
- Helper text visible in `nova/color/typography/muted` (if enabled)
- Cursor changes to pointer

**Behavior:**
- Indicates area is interactive
- Background darkens to provide visual feedback
- Prepares user for click or drop action

### Focus
When upload area receives keyboard focus.

**Visual:**
- Background: `global/color/dark-blue/50` (#e6f3ff - same as Hover)
- Border: 1px dashed `nova/button/secondary/default/color/primary`
- Focus ring: 2px border using `nova/color/focus` (#9ef1e4)
- Focus ring positioned -2px outside component border
- Label and helper text same as Default

**Behavior:**
- Keyboard accessible
- Enter/Space triggers file selection dialog
- Focus ring provides clear focus indicator

### Pressed
When upload area is being clicked or files are being dragged over it.

**Visual:**
- Background: `global/color/dark-blue/100` (#dbedfe - darkest)
- Border: 1px dashed `nova/button/secondary/default/color/primary`
- Label text visible in `nova/button/secondary/default/color/primary`
- Helper text visible in `nova/color/typography/muted` (if enabled)

**Behavior:**
- Active click state
- Drag-over state when files are hovering
- Darkest background indicates active press interaction

### Error
When file validation fails.

**Visual:**
- Upload area same as Default state
- Error message appears below:
  - Warning icon (12x12px) in `nova/color/critical/primary`
  - Error text in `nova/color/critical/primary`
  - Right-aligned

**Behavior:**
- Upload is blocked until valid file selected
- Error message explains the issue
- User can retry with different file

### Loading
When file is being uploaded or processed.

**Visual:**
- Upload area background and border same as Default
- Label and helper text dimmed to 20% opacity
- Animated loading spinner (79x84px) centered over area

**Behavior:**
- Upload area not interactive during loading
- Spinner indicates ongoing process
- User must wait for completion

---

## Visual Behavior Notes

### Component Architecture
The Form File Upload is a single, self-contained component with state-dependent visual changes and optional helper text.

**Visual Composition:**
- Main upload area (dashed border container)
- Label text (centered)
- Optional helper text (centered below label)
- Conditional error message (below upload area, right-aligned)
- Conditional loading overlay (centered spinner)

### Key Visual Behaviors

**Background Color Progression:**
- Background color **darkens progressively** through interaction states
- **Default:** `global/color/dark-blue/10` (#f5f7fa) - Lightest, neutral ready state
- **Hover:** `global/color/dark-blue/50` (#e6f3ff) - Darker, indicates interactivity
- **Focus:** `global/color/dark-blue/50` (#e6f3ff) - Same as Hover + focus ring
- **Pressed:** `global/color/dark-blue/100` (#dbedfe) - Darkest, indicates active press
- **Error/Loading:** Return to `global/color/dark-blue/10` - Same as Default
- This progression provides clear visual feedback for user interactions

**Error Message Display:**
- Error message appears **below** the upload area, not inside it
- Right-aligned with icon + text
- Icon is 12x12px warning icon
- Gap between icon and text is `nova/spacing/tight` (8px)

**Loading State Overlay:**
- Label and helper text remain visible but dimmed to 20% opacity
- Loading spinner is absolutely positioned and centered
- Spinner overlays the dimmed text
- Upload area maintains same dimensions
- Background returns to Default state color (`global/color/dark-blue/10`)

**Focus Ring Positioning:**
- Focus ring appears **outside** the dashed border
- 2px width, -2px inset positioning
- Matches component border radius (8px)
- Focus state combines Hover background + focus ring

**Dashed Border:**
- All states use dashed border style (not solid)
- Same color across all states: `nova/button/secondary/default/color/primary`
- Border style distinguishes upload areas from regular inputs
- Border color does NOT change across states (only background changes)

### Sizing Behavior
- **Width:** Full width of container (fill container)
- **Height:** Flexible, determined by content (label + helper text) + padding
- **Minimum height:** Sufficient to accommodate centered text + padding
- Upload area expands to fit content vertically

---

## Version History
- **Current Version:** Design system tokens extracted from Figma component
- **Last Updated:** Form file upload component with 6 states and optional helper text

---

## Questions or Clarifications
For implementation questions or design clarifications:
- Consult file upload best practices for drag-and-drop implementation
- Check with the design team for loading animation specifications
- Reference accessibility guidelines for file upload components
- Verify accepted file types and size limits with backend requirements
