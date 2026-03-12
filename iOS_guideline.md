#Design System Guidelines

Rules for how the AI should make generations look like our company's iOS 26 design system. Always utilize the established design tokens, CSS variables, and components to maintain visual consistency and a native iOS feel.

## General Guidelines

- **Source of Truth (`/src/styles/theme.css`)**: Never hardcode colors, fonts, or typography sizes. Always retrieve these values directly from the CSS variables defined in the `/src/styles/theme.css` file. This ensures the design system remains a maintainable, single source of truth.
- **Typography**: Strictly follow `/src/styles/theme.css` for all typography styling. The primary font family ('Libre Franklin') is applied globally in the CSS base layer. All text sizing must use the corresponding CSS variables (e.g., `var(--text-base)` for default text/buttons/inputs, and `var(--text-h1)` to `var(--text-h4)` for headers). Line height is consistently `1.5`.
- **Colors**: All background, text, border, and state colors must be referenced using their CSS variables (e.g., `var(--primary)`, `var(--card)`, `var(--background)`). Do not use raw hex or rgba values in the component markup.
- **Fluid Interfaces & Direct Manipulation**: iOS 26 components should feel immediately responsive. Elements must track with user gestures (e.g., swipe to close) and maintain continuous velocity.
- **Materials & Depth**: Rely heavily on iOS translucent materials and background blurs (`backdrop-filter: blur(25px)`) for floating elements, tab bars, and sticky headers.
- **Animations**:
  - Micro-interactions (hovers, focus): `150ms ease-in-out`.
  - State changes/Toggles: `250ms ease-out`.
  - Spatial transitions (sheets, modals): `300ms - 400ms cubic-bezier(0.25, 1, 0.5, 1)`.
- **Logo**: Use the `/src/lib/images/logo.svg` as the application logo.

---

## 1. Materials & Layout

### 1.1 iOS Liquid Glass Effect

A highly specific translucent material used for sticky navigation, floating bars, and contextual overlays.

- **Backdrop Blur**: Always apply `backdrop-filter: blur(25px)`.
- **Background Stack** (Bottom to Top):
  1. Base layer: Dark tint with `mix-blend-mode: color-dodge`.
  2. Mid layer: `rgba(255, 255, 255, 0.50)` with `mix-blend-mode: normal`.
  3. Top layer: `var(--popover)` with `mix-blend-mode: linear-burn`.
- **Usage**: Tab bars, contextual menus, and sticky headers upon scroll.

### 1.2 Base Card Component

The fundamental container for grouping related content.

- **Visual Style**: Background is `var(--card)`. Border radius is `var(--radius-card)`. Applies `var(--elevation-sm)` shadow.
- **Padding**: Always apply a standard inner padding of `16px` on all sides.
- **Title Placement**: Card titles must be placed **inside** the card container, typically aligned to the top-left using `var(--text-h4)`.
- **Usage**: The middle content area acts as a "Swap Instance" slot for lists, forms, or summaries.

### 1.3 Full Screen Sheet (Mobile Modal)

- **Behavior**: The originating background screen scales down to `0.95`, its top corners round out, and a dark overlay fades in. The modal sheet slides up from the bottom edge.
- **Anatomy**: Contains a small grey pill "grabber" handle at the top center, top-left/right text actions ("Cancel", "Done"), and a centered title.

### 1.4 Separators & Placeholders

# 🍏 Segmented Control

🍏 Segmented Control is a component set component measuring 365×228px.

## Overview

Use this component when you need a **🍏 Segmented Control** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Segmented Control`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Variants

- **segments=2 segments**: segments=2 segments
- **segments=3 segments**: segments=3 segments
- **segments=4 segments**: segments=4 segments
- **segments=5 segments**: segments=5 segments

## Props

### segments

- **Type**: `VARIANT`
- **Default**: `2 segments`
- **Options**: `2 segments`, `3 segments`, `4 segments`, `5 segments`

## Layout

- **Direction**: vertical
- **Gap**: 20px
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: auto
- **Vertical sizing**: auto

## Dimensions

- **Width**: 365px
- **Height**: 228px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "20px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Segmented Control (365×228px)
  ◈ segments=2 segments (325×32px)
    ◇ Segment 1 (161×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (161×28px)
      T Title (145×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=3 segments (325×32px)
    ◇ Segment 1 (108×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (108×28px)
      T Title (92×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (108×28px)
      T Title (92×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=4 segments (325×32px)
    ◇ Segment 1 (81×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 4 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=5 segments (325×32px)
    ◇ Segment 1 (65×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 4 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 5 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

- **Swap Instance**: Dashed outline using `var(--primary)`, diagonal striped background, text "Swap this instance". Used only in templates.

---

## 2. Headers & Hierarchy

### 2.1 Page Header (Large Title to Inline)

# 🍏 Tab Header

🍏 Tab Header is a component component measuring 375×166px.

## Overview

Use this component when you need a **🍏 Tab Header** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Tab Header`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Props

### has trailing 3

- **Type**: `BOOLEAN`
- **Default**: `true`

### has trailing 2

- **Type**: `BOOLEAN`
- **Default**: `false`

### has trailing 1

- **Type**: `BOOLEAN`
- **Default**: `false`

### has tabs

- **Type**: `BOOLEAN`
- **Default**: `true`

## Layout

- **Direction**: vertical
- **Gap**: 0px
- **Padding**: top 0px · right 0px · bottom 0px · left 0px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: auto
- **Vertical sizing**: fixed

## Dimensions

- **Width**: 375px
- **Height**: 166px

### Border Radius

- All corners: `0px`

## Typography

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Title

Sample text: *"Title"*

- **Font**: Libre Franklin SemiBold
- **Size**: `16px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Subtitle

Sample text: *"Subtitle"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "border-radius": "0px",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "16px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/subtitle/font-family": "Libre Franklin",
  "typography/subtitle/font-size": "13px",
  "typography/subtitle/font-weight": "Regular",
  "typography/subtitle/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "15px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "15px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "15px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈ 🍏 Tab Header (375×166px)
  ▣ Main (375×166px)
    ◇ 🍏 Status Bar (375×54px)
      ▣ Time (135×54px)
        T Time (37×12px) "9:41"
      ▬ Dynamic Island (120×37px)
      ▣ Levels (135×54px)
        ▣ Indicators (77×13px)
          ▣ Signal (20×12px)
          ▣ Connection (17×13px)
          ▣ Battery (27×13px)
    ▣ Toolbar (375×56px)
      ▣ Leading (188×56px)
        ◇ Leading (116×40px)
          ◇ 🍏 Avatar (40×40px)
          ▣ Text (48×35px)
      ▣ Trailing (188×56px)
        ◇ Trailing Action 1 (44×44px) [hidden]
          ◇ _🍏 Tab Header / Button (24×24px)
        ◇ Trailing Action 2 (44×44px) [hidden]
          ◇ _🍏 Tab Header / Button (24×24px)
        ◇ Trailing Action 3 (44×44px)
          ◇ _🍏 Tab Header / Button (24×24px)
    ◇ 🍏 Tab Header Tabs (375×56px)
      ◇ _🍏 Tab Header Tab 1 (56×32px)
        T Title (40×18px) "Label"
      ◇ _🍏 Tab Header Tab 2 (55×32px)
        T Title (39×18px) "Label"
      ◇ _🍏 Tab Header Tab 3 (55×32px)
        T Title (39×18px) "Label"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

### 2.2 Section / Card Headers

- **Anatomy**: Title (bold) with an optional Subtitle (`var(--muted-foreground)`) below it.
- **Trailing Actions**: Supports right-aligned trailing elements:
  1.  **More Menu**: Horizontal three-dot icon (`•••`).
  2.  **Status Badge**: A semantic colored pill (e.g., `var(--success-subtle)`).
  3.  **Action Link**: Prominent text link in `var(--primary)`.

### 2.3 Copyable Account Header

- **Usage**: Used at the top of account details screens.
- **Anatomy**: Muted "Account name" label -> Large Bold Account Title -> Trailing copy icon colored with `var(--primary)`.

---

## 3. Actions & Buttons

### 3.1 Buttons

Always use `var(--radius-button)` to create the standard iOS pill shape. Supports Default, Hover, Pressed, Loading (spinner), and Disabled states.

# Button Component

Default buttons are heavily used interactive elements for user actions across the application. They support multiple configurations, sizes, themes, and states.

- **Button General**: Includes a slight scale-down animation on press (`transform: scale(0.96)`). Hover uses `var(--primary-hover)`. Pressed uses `var(--primary-pressed)`.

## Typography

- **Font Family**: `var(--font-family)` ("Libre Franklin")
- **Font Size**: `--text-base` (17px)
- **Font Weight**: `--font-weight-regular` (400)
- **Line Height**: 1.5

## Styles

### Primary

- **Background**: `--primary` (#295eff)
- **Foreground**: `--primary-foreground` (#ffffff)
- **Hover**: `--primary-hover` (#2049c6)
- **Pressed**: `--primary-pressed` (#152f80)

### Secondary

- **Background**: `--secondary` (transparent) / `--accent` (#dee2ff)
- **Foreground**: `--secondary-foreground` (#295eff)
- **Hover**: `--secondary-hover` (#dee2ff)

### Tertiary

- **Background**: Transparent
- **Foreground**: `--foreground` (#061223)
- **Hover**: `--muted-hover` or transparent with opacity shift

### Success

- **Background**: `--success` (#0e813e)
- **Foreground**: `--primary-foreground` (#ffffff)
- **Hover**: Darker shade of success color

### Danger

- **Background**: `--destructive` (#bf2310)
- **Foreground**: `--destructive-foreground` (#ffffff)
- **Hover**: Darker shade of destructive color

## Configurations

- **Icons**: Left (leading) and right (trailing) icons can be toggled on or hidden independently.
- **Sizes**:
  - **Medium**: Standard default size for most UI elements.
  - **Small**: Compact size for denser layouts.
- **Themes**: Fully supports Light and Dark modes via dynamic CSS variables.

## States

- **Default**: The standard, resting appearance of the button.
- **Hover**: Triggered on mouse hover; background darkens or shifts to the hover token.
- **Active**: Triggered on click/press; utilizes the pressed color tokens for high contrast.
- **Loading**: Replaces icons/text with a centered or inline spinner icon to indicate background processing.
- **Disabled**: Non-interactive state utilizing `--muted` (#ccd5df) for the background and `--muted-foreground` (#7189a7) for text/icons.

## Specifications

- **Corner Radius**: `--radius-button` (99px / Pill)

### # 🍏 Icon Button

🍏 Icon Button is a component set component measuring 384×248px.

## Overview

Use this component when you need a **🍏 Icon Button** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Icon Button`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **style=primary, state=default**: style=primary, state=default
- **style=primary, state=pressed**: style=primary, state=pressed
- **style=primary, state=loading**: style=primary, state=loading
- **style=primary, state=disabled**: style=primary, state=disabled
- **style=danger, state=default**: style=danger, state=default
- **style=danger, state=pressed**: style=danger, state=pressed
- **style=danger, state=loading**: style=danger, state=loading
- **style=danger, state=disabled**: style=danger, state=disabled

## Props

### title

- **Type**: `TEXT`
- **Default**: `Button`

### icon

- **Type**: `INSTANCE_SWAP`
- **Default**: `41781:10703`

### style

- **Type**: `VARIANT`
- **Default**: `primary`
- **Options**: `primary`, `danger`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `pressed`, `loading`, `disabled`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 384px
- **Height**: 248px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#7189A7`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#BF2310`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#BF2310`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#BF2310`

### Label

Sample text: *"Button"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#7189A7`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Icon Button (384×248px)
  ◈ style=primary, state=default (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=primary, state=pressed (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=primary, state=loading (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ 🍏 Activity Indicator (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=primary, state=disabled (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=danger, state=default (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=danger, state=pressed (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=danger, state=loading (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ 🍏 Activity Indicator (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
  ◈ style=danger, state=disabled (56×84px)
    ▣ Button (56×56px)
      ○ Icon Container (24×24px)
        ○ Icon (24×24px)
          ◇ swap_vert (24×24px)
        ▬ Color (24×24px)
    T Label (56×18px) "Button"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---


### 3.3 Text Links

# 🍏 Link

🍏 Link is a component set component measuring 288×552px.

## Overview

Use this component when you need a **🍏 Link** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Link`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, on color=false**: state=default, on color=false
- **state=pressed, on color=false**: state=pressed, on color=false
- **state=loading, on color=false**: state=loading, on color=false
- **state=disabled, on color=false**: state=disabled, on color=false
- **state=default, on color=true**: state=default, on color=true
- **state=pressed, on color=true**: state=pressed, on color=true
- **state=loading, on color=true**: state=loading, on color=true
- **state=disabled, on color=true**: state=disabled, on color=true

## Props

### icon

- **Type**: `INSTANCE_SWAP`
- **Default**: `41781:10477`

### title

- **Type**: `TEXT`
- **Default**: `Text link`

### has icon

- **Type**: `BOOLEAN`
- **Default**: `true`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `pressed`, `loading`, `disabled`

### on color

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `false`, `true`

## Layout

- **Direction**: vertical
- **Gap**: 40px
- **Padding**: top 40px · right 100px · bottom 40px · left 100px
- **Primary axis alignment**: center
- **Counter axis alignment**: center
- **Horizontal sizing**: auto
- **Vertical sizing**: auto

## Dimensions

- **Width**: 288px
- **Height**: 552px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#152F80`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#152F80`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Label

Sample text: *"Text link"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "40px 100px 40px 100px",
  "border-radius": "5px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "15px",
  "typography/label/font-weight": "SemiBold",
  "typography/label/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Link (288×552px)
  ◈ state=default, on color=false (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
  ◈ state=pressed, on color=false (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      ▣ Text (60×20px)
        T Label (60×18px) "Text link"
  ◈ state=loading, on color=false (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
    ◇ 🍏 Activity Indicator (24×24px)
      ○ Spinning Icon (24×24px)
        ▬ 325 (3×8px)
        ▬ 270 (3×8px)
        ▬ 225 (3×8px)
        ▬ 180 (3×8px)
        ▬ 135 (3×8px)
        ▬ 90 (3×8px)
        ▬ 45 (3×8px)
        ▬ 0 (3×8px)
  ◈ state=disabled, on color=false (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
  ◈ state=default, on color=true (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
  ◈ state=pressed, on color=true (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      ▣ Text (60×20px)
        T Label (60×18px) "Text link"
  ◈ state=loading, on color=true (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
    ◇ 🍏 Activity Indicator (24×24px)
      ○ Spinning Icon (24×24px)
        ▬ 325 (3×8px)
        ▬ 270 (3×8px)
        ▬ 225 (3×8px)
        ▬ 180 (3×8px)
        ▬ 135 (3×8px)
        ▬ 90 (3×8px)
        ▬ 45 (3×8px)
        ▬ 0 (3×8px)
  ◈ state=disabled, on color=true (88×24px)
    ▣ Content (88×24px)
      ◇ open_in_new (24×24px)
        ✦ Vector (18×18px)
      T Label (60×18px) "Text link"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

## 4. Form Inputs & Data Entry

Inputs mirror iOS grouped list styles.

- **Structure**: Top label (bold), optional secondary label, input container (`var(--radius)` radius, `var(--input-background)`, `var(--border)` outline), and bottom helper/error text.
- **States**:
  - **Default**: `var(--border)` outline.
  - **Focus**: Border turns `var(--ring)` with a subtle glow.
  - **Error**: Border and text turn `var(--destructive)`. Trailing red `!` icon appears.
  - **Disabled**: Background becomes `var(--muted)`.

### Specific Input Types

# 🍏 Search Bar / Standalone

🍏 Search Bar / Standalone is a component set component measuring 383×468px.

## Overview

Use this component when you need a **🍏 Search Bar / Standalone** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Search Bar / Standalone`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=idle, on color=false**: state=idle, on color=false
- **state=focus, on color=false**: state=focus, on color=false
- **state=typing, on color=false**: state=typing, on color=false
- **state=filled, on color=false**: state=filled, on color=false
- **state=idle, on color=true**: state=idle, on color=true
- **state=focus, on color=true**: state=focus, on color=true
- **state=typing, on color=true**: state=typing, on color=true
- **state=filled, on color=true**: state=filled, on color=true

## Props

### text

- **Type**: `TEXT`
- **Default**: `Text`

### placeholder

- **Type**: `TEXT`
- **Default**: `Search`

### has clear

- **Type**: `BOOLEAN`
- **Default**: `true`

### state

- **Type**: `VARIANT`
- **Default**: `idle`
- **Options**: `focus`, `typing`, `filled`, `idle`

### on color

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `false`, `true`

## Layout

- **Direction**: vertical
- **Gap**: 20px
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: auto
- **Vertical sizing**: auto

## Dimensions

- **Width**: 383px
- **Height**: 468px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Text

Sample text: *"Text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Text

Sample text: *"Text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Text

Sample text: *"Text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Text

Sample text: *"Text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Cancel

Sample text: *"Cancel"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "20px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/cancel/font-family": "Libre Franklin",
  "typography/cancel/font-size": "17px",
  "typography/cancel/font-weight": "Regular",
  "typography/cancel/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Search Bar / Standalone (383×468px)
  ◈ state=idle, on color=false (343×36px)
    ▣ Field (343×36px)
      ▣ Icon (16×16px)
        ✦ Icon (16×16px)
      ▣ Value (297×22px)
        T Placeholder (56×21px) "Search"
  ◈ state=focus, on color=false (343×36px)
    ▣ Container (343×36px)
      ▣ Field (276×36px)
        ▣ Icon (16×16px)
          ✦ Icon (16×16px)
        ▣ Value (230×22px)
          T Placeholder (56×21px) "Search"
          ◇ 🍏 Cursor (2×20px)
      ▣ Button (55×36px)
        T Cancel (55×21px) "Cancel"
  ◈ state=typing, on color=false (343×36px)
    ▣ Field (276×36px)
      ▣ Icon (16×16px)
        ✦ Icon (16×16px)
      ▣ Value (204×22px)
        T Text (35×21px) "Text"
        ◇ 🍏 Cursor (2×22px)
          ▬ Pipe (2×20px)
      ✦ xmark.circle.fill (16×16px)
    ▣ Button (55×36px)
      T Cancel (55×21px) "Cancel"
  ◈ state=filled, on color=false (343×36px)
    ▣ Field (276×36px)
      ▣ Icon (16×16px)
        ✦ Icon (16×16px)
      ▣ Value (204×22px)
        T Text (35×21px) "Text"
      ✦ xmark.circle.fill (16×16px)
    ▣ Button (55×36px)
      T Cancel (55×21px) "Cancel"
  ◈ state=idle, on color=true (343×36px)
    ▣ Field (343×36px)
      ▣ Icon (16×16px)
        ✦ Icon (16×16px)
      ▣ Value (297×22px)
        T Placeholder (56×21px) "Search"
      ▬ Background (343×36px)
  ◈ state=focus, on color=true (343×36px)
    ▣ Container (276×36px)
      ▣ Field (276×36px)
        ▣ Icon (16×16px)
          ✦ Icon (16×16px)
        ▣ Value (230×22px)
          T Placeholder (56×21px) "Search"
          ◇ 🍏 Cursor (2×20px)
        ▬ Background (276×36px)
    ▣ Button (55×36px)
      T Cancel (55×21px) "Cancel"
  ◈ state=typing, on color=true (343×36px)
    ▣ Container (276×36px)
      ▣ Field (276×36px)
        ▣ Icon (16×16px)
          ✦ Icon (16×16px)
        ▣ Value (204×22px)
          T Text (35×21px) "Text"
          ◇ 🍏 Cursor (2×20px)
        ✦ xmark.circle.fill (16×16px)
        ▬ Background (276×36px)
    ▣ Button (55×36px)
      T Cancel (55×21px) "Cancel"
  ◈ state=filled, on color=true (343×36px)
    ▣ Container (276×36px)
      ▣ Field (276×36px)
        ▣ Icon (16×16px)
          ✦ Icon (16×16px)
        ▣ Value (204×22px)
          T Text (35×21px) "Text"
        ✦ xmark.circle.fill (16×16px)
        ▬ Background (276×36px)
    ▣ Button (55×36px)
      T Cancel (55×21px) "Cancel"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Text Area

🍏 Text Area is a component set component measuring 766×1087px.

## Overview

Use this component when you need a **🍏 Text Area** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Text Area`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, filled=false**: state=default, filled=false
- **state=default, filled=true**: state=default, filled=true
- **state=focus, filled=false**: state=focus, filled=false
- **state=focus, filled=true**: state=focus, filled=true
- **state=error, filled=false**: state=error, filled=false
- **state=error, filled=true**: state=error, filled=true
- **state=read-only, filled=false**: state=read-only, filled=false
- **state=read-only, filled=true**: state=read-only, filled=true
- **state=disabled, filled=false**: state=disabled, filled=false
- **state=disabled, filled=true**: state=disabled, filled=true

## Props

### placeholder

- **Type**: `TEXT`
- **Default**: `Enter text`

### value

- **Type**: `TEXT`
- **Default**: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore.`

### is editing

- **Type**: `BOOLEAN`
- **Default**: `false`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `true`

### has limit

- **Type**: `BOOLEAN`
- **Default**: `true`

### has sublabel

- **Type**: `BOOLEAN`
- **Default**: `true`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### has placeholder

- **Type**: `BOOLEAN`
- **Default**: `true`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focus`, `error`, `read-only`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `true`, `false`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 16px · right 20px · bottom 16px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: fixed

## Dimensions

- **Width**: 766px
- **Height**: 1087px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder height

Sample text: *" "*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left

### Placeholder

Sample text: *"Enter text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder text

Sample text: *" "*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder text

Sample text: *"Enter text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter text"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Current Count

Sample text: *"0"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Max Limit

Sample text: *"500"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "16px 20px 16px 20px",
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder-height/font-family": "Libre Franklin",
  "typography/placeholder-height/font-size": "17px",
  "typography/placeholder-height/font-weight": "Regular",
  "typography/placeholder-height/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder-text/font-family": "Libre Franklin",
  "typography/placeholder-text/font-size": "17px",
  "typography/placeholder-text/font-weight": "Regular",
  "typography/placeholder-text/line-height": "auto",
  "typography/placeholder-text/font-family": "Libre Franklin",
  "typography/placeholder-text/font-size": "17px",
  "typography/placeholder-text/font-weight": "Regular",
  "typography/placeholder-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/current-count/font-family": "Libre Franklin",
  "typography/current-count/font-size": "15px",
  "typography/current-count/font-weight": "Regular",
  "typography/current-count/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "15px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/max-limit/font-family": "Libre Franklin",
  "typography/max-limit/font-size": "15px",
  "typography/max-limit/font-weight": "Regular",
  "typography/max-limit/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Text Area (766×1087px)
  ◈ state=default, filled=false (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Placeholder (311×21px) "Enter text"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=default, filled=true (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Value (311×104px) "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=focus, filled=false (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        ▣ Cursor position (2×21px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder height (0×21px) " "
        T Placeholder (311×21px) "Enter text"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=focus, filled=true (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (287×120px)
        T Value (271×104px) "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
      ◇ Clear Button (56×24px)
        ◇ cancel (rounded) (24×24px)
          ✦ Vector (20×20px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=error, filled=false (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        ▣ Typing area (287×104px)
          ▣ Cursor position (2×21px) [hidden]
          T Placeholder text (279×21px) "Enter text"
        ◇ error (24×24px)
          ✦ Vector (20×20px)
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ─ { empty spacing } (263×0px)
        ◇ Error Label (263×30px)
          T Text (263×18px) "Error text"
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=error, filled=true (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Value (271×104px) "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"
        ◇ error (24×24px)
          ✦ Vector (20×20px)
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ─ { empty spacing } (263×0px)
        ◇ Error Label (263×30px)
          T Text (263×18px) "Error text"
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=read-only, filled=false (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Placeholder (311×21px) "Enter text"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=read-only, filled=true (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Value (311×104px) "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=disabled, filled=false (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Placeholder (311×21px) "Enter text"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
  ◈ state=disabled, filled=true (343×179px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×120px)
      ▣ Content area (343×120px)
        T Value (311×104px) "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed"
      ○ Height (0×120px)
        ◇ Text View Height (0×120px)
          ✦ { height } (120×0px)
    ▣ Bottom labels (343×30px)
      ▣ Leading labels (263×30px)
        ◇ Helper Label (263×30px)
          T Text (263×18px) "Helper text"
        ─ { empty spacing } (263×0px)
      ─ { empty spacing } (32×0px)
      ◇ Character Limit Label (48×26px)
        T Current Count (11×18px) "0"
        T Separator (6×18px) "/"
        T Max Limit (31×18px) "500"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Input Phone

🍏 Input Phone is a component set component measuring 766×715px.

## Overview

Use this component when you need a **🍏 Input Phone** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Input Phone`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, filled=false**: state=default, filled=false
- **state=default, filled=true**: state=default, filled=true
- **state=focus, filled=false**: state=focus, filled=false
- **state=focus, filled=true**: state=focus, filled=true
- **state=error, filled=false**: state=error, filled=false
- **state=error, filled=true**: state=error, filled=true
- **state=read-only, filled=false**: state=read-only, filled=false
- **state=read-only, filled=true**: state=read-only, filled=true
- **state=disabled, filled=false**: state=disabled, filled=false
- **state=disabled, filled=true**: state=disabled, filled=true

## Props

### is editing

- **Type**: `BOOLEAN`
- **Default**: `false`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `true`

### has sublabel

- **Type**: `BOOLEAN`
- **Default**: `true`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### value

- **Type**: `TEXT`
- **Default**: `987 998 889`

### has placeholder

- **Type**: `BOOLEAN`
- **Default**: `true`

### placeholder

- **Type**: `TEXT`
- **Default**: `Enter phone number`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focus`, `error`, `read-only`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `true`, `false`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 766px
- **Height**: 715px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Input Phone (766×715px)
  ◈ state=default, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=default, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (159×21px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (119×21px)
          T Value Text (108×21px) "987 998 889"
          ◇ 🍏 Cursor (2×20px)
        ◇ Clear Button (56×24px)
          ◇ cancel (rounded) (24×24px)
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=error, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (127×21px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (optional) (127×21px) "Enter phone number"
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=error, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (127×21px)
          T Value Text (108×21px) "987 998 889"
          ◇ 🍏 Cursor (2×20px) [hidden]
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=read-only, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=read-only, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Input Phone

🍏 Input Phone is a component set component measuring 766×715px.

## Overview

Use this component when you need a **🍏 Input Phone** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Input Phone`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, filled=false**: state=default, filled=false
- **state=default, filled=true**: state=default, filled=true
- **state=focus, filled=false**: state=focus, filled=false
- **state=focus, filled=true**: state=focus, filled=true
- **state=error, filled=false**: state=error, filled=false
- **state=error, filled=true**: state=error, filled=true
- **state=read-only, filled=false**: state=read-only, filled=false
- **state=read-only, filled=true**: state=read-only, filled=true
- **state=disabled, filled=false**: state=disabled, filled=false
- **state=disabled, filled=true**: state=disabled, filled=true

## Props

### is editing

- **Type**: `BOOLEAN`
- **Default**: `false`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `true`

### has sublabel

- **Type**: `BOOLEAN`
- **Default**: `true`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### value

- **Type**: `TEXT`
- **Default**: `987 998 889`

### has placeholder

- **Type**: `BOOLEAN`
- **Default**: `true`

### placeholder

- **Type**: `TEXT`
- **Default**: `Enter phone number`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focus`, `error`, `read-only`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `true`, `false`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 766px
- **Height**: 715px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder (optional)

Sample text: *"Enter phone number"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"+1"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value Text

Sample text: *"987 998 889"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/placeholder--optional-/font-family": "Libre Franklin",
  "typography/placeholder--optional-/font-size": "17px",
  "typography/placeholder--optional-/font-weight": "Regular",
  "typography/placeholder--optional-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/value-text/font-family": "Libre Franklin",
  "typography/value-text/font-size": "17px",
  "typography/value-text/font-weight": "Regular",
  "typography/value-text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Input Phone (766×715px)
  ◈ state=default, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=default, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (159×21px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (119×21px)
          T Value Text (108×21px) "987 998 889"
          ◇ 🍏 Cursor (2×20px)
        ◇ Clear Button (56×24px)
          ◇ cancel (rounded) (24×24px)
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=error, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (127×21px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (optional) (127×21px) "Enter phone number"
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=error, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        ▣ Typing area (127×21px)
          T Value Text (108×21px) "987 998 889"
          ◇ 🍏 Cursor (2×20px) [hidden]
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=read-only, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=read-only, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=false (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Placeholder (optional) (159×21px) "Enter phone number"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=true (343×103px)
    ▣ Title Labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ○ { conditional spacing @ 4px } (5×0px)
        ─ { 3px } (3×0px)
        ─ { 1px } (1×0px)
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Fields (343×44px)
      ◇ Country Select (144×44px)
        ◇ 🍏 Leading Image (56×20px)
          ○ Image (28×20px)
        ▣ Value area (48×21px)
          T Value Text (18×21px) "+1"
        ◇ arrow_drop_down (24×24px)
          ✦ Vector (10×5px)
      ▣ Number field (191×44px)
        T Value Text (159×21px) "987 998 889"
    ◇ Helper Label (343×30px)
      T Text (343×18px) "Helper text"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Input Password

🍏 Input Password is a component set component measuring 766×572px.

## Overview

Use this component when you need a **🍏 Input Password** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Input Password`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, filled=false**: state=default, filled=false
- **state=default, filled=true**: state=default, filled=true
- **state=focus, filled=false**: state=focus, filled=false
- **state=focus, filled=true**: state=focus, filled=true
- **state=error, filled=false**: state=error, filled=false
- **state=error, filled=true**: state=error, filled=true
- **state=disabled, filled=false**: state=disabled, filled=false
- **state=disabled, filled=true**: state=disabled, filled=true

## Props

### placeholder

- **Type**: `TEXT`
- **Default**: `Enter your password`

### value

- **Type**: `TEXT`
- **Default**: `Str0ng@P4ssw0rd`

### is editing

- **Type**: `BOOLEAN`
- **Default**: `false`

### hidden

- **Type**: `BOOLEAN`
- **Default**: `true`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `true`

### has icon

- **Type**: `BOOLEAN`
- **Default**: `true`

### has sublabel

- **Type**: `BOOLEAN`
- **Default**: `true`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### has placeholder

- **Type**: `BOOLEAN`
- **Default**: `true`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focus`, `error`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `false`, `true`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 766px
- **Height**: 572px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter your password"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Str0ng@P4ssw0rd"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Mask

Sample text: *"••••••••••••••••••••••••••••••••••••••••••••••••••••••••••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter your password"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Str0ng@P4ssw0rd"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Mask

Sample text: *"••••••••••••••••••••••••••••••••••••••••••••••••••••••••••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter your password"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Str0ng@P4ssw0rd"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Mask

Sample text: *"••••••••••••••••••••••••••••••••••••••••••••••••••••••••••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Enter your password"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Value

Sample text: *"Str0ng@P4ssw0rd"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Mask

Sample text: *"••••••••••••••••••••••••••••••••••••••••••••••••••••••••••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/mask/font-family": "Libre Franklin",
  "typography/mask/font-size": "17px",
  "typography/mask/font-weight": "Regular",
  "typography/mask/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/mask/font-family": "Libre Franklin",
  "typography/mask/font-size": "17px",
  "typography/mask/font-weight": "Regular",
  "typography/mask/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/mask/font-family": "Libre Franklin",
  "typography/mask/font-size": "17px",
  "typography/mask/font-weight": "Regular",
  "typography/mask/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "17px",
  "typography/value/font-weight": "Regular",
  "typography/value/line-height": "auto",
  "typography/mask/font-family": "Libre Franklin",
  "typography/mask/font-size": "17px",
  "typography/mask/font-weight": "Regular",
  "typography/mask/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Input Password (766×572px)
  ◈ state=default, filled=false (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Value area (231×21px)
        T Placeholder (231×21px) "Enter your password"
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
  ◈ state=default, filled=true (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Value area (231×21px)
        ▣ Value Masking (152×21px)
          ▣ Unmasked Value (152×21px)
          ◇ 🍏 Password Mask (152×21px)
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
  ◈ state=focus, filled=false (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Typing area (231×21px)
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
        T Placeholder (215×21px) "Enter your password"
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
  ◈ state=focus, filled=true (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Typing area (231×21px)
        ▣ Value Masking (152×21px)
          ▣ Unmasked Value (152×21px)
          ◇ 🍏 Password Mask (152×21px)
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
  ◈ state=error, filled=false (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Typing area (247×21px)
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
        T Placeholder (231×21px) "Enter your password"
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ▣ Footer Labels (343×30px)
      ─ { empty spacing } (343×0px)
      ◇ Error Label (343×30px)
        T Text (343×18px) "Error text"
  ◈ state=error, filled=true (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Typing area (247×21px)
        ▣ Value Masking (152×21px)
          ▣ Unmasked Value (152×21px)
          ◇ 🍏 Password Mask (152×21px)
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ▣ Footer Labels (343×30px)
      ─ { empty spacing } (343×0px)
      ◇ Error Label (343×30px)
        T Text (343×18px) "Error text"
  ◈ state=disabled, filled=false (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Value area (231×21px)
        T Placeholder (231×21px) "Enter your password"
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
  ◈ state=disabled, filled=true (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ▣ Value area (231×21px)
        ▣ Value Masking (152×21px)
          ▣ Unmasked Value (152×21px)
          ◇ 🍏 Password Mask (152×21px)
      ○ Trailing Button (56×24px)
        ○ Off (56×24px)
          ▬ { hide toggle } (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
        ○ On (56×24px)
          ◇ 🍏 Password Toggle (56×24px)
    ▣ Footer Labels (343×30px)
      ◇ Helper Label (343×30px)
        T Text (343×18px) "Helper text"
      ─ { empty spacing } (343×0px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Input Date

🍏 Input Date is a component set component measuring 766×595px.

## Overview

Use this component when you need a **🍏 Input Date** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Input Date`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **state=default, filled=false**: state=default, filled=false
- **state=default, filled=true**: state=default, filled=true
- **state=focus, filled=false**: state=focus, filled=false
- **state=focus, filled=true**: state=focus, filled=true
- **state=error, filled=false**: state=error, filled=false
- **state=error, filled=true**: state=error, filled=true
- **state=read-only, filled=false**: state=read-only, filled=false
- **state=read-only, filled=true**: state=read-only, filled=true
- **state=disabled, filled=false**: state=disabled, filled=false
- **state=disabled, filled=true**: state=disabled, filled=true

## Props

### placeholder

- **Type**: `TEXT`
- **Default**: `Select date`

### has icon

- **Type**: `BOOLEAN`
- **Default**: `true`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `false`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### has sublabel

- **Type**: `BOOLEAN`
- **Default**: `true`

### has placeholder

- **Type**: `BOOLEAN`
- **Default**: `true`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focus`, `error`, `read-only`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `true`, `false`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 766px
- **Height**: 595px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Select date"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Month

Sample text: *"12"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Day

Sample text: *"24"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Year

Sample text: *"2023"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Select date"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Month

Sample text: *"12"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Day

Sample text: *"24"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Year

Sample text: *"2023"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Select date"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Month

Sample text: *"12"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Day

Sample text: *"24"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Year

Sample text: *"2023"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Select date"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Month

Sample text: *"12"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Day

Sample text: *"24"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Year

Sample text: *"2023"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Placeholder

Sample text: *"Select date"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"(optional)"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Month

Sample text: *"12"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Day

Sample text: *"24"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### separator

Sample text: *"/"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Year

Sample text: *"2023"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/month/font-family": "Libre Franklin",
  "typography/month/font-size": "17px",
  "typography/month/font-weight": "Regular",
  "typography/month/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/day/font-family": "Libre Franklin",
  "typography/day/font-size": "17px",
  "typography/day/font-weight": "Regular",
  "typography/day/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/year/font-family": "Libre Franklin",
  "typography/year/font-size": "17px",
  "typography/year/font-weight": "Regular",
  "typography/year/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/month/font-family": "Libre Franklin",
  "typography/month/font-size": "17px",
  "typography/month/font-weight": "Regular",
  "typography/month/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/day/font-family": "Libre Franklin",
  "typography/day/font-size": "17px",
  "typography/day/font-weight": "Regular",
  "typography/day/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/year/font-family": "Libre Franklin",
  "typography/year/font-size": "17px",
  "typography/year/font-weight": "Regular",
  "typography/year/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/month/font-family": "Libre Franklin",
  "typography/month/font-size": "17px",
  "typography/month/font-weight": "Regular",
  "typography/month/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/day/font-family": "Libre Franklin",
  "typography/day/font-size": "17px",
  "typography/day/font-weight": "Regular",
  "typography/day/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/year/font-family": "Libre Franklin",
  "typography/year/font-size": "17px",
  "typography/year/font-weight": "Regular",
  "typography/year/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/month/font-family": "Libre Franklin",
  "typography/month/font-size": "17px",
  "typography/month/font-weight": "Regular",
  "typography/month/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/day/font-family": "Libre Franklin",
  "typography/day/font-size": "17px",
  "typography/day/font-weight": "Regular",
  "typography/day/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/year/font-family": "Libre Franklin",
  "typography/year/font-size": "17px",
  "typography/year/font-weight": "Regular",
  "typography/year/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/month/font-family": "Libre Franklin",
  "typography/month/font-size": "17px",
  "typography/month/font-weight": "Regular",
  "typography/month/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/day/font-family": "Libre Franklin",
  "typography/day/font-size": "17px",
  "typography/day/font-weight": "Regular",
  "typography/day/line-height": "auto",
  "typography/separator/font-family": "Libre Franklin",
  "typography/separator/font-size": "17px",
  "typography/separator/font-weight": "Regular",
  "typography/separator/line-height": "auto",
  "typography/year/font-family": "Libre Franklin",
  "typography/year/font-size": "17px",
  "typography/year/font-weight": "Regular",
  "typography/year/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Input Date (766×595px)
  ◈ state=default, filled=false (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      T Placeholder (271×21px) "Select date"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=default, filled=true (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ◇ Current Date (112×21px)
        T Month (19×21px) "12"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Day (22×21px) "24"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Year (43×21px) "2023"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=false (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      T Placeholder (271×21px) "Select date"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=focus, filled=true (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Leading content (287×24px)
        ▣ Image (56×24px)
          ─ { left-padding } (16×0px)
          ◇ Leading Image (56×24px)
        ◇ Current Date (112×21px)
          T Month (19×21px) "12"
          ◇ _🍏 Date Separator / slash (14×21px)
          T Day (22×21px) "24"
          ◇ _🍏 Date Separator / slash (14×21px)
          T Year (43×21px) "2023"
      ◇ Clear Button (56×24px)
        ◇ cancel (rounded) (24×24px)
          ✦ Vector (20×20px)
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=error, filled=false (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Leading content (295×24px)
        ▣ Image (56×24px)
          ─ { left-padding } (16×0px)
          ◇ Leading Image (56×24px)
        T Placeholder (239×21px) "Select date"
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=error, filled=true (343×103px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Leading content (295×24px)
        ▣ Image (56×24px)
          ─ { left-padding } (16×0px)
          ◇ Leading Image (56×24px)
        ◇ Current Date (112×21px)
          T Month (19×21px) "12"
          ◇ _🍏 Date Separator / slash (14×21px)
          T Day (22×21px) "24"
          ◇ _🍏 Date Separator / slash (14×21px)
          T Year (43×21px) "2023"
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (343×30px)
      T Text (343×18px) "Error text"
  ◈ state=read-only, filled=false (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      T Placeholder (271×21px) "Select date"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=read-only, filled=true (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ◇ Current Date (112×21px)
        T Month (19×21px) "12"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Day (22×21px) "24"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Year (43×21px) "2023"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=false (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      T Placeholder (271×21px) "Select date"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
  ◈ state=disabled, filled=true (343×73px)
    ▣ Title labels (343×29px)
      ◇ Title Label (45×29px)
        T Text (45×21px) "Label"
      ◇ Subtitle Label (74×29px)
        T Text (74×21px) "(optional)"
    ▣ Field (343×44px)
      ▣ Image (56×24px)
        ─ { left-padding } (16×0px)
        ◇ Leading Image (56×24px)
          ○ Image (24×24px)
      ◇ Current Date (112×21px)
        T Month (19×21px) "12"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Day (22×21px) "24"
        ◇ _🍏 Date Separator / slash (14×21px)
          T separator (6×21px) "/"
        T Year (43×21px) "2023"
    ◇ Helper Label (343×30px) [hidden]
      T Text (343×18px) "Helper text"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

## 5. Financial & Complex Data Components

### # 🍏 Input Amount

🍏 Input Amount is a component set component measuring 2808×1550px.

## Overview

Use this component when you need a **🍏 Input Amount** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Input Amount`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors

## Variants

- **style=default, multi-currency=True, state=disabled, filled=true, currency position=left**: style=default, multi-currency=True, state=disabled, filled=true, currency position=left
- **style=prominent, multi-currency=True, state=disabled, filled=true, currency position=left**: style=prominent, multi-currency=True, state=disabled, filled=true, currency position=left
- **style=default, multi-currency=True, state=disabled, filled=false, currency position=left**: style=default, multi-currency=True, state=disabled, filled=false, currency position=left
- **style=prominent, multi-currency=True, state=disabled, filled=false, currency position=left**: style=prominent, multi-currency=True, state=disabled, filled=false, currency position=left
- **style=default, multi-currency=True, state=read-only, filled=true, currency position=left**: style=default, multi-currency=True, state=read-only, filled=true, currency position=left
- **style=prominent, multi-currency=True, state=read-only, filled=true, currency position=left**: style=prominent, multi-currency=True, state=read-only, filled=true, currency position=left
- **style=default, multi-currency=True, state=read-only, filled=false, currency position=left**: style=default, multi-currency=True, state=read-only, filled=false, currency position=left
- **style=prominent, multi-currency=True, state=read-only, filled=false, currency position=left**: style=prominent, multi-currency=True, state=read-only, filled=false, currency position=left
- **style=default, multi-currency=True, state=error, filled=true, currency position=left**: style=default, multi-currency=True, state=error, filled=true, currency position=left
- **style=prominent, multi-currency=True, state=error, filled=true, currency position=left**: style=prominent, multi-currency=True, state=error, filled=true, currency position=left
- **style=default, multi-currency=True, state=error, filled=false, currency position=left**: style=default, multi-currency=True, state=error, filled=false, currency position=left
- **style=prominent, multi-currency=True, state=error, filled=false, currency position=left**: style=prominent, multi-currency=True, state=error, filled=false, currency position=left
- **style=default, multi-currency=True, state=focused, filled=true, currency position=left**: style=default, multi-currency=True, state=focused, filled=true, currency position=left
- **style=prominent, multi-currency=True, state=focused, filled=true, currency position=left**: style=prominent, multi-currency=True, state=focused, filled=true, currency position=left
- **style=default, multi-currency=True, state=focused, filled=false, currency position=left**: style=default, multi-currency=True, state=focused, filled=false, currency position=left
- **style=prominent, multi-currency=True, state=focused, filled=false, currency position=left**: style=prominent, multi-currency=True, state=focused, filled=false, currency position=left
- **style=default, multi-currency=True, state=default, filled=true, currency position=left**: style=default, multi-currency=True, state=default, filled=true, currency position=left
- **style=prominent, multi-currency=True, state=default, filled=true, currency position=left**: style=prominent, multi-currency=True, state=default, filled=true, currency position=left
- **style=default, multi-currency=True, state=default, filled=false, currency position=left**: style=default, multi-currency=True, state=default, filled=false, currency position=left
- **style=prominent, multi-currency=True, state=default, filled=false, currency position=left**: style=prominent, multi-currency=True, state=default, filled=false, currency position=left
- **style=default, multi-currency=False, state=disabled, filled=true, currency position=right**: style=default, multi-currency=False, state=disabled, filled=true, currency position=right
- **style=prominent, multi-currency=False, state=disabled, filled=true, currency position=right**: style=prominent, multi-currency=False, state=disabled, filled=true, currency position=right
- **style=default, multi-currency=False, state=disabled, filled=false, currency position=right**: style=default, multi-currency=False, state=disabled, filled=false, currency position=right
- **style=prominent, multi-currency=False, state=disabled, filled=false, currency position=right**: style=prominent, multi-currency=False, state=disabled, filled=false, currency position=right
- **style=default, multi-currency=False, state=read-only, filled=true, currency position=right**: style=default, multi-currency=False, state=read-only, filled=true, currency position=right
- **style=prominent, multi-currency=False, state=read-only, filled=true, currency position=right**: style=prominent, multi-currency=False, state=read-only, filled=true, currency position=right
- **style=default, multi-currency=False, state=read-only, filled=false, currency position=right**: style=default, multi-currency=False, state=read-only, filled=false, currency position=right
- **style=prominent, multi-currency=False, state=read-only, filled=false, currency position=right**: style=prominent, multi-currency=False, state=read-only, filled=false, currency position=right
- **style=default, multi-currency=False, state=error, filled=true, currency position=right**: style=default, multi-currency=False, state=error, filled=true, currency position=right
- **style=prominent, multi-currency=False, state=error, filled=true, currency position=right**: style=prominent, multi-currency=False, state=error, filled=true, currency position=right
- **style=default, multi-currency=False, state=error, filled=false, currency position=right**: style=default, multi-currency=False, state=error, filled=false, currency position=right
- **style=prominent, multi-currency=False, state=error, filled=false, currency position=right**: style=prominent, multi-currency=False, state=error, filled=false, currency position=right
- **style=default, multi-currency=False, state=focused, filled=true, currency position=right**: style=default, multi-currency=False, state=focused, filled=true, currency position=right
- **style=prominent, multi-currency=False, state=focused, filled=true, currency position=right**: style=prominent, multi-currency=False, state=focused, filled=true, currency position=right
- **style=default, multi-currency=False, state=focused, filled=false, currency position=right**: style=default, multi-currency=False, state=focused, filled=false, currency position=right
- **style=prominent, multi-currency=False, state=focused, filled=false, currency position=right**: style=prominent, multi-currency=False, state=focused, filled=false, currency position=right
- **style=default, multi-currency=False, state=default, filled=true, currency position=right**: style=default, multi-currency=False, state=default, filled=true, currency position=right
- **style=prominent, multi-currency=False, state=default, filled=true, currency position=right**: style=prominent, multi-currency=False, state=default, filled=true, currency position=right
- **style=default, multi-currency=False, state=default, filled=false, currency position=right**: style=default, multi-currency=False, state=default, filled=false, currency position=right
- **style=prominent, multi-currency=False, state=default, filled=false, currency position=right**: style=prominent, multi-currency=False, state=default, filled=false, currency position=right
- **style=default, multi-currency=False, state=disabled, filled=true, currency position=left**: style=default, multi-currency=False, state=disabled, filled=true, currency position=left
- **style=prominent, multi-currency=False, state=disabled, filled=true, currency position=left**: style=prominent, multi-currency=False, state=disabled, filled=true, currency position=left
- **style=default, multi-currency=False, state=disabled, filled=false, currency position=left**: style=default, multi-currency=False, state=disabled, filled=false, currency position=left
- **style=prominent, multi-currency=False, state=disabled, filled=false, currency position=left**: style=prominent, multi-currency=False, state=disabled, filled=false, currency position=left
- **style=default, multi-currency=False, state=read-only, filled=true, currency position=left**: style=default, multi-currency=False, state=read-only, filled=true, currency position=left
- **style=prominent, multi-currency=False, state=read-only, filled=true, currency position=left**: style=prominent, multi-currency=False, state=read-only, filled=true, currency position=left
- **style=default, multi-currency=False, state=read-only, filled=false, currency position=left**: style=default, multi-currency=False, state=read-only, filled=false, currency position=left
- **style=prominent, multi-currency=False, state=read-only, filled=false, currency position=left**: style=prominent, multi-currency=False, state=read-only, filled=false, currency position=left
- **style=default, multi-currency=False, state=error, filled=true, currency position=left**: style=default, multi-currency=False, state=error, filled=true, currency position=left
- **style=prominent, multi-currency=False, state=error, filled=true, currency position=left**: style=prominent, multi-currency=False, state=error, filled=true, currency position=left
- **style=default, multi-currency=False, state=error, filled=false, currency position=left**: style=default, multi-currency=False, state=error, filled=false, currency position=left
- **style=prominent, multi-currency=False, state=error, filled=false, currency position=left**: style=prominent, multi-currency=False, state=error, filled=false, currency position=left
- **style=default, multi-currency=False, state=focused, filled=true, currency position=left**: style=default, multi-currency=False, state=focused, filled=true, currency position=left
- **style=prominent, multi-currency=False, state=focused, filled=true, currency position=left**: style=prominent, multi-currency=False, state=focused, filled=true, currency position=left
- **style=default, multi-currency=False, state=focused, filled=false, currency position=left**: style=default, multi-currency=False, state=focused, filled=false, currency position=left
- **style=prominent, multi-currency=False, state=focused, filled=false, currency position=left**: style=prominent, multi-currency=False, state=focused, filled=false, currency position=left
- **style=default, multi-currency=False, state=default, filled=true, currency position=left**: style=default, multi-currency=False, state=default, filled=true, currency position=left
- **style=prominent, multi-currency=False, state=default, filled=true, currency position=left**: style=prominent, multi-currency=False, state=default, filled=true, currency position=left
- **style=default, multi-currency=False, state=default, filled=false, currency position=left**: style=default, multi-currency=False, state=default, filled=false, currency position=left
- **style=prominent, multi-currency=False, state=default, filled=false, currency position=left**: style=prominent, multi-currency=False, state=default, filled=false, currency position=left

## Props

### value

- **Type**: `TEXT`
- **Default**: `9,999.99`

### has label

- **Type**: `BOOLEAN`
- **Default**: `true`

### has error

- **Type**: `BOOLEAN`
- **Default**: `true`

### has helper

- **Type**: `BOOLEAN`
- **Default**: `true`

### placeholder

- **Type**: `TEXT`
- **Default**: `0.00`

### is editing

- **Type**: `BOOLEAN`
- **Default**: `false`

### style

- **Type**: `VARIANT`
- **Default**: `prominent`
- **Options**: `prominent`, `default`

### multi-currency

- **Type**: `VARIANT`
- **Default**: `False`
- **Options**: `False`, `True`

### state

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `focused`, `error`, `read-only`, `disabled`

### filled

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `false`, `true`

### currency position

- **Type**: `VARIANT`
- **Default**: `left`
- **Options**: `left`, `right`

## Dimensions

- **Width**: 2808px
- **Height**: 1550px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7189A7`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#7E848C`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Error text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#BF2310`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Value

Sample text: *"9,999.99"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### $

Sample text: *"$"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"0.00"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

### Text

Sample text: *"Helper text"*

- **Font**: Libre Franklin Regular
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#3A495D`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "border-radius": "5px",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/value/font-family": "Libre Franklin",
  "typography/value/font-size": "34px",
  "typography/value/font-weight": "Bold",
  "typography/value/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "17px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/-/font-family": "Libre Franklin",
  "typography/-/font-size": "34px",
  "typography/-/font-weight": "Bold",
  "typography/-/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "34px",
  "typography/placeholder/font-weight": "Bold",
  "typography/placeholder/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "15px",
  "typography/text/font-weight": "Regular",
  "typography/text/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Input Amount (2808×1550px)
  ◈ style=default, multi-currency=True, state=disabled, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=disabled, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=disabled, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=disabled, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=read-only, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=read-only, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=read-only, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=read-only, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=error, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (172×52px)
          T Value (157×41px) "9,999.99"
          ◇ 🍏 Cursor (2×20px) [hidden]
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=True, state=error, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (172×52px)
          T Value (157×41px) "9,999.99"
          ◇ 🍏 Cursor (2×20px) [hidden]
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=True, state=error, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (172×52px)
          ▣ Typing area (164×41px)
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=True, state=error, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (172×52px)
          ▣ Typing area (164×41px)
        ◇ error (24×24px)
          ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=True, state=focused, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (157×41px)
          T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=focused, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (157×41px)
          T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=focused, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×41px)
          ▣ Typing area (196×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=focused, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×41px)
          ▣ Typing area (196×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=default, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=default, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Value (196×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=True, state=default, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=True, state=default, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Combo field (311×56px)
      ▣ Currency dropdown (75×56px)
        ▣ Content (51×52px)
          ▣ Currency (23×41px)
          ▣ Trailing image (28×24px)
      ▣ Field (228×56px)
        ▣ Content (196×52px)
          T Placeholder (196×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=disabled, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=disabled, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=disabled, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=disabled, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=read-only, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=read-only, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=read-only, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=read-only, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=error, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        T Value (224×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=False, state=error, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        T Value (224×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=False, state=error, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Typing area (224×41px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (224×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=False, state=error, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Typing area (224×41px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (224×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=False, state=focused, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (256×41px)
        T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
      ▣ Currency (23×41px)
        ○ Mask (23×41px)
          ◇ Currency (23×41px)
        ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=focused, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (256×41px)
        T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px)
          ▬ Pipe (2×20px)
      ▣ Currency (23×41px)
        ○ Mask (23×41px)
          ◇ Currency (23×41px)
        ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=focused, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×41px)
        ▣ Typing area (256×41px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=focused, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×41px)
        ▣ Typing area (256×41px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=default, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=default, filled=true, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Value (256×41px) "9,999.99"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=default, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=default, filled=false, currency position=right (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        T Placeholder (256×41px) "0.00"
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=disabled, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=disabled, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=disabled, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=disabled, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=read-only, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=read-only, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=read-only, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=read-only, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=error, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=False, state=error, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (157×41px) "9,999.99"
        ◇ 🍏 Cursor (2×20px) [hidden]
          ▬ Pipe (2×20px)
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=False, state=error, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ▣ Typing area (224×41px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (224×41px) "0.00"
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=prominent, multi-currency=False, state=error, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (255×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ▣ Typing area (224×41px)
          ◇ 🍏 Cursor (2×20px) [hidden]
          T Placeholder (224×41px) "0.00"
      ◇ error (24×24px)
        ✦ Vector (20×20px)
    ◇ Error Label (311×30px)
      T Text (311×18px) "Error text"
  ◈ style=default, multi-currency=False, state=focused, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (180×41px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (157×41px) "9,999.99"
      ◇ 🍏 Cursor (2×20px)
        ▬ Pipe (2×20px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=focused, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (180×41px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (157×41px) "9,999.99"
      ◇ 🍏 Cursor (2×20px)
        ▬ Pipe (2×20px)
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=focused, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×41px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ▣ Typing area (256×41px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=focused, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×41px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        ▣ Typing area (256×41px)
          ◇ 🍏 Cursor (2×20px)
          T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=default, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=default, filled=true, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Value (256×41px) "9,999.99"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=default, multi-currency=False, state=default, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
  ◈ style=prominent, multi-currency=False, state=default, filled=false, currency position=left (311×115px)
    ◇ Title Label (311×29px)
      T Text (45×21px) "Label"
    ▣ Field (311×56px)
      ▣ Content (279×52px)
        ▣ Currency (23×41px)
          ○ Mask (23×41px)
          ▬ { tint } (23×41px)
        T Placeholder (256×41px) "0.00"
    ◇ Helper Label (311×30px)
      T Text (311×18px) "Helper text"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

### 5.2 Account Selector (Transfer)

- **Visual Style**: Two inputs stacked ("From" and "To") bridged by a circular downward arrow. When filled, displays a leading Emblem, Account Name, and available balance.

### 5.3 Passcode Input

- **Visual**: Horizontal row of individual square boxes.
- **States**: Shows a centered dot when filled. Outlines `var(--destructive)` and triggers a rapid horizontal shake animation on error.

### 5.4 Payment Cards

# 🍏 Payment Card

🍏 Payment Card is a component set component measuring 774×526px.

## Overview

Use this component when you need a **🍏 Payment Card** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Payment Card`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **card side=front, locked=false**: card side=front, locked=false
- **card side=back, locked=false**: card side=back, locked=false
- **card side=front, locked=true**: card side=front, locked=true
- **card side=back, locked=true**: card side=back, locked=true

## Props

### card holder

- **Type**: `TEXT`
- **Default**: `Ricardo Jones Peterson`

### card number

- **Type**: `TEXT`
- **Default**: `4350`

### expiry date

- **Type**: `TEXT`
- **Default**: `12/24`

### card type

- **Type**: `TEXT`
- **Default**: `Debit`

### cvv

- **Type**: `TEXT`
- **Default**: `XXX`

### expiry label

- **Type**: `TEXT`
- **Default**: `Valid thru`

### is virtual

- **Type**: `BOOLEAN`
- **Default**: `false`

### card side

- **Type**: `VARIANT`
- **Default**: `front`
- **Options**: `front`, `back`

### locked

- **Type**: `VARIANT`
- **Default**: `false`
- **Options**: `false`, `true`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 40px · right 40px · bottom 40px · left 40px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 774px
- **Height**: 526px

### Border Radius

- All corners: `8px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Card Number Mask

Sample text: *"•••• •••• ••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Card Number Digits

Sample text: *"4350"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Card Holder

Sample text: *"Ricardo Jones Peterson"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Valid Thru Title

Sample text: *"Valid thru"*

- **Font**: Libre Franklin Regular
- **Size**: `11px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Valid Thru Date

Sample text: *"12/24"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Vendor Label

Sample text: *"Debit"*

- **Font**: Libre Franklin Regular
- **Size**: `11px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FFFFFF`

### Virtual

Sample text: *"Virtual"*

- **Font**: Libre Franklin Regular
- **Size**: `12px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FFFFFF`

### Code

Sample text: *"XXX"*

- **Font**: Libre Franklin Regular
- **Size**: `16px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Text

Sample text: *"LOCKED"*

- **Font**: Libre Franklin SemiBold
- **Size**: `11px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Card Number Mask

Sample text: *"•••• •••• ••••"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Card Number Digits

Sample text: *"4350"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Card Holder

Sample text: *"Ricardo Jones Peterson"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Valid Thru Title

Sample text: *"Valid thru"*

- **Font**: Libre Franklin Regular
- **Size**: `11px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Valid Thru Date

Sample text: *"12/24"*

- **Font**: Libre Franklin SemiBold
- **Size**: `15px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### vendor-label

Sample text: *"Debit"*

- **Font**: Libre Franklin Regular
- **Size**: `11px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FFFFFF`

### Virtual

Sample text: *"Virtual"*

- **Font**: Libre Franklin Regular
- **Size**: `12px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FFFFFF`

### Code

Sample text: *"XXX"*

- **Font**: Libre Franklin Regular
- **Size**: `16px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "40px 40px 40px 40px",
  "border-radius": "8px",
  "typography/card-number-mask/font-family": "Libre Franklin",
  "typography/card-number-mask/font-size": "17px",
  "typography/card-number-mask/font-weight": "Regular",
  "typography/card-number-mask/line-height": "auto",
  "typography/card-number-digits/font-family": "Libre Franklin",
  "typography/card-number-digits/font-size": "17px",
  "typography/card-number-digits/font-weight": "Regular",
  "typography/card-number-digits/line-height": "auto",
  "typography/card-holder/font-family": "Libre Franklin",
  "typography/card-holder/font-size": "15px",
  "typography/card-holder/font-weight": "SemiBold",
  "typography/card-holder/line-height": "auto",
  "typography/valid-thru-title/font-family": "Libre Franklin",
  "typography/valid-thru-title/font-size": "11px",
  "typography/valid-thru-title/font-weight": "Regular",
  "typography/valid-thru-title/line-height": "auto",
  "typography/valid-thru-date/font-family": "Libre Franklin",
  "typography/valid-thru-date/font-size": "15px",
  "typography/valid-thru-date/font-weight": "SemiBold",
  "typography/valid-thru-date/line-height": "auto",
  "typography/vendor-label/font-family": "Libre Franklin",
  "typography/vendor-label/font-size": "11px",
  "typography/vendor-label/font-weight": "Regular",
  "typography/vendor-label/line-height": "auto",
  "typography/virtual/font-family": "Libre Franklin",
  "typography/virtual/font-size": "12px",
  "typography/virtual/font-weight": "Regular",
  "typography/virtual/line-height": "auto",
  "typography/code/font-family": "Libre Franklin",
  "typography/code/font-size": "16px",
  "typography/code/font-weight": "Regular",
  "typography/code/line-height": "auto",
  "typography/text/font-family": "Libre Franklin",
  "typography/text/font-size": "11px",
  "typography/text/font-weight": "SemiBold",
  "typography/text/line-height": "auto",
  "typography/card-number-mask/font-family": "Libre Franklin",
  "typography/card-number-mask/font-size": "17px",
  "typography/card-number-mask/font-weight": "Regular",
  "typography/card-number-mask/line-height": "auto",
  "typography/card-number-digits/font-family": "Libre Franklin",
  "typography/card-number-digits/font-size": "17px",
  "typography/card-number-digits/font-weight": "Regular",
  "typography/card-number-digits/line-height": "auto",
  "typography/card-holder/font-family": "Libre Franklin",
  "typography/card-holder/font-size": "15px",
  "typography/card-holder/font-weight": "SemiBold",
  "typography/card-holder/line-height": "auto",
  "typography/valid-thru-title/font-family": "Libre Franklin",
  "typography/valid-thru-title/font-size": "11px",
  "typography/valid-thru-title/font-weight": "Regular",
  "typography/valid-thru-title/line-height": "auto",
  "typography/valid-thru-date/font-family": "Libre Franklin",
  "typography/valid-thru-date/font-size": "15px",
  "typography/valid-thru-date/font-weight": "SemiBold",
  "typography/valid-thru-date/line-height": "auto",
  "typography/vendor-label/font-family": "Libre Franklin",
  "typography/vendor-label/font-size": "11px",
  "typography/vendor-label/font-weight": "Regular",
  "typography/vendor-label/line-height": "auto",
  "typography/virtual/font-family": "Libre Franklin",
  "typography/virtual/font-size": "12px",
  "typography/virtual/font-weight": "Regular",
  "typography/virtual/line-height": "auto",
  "typography/code/font-family": "Libre Franklin",
  "typography/code/font-size": "16px",
  "typography/code/font-weight": "Regular",
  "typography/code/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Payment Card (774×526px)
  ◈ card side=front, locked=false (327×203px)
    ◇ Background (327×203px)
      ▬ gradient (327×203px)
    ▣ Content (279×155px)
      ▣ Leading Content (223×155px)
        ◇ Card Logo (40×40px)
          ▣ Auto Layout for positioning and resizing (33×40px)
        ▣ Card Data (223×90px)
          ▣ Card Number (120×21px)
          T Card Holder (223×18px) "Ricardo Jones Peterson"
          ▣ Valid Thru (223×35px)
      ▣ Trailing Content (40×155px)
        ▣ Top View (40×52px)
          ◇ Vendor Logo (40×30px)
          T Vendor Label (40×13px) "Debit"
        ▣ Middle View (24×52px)
          ◇ 🍏 Payment Card / Middle Image (24×24px)
        ▣ Bottom View (24×52px)
          ◇ 🍏 Payment Card / Bottom Image (24×24px)
          ◇ 🍏 Payment Card / Tag (53×23px) [hidden]
  ◈ card side=back, locked=false (327×203px)
    ◇ Background (327×203px)
      ▬ gradient (327×203px)
    ▬ Top Stripe (327×40px)
    ▣ Bottom Container (327×80px)
      ▣ CVV Code (49×32px)
        T Code (33×19px) "XXX"
  ◈ card side=front, locked=true (327×203px)
    ◇ Status View (98×32px)
      ◇ lock (16×16px)
        ✦ Vector (11×14px)
      T Text (46×13px) "LOCKED"
    ▣ Content (279×155px)
      ▣ Leading Content (223×155px)
        ◇ Card Logo (40×40px)
          ▣ Auto Layout for positioning and resizing (33×40px)
        ▣ Card Data (223×90px)
          ▣ Card Number (120×21px)
          T Card Holder (223×18px) "Ricardo Jones Peterson"
          ▣ Valid Thru (223×35px)
      ▣ Trailing Content (40×155px)
        ▣ Top View (40×52px)
          ▣ card-vendor (40×43px)
        ▣ Middle View (24×52px)
          ◇ 🍏 Payment Card / Middle Image (24×24px)
        ▣ Bottom View (24×52px)
          ◇ 🍏 Payment Card / Bottom Image (24×24px)
          ◇ 🍏 Payment Card / Tag (53×23px) [hidden]
  ◈ card side=back, locked=true (327×203px)
    ▬ Top Stripe (327×40px)
    ▣ Bottom Container (327×80px)
      ▣ CVV Code (49×32px)
        T Code (33×19px) "XXX"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

### 5.5 Summary Stacks

- **Vertical Stack**: Centered. Emblem Icon -> Primary Text -> Secondary Text -> Huge Amount String -> Subtext -> Badge.

---

## 6. Lists & Rows

### 6.1 Standard List Rows

- **Standard**: Leading Avatar/Emblem, Title, Subtitle. Trailing chevron (`>`).
- **Transaction Row**: Right-aligned side contains the Amount (Uses `var(--success)` for positive `+300.00`, standard `var(--foreground)` for negative).
- **File Upload Item**: Leading file type icon. States include trailing Trash icon, a `var(--primary)` progress bar along the bottom edge, or a `var(--destructive)` error state border.

---

## 7. Selection Controls

# 🍏 iOS 26+/ Switch

🍏 iOS 26+/ Switch is a component set component measuring 104×209px.

## Overview

Use this component when you need a **🍏 iOS 26+/ Switch** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 iOS 26+/ Switch`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors

## Variants

- **Selected=Off, Disabled=True**: Selected=Off, Disabled=True
- **Selected=Off, Disabled=False**: Selected=Off, Disabled=False
- **Selected=On, Disabled=True**: Selected=On, Disabled=True
- **Selected=On, Disabled=False**: Selected=On, Disabled=False

## Props

### Selected

- **Type**: `VARIANT`
- **Default**: `On`
- **Options**: `On`, `Off`

### Disabled

- **Type**: `VARIANT`
- **Default**: `False`
- **Options**: `False`, `True`

## Dimensions

- **Width**: 104px
- **Height**: 209px

## Visual Style

### Background

- Fill: `#9747FF` at 12% opacity

### Border Radius

- All corners: `4px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 2, 2px

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "border-radius": "4px",
  "color/background-1": "#9747FF"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 iOS 26+/ Switch (104×209px)
  ◈ Selected=Off, Disabled=True (64×28px)
    ▬ Knob (39×24px)
  ◈ Selected=Off, Disabled=False (64×28px)
    ▬ Knob (39×24px)
  ◈ Selected=On, Disabled=True (64×28px)
    ▬ Knob (39×24px)
  ◈ Selected=On, Disabled=False (64×28px)
    ▬ Knob (39×24px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Segmented Control

🍏 Segmented Control is a component set component measuring 365×228px.

## Overview

Use this component when you need a **🍏 Segmented Control** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Segmented Control`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Variants

- **segments=2 segments**: segments=2 segments
- **segments=3 segments**: segments=3 segments
- **segments=4 segments**: segments=4 segments
- **segments=5 segments**: segments=5 segments

## Props

### segments

- **Type**: `VARIANT`
- **Default**: `2 segments`
- **Options**: `2 segments`, `3 segments`, `4 segments`, `5 segments`

## Layout

- **Direction**: vertical
- **Gap**: 20px
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: auto
- **Vertical sizing**: auto

## Dimensions

- **Width**: 365px
- **Height**: 228px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin SemiBold
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

### Title

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `13px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#000000`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "20px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "13px",
  "typography/title/font-weight": "Regular",
  "typography/title/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Segmented Control (365×228px)
  ◈ segments=2 segments (325×32px)
    ◇ Segment 1 (161×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (161×28px)
      T Title (145×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=3 segments (325×32px)
    ◇ Segment 1 (108×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (108×28px)
      T Title (92×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (108×28px)
      T Title (92×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=4 segments (325×32px)
    ◇ Segment 1 (81×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 4 (81×28px)
      T Title (65×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
  ◈ segments=5 segments (325×32px)
    ◇ Segment 1 (65×28px)
      T Title (35×16px) "Label"
    ◇ Segment 2 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 3 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 4 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px) [hidden]
        ▬ Separator Line (1×16px)
    ◇ Segment 5 (65×28px)
      T Title (49×16px) "Label"
      ▣ Separator (1×16px)
        ▬ { hide if last } (1×20px)
        ▬ Separator Line (1×16px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# Checkbox

🍏 Checkbox is a component set component measuring 276×144px.

## Overview

Use this component when you need a **Checkbox** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Checkbox`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **vertical** auto layout — do not switch to absolute positioning inside it

## Variants

- **alignment=top**: alignment=top
- **alignment=center**: alignment=center

## Props

### title

- **Type**: `TEXT`
- **Default**: `Something that is two lines long`

### alignment

- **Type**: `VARIANT`
- **Default**: `top`
- **Options**: `top`, `center`

## Layout

- **Direction**: vertical
- **Gap**: 20px
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: auto
- **Vertical sizing**: auto

## Dimensions

- **Width**: 276px
- **Height**: 144px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Something that is two lines long

Sample text: *"Something that is two lines long"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Something that is two lines long

Sample text: *"Something that is two lines long"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "20px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/something-that-is-two-lines-long/font-family": "Libre Franklin",
  "typography/something-that-is-two-lines-long/font-size": "17px",
  "typography/something-that-is-two-lines-long/font-weight": "SemiBold",
  "typography/something-that-is-two-lines-long/line-height": "auto",
  "typography/something-that-is-two-lines-long/font-family": "Libre Franklin",
  "typography/something-that-is-two-lines-long/font-size": "17px",
  "typography/something-that-is-two-lines-long/font-weight": "SemiBold",
  "typography/something-that-is-two-lines-long/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Checkbox (276×144px)
  ◈ alignment=top (236×42px)
    ◇ Checkbox (24×24px)
      ▣ Icon (24×24px)
        ⊕ Shape (20×20px)
          ▬ Oval (20×20px)
          ✦ Check (12×9px)
    T Something that is two lines long (196×42px) "Something that is two lines long"
  ◈ alignment=center (236×42px)
    ◇ Checkbox (24×24px)
      ▣ Icon (24×24px)
        ⊕ Shape (20×20px)
          ▬ Oval (20×20px)
          ✦ Check (12×9px)
    T Something that is two lines long (196×42px) "Something that is two lines long"
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Chip

🍏 Chip is a component set component measuring 141×126px.

## Overview

Use this component when you need a **🍏 Chip** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Chip`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors

## Variants

- **State=Active**: State=Active
- **State=Inactive**: State=Inactive

## Props

### icon

- **Type**: `INSTANCE_SWAP`
- **Default**: `41781:10779`

### dismissable

- **Type**: `BOOLEAN`
- **Default**: `true`

### label

- **Type**: `TEXT`
- **Default**: `Chip`

### has Icon

- **Type**: `BOOLEAN`
- **Default**: `true`

### State

- **Type**: `VARIANT`
- **Default**: `Active`
- **Options**: `Active`, `Inactive`

## Dimensions

- **Width**: 141px
- **Height**: 126px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Label

Sample text: *"Chip"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#152F80`

### Label

Sample text: *"Chip"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "border-radius": "5px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Chip (141×126px)
  ◈ State=Active (101×33px)
    ▣ Chip Icon (32×32px)
      ─ { left-padding } (12×0px)
      ▣ Image (32×32px)
        ○ Image (16×16px)
          ○ Icon Mask (16×16px)
          ▬ { color retainer } (16×16px)
    ▣ Label (37×29px)
      T Label (37×21px) "Chip"
    ▣ Trailing Icon (32×32px)
      ─ { Right-padding } (12×0px)
      ▣ Image (32×32px)
        ○ Image (16×16px)
          ○ Icon Mask (16×16px)
          ▬ { color retainer } (16×16px)
  ◈ State=Inactive (81×33px)
    ▣ Chip Icon (32×32px)
      ─ { left-padding } (12×0px)
      ▣ Image (32×32px)
        ○ Image (16×16px)
          ○ Icon Mask (16×16px)
          ▬ { color retainer } (16×16px)
    ▣ Label (37×29px)
      T Label (37×21px) "Chip"
    ▣ Trailing Icon (12×0px)
      ─ { Right-padding } (12×0px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

*Generated by PixelFlow – Component Spec Generator. Place this file in the `guidelines/` folder of your Figma Make project.*

---

## 8. Indicators & Display

### 8.1 Avatars & Emblems

- **Avatars**: Circular. Initial-based, generic person icon, or user photos. Sizes S to XL.
- **Emblems**: Soft rounded-square (squircle) backgrounds containing a darker solid icon.

### 8.2 Badges & Chips

<!-- - **Badges**: Rectangular pills (`4px` radius). Uses subtle background tints: Warning (`var(--warning-subtle)`), Danger (`var(--destructive-subtle)`), Info (`var(--info-subtle)`), Success (`var(--success-subtle)`). -->

- **Chips**: Interactive `var(--radius-button)` tags. Outline style or Solid style. Supports leading icons and trailing 'X'.
- **Text Status Indicators**: Text labels with a leading icon indicating object state: `INACTIVE`, `LOCKED`, `CANCELLED`, `BLOCKED`, `EXPIRED`.

- **Badges**
  The Badge is a compact element used to denote status, categories, or metadata.

## Typography

- **Font Family**: `var(--font-family)` ("Libre Franklin")
- **Font Size**: `--text-label` (15px)
- **Font Weight**: `--font-weight-regular` (400)
- **Line Height**: 1.5

## Variants

| Variant     | Background Token       | Text Color Token      |
| :---------- | :--------------------- | :-------------------- |
| **Warning** | `--warning-subtle`     | `--warning`           |
| **Danger**  | `--destructive-subtle` | `--destructive`       |
| **Success** | `--success-subtle`     | `--success`           |
| **Info**    | `--accent`             | `--accent-foreground` |
| **Neutral** | `--muted`              | `--muted-foreground`  |

## Specifications

- **Border Radius**: `--radius` (8px)
- **Padding**: Recommended 4px vertical, 12px horizontal.

### 8.3 Context Menus (iOS Specific)

- **Behavior**: Long-pressing an item scales it up (`transform: scale(1.05)`), applies the Liquid Glass blur to the background to isolate the element, and displays a floating list of actions.

---

## 9. Feedback, Alerts & Empty States

### 9.1 Spinners & Shimmer

- **Spinners**: iOS-style rotating multi-spoke wheel.
- **Shimmer (Skeleton)**: Animated left-to-right gradient light sweep on `var(--muted)` skeleton shapes.

### 9.2 Banners (Inline Alerts)

- **Visual Style**: Card layout with subtle colored backgrounds (e.g., `var(--warning-subtle)`). Bottom section separated by a 1px `var(--border-subtle)` line containing primary text actions.

### 9.3 Full-Page Empty States

- **Usage**: Centered, full-screen layouts used when no data is present (e.g., No Internet, No Transactions, Success, Failure).
- **Anatomy**: Large 3D Illustration -> `var(--text-h3)` Bold Title -> Body Subtitle -> Primary Pill Button.

---

## 10. Navigation

# 🍏  iOS26+/Tab Bar

🍏  iOS26+/Tab Bar is a component set component measuring 442×933px.

## Overview

Use this component when you need a **🍏  iOS26+/Tab Bar** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏  iOS26+/Tab Bar`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors

## Variants

- **Separate Search=False, Tabs=5**: Separate Search=False, Tabs=5
- **Separate Search=False, Tabs=4**: Separate Search=False, Tabs=4
- **Separate Search=False, Tabs=3**: Separate Search=False, Tabs=3
- **Separate Search=False, Tabs=2**: Separate Search=False, Tabs=2
- **Separate Search=True, Tabs=2**: Separate Search=True, Tabs=2
- **Separate Search=True, Tabs=3**: Separate Search=True, Tabs=3
- **Separate Search=True, Tabs=4**: Separate Search=True, Tabs=4
- **Separate Search=True, Tabs=5**: Separate Search=True, Tabs=5

## Props

### Separate Search

- **Type**: `VARIANT`
- **Default**: `False`
- **Options**: `False`, `True`

### Tabs

- **Type**: `VARIANT`
- **Default**: `5`
- **Options**: `2`, `3`, `4`, `5`

## Dimensions

- **Width**: 442px
- **Height**: 933px

## Visual Style

### Background

- Fill: `#9747FF` at 12% opacity

### Border Radius

- All corners: `4px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 2, 2px

## Typography

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `10px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "border-radius": "4px",
  "color/background-1": "#9747FF",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "10px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏  iOS26+/Tab Bar (442×933px)
  ◈ Separate Search=False, Tabs=5 (402×110px)
    ▣ Tab bar (346×62px)
      ▣ Blur (398×114px)
        ▣ Mask (534×214px)
          ▬ Shape (347×62px)
        ▣ Blur (329×62px)
      ▣ Tab Bar Buttons (346×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 1 (76×54px)
          ▬ Selection (76×54px)
          ◇ Icon (24×24px)
          T Label (60×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 2 (76×54px)
          ◇ Icon (24×24px)
          T Label (60×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 3 (76×54px)
          ◇ Icon (24×24px)
          T Label (60×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 4 (76×54px)
          ◇ Icon (24×24px)
          T Label (60×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 05 (76×54px)
          ◇ Icon (24×24px)
          T Label (60×12px) "Label"
  ◈ Separate Search=False, Tabs=4 (402×110px)
    ▣ Tab bar (346×62px)
      ▣ Blur (398×114px)
        ▣ Mask (534×214px)
          ▬ Shape (347×62px)
        ▣ Blur (329×62px)
      ▣ Tab Bar Buttons (346×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 4 (92×54px)
          ▬ Selection (92×54px)
          ◇ Icon (24×24px)
          T Label (76×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 04 (92×54px)
          ◇ Icon (24×24px)
          T Label (76×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 3 (92×54px)
          ◇ Icon (24×24px)
          T Label (76×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 04 (92×54px)
          ◇ Icon (24×24px)
          T Label (76×12px) "Label"
  ◈ Separate Search=False, Tabs=3 (402×110px)
    ▣ Tab bar (294×62px)
      ▣ Blur (346×114px)
        ▣ Mask (482×214px)
          ▬ Shape (295×62px)
        ▣ Blur (277×62px)
      ▣ Tab Bar Buttons (294×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 3 (102×54px)
          ▬ Selection (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 03 (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 03 (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
  ◈ Separate Search=False, Tabs=2 (402×110px)
    ▣ Tab bar (202×62px)
      ▣ Blur (254×114px)
        ▣ Mask (390×214px)
          ▬ Shape (203×62px)
        ▣ Blur (185×62px)
      ▣ Tab Bar Buttons (202×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 2 (102×54px)
          ▬ Selection (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 02 (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
  ◈ Separate Search=True, Tabs=2 (402×110px)
    ▣ Tab Bar (110×62px)
      ▣ Blur (170×114px)
        ▣ Mask (270×214px)
          ▬ Shape (118×62px)
        ▣ Blur (118×62px)
      ▣ Tab Bar Buttons (110×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 1 (102×54px)
          ▬ Selection (102×54px)
          ◇ Icon (24×24px)
          T Label (86×12px) "Label"
    ▣ Search (62×62px)
      ◇ Search Tab (62×62px)
        ◇ Icon (32×32px)
          ◇ search (32×32px)
  ◈ Separate Search=True, Tabs=3 (402×110px)
    ▣ Tab Bar (142×62px)
      ▣ Blur (170×114px)
        ▣ Mask (270×214px)
          ▬ Shape (118×62px)
        ▣ Blur (118×62px)
      ▣ Tab Bar Buttons (142×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 1 (72×54px)
          ▬ Selection (72×54px)
          ◇ Icon (24×24px)
          T Label (56×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 2 (72×54px)
          ◇ Icon (24×24px)
          T Label (56×12px) "Label"
    ▣ Search (62×62px)
      ◇ Search Tab (62×62px)
        ◇ Icon (32×32px)
          ◇ search (32×32px)
  ◈ Separate Search=True, Tabs=4 (402×110px)
    ▣ Tab Bar (241×62px)
      ▣ Tab Bar Buttons (241×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 1 (84×54px)
          ▬ Selection (84×54px)
          ◇ Icon (24×24px)
          T Label (68×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 2 (84×54px)
          ◇ Icon (24×24px)
          T Label (68×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 3 (84×54px)
          ◇ Icon (24×24px)
          T Label (68×12px) "Label"
    ▣ Search (62×62px)
      ◇ Search Tab (62×62px)
        ◇ Icon (32×32px)
          ◇ search (32×32px)
  ◈ Separate Search=True, Tabs=5 (402×110px)
    ▣ Tab bar (241×62px)
      ▣ Tab Bar Buttons (241×62px)
        ◇ 🍏 iOS 26+ / Tab Bar Item 1 (66×54px)
          ▬ Selection (66×54px)
          ◇ Icon (24×24px)
          T Label (50×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 2 (66×54px)
          ◇ Icon (24×24px)
          T Label (50×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 3 (66×54px)
          ◇ Icon (24×24px)
          T Label (50×12px) "Label"
        ◇ 🍏 iOS 26+ / Tab Bar Item 4 (66×54px)
          ◇ Icon (24×24px)
          T Label (50×12px) "Label"
    ▣ Search (62×62px)
      ◇ Search Tab (62×62px)
        ◇ Icon (32×32px)
          ◇ search (32×32px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---

# 🍏 Navigation Controller

🍏 Navigation Controller is a component set component measuring 1245×370px.

## Overview

Use this component when you need a **🍏 Navigation Controller** in your layout. It is defined with the exact dimensions, spacing, typography, and visual styles documented below.

## Usage

- Reference this component by its exact name: `🍏 Navigation Controller`
- Do not override its internal spacing or typography unless a variant explicitly supports it
- Always apply this component on a background that provides sufficient contrast with its fill colors
- The component uses **horizontal** auto layout — do not switch to absolute positioning inside it

## Variants

- **variant=default, mode=large**: variant=default, mode=large
- **variant=modal, mode=large**: variant=modal, mode=large
- **variant=modalPage, mode=large**: variant=modalPage, mode=large
- **variant=default, mode=inline**: variant=default, mode=inline
- **variant=modal, mode=inline**: variant=modal, mode=inline
- **variant=modalPage, mode=inline**: variant=modalPage, mode=inline

## Props

### title

- **Type**: `TEXT`
- **Default**: `Large title`

### has handle

- **Type**: `BOOLEAN`
- **Default**: `true`

### has leading item

- **Type**: `BOOLEAN`
- **Default**: `true`

### has trailing item

- **Type**: `BOOLEAN`
- **Default**: `true`

### has search

- **Type**: `BOOLEAN`
- **Default**: `false`

### has toolbar

- **Type**: `BOOLEAN`
- **Default**: `true`

### has title

- **Type**: `BOOLEAN`
- **Default**: `true`

### variant

- **Type**: `VARIANT`
- **Default**: `default`
- **Options**: `default`, `modal`, `modalPage`

### mode

- **Type**: `VARIANT`
- **Default**: `large`
- **Options**: `inline`, `large`

## Layout

- **Direction**: horizontal
- **Gap**: 40px
- **Wrap**: enabled
- **Padding**: top 20px · right 20px · bottom 20px · left 20px
- **Primary axis alignment**: min
- **Counter axis alignment**: min
- **Horizontal sizing**: fixed
- **Vertical sizing**: auto

## Dimensions

- **Width**: 1245px
- **Height**: 370px

### Border Radius

- All corners: `5px`

### Border / Stroke

- **Weight**: 1px
- **Alignment**: inside
- **Color**: `#9747FF` at 100% opacity
- **Dash pattern**: 10, 5px

## Typography

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Title

Sample text: *"Large title"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Title

Sample text: *"Large title"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#000000`

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Title

Sample text: *"Large title"*

- **Font**: Libre Franklin Bold
- **Size**: `34px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#061223`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#000000`

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Title

Sample text: *"Title"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FFFFFF`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#FFFFFF`

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Title

Sample text: *"Title"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#000000`

### Time

Sample text: *"9:41"*

- **Font**: SF Pro Semibold
- **Size**: `17px`
- **Line height**: `13px`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#FF0000`

### Percentage

Sample text: *"80"*

- **Font**: SF Pro Text Bold
- **Size**: `10px`
- **Line height**: `13px`
- **Letter spacing**: `0.05999999865889549px`
- **Alignment**: center
- **Color**: `#FF0000`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Label

Sample text: *"Label"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#295EFF`

### Title

Sample text: *"Title"*

- **Font**: Libre Franklin SemiBold
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: center
- **Color**: `#061223`

### Placeholder

Sample text: *"Search"*

- **Font**: Libre Franklin Regular
- **Size**: `17px`
- **Line height**: `auto`
- **Letter spacing**: `0`
- **Alignment**: left
- **Color**: `#000000`

## Design Tokens

Use these exact token values when implementing this component in code:

```json
{
  "spacing/gap": "40px",
  "spacing/padding": "20px 20px 20px 20px",
  "border-radius": "5px",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "34px",
  "typography/title/font-weight": "Bold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "34px",
  "typography/title/font-weight": "Bold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "34px",
  "typography/title/font-weight": "Bold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "17px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "17px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto",
  "typography/time/font-family": "SF Pro",
  "typography/time/font-size": "17px",
  "typography/time/font-weight": "Semibold",
  "typography/time/line-height": "13px",
  "typography/percentage/font-family": "SF Pro Text",
  "typography/percentage/font-size": "10px",
  "typography/percentage/font-weight": "Bold",
  "typography/percentage/line-height": "13px",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/label/font-family": "Libre Franklin",
  "typography/label/font-size": "17px",
  "typography/label/font-weight": "Regular",
  "typography/label/line-height": "auto",
  "typography/title/font-family": "Libre Franklin",
  "typography/title/font-size": "17px",
  "typography/title/font-weight": "SemiBold",
  "typography/title/line-height": "auto",
  "typography/placeholder/font-family": "Libre Franklin",
  "typography/placeholder/font-size": "17px",
  "typography/placeholder/font-weight": "Regular",
  "typography/placeholder/line-height": "auto"
}
```

## Layer Structure

The internal layer hierarchy of this component (for reference only — do not replicate manually):

```
◈◈ 🍏 Navigation Controller (1245×370px)
  ◈ variant=default, mode=large (375×148px)
    ◇ Status Bar (375×54px)
      ▣ Time (135×54px)
        T Time (37×12px) "9:41"
      ▬ Dynamic Island (120×37px)
      ▣ Levels (135×54px)
        ▣ Indicators (77×13px)
          ▣ Signal (20×12px)
          ▣ Connection (17×13px)
          ▣ Battery (27×13px)
    ▣ Main (375×94px)
      ▣ Container (375×94px)
        ▣ Wrapper (375×94px)
          ▣ Toolbar (375×44px)
          ▣ Large Title (375×50px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
  ◈ variant=modal, mode=large (375×170px)
    ▣ Stacked Views (375×64px)
      ○ Bottom View (343×10px)
        ▬ Overlay (15%) (343×10px)
      ⊕ Background (375×78px)
        ▬ Black Background (375×78px)
        ⊕ Shape (375×24px)
          ▬ Background (343×10px)
          ▬ Foreground (375×14px)
      ◇ 🍏 Status Bar (374×54px)
        ▣ Time (135×54px)
          T Time (37×12px) "9:41"
        ▬ Dynamic Island (120×37px)
        ▣ Levels (135×54px)
          ▣ Indicators (77×13px)
      ▬ Handle (36×4px)
    ▣ Main (375×106px)
      ▣ Container (375×106px)
        ▣ Wrapper (375×106px)
          ▣ Toolbar (375×56px)
          ▣ Large Title (375×50px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
  ◈ variant=modalPage, mode=large (375×170px)
    ▣ Stacked Views (375×64px)
      ○ Bottom View (343×10px)
        ▬ Overlay (15%) (343×10px)
      ⊕ Background (375×78px)
        ▬ Black Background (375×78px)
        ⊕ Shape (375×24px)
          ▬ Background (343×10px)
          ▬ Foreground (375×14px)
      ◇ 🍏 Status Bar (374×54px)
        ▣ Time (135×54px)
          T Time (37×12px) "9:41"
        ▬ Dynamic Island (120×37px)
        ▣ Levels (135×54px)
          ▣ Indicators (77×13px)
      ▬ Handle (36×4px)
    ▣ Main (375×106px)
      ▣ Container (375×106px)
        ▣ Wrapper (375×106px)
          ▣ Toolbar (375×56px)
          ▣ Large Title (375×50px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
  ◈ variant=default, mode=inline (375×98px)
    ◇ Status Bar (375×54px)
      ▣ Time (135×54px)
        T Time (37×12px) "9:41"
      ▬ Dynamic Island (120×37px)
      ▣ Levels (135×54px)
        ▣ Indicators (77×13px)
          ▣ Signal (20×12px)
          ▣ Connection (17×13px)
          ▣ Battery (27×13px)
    ▣ Main (375×44px)
      ▣ Container (375×44px)
        ▣ Wrapper (375×44px)
          ▣ Toolbar (375×44px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
  ◈ variant=modal, mode=inline (375×120px)
    ▣ Stacked Views (375×64px)
      ○ Bottom View (343×10px)
        ▬ Overlay (15%) (343×10px)
      ⊕ Background (375×78px)
        ▬ Black Background (375×78px)
        ⊕ Shape (375×24px)
          ▬ Background (343×10px)
          ▬ Foreground (375×14px)
      ◇ 🍏 Status Bar (375×54px)
        ▣ Time (135×54px)
          T Time (37×12px) "9:41"
        ▬ Dynamic Island (120×37px)
        ▣ Levels (135×54px)
          ▣ Indicators (77×13px)
      ▬ Handle (36×4px)
    ▣ Main (375×56px)
      ▣ Container (375×56px)
        ▣ Wrapper (375×56px)
          ▣ Toolbar (375×56px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
  ◈ variant=modalPage, mode=inline (375×120px)
    ▣ Stacked Views (375×64px)
      ○ Bottom View (343×10px)
        ▬ Overlay (15%) (343×10px)
      ⊕ Background (375×78px)
        ▬ Black Background (375×78px)
        ⊕ Shape (375×24px)
          ▬ Background (343×10px)
          ▬ Foreground (375×14px)
      ◇ 🍏 Status Bar (375×54px)
        ▣ Time (135×54px)
          T Time (37×12px) "9:41"
        ▬ Dynamic Island (120×37px)
        ▣ Levels (135×54px)
          ▣ Indicators (77×13px)
      ▬ Handle (36×4px)
    ▣ Main (375×56px)
      ▣ Container (375×56px)
        ▣ Wrapper (375×56px)
          ▣ Toolbar (375×56px)
        ▬ { spacing } (375×16px)
      ▣ Search (375×44px) [hidden]
        ◇ Search Bar (343×36px)
          ▣ Field (343×36px)
```

## Dos and Don'ts

**Do:**
- Use this component exactly as defined in the Figma library
- Apply allowed variants through component properties
- Maintain the spacing and layout ratios when placing this in a frame

**Don't:**
- Detach this component and manually edit its internals
- Change its fill colors outside of defined variant properties
- Nest this inside another auto layout frame with conflicting alignment

---