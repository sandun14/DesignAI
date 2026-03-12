# iOS 26 Design System — Figma Make Guidelines

Rules for how Figma Make AI should generate UI that matches this iOS 26 design system. Always use the established design tokens, CSS variables, and component names to maintain visual consistency and a native iOS feel.

---

## Core Rules

- **Single Source of Truth**: All colors, fonts, and spacing come from `theme.css`. Never hardcode hex values or raw pixel sizes — always use the corresponding CSS variable (e.g., `var(--primary)`, `var(--text-base)`).
- **Font Family**: Apply `var(--font-family)` ("Libre Franklin") globally. Use `var(--font-weight-semibold)` for labels, titles, and buttons; `var(--font-weight-regular)` for body, helper, and placeholder text.
- **Component Names**: When referencing library components, use the exact name prefixed with 🍏 (e.g., `🍏 Tab Header`). Do not detach or manually override internal spacing.
- **Logo**: Use `/src/lib/images/logo.svg` as the application logo.

---

## 1. Materials & Depth

### 1.1 iOS Liquid Glass Effect

Used for tab bars, sticky headers, contextual menus, and floating overlays.

| Property         | Value                               |
|------------------|-------------------------------------|
| `backdrop-filter`| `var(--blur-glass)` → `blur(25px)`  |
| Bottom layer     | Dark tint + `mix-blend-mode: color-dodge` |
| Mid layer        | `var(--glass-overlay)` → `rgba(255,255,255,0.50)` + `mix-blend-mode: normal` |
| Top layer        | `var(--popover)` + `mix-blend-mode: linear-burn` |

### 1.2 Base Card

The primary container for grouping related content.

| Property       | Value                         |
|----------------|-------------------------------|
| Background     | `var(--card)`                 |
| Border radius  | `var(--radius-card)` → 16px   |
| Shadow         | `var(--elevation-sm)`         |
| Inner padding  | `var(--space-4)` → 16px all sides |
| Title style    | `var(--text-h4)`, `var(--font-weight-semibold)`, top-left |

### 1.3 Full Screen Sheet (Modal)

| Property           | Value                                             |
|--------------------|---------------------------------------------------|
| Background scale   | Originating screen scales to `0.95`               |
| Corner rounding    | Top corners of sheet: `var(--radius-sheet)` → 20px |
| Overlay            | Dark overlay fades in                             |
| Entry animation    | Slides up from bottom, `var(--duration-spatial)` `var(--ease-spatial)` |
| Anatomy            | Grey pill grabber handle at top center, "Cancel" (left) / "Done" (right) text actions, centered title |

---

## 2. Animation

| Interaction Type               | Duration                   | Easing                      |
|--------------------------------|----------------------------|-----------------------------|
| Micro (hover, focus)           | `var(--duration-micro)` → 150ms | `var(--ease-micro)` → ease-in-out |
| State change / toggle          | `var(--duration-state)` → 250ms | `var(--ease-state)` → ease-out |
| Spatial (sheet, modal, screen) | `var(--duration-spatial)` → 350ms | `var(--ease-spatial)` → cubic-bezier(0.25, 1, 0.5, 1) |
| Passcode error shake           | Rapid horizontal shake on `var(--destructive)` border |

- Buttons scale down on press: `transform: scale(0.96)`
- Context menus: Long-press target scales up to `transform: scale(1.05)`, background blurs

---

## 3. Color System

All colors must use CSS variables. Map hardcoded values as follows:

| CSS Variable              | Value     | Usage                                    |
|---------------------------|-----------|------------------------------------------|
| `var(--primary)`          | `#295EFF` | Primary actions, links, active states    |
| `var(--primary-hover)`    | `#2049C6` | Button hover                             |
| `var(--primary-pressed)`  | `#152F80` | Button press / active                    |
| `var(--primary-foreground)`| `#FFFFFF` | Text on primary backgrounds             |
| `var(--destructive)`      | `#BF2310` | Error borders, error text, danger buttons|
| `var(--success)`          | `#0E813E` | Positive amounts, success states         |
| `var(--foreground)`       | `#061223` | Default body text                        |
| `var(--muted-foreground)` | `#7189A7` | Disabled text, secondary metadata        |
| `var(--helper-foreground)`| `#3A495D` | Helper text, placeholder, optional label |
| `var(--card)`             | `#FFFFFF` | Card / surface backgrounds               |
| `var(--background)`       | `#F2F5F8` | App-level background                     |
| `var(--muted)`            | `#CCD5DF` | Disabled backgrounds, skeleton loaders   |
| `var(--accent)`           | `#DEE2FF` | Secondary chip/button highlight          |
| `var(--border)`           | `rgba(6,18,35,0.12)` | Default borders / dividers   |
| `var(--ring)`             | `#295EFF` | Focus ring                               |

---

## 4. Typography Scale

| Variable          | Size  | Weight            | Usage                              |
|-------------------|-------|-------------------|------------------------------------|
| `var(--text-h1)`  | 34px  | Bold              | Large titles, hero amounts         |
| `var(--text-h2)`  | 28px  | Bold              | Section titles                     |
| `var(--text-h3)`  | 22px  | Bold              | Empty state headings               |
| `var(--text-h4)`  | 20px  | SemiBold          | Card headers, sub-section titles   |
| `var(--text-base)`| 17px  | Regular/SemiBold  | Body, buttons, input text          |
| `var(--text-sm)`  | 15px  | Regular/SemiBold  | Helper text, links, secondary labels |
| `var(--text-xs)`  | 13px  | Regular/SemiBold  | Segment labels, small metadata     |
| `var(--text-tab)` | 10px  | Regular           | Tab bar labels                     |
| `var(--text-xxs)` | 11px  | Regular           | Card micro-text, CVV labels        |

Line height: `var(--leading-normal)` → `1.5` globally.

---

## 5. Headers & Navigation

### 5.1 Page Header — `🍏 Tab Header`

**Component**: `🍏 Tab Header` · 375×166px

| Prop             | Type    | Default | Options       |
|------------------|---------|---------|---------------|
| `has trailing 3` | Boolean | `true`  | —             |
| `has trailing 2` | Boolean | `false` | —             |
| `has trailing 1` | Boolean | `false` | —             |
| `has tabs`       | Boolean | `true`  | —             |

- Contains: iOS Status Bar → Toolbar (leading Avatar + app name, trailing action buttons) → horizontal scrolling tab strip
- Title: `var(--text-base)` SemiBold, `var(--primary-foreground)`
- Subtitle: `var(--text-xs)`, `var(--primary-foreground)`
- Tab labels: `var(--text-sm)` SemiBold active / Regular inactive

### 5.2 Section / Card Headers

- **Title**: `var(--text-h4)`, `var(--font-weight-semibold)`, `var(--foreground)`
- **Subtitle**: `var(--text-xs)`, `var(--muted-foreground)`
- **Trailing — More Menu**: Horizontal `•••` icon
- **Trailing — Status Badge**: Semantic pill using badge color tokens (see §10)
- **Trailing — Action Link**: `var(--text-sm)` SemiBold, `var(--primary)`

### 5.3 Copyable Account Header

- Muted "Account name" label (`var(--muted-foreground)`)
- Large Bold title (`var(--text-h1)`, `var(--font-weight-bold)`)
- Trailing copy icon in `var(--primary)`

---

## 6. Navigation

### 6.1 Tab Bar — `🍏  iOS26+/Tab Bar`

**Component**: `🍏  iOS26+/Tab Bar` · Uses Liquid Glass material

| Prop              | Type    | Default | Options              |
|-------------------|---------|---------|----------------------|
| `Separate Search` | Variant | `False` | `False`, `True`      |
| `Tabs`            | Variant | `5`     | `2`, `3`, `4`, `5`   |

- Tab labels: `var(--text-tab)` → 10px, Regular
- Active tab icon + label: `var(--primary)`
- Inactive tab: `var(--foreground)`
- Background: Liquid Glass (see §1.1)

### 6.2 Navigation Controller — `🍏 Navigation Controller`

**Component**: `🍏 Navigation Controller`

| Prop               | Type    | Default     | Options                          |
|--------------------|---------|-------------|----------------------------------|
| `variant`          | Variant | `default`   | `default`, `modal`, `modalPage`  |
| `mode`             | Variant | `large`     | `large`, `inline`                |
| `title`            | Text    | `Large title` | —                              |
| `has handle`       | Boolean | `true`      | —                                |
| `has leading item` | Boolean | `true`      | —                                |
| `has trailing item`| Boolean | `true`      | —                                |
| `has search`       | Boolean | `false`     | —                                |
| `has toolbar`      | Boolean | `true`      | —                                |

- **large mode**: Full-size title `var(--text-h1)` Bold collapses to inline on scroll
- **inline mode**: Compact centered title `var(--text-base)` SemiBold
- **modal variant**: Includes grabber handle; modal sheet presentation
- **modalPage variant**: Page within a modal, includes leading "Back" / "Cancel"

---

## 7. Buttons & Actions

### 7.1 Standard Buttons

- Corner radius: `var(--radius-button)` → 99px (pill shape)
- Font: `var(--text-sm)` SemiBold for standard; `var(--text-base)` for large
- Press animation: `transform: scale(0.96)`

| Style       | Background              | Text Color                  | Hover                        |
|-------------|-------------------------|-----------------------------|------------------------------|
| Primary     | `var(--primary)`        | `var(--primary-foreground)` | `var(--primary-hover)`       |
| Secondary   | `var(--accent)`         | `var(--secondary-foreground)`| `var(--secondary-hover)`    |
| Tertiary    | `transparent`           | `var(--foreground)`         | `var(--muted-hover)`         |
| Success     | `var(--success)`        | `var(--success-foreground)` | Darker success               |
| Danger      | `var(--destructive)`    | `var(--destructive-foreground)` | Darker destructive       |

| State    | Behavior                                                 |
|----------|----------------------------------------------------------|
| Default  | Standard resting appearance                              |
| Hover    | Background shifts to hover token                         |
| Pressed  | `var(--primary-pressed)`, scale 0.96                    |
| Loading  | Replace content with centered spinner (`🍏 Activity Indicator`) |
| Disabled | Background `var(--muted)`, text `var(--muted-foreground)` |

### 7.2 Icon Button — `🍏 Icon Button`

**Component**: `🍏 Icon Button`

| Prop    | Type    | Default   | Options                     |
|---------|---------|-----------|-----------------------------|
| `title` | Text    | `Button`  | —                           |
| `icon`  | Instance Swap | — | Any 24×24 icon           |
| `style` | Variant | `primary` | `primary`, `danger`         |
| `state` | Variant | `default` | `default`, `pressed`, `loading`, `disabled` |

### 7.3 Text Links — `🍏 Link`

**Component**: `🍏 Link`

| Prop       | Type    | Default    | Options                                    |
|------------|---------|------------|--------------------------------------------|
| `title`    | Text    | `Text link`| —                                          |
| `icon`     | Instance Swap | — | Trailing icon (default: `open_in_new`)   |
| `has icon` | Boolean | `true`     | —                                          |
| `state`    | Variant | `default`  | `default`, `pressed`, `loading`, `disabled`|
| `on color` | Variant | `false`    | `false` (primary), `true` (white, for colored backgrounds) |

- Font: `var(--text-sm)` SemiBold
- Default color: `var(--primary)` · On-color: `var(--primary-foreground)`
- Disabled: `var(--muted-foreground)`

---

## 8. Form Inputs & Data Entry

All inputs follow iOS grouped list styling:

- **Label**: `var(--text-base)` SemiBold, `var(--foreground)`
- **Optional marker**: "(optional)" `var(--text-base)` Regular, `var(--helper-foreground)` — inline after label
- **Input container**: `var(--radius-input)` radius, `var(--input-background)`, `var(--border)` outline
- **Helper text**: `var(--text-sm)` Regular, `var(--helper-foreground)` — below input
- **Error text**: `var(--text-sm)` Regular, `var(--destructive)` — replaces helper on error

| State      | Border / Behavior                               |
|------------|-------------------------------------------------|
| Default    | `var(--border)`                                 |
| Focus      | `var(--ring)`, subtle glow                      |
| Error      | `var(--destructive)`, trailing `!` icon, error text |
| Read-only  | No interaction; standard border                 |
| Disabled   | Background `var(--muted)`, text `var(--muted-foreground)` |

### 8.1 Search Bar — `🍏 Search Bar / Standalone`

**Component**: `🍏 Search Bar / Standalone`

| Prop         | Type    | Default   | Options                                    |
|--------------|---------|-----------|--------------------------------------------|
| `state`      | Variant | `idle`    | `idle`, `focus`, `typing`, `filled`        |
| `on color`   | Variant | `false`   | `false`, `true`                            |

- Magnifier leading icon; optional clear `×` trailing icon when typing/filled
- `on color=true`: Use for placement on colored/image backgrounds

### 8.2 Text Area — `🍏 Text Area`

**Component**: `🍏 Text Area`

| Prop     | Type    | Default   | Options                                                    |
|----------|---------|-----------|------------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled`       |
| `filled` | Boolean | `false`   | —                                                          |

- Shows character count at bottom-right
- Optional leading icon / flag image supported

### 8.3 Phone Input — `🍏 Input Phone`

**Component**: `🍏 Input Phone`

| Prop     | Type    | Default   | Options                                                    |
|----------|---------|-----------|------------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled`       |
| `filled` | Boolean | `false`   | —                                                          |

- Leading country flag + dial code (e.g., "+1") selector
- Placeholder: "Enter phone number", `var(--helper-foreground)`
- Value text: `var(--text-base)` Regular, `var(--foreground)`

### 8.4 Password Input — `🍏 Input Password`

**Component**: `🍏 Input Password`

| Prop     | Type    | Default   | Options                                               |
|----------|---------|-----------|-------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `disabled`               |
| `filled` | Boolean | `false`   | —                                                     |

- Trailing `🍏 Password Toggle` icon to show/hide value
- Masked display uses `🍏 Password Mask`

### 8.5 Date Input — `🍏 Input Date`

**Component**: `🍏 Input Date`

- Trailing calendar icon; opens native iOS date picker on tap
- Supports same 5-state pattern as other inputs

### 8.6 Segmented Control — `🍏 Segmented Control`

**Component**: `🍏 Segmented Control`

| Prop       | Type    | Default      | Options                                         |
|------------|---------|--------------|--------------------------------------------------|
| `segments` | Variant | `2 segments` | `2 segments`, `3 segments`, `4 segments`, `5 segments` |

- Selected segment label: `var(--text-xs)` SemiBold, `var(--foreground)`
- Unselected segment label: `var(--text-xs)` Regular, `var(--muted-foreground)`
- Separator line between segments: `var(--border-subtle)`
- Selected pill: `var(--card)` background with `var(--elevation-sm)`

---

## 9. Financial & Complex Components

### 9.1 Amount Input — `🍏 Input Amount`

**Component**: `🍏 Input Amount`

| Prop               | Type    | Default   | Options                              |
|--------------------|---------|-----------|--------------------------------------|
| `style`            | Variant | `default` | `default`, `prominent`               |
| `state`            | Variant | `default` | `default`, `focused`, `error`, `read-only`, `disabled` |
| `filled`           | Boolean | `false`   | —                                    |
| `multi-currency`   | Boolean | `True`    | —                                    |
| `currency position`| Variant | `left`    | `left`, `right`                      |

- **default style**: Standard input height
- **prominent style**: Large hero amount display (`var(--text-h1)` Bold)
- Amount text: `var(--foreground)`; currency symbol: `var(--muted-foreground)`

### 9.2 Account Selector (Transfer)

- Two stacked inputs ("From" / "To") bridged by a circular swap icon
- When filled: leading `🍏 Avatar` / Emblem + Account Name + available balance
- Swap icon color: `var(--primary)`

### 9.3 Passcode Input

- Horizontal row of equal-width square boxes
- Filled box: centered dot (`var(--foreground)`)
- Error state: border turns `var(--destructive)` + rapid horizontal shake animation

### 9.4 Payment Card — `🍏 Payment Card`

**Component**: `🍏 Payment Card`

| Prop           | Type    | Default                  | Options              |
|----------------|---------|--------------------------|----------------------|
| `card side`    | Variant | `front`                  | `front`, `back`      |
| `locked`       | Variant | `false`                  | `false`, `true`      |
| `card holder`  | Text    | `Ricardo Jones Peterson` | —                    |
| `card number`  | Text    | `4350`                   | Last 4 digits        |
| `expiry date`  | Text    | `12/24`                  | —                    |
| `card type`    | Text    | `Debit`                  | —                    |
| `cvv`          | Text    | `XXX`                    | —                    |

- Corner radius: `var(--radius-card)` → 16px
- Locked state: Overlay with lock icon
- Gradient background; card number masked except last 4 digits

### 9.5 Summary Stacks

- Compact label/value pairs stacked vertically inside a card
- Label: `var(--text-xs)` Regular, `var(--muted-foreground)` — uppercase or title-case
- Value: `var(--text-base)` SemiBold, `var(--foreground)`
- Separated by `var(--border-subtle)` 1px dividers

---

## 10. Lists & Rows

### 10.1 Standard List Row

- **Leading**: `🍏 Avatar` or Emblem (squircle icon) + Title + Subtitle
- **Trailing**: Chevron `›` icon in `var(--muted-foreground)`
- Title: `var(--text-base)` SemiBold, `var(--foreground)`
- Subtitle: `var(--text-sm)` Regular, `var(--muted-foreground)`

### 10.2 Transaction Row

- Right-aligned: Amount
  - Positive (credit): `var(--text-base)` SemiBold, `var(--success)` — prefix `+`
  - Negative (debit): `var(--text-base)` SemiBold, `var(--foreground)` — prefix `-`
- Row divided by `var(--border-subtle)` hairline

### 10.3 File Upload Item

- Leading: File type icon
- Trailing states: Trash icon (delete) / `var(--primary)` progress bar (uploading) / `var(--destructive)` error border

---

## 11. Selection Controls

### 11.1 Switch — `🍏 iOS 26+/ Switch`

**Component**: `🍏 iOS 26+/ Switch`

| Prop       | Type    | Default | Options         |
|------------|---------|---------|-----------------|
| `Selected` | Variant | `On`    | `On`, `Off`     |
| `Disabled` | Variant | `False` | `False`, `True` |

- **On**: Track `var(--primary)`, white knob
- **Off**: Track `var(--muted)`, white knob
- **Disabled**: Reduced opacity on track and knob
- Transition: `var(--duration-state)` `var(--ease-state)`

### 11.2 Checkbox — `🍏 Checkbox`

**Component**: `🍏 Checkbox`

- Unchecked: `var(--border)` outline, transparent fill
- Checked: `var(--primary)` fill, white checkmark icon
- Disabled: `var(--muted)` fill

### 11.3 Chip — `🍏 Chip`

**Component**: `🍏 Chip`

- Corner radius: `var(--radius-button)` → pill shape
- **Outline style**: `var(--border)` stroke, `var(--card)` fill
- **Solid style**: `var(--accent)` fill, `var(--accent-foreground)` text
- Label: `var(--text-sm)` SemiBold
- Optional leading icon (24×24) and trailing `×` dismiss icon

---

## 12. Indicators & Display

### 12.1 Avatars

- **Component**: `🍏 Avatar`
- Shape: Circle
- Content: Initials (2-char), generic person icon, or user photo
- Sizes: S (24px) → M (32px) → L (40px) → XL (56px)
- Background: `var(--accent)`, text `var(--accent-foreground)` for initial avatars

### 12.2 Emblems

- Soft rounded-square (squircle) background with a solid icon inside
- Background: `var(--accent)`, icon `var(--primary)`

### 12.3 Badges

| Variant   | Background                   | Text Color             |
|-----------|------------------------------|------------------------|
| Warning   | `var(--warning-subtle)`      | `var(--warning)`       |
| Danger    | `var(--destructive-subtle)`  | `var(--destructive)`   |
| Success   | `var(--success-subtle)`      | `var(--success)`       |
| Info      | `var(--accent)`              | `var(--accent-foreground)` |
| Neutral   | `var(--muted)`               | `var(--muted-foreground)` |

- Radius: `var(--radius)` → 8px
- Padding: `var(--space-1)` vertical, `var(--space-3)` horizontal
- Font: `var(--text-label)` Regular

### 12.4 Text Status Indicators

Inline text labels with a leading icon: `INACTIVE`, `LOCKED`, `CANCELLED`, `BLOCKED`, `EXPIRED`

- Font: `var(--text-xs)` SemiBold
- Color: matches appropriate badge variant (Neutral for INACTIVE, Danger for BLOCKED, etc.)

### 12.5 Context Menus (iOS 26)

- Long-press scales target to `transform: scale(1.05)`
- Background blurs using Liquid Glass effect (§1.1) to isolate element
- Floating action list appears above/below element

---

## 13. Feedback & Empty States

### 13.1 Spinners

- **Component**: `🍏 Activity Indicator`
- iOS-style rotating multi-spoke wheel
- Color: `var(--primary)` or `var(--primary-foreground)` (on colored backgrounds)

### 13.2 Shimmer / Skeleton Loaders

- Shape: Matches destination content dimensions
- Base color: `var(--muted)` → `#CCD5DF`
- Animation: Animated left-to-right gradient sweep

### 13.3 Inline Alert Banners

- Layout: Card with `var(--elevation-sm)`
- Background: Semantic subtle variant (e.g., `var(--warning-subtle)`)
- Bottom section separated by `var(--border-subtle)` 1px line
- Action: `var(--text-sm)` SemiBold text link in `var(--primary)`

### 13.4 Full-Page Empty States

Used when no data is present (No Internet, No Transactions, Success, Failure).

- Layout: Vertically centered, full-screen
- Anatomy (top to bottom):
  1. Large 3D illustration
  2. Title: `var(--text-h3)` Bold, `var(--foreground)`
  3. Subtitle: `var(--text-base)` Regular, `var(--muted-foreground)`
  4. Primary pill button (§7.1)

---

## 14. Quick Reference — Component Mapping

| Use Case               | Component Name                  |
|------------------------|---------------------------------|
| Page header with tabs  | `🍏 Tab Header`                 |
| Navigation stack       | `🍏 Navigation Controller`      |
| Bottom tab navigation  | `🍏  iOS26+/Tab Bar`            |
| Segmented filter       | `🍏 Segmented Control`          |
| Primary/danger button  | Standard button (§7.1)          |
| Icon-only button       | `🍏 Icon Button`                |
| Text link              | `🍏 Link`                       |
| Search field           | `🍏 Search Bar / Standalone`    |
| Multi-line text input  | `🍏 Text Area`                  |
| Phone number input     | `🍏 Input Phone`                |
| Password input         | `🍏 Input Password`             |
| Date picker input      | `🍏 Input Date`                 |
| Currency / amount      | `🍏 Input Amount`               |
| Payment card display   | `🍏 Payment Card`               |
| Toggle on/off          | `🍏 iOS 26+/ Switch`            |
| Tag / filter chip      | `🍏 Chip`                       |
| User avatar            | `🍏 Avatar`                     |
| Loading spinner        | `🍏 Activity Indicator`         |
| Text cursor            | `🍏 Cursor`                     |

---

## 15. Global Do / Don't

**Do:**
- Always reference `🍏` components by their exact name
- Apply variants exclusively through component properties
- Use `var(--...)` for all color, typography, and spacing values
- Apply Liquid Glass effect to all floating / sticky elements
- Support all defined states (default, focus, error, disabled) in interactive components

**Don't:**
- Detach library components and manually edit internals
- Hardcode `#hex`, `px`, or `rgba` values in markup — use CSS variables
- Change fill colors outside of defined variant properties
- Use `#9747FF` — this is an internal Figma annotation color, not a production token
- Skip disabled / error states for interactive components
