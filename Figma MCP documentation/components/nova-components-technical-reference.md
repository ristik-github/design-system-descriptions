# Nova Components - Technical Reference

**Version:** 1.0  
**Purpose:** Concise visual properties reference for developers. Only properties with values are listed.  
**Format:** Base properties → Size variants → Interactive states (only changed properties)

---

## 1. Button Component

### Base (All Sizes, All Variants)
- Border Radius: `nova/radii/component/button`
- Typography: `nova/typography/instructional/regular`
- Font Size: `global/typography/fontsize/14`
- Gap: `nova/spacing/next`

### Small Size
- Height: 28px
- Padding Horizontal: `nova/spacing/tight`
- Padding Vertical: `nova/spacing/next`

### Large Size
- Height: 36px
- Padding Horizontal: `nova/spacing/close`
- Padding Vertical: `nova/spacing/tight`

---

### Primary Variant - Default Color

#### Default State
- Background: `nova/button/primary/default/color/primary`
- Foreground: `nova/button/primary/default/color/neutral`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/primary/default/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/primary/default/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`

---

### Primary Variant - Destructive Color

#### Default State
- Background: `nova/button/primary/destructive/color/primary`
- Foreground: `nova/button/primary/destructive/color/neutral`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/primary/destructive/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/primary/destructive/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`

---

### Secondary Variant - Default Color

#### Default State
- Background: `nova/button/secondary/default/color/neutral`
- Foreground: `nova/button/secondary/default/color/primary`
- Border: `nova/border/basic` width, `nova/button/secondary/default/color/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/secondary/default/color/tertiary`
- Foreground: `nova/button/secondary/default/color/secondary`
- Border: `nova/button/secondary/default/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/secondary/default/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Destructive Color

#### Default State
- Background: `nova/button/secondary/destructive/color/neutral`
- Foreground: `nova/button/secondary/destructive/color/primary`
- Border: `nova/border/basic` width, `nova/button/secondary/destructive/color/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/secondary/destructive/color/tertiary`
- Foreground: `nova/button/secondary/destructive/color/secondary`
- Border: `nova/button/secondary/destructive/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/secondary/destructive/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Error Color

#### Default State
- Background: `nova/color/critical/quaternary`
- Foreground: `nova/color/critical/primary`
- Border: `nova/border/basic` width, `nova/color/critical/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/critical/accent`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Success Color

#### Default State
- Background: `nova/color/success/quaternary`
- Foreground: `nova/color/success/primary`
- Border: `nova/border/basic` width, `nova/color/success/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/success/dark`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Neutral Color

#### Default State
- Background: `nova/color/neutral/quaternary`
- Foreground: `nova/color/neutral/primary`
- Border: `nova/border/basic` width, `nova/color/neutral/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/neutral/dark`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Warning Color

#### Default State
- Background: `nova/color/warning/quaternary`
- Foreground: `nova/color/warning/primary`
- Border: `nova/border/basic` width, `nova/color/warning/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/warning/dark`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Informative Color

#### Default State
- Background: `nova/color/informative/quaternary`
- Foreground: `nova/color/informative/primary`
- Border: `nova/border/basic` width, `nova/color/informative/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/informative/dark`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Secondary Variant - Feature Color

#### Default State
- Background: `nova/color/feature/quaternary`
- Foreground: `nova/color/feature/primary`
- Border: `nova/border/basic` width, `nova/color/feature/primary` color

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/feature/dark`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`
- Border: `nova/color/skeleton/secondary`

---

### Tertiary Variant - Default Color

#### Default State
- Background: `nova/button/tertiary/default/color/neutral`
- Foreground: `nova/button/tertiary/default/color/primary`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/tertiary/default/color/tertiary`
- Foreground: `nova/button/tertiary/default/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/tertiary/default/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`

---

### Tertiary Variant - Destructive Color

#### Default State
- Background: `nova/button/tertiary/destructive/color/neutral`
- Foreground: `nova/button/tertiary/destructive/color/primary`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/tertiary/destructive/color/tertiary`
- Foreground: `nova/button/tertiary/destructive/color/secondary`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/button/tertiary/destructive/color/tertiary`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/color/skeleton/primary`
- Foreground: `nova/color/skeleton/secondary`

---

## 2. Text Input Component

### Base (All States)
- Height: 36px
- Border Radius: `nova/radii/component/input`
- Padding: `nova/spacing/tight` (all sides)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`

---

### Default State

#### Filled Off (Empty)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground (Placeholder): `nova/input/color/placeholder`

#### Filled On (Has Content)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground: `nova/color/typography/base`

---

### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Border: `nova/input/color/accent` (slightly emphasized, implementation-specific)

---

### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/focus` color
- Focus Ring: 2px, `nova/color/focus`

---

### Error State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/critical/primary` color

---

### Focus (Error) State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/critical/primary` color
- Focus Ring: 2px, `nova/color/focus`

---

### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/input/color/disabled`
- Foreground: `nova/color/typography/muted`
- Icon Color: `nova/color/skeleton/secondary`

---

### Readonly State

#### Filled Off (Empty)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground (Placeholder): "-" (hyphen)

#### Filled On (Has Content)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground: `nova/color/typography/base`

---

### With Icon (Optional)
- Icon Size: 20x20px
- Icon Color: `nova/input/color/secondary`
- Gap to Text: `nova/spacing/next`

---

## 3. Form Label Component

### Base (All Variants)
- Typography: `nova/typography/body/regular`
- Font Size: 16px
- Foreground: `nova/color/typography/base`
- Height: 22px

---

### Default Variant
- (No additional properties - only label text)

---

### Required Variant
- Asterisk Typography: `nova/typography/base/strong`
- Asterisk Font Size: `global/typography/fontsize/14`
- Asterisk Foreground: `nova/color/critical/primary`
- Gap to Asterisk: 10px

---

### Optional Variant
- Optional Text Typography: `nova/typography/supporting/regular`
- Optional Text Font Size: `global/typography/fontsize/12`
- Optional Text Foreground: `nova/color/typography/muted`
- Gap to Optional Text: 10px

---

## 4. Icon Button Component

### Base (All Sizes, All Variants)
- Border Radius: `nova/radii/component/button`
- Icon Size: 20x20px
- Padding: 6px (all sides)

### Small Size
- Total Size: 28x28px

### Large Size
- Total Size: 36x36px

---

### Subtle Off Variant

#### Default State
- Border: `nova/icon-button/color/border-muted`
- Foreground (Icon): `nova/color/typography/base`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background Overlay: `global/color/alpha-dark-blue/400`

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background Overlay: `global/color/alpha-dark-blue/500`

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: 1px, `nova/color/focus`, -1px offset

#### Selected (Active) State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/700`
- Foreground (Icon): (adjusted for contrast)

#### Loading State
- Loading Skeleton Size: 32x32px
- Background: `nova/color/skeleton/primary`
- Border: `nova/color/skeleton/primary`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Foreground (Icon): `nova/color/skeleton/secondary`

---

### Subtle On Variant

#### Default State
- Foreground (Icon): `nova/color/typography/base`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background Overlay: (subdued, implementation-specific)

#### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background Overlay: (darker, implementation-specific)

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Focus Ring: 1px, `nova/color/focus`, -1px offset

#### Selected (Active) State
_(Only changed properties listed; all others inherited from Default State)_
- Background: (distinct selection color)

#### Loading State
- Loading Skeleton Size: 32x32px
- Background: `nova/color/skeleton/primary`
- Border: `nova/color/skeleton/primary`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Foreground (Icon): `nova/color/skeleton/secondary`

---

### Tooltip (Optional Feature)
- Typography: `nova/typography/supporting/regular`
- Font Size: `global/typography/fontsize/12`
- Background: `nova/tooltip/color/background`
- Foreground: `nova/tooltip/color/foreground`
- Padding Horizontal: `semantic/spacing/tight`
- Padding Vertical: `semantic/spacing/next`
- Border Radius (Subtle Off): `semantic/radii/softened`
- Border Radius (Subtle On): `semantic/radii/regular`
- Shadow: 0px 2px 4px 0px rgba(0,0,0,0.13)

---

## 5. Dropdown Component

### Base (All States)
- Input Height: 36px (minimum)
- Input Border Radius: `nova/radii/component/input`
- Input Padding: `nova/spacing/tight` (all sides)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Gap Label to Input: `nova/spacing/tight`

---

### Dropdown Off (Closed)

#### Filled Off (Empty)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground (Placeholder): `nova/input/color/placeholder`
- Icon Size: 20x20px
- Icon: Chevron down

#### Filled On (Has Selection)
##### Single Select Mode
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground: `nova/color/typography/base`

##### Multi Select Mode
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Chip Background: `nova/color/neutral/secondary`
- Chip Border: `nova/color/neutral/primary`
- Chip Foreground: `nova/color/typography/base`
- Chip Font Size: 12px
- Chip Border Radius: 4px
- Chip Padding Left: `nova/spacing/tight`
- Chip Padding Right: `nova/spacing/next`
- Chip Padding Vertical: 4px
- Gap Between Chips: 6px
- Chip Close Icon Size: 20x20px
- Gap Chip Text to Icon: `nova/spacing/next`

---

### Dropdown On (Open)
_(Only changed properties listed; all others inherited from Closed State)_
- Border: `nova/border/basic` width, `nova/input/color/secondary` color
- Focus Ring: 2px, `nova/color/focus`
- Dropdown Menu Visible: Yes
- Dropdown Menu Position: Below input, 2px gap
- Dropdown Menu Background: `nova/input/color/background`
- Dropdown Menu Border Radius: `nova/radii/softened`
- Dropdown Menu Padding: `nova/spacing/tight`
- Dropdown Menu Shadow: 0px 8px 24px 0px rgba(0,0,0,0.13)
- Dropdown Menu Max Height: 372px

---

### Dropdown Menu Options

#### Single Select Mode

##### Default Option
- Background: transparent
- Foreground: `nova/link-option/color/neutral`
- Padding: `nova/spacing/tight` (all sides)
- Border Radius: `nova/spacing/next`
- Min Height: 32px
- Gap Between Options: `nova/spacing/next`

##### Hover/First Option
_(Only changed properties listed; all others inherited from Default Option)_
- Background: `nova/link-option/color/accent`

##### Selected Option
_(Only changed properties listed; all others inherited from Default Option)_
- Background: `nova/link-option/color/accent`

---

#### Multi Select Mode

##### Unselected Option
- Background: transparent
- Foreground: `nova/link-option/color/neutral`
- Padding: `nova/spacing/tight` (all sides)
- Border Radius: `nova/spacing/next`
- Min Height: 32px
- Gap Between Options: `nova/spacing/next`
- Checkbox Size: 20x20px
- Checkbox Background: `nova/input/color/background`
- Checkbox Border: `nova/border/basic` width, `nova/input/color/accent` color
- Checkbox Border Radius: `nova/radii/component/checkbox`
- Gap Checkbox to Text: `nova/spacing/tight`

##### Hover Option (Unselected)
_(Only changed properties listed; all others inherited from Unselected Option)_
- Background: `nova/link-option/color/accent`

##### Selected Option
_(Only changed properties listed; all others inherited from Unselected Option)_
- Background: `nova/link-option/color/secondary`
- Foreground: `nova/color/static/white`
- Checkbox Background: `nova/input/color/highlight1`
- Checkbox Checkmark: White icon, 16x16px

---

### Label (Always Present)
- Typography: `nova/typography/body/regular`
- Font Size: 16px
- Foreground: `nova/color/typography/base`

---

## Notes

- **Base Section:** Contains properties shared across all variants and sizes
- **Size Variants:** Listed immediately after Base, only showing size-specific properties
- **States:** Only changed properties listed; all others inherited from Default or Base
- **Optional Features:** Listed separately when not part of all variants
- **Token Format:** All design tokens listed with their full path (e.g., `nova/spacing/tight`)
- **Fixed Values:** Properties without tokens show raw values (e.g., 28px, 6px)

---

## 6. Form Field Component

### Base (All States, All Variants)
- Layout: Vertical flex column
- Gap Label to Input: `nova/spacing/tight`
- Input Height: 36px
- Input Border Radius: `nova/radii/component/input`
- Input Padding: `nova/spacing/tight` (all sides)
- Input Typography: `nova/typography/base/regular`
- Input Font Size: `global/typography/fontsize/14`

---

### Label Variants

#### Default Label
- Typography: `nova/typography/body/regular`
- Foreground: `nova/color/typography/base`

#### Required Label
- Label Typography: `nova/typography/body/regular`
- Label Foreground: `nova/color/typography/base`
- Asterisk Typography: `nova/typography/base/strong`
- Asterisk Font Size: `global/typography/fontsize/14`
- Asterisk Foreground: `nova/color/critical/primary`
- Gap to Asterisk: 10px

#### Optional Label
- Label Typography: `nova/typography/body/regular`
- Label Foreground: `nova/color/typography/base`
- Optional Text Typography: `nova/typography/supporting/regular`
- Optional Text Font Size: `global/typography/fontsize/12`
- Optional Text Foreground: `nova/color/typography/muted`
- Gap to Optional Text: 10px

---

### Input States

#### Default State
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground (Placeholder): `nova/input/color/placeholder`
- Foreground (Filled): `nova/color/typography/base`

#### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- (Implementation-specific subtle emphasis)

#### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/focus` color
- Focus Ring: 2px, `nova/color/focus`

#### Error State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/critical/primary` color

#### Focus (Error) State
_(Only changed properties listed; all others inherited from Default State)_
- Border: 2px width, `nova/color/critical/primary` color
- Focus Ring: 2px, `nova/color/focus`

#### Disabled State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `nova/input/color/disabled`
- Foreground: `nova/color/typography/muted`
- Icon Color: `nova/color/skeleton/secondary`

#### Readonly State (Empty)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground: `nova/input/color/placeholder`

#### Readonly State (Filled)
- Background: `nova/input/color/background`
- Border: `nova/border/basic` width, `nova/input/color/accent` color
- Foreground: `nova/color/typography/base`

---

### With Icon (Optional)
- Icon Size: 20x20px
- Icon Color: `nova/input/color/secondary`
- Icon Color (Disabled): `nova/color/skeleton/secondary`
- Gap to Text: `nova/spacing/next`

---

## 7. Form File Upload Component

### Base (All States)
- Border: `nova/border/basic` width, dashed style, `nova/button/secondary/default/color/primary` color
- Border Radius: `nova/radii/component/button`
- Padding: `nova/spacing/tight` (all sides)
- Layout: Vertical flex column, centered alignment
- Gap Label to Helper Text: `nova/spacing/next`

### Label Text (All States)
- Typography: `nova/typography/instructional/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/button/secondary/default/color/primary`

### Helper Text (All States)
- Typography: `nova/typography/supporting/regular`
- Font Size: `global/typography/fontsize/12`
- Foreground: `nova/color/typography/muted`

---

### Default State
- Background: `global/color/dark-blue/10`

### Hover State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/50`

### Focus State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/50`
- Focus Ring: 2px, `nova/color/focus`, -2px offset

### Pressed State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/100`

### Error State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/10`
- Error Message Typography: `nova/typography/supporting/regular`
- Error Message Font Size: `global/typography/fontsize/12`
- Error Message Foreground: `nova/color/critical/primary`
- Error Icon Size: 12x12px
- Error Icon Color: `nova/color/critical/primary`
- Gap Icon to Text: `nova/spacing/tight`

### Loading State
_(Only changed properties listed; all others inherited from Default State)_
- Background: `global/color/dark-blue/10`
- Label Opacity: 20%
- Helper Text Opacity: 20%
- Loading Spinner Size: 79x84px (centered)

---

## 8. Header Top Nav Component

### Base (Large Width, Legacy=off)
- Primary Bar Background: `nova/navigation/primary`
- Primary Bar Height: 52px
- Primary Bar Padding Top/Bottom: `nova/spacing/tight`
- Primary Bar Padding Left: `nova/spacing/close`
- Primary Bar Padding Right: `nova/spacing/tight`
- Gap Between Sections: `nova/spacing/tight`

---

### Logo & Branding Section
- Logo Mark Size: 20.049x19.819px
- Divider: `nova/border/basic` width, white color, full height
- Product Name Typography: `nova/typography/base/strong`
- Product Name Font Size: `global/typography/fontsize/14`
- Product Name Foreground: `nova/color/static/white`
- Gap: `nova/spacing/near`

### Context Tag (Optional)
- Border: `nova/border/basic` width, white color
- Border Radius: `nova/radii/relaxed`
- Typography: `nova/typography/supporting/regular`
- Font Size: `global/typography/fontsize/12`
- Foreground: `nova/color/static/white`
- Padding Horizontal: `nova/spacing/close`
- Padding Vertical: `nova/spacing/tight`

---

### Primary Nav Items (Large, Legacy=off)

#### Default Nav Item
- Foreground: `nova/color/static/white`
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Padding Horizontal: `nova/spacing/close`
- Min Height: 32px
- Border Radius: `nova/radii/component/button`
- Gap Between Items: `nova/spacing/slight`

#### Hover Nav Item
_(Only changed properties listed; all others inherited from Default Nav Item)_
- Background: `global/color/muted-teal/700`
- Foreground: `nova/color/static/white`

#### Active Nav Item
_(Only changed properties listed; all others inherited from Default Nav Item)_
- Background: `global/color/pale-green/150`
- Foreground: `global/color/green/900`

---

### Search & Actions

#### Search Box
- Width: 160px (Large), 100px (Medium)
- Height: 36px
- Background: `global/color/muted-teal/700`
- Border Radius: `nova/radii/component/input`
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground (Placeholder): `nova/color/static/white-60%`
- Foreground (Focused): `nova/color/static/white`
- Padding Right: `nova/spacing/next`
- Icon Size: 20px
- Icon Color: White

#### Icon Buttons
- Size: 36x36px
- Border Radius: `nova/radii/component/button`
- Background: `global/color/muted-teal/700`
- Icon Size: 20px
- Icon Color: White

#### Global Actions Container
- Height: 36px
- Border Radius: `nova/radii/full`
- Background: `global/color/muted-teal/700`
- Padding: `nova/spacing/next`
- Gap: `nova/spacing/next`

---

### Secondary Navigation (When Enabled)

#### Secondary Nav Bar
- Background: `global/color/pale-green/150`
- Border: `nova/border/basic` width, `global/color/pale-green/200` color (bottom/sides)
- Border Radius: `nova/radii/component/header` (bottom corners)
- Padding Vertical: `nova/spacing/tight`
- Padding Horizontal: `nova/spacing/close`

#### Default Sub-Nav Item
- Foreground: `global/color/green/900`
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Padding Horizontal: `nova/spacing/close`
- Min Height: 32px
- Border Radius: `nova/radii/component/button`

#### Hover Sub-Nav Item
_(Only changed properties listed; all others inherited from Default Sub-Nav Item)_
- Background: `global/color/pale-green/200`

#### Active Sub-Nav Item
_(Only changed properties listed; all others inherited from Default Sub-Nav Item)_
- Background: `global/color/muted-teal/800`
- Foreground: `global/color/pale-green/150`

---

### Medium Width Modifications
_(Only changed properties listed; all others inherited from Large Width)_
- Search Box Width: 100px
- Nav Items: May overflow with horizontal scroll
- Overflow Indicator: Chevron icon (20px)

---

### Legacy=on Modifications
_(Only changed properties listed; all others inherited from Legacy=off)_
- Primary navigation moves to separate row below branding bar
- Branding bar contains: Logo, divider, product name, context tag, search, icons, avatar

---

### Vertical Nav=on Modifications
_(Only changed properties listed; all others inherited from Vertical Nav=off)_
- Hamburger Menu Icon: 36px button
- No inline primary navigation (moved to vertical sidebar)
- Simplified header: Menu, Logo, Divider, Product Name, Search, Icons, Avatar

---

## 9. Vertical Navigation Component

### Base (All Levels)
- Container Width: 256px
- Container Background: `nova/navigation/secondary`
- Container Border: `nova/border/basic` width, `nova/surfaces/color/workspace-border` color
- Container Border Radius: `nova/radii/softened`
- Container Padding Horizontal: `nova/spacing/tight`
- Container Padding Vertical: `nova/spacing/near`
- Gap Between Items: `nova/spacing/slight`

### Nav Item Base (All Levels, All States)
- Display: Flex row
- Align Items: Center
- Justify Content: Space between
- Border Radius: `nova/radii/softened`
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/navigation/primary`
- Icon Size: 20x20px
- Gap Icon to Label: 8px

---

### Child=0 (Top Level)

#### Unselected State
- Width: 240px
- Height: 45px
- Padding Horizontal: `nova/spacing/tight`
- Padding Vertical: `nova/spacing/close`
- Background: Transparent

#### Selected State
_(Only changed properties listed; all others inherited from Unselected State)_
- Background: `global/color/neutral/white`
- Border: `nova/border/basic` width, `nova/surfaces/color/workspace-border` color
- Gap: 12px

---

### Child=1 (Second Level)

#### Unselected State
- Outer Width: 240px
- Inner Content Width: 224px
- Height: 45px
- Padding Left: 16px (creates hierarchy indent)
- Inner Padding Horizontal: `nova/spacing/tight`
- Inner Padding Vertical: `nova/spacing/close`
- Background: Transparent

#### Selected State
_(Only changed properties listed; all others inherited from Unselected State)_
- Inner Content Background: `global/color/neutral/white`
- Inner Content Border: `nova/border/basic` width, `nova/surfaces/color/workspace-border` color
- Gap: 12px

---

### Child=2 (Third Level)

#### Unselected State
- Outer Width: 240px
- Inner Content Width: 224px
- Height: 45px
- Padding Left: 32px (creates hierarchy indent)
- Inner Padding Horizontal: `nova/spacing/tight`
- Inner Padding Vertical: `nova/spacing/close`
- Background: Transparent

#### Selected State
_(Only changed properties listed; all others inherited from Unselected State)_
- Inner Content Background: `global/color/neutral/white`
- Inner Content Border: `nova/border/basic` width, `nova/surfaces/color/workspace-border` color
- Gap: 12px

---

## 10. Workspace Component

### Base (All Variants)
- Layout: Vertical flex column
- Border Radius: `nova/radii/component/workspace`
- Background: `nova/surfaces/color/workspace`

---

### Title Bar (When showTitle=true)
- Height: 52px (calculated from padding + content)
- Background: `nova/surfaces/color/workspace`
- Border Bottom: `nova/border/basic` width, `nova/surfaces/color/workspace border` color
- Padding Horizontal: `nova/spacing/near`
- Padding Vertical: `nova/spacing/close`
- Layout: Horizontal flex row
- Gap: 8px

#### Title Text
- Typography: `nova/typography/heading/3`
- Font Size: 18px
- Foreground: `nova/color/typography/base`

#### Metadata Text
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`
- Padding Bottom: 3px (baseline alignment)

#### Gap Title to Metadata
- Gap: `nova/spacing/tight`

#### Badge
- Background: `nova/color/neutral/secondary`
- Border: `nova/color/neutral/primary`
- Border Radius: `nova/radii/component/badge`
- Typography: `nova/typography/supporting/regular`
- Font Size: `global/typography/fontsize/12`
- Foreground: `nova/color/neutral/dark`
- Padding Horizontal: `nova/spacing/tight`
- Padding Vertical: `nova/spacing/next`

#### Buttons Container
- Height: 28px
- Gap: `nova/spacing/next`

---

### Content Area

#### Padding=On
- Padding: `nova/spacing/near` (all sides)
- Gap: 8px (internal content gap)

#### Padding=Off
- (No padding - content extends to edges)

---

### showTitle=false
- Title bar hidden
- Content area starts at top

---

## 11. Modal Component

### Base (All Variants)
- Border Radius: `nova/radii/component/modal`
- Background: `nova/drawer/color/background`
- Layout: Vertical flex column

---

### Header (All Variants)
- Border Bottom: `nova/border/basic` width, `nova/surfaces/color/workspace border` color
- Padding Horizontal: `nova/spacing/near`
- Padding Vertical: `nova/spacing/close`
- Layout: Horizontal flex row
- Gap: `nova/spacing/close`

#### Title Section
- Typography: `nova/typography/heading/3`
- Font Size: 18px
- Foreground: `nova/color/typography/base`
- Gap Title to Subtitle: `nova/spacing/slight`

#### Subtitle (When showSubtitle=true)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`

#### Close Button (When closeable=true)
- Size: 36x36px
- Icon Size: 20x20px
- Padding: 6px
- Border Radius: `nova/radii/component/button`

#### Actions Container (When showActions=true)
- Gap: `nova/spacing/tight`

---

### Modal Variant (Variant=Modal)
- Width: 720px
- Header Height: 56px
- Content Min Height: 80px

### Dialog Variant (Variant=Dialog)
- Width: 288px
- Header Height: 60px
- Content Min Height: 80px

---

### Content Area

#### Padding=On
- Padding: `nova/spacing/near` (all sides)

#### Padding=Off
- (No padding - content extends to edges)

---

### Footer (When showFooter=true)
- (Fixed at bottom, properties implementation-specific)

---

## 12. Title Bar / Page Title Component

### Base (All Variants)
- Layout: Horizontal flex row
- Full width

---

### Title Text (All Mobile Variants)
- Typography: `nova/typography/heading/1`
- Font Size: 24px
- Foreground: `nova/color/typography/base`
- Overflow: Ellipsis
- Text: Nowrap

### Subtitle Text (When showSubtitle=true)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`
- Height: 23px
- Width: 84px (fixed for Desktop)
- Overflow: Ellipsis
- Text: Nowrap

---

### Context Section

#### Mobile=off (Desktop)
- Layout: Horizontal flex
- Gap: `nova/spacing/tight`
- Min Width: 343px
- Items Align: End (bottom)

#### Mobile=on
- Layout: Horizontal flex with wrap
- Gap: `nova/spacing/tight`
- Flex Basis: 0
- Flex Grow: 1
- Items Align: End (bottom)

---

### Actions Section (When showTitleBarAction=true)

#### Mobile=off
- (Positioned to right of context)

#### Mobile=on
- Gap from Context: `nova/spacing/next`

---

### Actions Slot Wrapper
- Padding Horizontal: `nova/spacing/near`
- Padding Vertical: `nova/spacing/tight`
- Gap: 10px

---

## 13. Title Bar / Section Title Component

### Base (All Variants)
- Variant: Wide (full width)
- Layout: Horizontal flex row

---

### SH1 Hierarchy

#### Title Text
- Typography: `nova/typography/heading/3`
- Font Size: 18px
- Foreground: `nova/color/typography/base`
- Min Height: 28px
- Overflow: Ellipsis
- Text: Nowrap

#### Subtitle Text (When showSubtitle=true)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`
- Overflow: Ellipsis
- Text: Nowrap

#### Title Wrapper
- Layout: Horizontal flex
- Gap: `nova/spacing/tight`
- Min Height: 28px
- Items Align: End (bottom)

#### Subtitle Container
- Padding Bottom: 3px (baseline alignment)

---

### SH2 Hierarchy

#### Title Text
- Typography: `nova/typography/body/strong`
- Font Size: 16px
- Foreground: `nova/color/typography/base`
- Min Height: 16px
- Overflow: Ellipsis
- Text: Nowrap

#### Subtitle Text (When showSubtitle=true)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`
- Min Height: 16px
- Overflow: Ellipsis
- Text: Nowrap

#### Title and Subtitle Container
- Layout: Horizontal flex with wrap
- Gap: `nova/spacing/tight`
- Items Align: End (bottom)

---

### SH3 Hierarchy

#### Title Text
- Typography: `nova/typography/body/strong`
- Font Size: 16px
- Foreground: `nova/color/typography/base`
- Overflow: Ellipsis
- Text: Nowrap

#### Subtitle Text (When showSubtitle=true)
- Typography: `nova/typography/base/regular`
- Font Size: `global/typography/fontsize/14`
- Foreground: `nova/color/typography/muted`
- Min Height: 16px
- Overflow: Ellipsis

#### Mobile=off
- Layout: Horizontal flex with wrap
- Gap: `nova/spacing/next`
- Items Align: End (bottom)

#### Mobile=on
- Layout: Vertical flex column
- Gap: `nova/spacing/next`
- Max Width: 260px
- Items Align: Start

#### Decorative Line
- Height: 1px
- Color: `nova/surfaces/color/workspace border`
- Full width (grows to fill)

---

### Buttons Container (All Hierarchies)
- Layout: Horizontal flex
- Gap: `nova/spacing/next`

---

## Notes

- **Base Section:** Contains properties shared across all variants and sizes
- **Size Variants:** Listed immediately after Base, only showing size-specific properties
- **States:** Only changed properties listed; all others inherited from Default or Base
- **Optional Features:** Listed separately when not part of all variants
- **Token Format:** All design tokens listed with their full path (e.g., `nova/spacing/tight`)
- **Fixed Values:** Properties without tokens show raw values (e.g., 28px, 6px)
- **Hierarchy Levels:** SH1 (largest/primary), SH2 (medium/secondary), SH3 (compact/tertiary with decorative line)

---


