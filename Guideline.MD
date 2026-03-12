# iOS 26 Design System — Figma Make Guidelines

Rules for how Figma Make AI should generate UI that matches this iOS 26 design system. Always use the established design tokens, CSS variables, and component names to maintain visual consistency and a native iOS feel.

---

## Core Rules

- **Single Source of Truth**: All colors, fonts, and sizing come from `theme.css`. Never hardcode hex values — always use the corresponding CSS variable (e.g., `var(--primary)`, `var(--text-base)`).
- **Font Family**: Apply `var(--font-family)` ("Libre Franklin") globally. Use `var(--font-weight-semibold)` for labels, titles, and buttons; `var(--font-weight-regular)` for body, helper, and placeholder text.
- **Dark Mode**: All color tokens automatically switch via the `.dark` class on the root element. Build with semantic tokens; never hardcode light-only values.
- **Component Names**: When referencing library components, use the exact name prefixed with 🍏 (e.g., `🍏 Tab Header`). Do not detach or manually override internal spacing.
- **Logo**: Use `/src/lib/images/logo.svg` as the application logo.

---

## 1. Materials & Depth

### 1.1 iOS Liquid Glass Effect

Used for tab bars, sticky headers, contextual menus, and floating overlays.

| Property          | Value                                              |
|-------------------|----------------------------------------------------|
| `backdrop-filter` | `blur(25px)`                                       |
| Bottom layer      | Dark tint + `mix-blend-mode: color-dodge`          |
| Mid layer         | `rgba(255, 255, 255, 0.50)` + `mix-blend-mode: normal` |
| Top layer         | `var(--popover)` + `mix-blend-mode: linear-burn`   |

### 1.2 Base Card

The primary container for grouping related content.

| Property      | Value                                            |
|---------------|--------------------------------------------------|
| Background    | `var(--card)`                                    |
| Hover         | `var(--card-hover)`                              |
| Border radius | `var(--radius-card)` → 16px                      |
| Shadow        | `var(--elevation-sm)`                            |
| Inner padding | 16px all sides                                   |
| Title style   | `var(--text-h4)`, `var(--font-weight-semibold)`, top-left |

### 1.3 Full Screen Sheet (Modal)

| Property         | Value                                                             |
|------------------|-------------------------------------------------------------------|
| Background scale | Originating screen scales to `0.95`                               |
| Corner rounding  | Top corners: `var(--radius-card)` → 16px                         |
| Overlay          | Dark overlay fades in                                             |
| Entry animation  | Slides up from bottom, `350ms cubic-bezier(0.25, 1, 0.5, 1)`    |
| Anatomy          | Grey pill grabber handle at top center, "Cancel" (left) / "Done" (right) text actions, centered title |

---

## 2. Animation

| Interaction Type               | Duration | Easing                           |
|--------------------------------|----------|----------------------------------|
| Micro (hover, focus)           | `150ms`  | `ease-in-out`                    |
| State change / toggle          | `250ms`  | `ease-out`                       |
| Spatial (sheet, modal, screen) | `350ms`  | `cubic-bezier(0.25, 1, 0.5, 1)` |
| Passcode error shake           | Rapid horizontal shake on `var(--destructive)` border |

- Buttons scale down on press: `transform: scale(0.96)`
- Context menus: Long-press target scales up to `transform: scale(1.05)`, background blurs

---

## 3. Color System

All colors must use CSS variables. Light mode values shown; dark mode switches automatically via `.dark`.

### 3.1 Brand & Interactive

| CSS Variable               | Light          | Dark       | Usage                                     |
|----------------------------|----------------|------------|-------------------------------------------|
| `var(--primary)`           | `#295eff`      | `#295eff`  | Primary actions, links, active states     |
| `var(--primary-hover)`     | `#2049c6`      | —          | Button / icon hover                       |
| `var(--primary-pressed)`   | `#152f80`      | —          | Button press / active                     |
| `var(--primary-foreground)`| `#ffffff`      | `#ffffff`  | Text on primary-colored surfaces          |

### 3.2 Semantic

| CSS Variable                  | Light      | Dark       | Usage                              |
|-------------------------------|------------|------------|------------------------------------|
| `var(--destructive)`          | `#bf2310`  | `#bf2310`  | Error borders, danger buttons      |
| `var(--destructive-foreground)`| `#ffffff` | `#ffffff`  | Text on destructive surfaces       |
| `var(--destructive-subtle)`   | `#f5dedb`  | —          | Error/alert backgrounds            |
| `var(--success)`              | `#0e813e`  | —          | Positive amounts, success states   |
| `var(--success-subtle)`       | `#dbece2`  | —          | Success alert backgrounds          |
| `var(--warning)`              | `#fbc02d`  | —          | Cautionary states                  |
| `var(--warning-subtle)`       | `#fef6df`  | —          | Warning alert backgrounds          |

### 3.3 Surfaces & Text

| CSS Variable               | Light      | Dark       | Usage                                      |
|----------------------------|------------|------------|--------------------------------------------|
| `var(--background)`        | `#f3f6f9`  | `#061223`  | App-level background                       |
| `var(--foreground)`        | `#061223`  | `#f3f6f9`  | Default body text                          |
| `var(--card)`              | `#ffffff`  | `#061223`  | Card / surface backgrounds                 |
| `var(--card-hover)`        | `#e1e8ef`  | `#3a495d`  | Card hover state                           |
| `var(--card-foreground)`   | `#061223`  | `#f3f6f9`  | Text inside cards                          |
| `var(--popover)`           | `#f7f7f7`  | `#061223`  | Dropdowns, tooltips, glass effect top layer|
| `var(--muted)`             | `#ccd5df`  | `#7189a7`  | Disabled backgrounds, skeleton loaders     |
| `var(--muted-foreground)`  | `#7189a7`  | `#ccd5df`  | Disabled text, secondary metadata         |
| `var(--accent)`            | `#dee2ff`  | `#295eff`  | Secondary chip / button highlight          |
| `var(--accent-foreground)` | `#152f80`  | `#ffffff`  | Text on accent surfaces                    |

### 3.4 Borders, Inputs & Focus

| CSS Variable               | Light      | Dark       | Usage                               |
|----------------------------|------------|------------|-------------------------------------|
| `var(--border)`            | `#7189a7`  | `#7189a7`  | Default element borders             |
| `var(--border-subtle)`     | `#ccd5df`  | —          | Subtle dividers, row separators     |
| `var(--input)`             | `#ffffff`  | `#061223`  | Filled input background             |
| `var(--input-background)`  | `#ffffff`  | —          | Default (unfilled) input background |
| `var(--input-hover)`       | `#2049c6`  | —          | Input trailing icon hover           |
| `var(--ring)`              | `#295eff`  | `#295eff`  | Focus ring / outline                |

### 3.5 Helper / Placeholder Text

Use `var(--sidebar-foreground)` (`#3a495d`) for helper text, placeholder text, and optional field markers. This is the mid-tone between `var(--foreground)` and `var(--muted-foreground)`.

---

## 4. Typography Scale

Only these CSS variables exist in `theme.css`. For sizes below `--text-label`, use literal pixel values.

| Variable           | Size  | Weight Default     | Usage                                   |
|--------------------|-------|--------------------|-----------------------------------------|
| `var(--text-h1)`   | 34px  | Bold               | Large titles, hero amounts              |
| `var(--text-h2)`   | 28px  | SemiBold           | Section titles                          |
| `var(--text-h3)`   | 22px  | SemiBold           | Empty state headings                    |
| `var(--text-h4)`   | 20px  | SemiBold           | Card headers, sub-section titles        |
| `var(--text-base)` | 17px  | Regular / SemiBold | Body, buttons, input text               |
| `var(--text-label)`| 15px  | Regular / SemiBold | Labels, helper text, links, chips       |
| `13px` (literal)   | 13px  | Regular / SemiBold | Segment labels, small metadata          |
| `10px` (literal)   | 10px  | Regular            | Tab bar labels                          |
| `11px` (literal)   | 11px  | Regular            | Card micro-text, CVV labels             |

Line height: `1.5` globally (set in `theme.css` base layer).

Font weights: `var(--font-weight-regular)` · `var(--font-weight-semibold)` · `var(--font-weight-bold)`

---

## 5. Border Radius

| Variable              | Value  | Usage                               |
|-----------------------|--------|-------------------------------------|
| `var(--radius-button)`| 99px   | Pill — buttons, chips               |
| `var(--radius-card)`  | 16px   | Cards, sheets, payment cards        |
| `var(--radius-segment)`| 8px   | Segmented control pill              |
| `var(--radius)`       | 8px    | Badges, general elements            |
| `var(--radius-sm)`    | 4px    | Tight corners (computed: `calc(var(--radius) - 4px)`) |
| `var(--radius-xl)`    | 12px   | Input fields (computed: `calc(var(--radius) + 4px)`) |

---

## 6. Elevation

| Variable             | Value                                        | Usage             |
|----------------------|----------------------------------------------|-------------------|
| `var(--elevation-sm)`| `0px 4px 9px 0px rgba(16,47,67,0.12)`       | Cards, modals     |
| `var(--elevation-md)`| `0px 8px 16px 0px rgba(16,47,67,0.12)`      | Floating elements |
| `var(--elevation-lg)`| `0px 15px 20px 0px rgba(16,47,67,0.12)`     | Sheets, drawers   |

---

## 7. Chart Colors

For data visualization (charts, graphs, progress indicators):

| Variable          | Value     |
|-------------------|-----------|
| `var(--chart-1)`  | `#e01700` |
| `var(--chart-2)`  | `#ff8000` |
| `var(--chart-3)`  | `#ed5ea6` |
| `var(--chart-4)`  | `#295eff` |
| `var(--chart-5)`  | `#6817cf` |
| `var(--chart-6)`  | `#1ed2d2` |
| `var(--chart-7)`  | `#40bf84` |
| `var(--chart-8)`  | `#79c716` |
| `var(--chart-9)`  | `#f2bc0d` |
| `var(--chart-10)` | `#3a495d` |

---

## 8. Headers & Navigation

### 8.1 Page Header — `🍏 Tab Header`

**Component**: `🍏 Tab Header` · 375×166px

| Prop             | Type    | Default | Options |
|------------------|---------|---------|---------|
| `has trailing 3` | Boolean | `true`  | —       |
| `has trailing 2` | Boolean | `false` | —       |
| `has trailing 1` | Boolean | `false` | —       |
| `has tabs`       | Boolean | `true`  | —       |

- Contains: iOS Status Bar → Toolbar (leading Avatar + app name, trailing action buttons) → horizontal scrolling tab strip
- Title: `var(--text-base)` SemiBold, `var(--primary-foreground)`
- Subtitle: `13px`, `var(--primary-foreground)`
- Tab labels: `var(--text-label)` SemiBold active / Regular inactive

### 8.2 Section / Card Headers

- **Title**: `var(--text-h4)`, `var(--font-weight-semibold)`, `var(--foreground)`
- **Subtitle**: `13px`, `var(--muted-foreground)`
- **Trailing — More Menu**: Horizontal `•••` icon in `var(--muted-foreground)`
- **Trailing — Status Badge**: Semantic pill (see §12.3)
- **Trailing — Action Link**: `var(--text-label)` SemiBold, `var(--primary)`

### 8.3 Copyable Account Header

- Muted "Account name" label: `var(--muted-foreground)`
- Large Bold title: `var(--text-h1)`, `var(--font-weight-bold)`, `var(--foreground)`
- Trailing copy icon: `var(--primary)`

---

## 9. Navigation Components

### 9.1 Tab Bar — `🍏  iOS26+/Tab Bar`

**Component**: `🍏  iOS26+/Tab Bar` · Uses Liquid Glass material (§1.1)

| Prop              | Type    | Default | Options            |
|-------------------|---------|---------|--------------------|
| `Separate Search` | Variant | `False` | `False`, `True`    |
| `Tabs`            | Variant | `5`     | `2`, `3`, `4`, `5` |

- Tab labels: `10px` Regular
- Active tab icon + label: `var(--primary)`
- Inactive tab icon + label: `var(--foreground)`

### 9.2 Navigation Controller — `🍏 Navigation Controller`

**Component**: `🍏 Navigation Controller`

| Prop               | Type    | Default       | Options                         |
|--------------------|---------|---------------|---------------------------------|
| `variant`          | Variant | `default`     | `default`, `modal`, `modalPage` |
| `mode`             | Variant | `large`       | `large`, `inline`               |
| `title`            | Text    | `Large title` | —                               |
| `has handle`       | Boolean | `true`        | —                               |
| `has leading item` | Boolean | `true`        | —                               |
| `has trailing item`| Boolean | `true`        | —                               |
| `has search`       | Boolean | `false`       | —                               |
| `has toolbar`      | Boolean | `true`        | —                               |

- **large mode**: `var(--text-h1)` Bold title collapses to inline on scroll
- **inline mode**: Compact centered title `var(--text-base)` SemiBold
- **modal variant**: Includes grabber handle; modal sheet presentation
- **modalPage variant**: Page within a modal; includes leading "Back" / "Cancel"

---

## 10. Buttons & Actions

### 10.1 Standard Buttons

- Corner radius: `var(--radius-button)` → 99px (pill shape)
- Font: `var(--text-label)` SemiBold
- Press animation: `transform: scale(0.96)`

| Style     | Background           | Text                       | Hover                    |
|-----------|----------------------|----------------------------|--------------------------|
| Primary   | `var(--primary)`     | `var(--primary-foreground)`| `var(--primary-hover)`   |
| Secondary | `var(--accent)`      | `var(--accent-foreground)` | `var(--secondary-hover)` |
| Tertiary  | `transparent`        | `var(--foreground)`        | `var(--card-hover)`      |
| Success   | `var(--success)`     | `var(--primary-foreground)`| Darken success           |
| Danger    | `var(--destructive)` | `var(--destructive-foreground)` | Darken destructive  |

| State    | Behavior                                                       |
|----------|----------------------------------------------------------------|
| Default  | Standard resting appearance                                    |
| Hover    | Background shifts to hover token                               |
| Pressed  | `var(--primary-pressed)` + `scale(0.96)`                      |
| Loading  | Replace content with centered `🍏 Activity Indicator`         |
| Disabled | Background `var(--muted)`, text `var(--muted-foreground)`      |

### 10.2 Icon Button — `🍏 Icon Button`

**Component**: `🍏 Icon Button`

| Prop    | Type          | Default   | Options                                      |
|---------|---------------|-----------|----------------------------------------------|
| `title` | Text          | `Button`  | —                                            |
| `icon`  | Instance Swap | —         | Any 24×24 icon                               |
| `style` | Variant       | `primary` | `primary`, `danger`                          |
| `state` | Variant       | `default` | `default`, `pressed`, `loading`, `disabled`  |

### 10.3 Text Links — `🍏 Link`

**Component**: `🍏 Link`

| Prop       | Type          | Default     | Options                                      |
|------------|---------------|-------------|----------------------------------------------|
| `title`    | Text          | `Text link` | —                                            |
| `icon`     | Instance Swap | —           | Trailing icon (default: `open_in_new`)       |
| `has icon` | Boolean       | `true`      | —                                            |
| `state`    | Variant       | `default`   | `default`, `pressed`, `loading`, `disabled`  |
| `on color` | Variant       | `false`     | `false` (primary), `true` (white on colored bg) |

- Font: `var(--text-label)` SemiBold
- Default: `var(--primary)` · On-color: `var(--primary-foreground)`
- Disabled: `var(--muted-foreground)`

---

## 11. Form Inputs & Data Entry

All inputs follow iOS grouped list styling:

- **Label**: `var(--text-base)` SemiBold, `var(--foreground)`
- **Optional marker**: "(optional)" `var(--text-base)` Regular, `var(--sidebar-foreground)` — inline after label
- **Input container**: `var(--radius-xl)` → 12px radius, `var(--input-background)` fill, `var(--border)` outline
- **Helper text**: `var(--text-label)` Regular, `var(--sidebar-foreground)` — below input
- **Error text**: `var(--text-label)` Regular, `var(--destructive)` — replaces helper on error

| State     | Border / Behavior                                              |
|-----------|----------------------------------------------------------------|
| Default   | `var(--border)`                                                |
| Focus     | `var(--ring)`, subtle glow                                     |
| Filled    | `var(--input)` background                                      |
| Error     | `var(--destructive)` border + trailing `!` icon + error text   |
| Read-only | Standard border, no interaction                                |
| Disabled  | `var(--muted)` background, `var(--muted-foreground)` text      |

### 11.1 Search Bar — `🍏 Search Bar / Standalone`

**Component**: `🍏 Search Bar / Standalone`

| Prop       | Type    | Default | Options                             |
|------------|---------|---------|-------------------------------------|
| `state`    | Variant | `idle`  | `idle`, `focus`, `typing`, `filled` |
| `on color` | Variant | `false` | `false`, `true`                     |

- Leading magnifier icon; trailing clear `×` icon when typing / filled
- `on color=true`: For placement on colored or image backgrounds

### 11.2 Text Area — `🍏 Text Area`

**Component**: `🍏 Text Area`

| Prop     | Type    | Default   | Options                                              |
|----------|---------|-----------|------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled` |
| `filled` | Boolean | `false`   | —                                                    |

- Character count at bottom-right: `13px` Regular, `var(--muted-foreground)`

### 11.3 Phone Input — `🍏 Input Phone`

**Component**: `🍏 Input Phone`

| Prop     | Type    | Default   | Options                                              |
|----------|---------|-----------|------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled` |
| `filled` | Boolean | `false`   | —                                                    |

- Leading country flag + dial code (e.g., "+1") selector in `var(--foreground)`
- Placeholder: `var(--sidebar-foreground)`
- Value text: `var(--text-base)` Regular, `var(--foreground)`

### 11.4 Password Input — `🍏 Input Password`

**Component**: `🍏 Input Password`

| Prop     | Type    | Default   | Options                                    |
|----------|---------|-----------|--------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `disabled`    |
| `filled` | Boolean | `false`   | —                                          |

- Trailing `🍏 Password Toggle` icon; hover color `var(--input-hover)`
- Masked display uses `🍏 Password Mask`

### 11.5 Date Input — `🍏 Input Date`

**Component**: `🍏 Input Date`

- Trailing calendar icon; opens native iOS date picker on tap
- Supports the same 5-state pattern as other inputs

### 11.6 Segmented Control — `🍏 Segmented Control`

**Component**: `🍏 Segmented Control`

| Prop       | Type    | Default      | Options                                          |
|------------|---------|--------------|--------------------------------------------------|
| `segments` | Variant | `2 segments` | `2 segments`, `3 segments`, `4 segments`, `5 segments` |

- Radius: `var(--radius-segment)` → 8px
- Selected label: `13px` SemiBold, `var(--foreground)`
- Unselected label: `13px` Regular, `var(--muted-foreground)`
- Segment separator: `var(--border-subtle)`
- Selected pill: `var(--card)` + `var(--elevation-sm)`

---

## 12. Financial & Complex Components

### 12.1 Amount Input — `🍏 Input Amount`

**Component**: `🍏 Input Amount`

| Prop               | Type    | Default   | Options                                              |
|--------------------|---------|-----------|------------------------------------------------------|
| `style`            | Variant | `default` | `default`, `prominent`                               |
| `state`            | Variant | `default` | `default`, `focused`, `error`, `read-only`, `disabled` |
| `filled`           | Boolean | `false`   | —                                                    |
| `multi-currency`   | Boolean | `True`    | —                                                    |
| `currency position`| Variant | `left`    | `left`, `right`                                      |

- **default style**: Standard input height
- **prominent style**: Large hero display (`var(--text-h1)` Bold, `var(--foreground)`)
- Currency symbol: `var(--muted-foreground)`

### 12.2 Account Selector (Transfer)

- Two stacked inputs ("From" / "To") bridged by circular swap icon
- When filled: leading `🍏 Avatar` / Emblem + account name + balance (`var(--muted-foreground)`)
- Swap icon: `var(--primary)`

### 12.3 Passcode Input

- Horizontal row of equal-width square boxes
- Filled box: centered dot, `var(--foreground)`
- Error state: `var(--destructive)` border + rapid horizontal shake animation

### 12.4 Payment Card — `🍏 Payment Card`

**Component**: `🍏 Payment Card`

| Prop          | Type    | Default                  | Options         |
|---------------|---------|--------------------------|-----------------|
| `card side`   | Variant | `front`                  | `front`, `back` |
| `locked`      | Variant | `false`                  | `false`, `true` |
| `card holder` | Text    | `Ricardo Jones Peterson` | —               |
| `card number` | Text    | `4350`                   | Last 4 digits   |
| `expiry date` | Text    | `12/24`                  | —               |
| `card type`   | Text    | `Debit`                  | —               |
| `cvv`         | Text    | `XXX`                    | —               |

- Corner radius: `var(--radius-card)` → 16px
- Locked state: overlay with lock icon
- Card number masked except last 4 digits

### 12.5 Summary Stacks

- Label: `13px` Regular, `var(--muted-foreground)` — uppercase or title-case
- Value: `var(--text-base)` SemiBold, `var(--foreground)`
- Divider: `var(--border-subtle)` 1px hairline

---

## 13. Lists & Rows

### 13.1 Standard List Row

- **Leading**: `🍏 Avatar` or Emblem + Title + Subtitle
- **Trailing**: Chevron `›`, `var(--muted-foreground)`
- Title: `var(--text-base)` SemiBold, `var(--foreground)`
- Subtitle: `var(--text-label)` Regular, `var(--muted-foreground)`
- Row separator: `var(--border-subtle)` 1px

### 13.2 Transaction Row

- Positive (credit): `var(--text-base)` SemiBold, `var(--success)` — prefix `+`
- Negative (debit): `var(--text-base)` SemiBold, `var(--foreground)` — prefix `-`

### 13.3 File Upload Item

- Leading: file type icon
- Uploading: `var(--primary)` progress bar along bottom edge
- Error: `var(--destructive)` border
- Complete: trailing trash icon

---

## 14. Selection Controls

### 14.1 Switch — `🍏 iOS 26+/ Switch`

**Component**: `🍏 iOS 26+/ Switch`

| Prop       | Type    | Default | Options         |
|------------|---------|---------|-----------------|
| `Selected` | Variant | `On`    | `On`, `Off`     |
| `Disabled` | Variant | `False` | `False`, `True` |

- **On**: Track `var(--primary)`, white knob
- **Off**: Track `var(--muted)`, white knob
- **Disabled**: Reduced opacity; transition `250ms ease-out`

### 14.2 Checkbox — `🍏 Checkbox`

- Unchecked: `var(--border)` outline, transparent fill
- Checked: `var(--primary)` fill, white checkmark
- Disabled: `var(--muted)` fill

### 14.3 Chip — `🍏 Chip`

**Component**: `🍏 Chip`

- Corner radius: `var(--radius-button)` → pill
- **Outline style**: `var(--border)` stroke, `var(--card)` fill, `var(--foreground)` text
- **Solid style**: `var(--accent)` fill, `var(--accent-foreground)` text
- Label: `var(--text-label)` SemiBold
- Optional leading icon (24×24) + trailing `×` dismiss icon

---

## 15. Indicators & Display

### 15.1 Avatars — `🍏 Avatar`

- Shape: Circle
- Sizes: S (24px) → M (32px) → L (40px) → XL (56px)
- Initial avatar: `var(--accent)` background, `var(--accent-foreground)` text

### 15.2 Emblems

- Soft rounded-square (squircle) background with a solid icon
- Background: `var(--accent)`, icon: `var(--primary)`

### 15.3 Badges

| Variant | Background                  | Text                        |
|---------|-----------------------------|-----------------------------|
| Warning | `var(--warning-subtle)`     | `var(--warning)`            |
| Danger  | `var(--destructive-subtle)` | `var(--destructive)`        |
| Success | `var(--success-subtle)`     | `var(--success)`            |
| Info    | `var(--accent)`             | `var(--accent-foreground)`  |
| Neutral | `var(--muted)`              | `var(--muted-foreground)`   |

- Radius: `var(--radius)` → 8px · Padding: 4px vertical, 12px horizontal
- Font: `var(--text-label)` Regular

### 15.4 Text Status Indicators

Inline labels with leading icon: `INACTIVE`, `LOCKED`, `CANCELLED`, `BLOCKED`, `EXPIRED`

- Font: `13px` SemiBold · Colors: match badge variant above

### 15.5 Context Menus (iOS 26)

- Long-press: scale target to `1.05`, background blurs (Liquid Glass §1.1)
- Floating action list appears above/below

---

## 16. Feedback & Empty States

### 16.1 Spinners — `🍏 Activity Indicator`

- iOS rotating multi-spoke wheel
- Color: `var(--primary)` / `var(--primary-foreground)` on colored backgrounds

### 16.2 Shimmer / Skeleton Loaders

- Base: `var(--muted)` shaped to destination content
- Animation: left-to-right gradient sweep

### 16.3 Inline Alert Banners

- Card layout with `var(--elevation-sm)`
- Background: semantic subtle variant (e.g., `var(--warning-subtle)`)
- Separator: `var(--border-subtle)` 1px
- Action link: `var(--text-label)` SemiBold, `var(--primary)`

### 16.4 Full-Page Empty States

- Layout: vertically centered, full-screen
- Anatomy (top → bottom):
  1. Large 3D illustration
  2. Title: `var(--text-h3)` Bold, `var(--foreground)`
  3. Subtitle: `var(--text-base)` Regular, `var(--muted-foreground)`
  4. Primary pill button (§10.1)

---

## 17. Quick Reference — Component Mapping

| Use Case              | Component                          |
|-----------------------|------------------------------------|
| Page header with tabs | `🍏 Tab Header`                    |
| Navigation stack      | `🍏 Navigation Controller`         |
| Bottom tab navigation | `🍏  iOS26+/Tab Bar`               |
| Segmented filter      | `🍏 Segmented Control`             |
| Icon-only button      | `🍏 Icon Button`                   |
| Text link             | `🍏 Link`                          |
| Search field          | `🍏 Search Bar / Standalone`       |
| Multi-line text input | `🍏 Text Area`                     |
| Phone number input    | `🍏 Input Phone`                   |
| Password input        | `🍏 Input Password`                |
| Date picker input     | `🍏 Input Date`                    |
| Currency / amount     | `🍏 Input Amount`                  |
| Payment card display  | `🍏 Payment Card`                  |
| Toggle on/off         | `🍏 iOS 26+/ Switch`               |
| Tag / filter chip     | `🍏 Chip`                          |
| User avatar           | `🍏 Avatar`                        |
| Loading spinner       | `🍏 Activity Indicator`            |
| Text cursor           | `🍏 Cursor`                        |

---

## 18. Global Do / Don't

**Do:**
- Reference `🍏` components by their exact name
- Apply variants through component properties only
- Use `var(--...)` for all color, typography, and spacing values
- Apply Liquid Glass to all floating / sticky elements
- Support all defined states (default, focus, error, disabled) in every interactive component
- Use `var(--sidebar-foreground)` for helper and placeholder text

**Don't:**
- Detach library components or manually edit their internals
- Hardcode `#hex` or `rgba()` values — always use a CSS variable
- Use `#9747FF` — this is an internal Figma annotation color, not a production token
- Skip disabled or error states for interactive components
- Use `--text-sm` or `--text-xs` — these do not exist in `theme.css`; use `--text-label` (15px) or literal `13px`
