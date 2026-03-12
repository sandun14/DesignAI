# iOS 26 Design System — Figma Make Guidelines

> **How to read this file:**
> All visual values (colors, font sizes, weights, radii, shadows) are defined in `theme.css` as CSS custom properties.
> This document references them only by variable name — e.g. `var(--primary)`.
> **Never hardcode a hex, rgb, or raw pixel value in generated UI. Always use the CSS variable.**

---

## Core Rules

1. **Source of truth** — Every color, font size, font weight, radius, and shadow must come from `theme.css` via `var(--token)`.
2. **Typography** — The global font is `var(--font-family)`. Apply `var(--font-weight-semibold)` for labels, titles, and interactive elements; `var(--font-weight-regular)` for body, helper, and placeholder text. Line height is `1.5` globally.
3. **Dark mode** — All semantic color tokens flip automatically when the `.dark` class is on the root element. Build with semantic tokens; never pin light-only values.
4. **Component names** — Library components are referenced by their exact 🍏-prefixed name. Do not detach or manually override internals.
5. **Logo** — Use `/src/lib/images/logo.svg`.
6. **Fluid interactions** — Elements must track user gestures continuously (swipe, drag). Maintain velocity and feel immediately responsive.

---

## 1. Materials & Depth

### 1.1 iOS Liquid Glass Effect

Applied to: tab bars, sticky navigation headers, contextual menus, floating overlays.

**Construction (three stacked layers):**

| Layer | Treatment |
|-------|-----------|
| Base  | Dark tint fill · `mix-blend-mode: color-dodge` |
| Mid   | `rgba(255,255,255,0.50)` fill · `mix-blend-mode: normal` |
| Top   | `var(--popover)` fill · `mix-blend-mode: linear-burn` |

- `backdrop-filter: blur(25px)` on the container
- Use this material on any element that floats above content

### 1.2 Base Card

The primary grouping container for related content.

| Property      | Token                       |
|---------------|-----------------------------|
| Background    | `var(--card)`               |
| Hover state   | `var(--card-hover)`         |
| Text          | `var(--card-foreground)`    |
| Border radius | `var(--radius-card)`        |
| Shadow        | `var(--elevation-sm)`       |
| Inner padding | `16px` all sides            |

- **Title placement**: inside the card, top-left, `var(--text-h4)` + `var(--font-weight-semibold)`
- The content area is a "Swap Instance" slot — drop in lists, forms, or summaries

### 1.3 Full Screen Sheet (Modal)

| Property        | Behavior |
|-----------------|----------|
| Background scale | Originating screen animates to `scale(0.95)` |
| Top corners     | Round using `var(--radius-card)` |
| Overlay         | `var(--foreground)` at low opacity fades in |
| Sheet entry     | Slides up from bottom edge — `350ms cubic-bezier(0.25,1,0.5,1)` |

**Anatomy (top → bottom inside sheet):**
1. Grey pill grabber handle — centered at top
2. Top-left: "Cancel" text action · Top-right: "Done" text action
3. Centered title — `var(--text-base)` + `var(--font-weight-semibold)`
4. Content area

### 1.4 Separators & Dividers

- **Section divider**: 1px solid `var(--border-subtle)` — full width
- **Swap Instance placeholder**: dashed outline in `var(--primary)`, diagonal striped fill — used only in template frames, never in production screens

---

## 2. Animation

| Interaction                 | Duration | Easing                          |
|-----------------------------|----------|---------------------------------|
| Micro (hover, focus ring)   | `150ms`  | `ease-in-out`                   |
| State change / toggle       | `250ms`  | `ease-out`                      |
| Spatial (sheet, modal, nav) | `350ms`  | `cubic-bezier(0.25, 1, 0.5, 1)`|
| Button press                | Immediate | `transform: scale(0.96)`       |
| Context menu expand         | Immediate | target `transform: scale(1.05)` |
| Passcode error              | Rapid horizontal shake on `var(--destructive)` border |

---

## 3. Typography Hierarchy

All font sizes are defined in `theme.css`. Use the variables — do not substitute literal values.

| Variable           | Weight Default       | Role                                          |
|--------------------|----------------------|-----------------------------------------------|
| `var(--text-h1)`   | `var(--font-weight-bold)` | Large title — hero amounts, screen titles |
| `var(--text-h2)`   | `var(--font-weight-bold)` | Title 1 — major section headings          |
| `var(--text-h3)`   | `var(--font-weight-semibold)` | Title 2 — subsection headings, empty states |
| `var(--text-h4)`   | `var(--font-weight-semibold)` | Title 3 — card titles, inline headers     |
| `var(--text-base)` | `var(--font-weight-regular)` | Body — default text, input values, buttons |
| `var(--text-label)`| `var(--font-weight-regular)` | Label — helper text, secondary descriptions, chips |

For sizes smaller than `var(--text-label)` (segment labels `13px`, tab labels `10px`, micro-text `11px`), use literal `px` values since no variable is defined in `theme.css`.

---

## 4. Color Token Reference

Refer to `theme.css` for all values. Use these variable names in generated UI:

### Backgrounds & Surfaces
`var(--background)` · `var(--card)` · `var(--card-hover)` · `var(--card-foreground)` · `var(--popover)` · `var(--popover-foreground)`

### Brand & Interactive
`var(--primary)` · `var(--primary-hover)` · `var(--primary-pressed)` · `var(--primary-foreground)` · `var(--secondary)` · `var(--secondary-hover)` · `var(--secondary-foreground)`

### Accent
`var(--accent)` · `var(--accent-foreground)`

### Muted / Disabled
`var(--muted)` · `var(--muted-hover)` · `var(--muted-foreground)`

### Semantic States
`var(--destructive)` · `var(--destructive-foreground)` · `var(--destructive-subtle)`
`var(--success)` · `var(--success-subtle)`
`var(--warning)` · `var(--warning-subtle)`

### Text
`var(--foreground)` — primary text
`var(--muted-foreground)` — secondary / disabled text
`var(--sidebar-foreground)` — helper text, placeholders, optional field markers

### Borders & Focus
`var(--border)` · `var(--border-subtle)` · `var(--ring)`

### Inputs
`var(--input)` — filled input background
`var(--input-background)` — default (empty) input background
`var(--input-hover)` — trailing icon hover inside inputs

### Elevation (Shadows)
`var(--elevation-sm)` · `var(--elevation-md)` · `var(--elevation-lg)`

### Border Radii
`var(--radius-button)` · `var(--radius-card)` · `var(--radius-segment)` · `var(--radius)` · `var(--radius-sm)` · `var(--radius-md)` · `var(--radius-lg)` · `var(--radius-xl)`

### Chart Colors (data visualization only)
`var(--chart-1)` through `var(--chart-10)`

---

## 5. Headers & Hierarchy

### 5.1 Page Header — `🍏 Tab Header`

**Component**: `🍏 Tab Header`

**Props:**

| Prop             | Type    | Default |
|------------------|---------|---------|
| `has trailing 3` | Boolean | `true`  |
| `has trailing 2` | Boolean | `false` |
| `has trailing 1` | Boolean | `false` |
| `has tabs`       | Boolean | `true`  |

**Anatomy (top → bottom):**
1. `🍏 Status Bar` — iOS system status bar (time, Dynamic Island, indicators)
2. Toolbar row:
   - Leading: `🍏 Avatar` + app/account name
   - Trailing: up to 3 action buttons (`🍏 Tab Header / Button`, 44×44pt tap targets)
3. Tab strip — horizontal scrollable tabs (`🍏 Tab Header Tabs`)

**Typography:**
- Toolbar title: `var(--text-base)` + `var(--font-weight-semibold)` on `var(--primary-foreground)`
- Toolbar subtitle: `13px` on `var(--primary-foreground)`
- Active tab label: `var(--text-label)` + `var(--font-weight-semibold)` on `var(--primary)`
- Inactive tab label: `var(--text-label)` + `var(--font-weight-regular)` on `var(--foreground)`

### 5.2 Section / Card Headers

Used as the header row inside cards or between sections.

**Anatomy:**
- **Title** — left-aligned, `var(--text-h4)` + `var(--font-weight-semibold)`, `var(--foreground)`
- **Subtitle** — below title, `13px` + `var(--font-weight-regular)`, `var(--muted-foreground)`
- **Trailing options** (right-aligned, pick one):
  - **More Menu** — horizontal `•••` icon, `var(--muted-foreground)`
  - **Status Badge** — semantic pill (see §12.3)
  - **Action Link** — `var(--text-label)` + `var(--font-weight-semibold)`, `var(--primary)`

### 5.3 Copyable Account Header

Used at the top of account detail screens.

**Anatomy (top → bottom):**
1. "Account name" label — `var(--text-label)`, `var(--muted-foreground)`
2. Account title — `var(--text-h1)` + `var(--font-weight-bold)`, `var(--foreground)`
3. Trailing copy icon — `var(--primary)`

---

## 6. Navigation

### 6.1 Tab Bar — `🍏  iOS26+/Tab Bar`

**Component**: `🍏  iOS26+/Tab Bar`
**Material**: iOS Liquid Glass (§1.1) — floating above content

**Variants:**

| Prop              | Options              | Default |
|-------------------|----------------------|---------|
| `Tabs`            | `2`, `3`, `4`, `5`  | `5`     |
| `Separate Search` | `False`, `True`      | `False` |

**Tab item anatomy:**
- Icon: 24×24px symbol
- Label below icon: `10px` + `var(--font-weight-regular)`
- Active: icon + label in `var(--primary)`
- Inactive: icon + label in `var(--foreground)`

**Behavior:**
- Floating pill that hugs the bottom safe area
- Tapping inactive tab: icon bounces with `250ms ease-out`
- `Separate Search=True`: search icon is promoted to a standalone pill outside the tab group

### 6.2 Navigation Controller — `🍏 Navigation Controller`

**Component**: `🍏 Navigation Controller`

**Variants:**

| Prop       | Options                         | Default   |
|------------|---------------------------------|-----------|
| `variant`  | `default`, `modal`, `modalPage` | `default` |
| `mode`     | `large`, `inline`               | `large`   |

**Boolean props:**

| Prop               | Default |
|--------------------|---------|
| `title`            | text prop |
| `has handle`       | `true`  |
| `has leading item` | `true`  |
| `has trailing item`| `true`  |
| `has search`       | `false` |
| `has toolbar`      | `true`  |

**Mode behavior:**
- **large**: Prominent title `var(--text-h1)` + `var(--font-weight-bold)` shown below toolbar; collapses to inline title on scroll
- **inline**: Compact centered title `var(--text-base)` + `var(--font-weight-semibold)` in toolbar row

**Variant behavior:**
- **default**: Standard push navigation; back chevron in `var(--primary)`
- **modal**: Sheet presentation; includes grabber handle; leading "Cancel" in `var(--primary)`
- **modalPage**: Page inside a modal; leading "Back" or "Close"

---

## 7. Buttons & Actions

### 7.1 Standard Buttons

**Shape**: `var(--radius-button)` — pill
**Press animation**: `transform: scale(0.96)`
**Font**: `var(--text-label)` + `var(--font-weight-semibold)`

**Style tokens:**

| Style     | Background             | Text                          | Hover                     |
|-----------|------------------------|-------------------------------|---------------------------|
| Primary   | `var(--primary)`       | `var(--primary-foreground)`   | `var(--primary-hover)`    |
| Secondary | `var(--accent)`        | `var(--accent-foreground)`    | `var(--secondary-hover)`  |
| Tertiary  | `transparent`          | `var(--foreground)`           | `var(--card-hover)`       |
| Success   | `var(--success)`       | `var(--primary-foreground)`   | Darken via filter         |
| Danger    | `var(--destructive)`   | `var(--destructive-foreground)` | Darken via filter       |

**States:**

| State    | Behavior                                                              |
|----------|-----------------------------------------------------------------------|
| Default  | Resting appearance per style above                                    |
| Hover    | Background shifts to hover token · `150ms ease-in-out`               |
| Pressed  | `var(--primary-pressed)` background · `scale(0.96)`                  |
| Loading  | Text and icons hidden; centered `🍏 Activity Indicator` appears      |
| Disabled | Background → `var(--muted)` · Text → `var(--muted-foreground)` · no interaction |

**Sizes:**
- **Large** — full-width or prominent CTA; `var(--text-base)`
- **Medium** — standard; `var(--text-label)`
- **Small** — compact / dense layouts; `var(--text-label)` · reduced padding

### 7.2 Icon Button — `🍏 Icon Button`

**Component**: `🍏 Icon Button`

**Props:**

| Prop    | Type          | Default   | Options                                          |
|---------|---------------|-----------|--------------------------------------------------|
| `title` | Text          | `Button`  | —                                                |
| `icon`  | Instance Swap | —         | Any 24×24 icon                                   |
| `style` | Variant       | `primary` | `primary`, `danger`                              |
| `state` | Variant       | `default` | `default`, `pressed`, `loading`, `disabled`      |

**Layout:**
- Icon (56×56pt circular container) stacked above label
- Label: `var(--text-label)` + `var(--font-weight-semibold)`
- Primary style icon container: `var(--primary)` fill
- Danger style icon container: `var(--destructive)` fill

### 7.3 Text Links — `🍏 Link`

**Component**: `🍏 Link`

**Props:**

| Prop       | Type          | Default     | Options                                       |
|------------|---------------|-------------|-----------------------------------------------|
| `title`    | Text          | `Text link` | —                                             |
| `icon`     | Instance Swap | —           | Trailing icon, default: `open_in_new` (24×24) |
| `has icon` | Boolean       | `true`      | —                                             |
| `state`    | Variant       | `default`   | `default`, `pressed`, `loading`, `disabled`   |
| `on color` | Variant       | `false`     | `false`, `true`                               |

**Color by state and variant:**

| State    | on color=false               | on color=true                    |
|----------|------------------------------|----------------------------------|
| Default  | `var(--primary)`             | `var(--primary-foreground)`      |
| Pressed  | `var(--primary-pressed)` + underline | `var(--primary-foreground)` + underline |
| Loading  | `var(--primary)` + inline spinner | `var(--primary-foreground)` + spinner |
| Disabled | `var(--muted-foreground)`    | `var(--muted-foreground)`        |

---

## 8. Form Inputs & Data Entry

### 8.1 Input Anatomy (All Types)

Every input follows the same structural hierarchy:

```
Label row
  ├─ Field label        var(--text-base) · semibold · var(--foreground)
  └─ "(optional)" tag   var(--text-base) · regular  · var(--sidebar-foreground)
Input container
  ├─ Leading slot       icon or flag (optional)
  ├─ Value / placeholder
  │    value text       var(--text-base) · regular  · var(--foreground)
  │    placeholder      var(--text-base) · regular  · var(--sidebar-foreground)
  └─ Trailing slot      icon, toggle, or error indicator (optional)
Helper / error row
  ├─ Helper text        var(--text-label) · regular · var(--sidebar-foreground)
  └─ Error text         var(--text-label) · regular · var(--destructive)
```

**Container styling:**
- Border radius: `var(--radius-xl)` (computed from `theme.css`)
- Default fill: `var(--input-background)`
- Filled fill: `var(--input)`
- Border: `var(--border)`

### 8.2 Input States

| State     | Border            | Background           | Additional                          |
|-----------|-------------------|----------------------|-------------------------------------|
| Default   | `var(--border)`   | `var(--input-background)` | —                              |
| Focus     | `var(--ring)`     | `var(--input-background)` | Subtle glow on ring             |
| Filled    | `var(--border)`   | `var(--input)`       | —                                   |
| Error     | `var(--destructive)` | `var(--input-background)` | Trailing `!` icon · error text replaces helper |
| Read-only | `var(--border)`   | `var(--input-background)` | No cursor · no interaction      |
| Disabled  | `var(--border-subtle)` | `var(--muted)` | Text → `var(--muted-foreground)` · no interaction |

### 8.3 Search Bar — `🍏 Search Bar / Standalone`

**Component**: `🍏 Search Bar / Standalone`

**Props:**

| Prop       | Type    | Default | Options                              |
|------------|---------|---------|--------------------------------------|
| `state`    | Variant | `idle`  | `idle`, `focus`, `typing`, `filled`  |
| `on color` | Variant | `false` | `false`, `true`                      |

**State anatomy:**
- **idle** — magnifier icon in `var(--muted-foreground)` · placeholder text in `var(--sidebar-foreground)`
- **focus** — cursor appears · keyboard opens
- **typing** — trailing `×` clear button in `var(--muted-foreground)` appears
- **filled** — value text in `var(--foreground)` · `×` remains
- **on color=true** — for placement on `var(--primary)` or image backgrounds

### 8.4 Text Area — `🍏 Text Area`

**Component**: `🍏 Text Area`

**Props:**

| Prop     | Type    | Default   | Options                                               |
|----------|---------|-----------|-------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled`  |
| `filled` | Boolean | `false`   | —                                                     |

**Additional anatomy:**
- Character count — bottom-right, `13px` + `var(--font-weight-regular)`, `var(--muted-foreground)`
- Expands vertically with content

### 8.5 Phone Input — `🍏 Input Phone`

**Component**: `🍏 Input Phone`

**Props:**

| Prop     | Type    | Default   | Options                                               |
|----------|---------|-----------|-------------------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `read-only`, `disabled`  |
| `filled` | Boolean | `false`   | —                                                     |

**Leading element:** Country flag + dial code selector
- Flag image (20×14px) + dial code (e.g. "+1") — `var(--text-base)` + `var(--foreground)`
- Separated from input field by `var(--border-subtle)` vertical line
- Tapping flag opens country picker sheet

### 8.6 Password Input — `🍏 Input Password`

**Component**: `🍏 Input Password`

**Props:**

| Prop     | Type    | Default   | Options                                     |
|----------|---------|-----------|---------------------------------------------|
| `state`  | Variant | `default` | `default`, `focus`, `error`, `disabled`     |
| `filled` | Boolean | `false`   | —                                           |

**Trailing toggle** — `🍏 Password Toggle` icon:
- Hidden state: eye-slash icon · value masked via `🍏 Password Mask`
- Shown state: eye icon · value revealed as plain text
- Icon color: `var(--muted-foreground)` · hover: `var(--input-hover)`

### 8.7 Date Input — `🍏 Input Date`

**Component**: `🍏 Input Date`

- Trailing calendar icon · `var(--muted-foreground)` · hover: `var(--input-hover)`
- Tap opens native iOS date picker as bottom sheet
- Supports same 5-state pattern as other inputs (default, focus, error, read-only, disabled)
- Displayed value: `var(--text-base)` + `var(--foreground)`

### 8.8 Segmented Control — `🍏 Segmented Control`

**Component**: `🍏 Segmented Control`

**Variants:**

| Prop       | Options                                          | Default      |
|------------|--------------------------------------------------|--------------|
| `segments` | `2 segments`, `3 segments`, `4 segments`, `5 segments` | `2 segments` |

**Anatomy:**
- Outer track — `var(--muted)` fill · `var(--radius-segment)` corners
- Selected segment pill — `var(--card)` fill · `var(--elevation-sm)` · `var(--radius-segment)` corners
- Segment separators — 1px `var(--border-subtle)` vertical lines (hidden on selected/adjacent segments)

**Typography:**
- Selected label: `13px` + `var(--font-weight-semibold)` · `var(--foreground)`
- Unselected label: `13px` + `var(--font-weight-regular)` · `var(--muted-foreground)`
- All labels: centered · transition `250ms ease-out`

---

## 9. Financial & Complex Components

### 9.1 Amount Input — `🍏 Input Amount`

**Component**: `🍏 Input Amount`

**Variants:**

| Prop               | Options                                              | Default   |
|--------------------|------------------------------------------------------|-----------|
| `style`            | `default`, `prominent`                               | `default` |
| `state`            | `default`, `focused`, `error`, `read-only`, `disabled` | `default` |
| `filled`           | `true`, `false`                                      | `false`   |
| `multi-currency`   | `True`, `False`                                      | `True`    |
| `currency position`| `left`, `right`                                      | `left`    |

**Style anatomy:**
- **default** — standard input container height; label above; amount and currency inline
- **prominent** — hero display; amount in `var(--text-h1)` + `var(--font-weight-bold)` · `var(--foreground)` · currency in `var(--muted-foreground)`

**Currency selector (multi-currency=True):**
- Currency code + chevron → tapping opens bottom sheet currency picker
- Color: `var(--primary)` for the currency code + chevron

### 9.2 Account Selector (Transfer)

Two input rows stacked with a swap control between them.

**Anatomy:**
- "From" row — same structure as a standard list row (leading emblem + account name + balance)
- Circular swap button — centered between rows · icon `var(--primary-foreground)` on `var(--primary)` fill · 40×40pt
- "To" row — same structure; placeholder when empty

**Filled state:**
- Leading `🍏 Avatar` or Emblem
- Account name — `var(--text-base)` + `var(--font-weight-semibold)` · `var(--foreground)`
- Available balance — `var(--text-label)` + `var(--font-weight-regular)` · `var(--muted-foreground)`

### 9.3 Passcode Input

Horizontal row of 4–6 equal-width square boxes.

| State   | Appearance                                                         |
|---------|--------------------------------------------------------------------|
| Empty   | `var(--border)` outline · transparent fill                         |
| Filled  | Centered dot · `var(--foreground)` fill                            |
| Active  | `var(--ring)` outline (current position being typed)               |
| Error   | All boxes: `var(--destructive)` outline + rapid horizontal shake animation |

### 9.4 Payment Card — `🍏 Payment Card`

**Component**: `🍏 Payment Card`

**Variants:**

| Prop        | Options         | Default |
|-------------|-----------------|---------|
| `card side` | `front`, `back` | `front` |
| `locked`    | `false`, `true` | `false` |

**Editable text props:** `card holder` · `card number` (last 4 digits) · `expiry date` · `card type` · `cvv`

**Front anatomy:**
- Gradient background (brand or network colors)
- Network logo — top-right
- Card type badge — `var(--text-label)` + `var(--font-weight-semibold)` on semi-transparent pill
- Masked number — `•••• •••• •••• [last4]` — `var(--text-base)` + `var(--font-weight-semibold)`
- Card holder name — `var(--text-label)` + `var(--font-weight-regular)`
- Expiry — `var(--text-label)` + `var(--font-weight-regular)`
- Corner radius: `var(--radius-card)`

**Back anatomy:**
- Magnetic stripe band — full width
- CVV field — `var(--foreground)` text on `var(--card)` strip; `11px` + `var(--font-weight-regular)`

**Locked state:** Full-card overlay with lock icon centered · `var(--muted-foreground)`

### 9.5 Summary Stacks

Compact label/value pairs inside a card, separated by hairlines.

**Row anatomy:**
- Label — `13px` + `var(--font-weight-regular)` · `var(--muted-foreground)` · uppercase
- Value — `var(--text-base)` + `var(--font-weight-semibold)` · `var(--foreground)`
- Divider — 1px `var(--border-subtle)` · full width (omit after last row)

---

## 10. Lists & Rows

### 10.1 Standard List Row

**Anatomy:**
- **Leading** — `🍏 Avatar` (circular) or Emblem (squircle) · 40×40pt
- **Content** — stacked Title + Subtitle
  - Title: `var(--text-base)` + `var(--font-weight-semibold)` · `var(--foreground)`
  - Subtitle: `var(--text-label)` + `var(--font-weight-regular)` · `var(--muted-foreground)`
- **Trailing** — chevron `›` · `var(--muted-foreground)`
- **Separator** — 1px `var(--border-subtle)` left-inset to align with title (not full-bleed)
- **Press state** — background → `var(--card-hover)` · `150ms ease-in-out`

### 10.2 Transaction Row

Extends the standard list row with a right-side amount column.

**Trailing amount:**
- Credit (positive): `var(--text-base)` + `var(--font-weight-semibold)` · `var(--success)` · prefix `+`
- Debit (negative): `var(--text-base)` + `var(--font-weight-semibold)` · `var(--foreground)` · prefix `−`
- Sub-label (date/status): `var(--text-label)` + `var(--font-weight-regular)` · `var(--muted-foreground)`

### 10.3 File Upload Row

**Anatomy:**
- **Leading** — file type icon on `var(--accent)` squircle background
- **Content** — file name (`var(--text-base)` + semibold) + file size (`var(--text-label)` + `var(--muted-foreground)`)

**States:**
- **Uploading** — `var(--primary)` progress bar along bottom edge of row
- **Complete** — trailing trash icon · `var(--muted-foreground)`
- **Error** — full row border → `var(--destructive)` · trailing error icon

---

## 11. Selection Controls

### 11.1 Switch — `🍏 iOS 26+/ Switch`

**Component**: `🍏 iOS 26+/ Switch`

**Variants:**

| Prop       | Options         | Default |
|------------|-----------------|---------|
| `Selected` | `On`, `Off`     | `On`    |
| `Disabled` | `False`, `True` | `False` |

**Anatomy:**
- Track: 51×31pt pill
- Knob: white circle · slides left (Off) or right (On) · `250ms ease-out`

**Visual states:**

| Variant         | Track                    | Knob              |
|-----------------|--------------------------|-------------------|
| On, enabled     | `var(--primary)`         | white             |
| Off, enabled    | `var(--muted)`           | white             |
| On, disabled    | `var(--primary)` at 50%  | white at 50%      |
| Off, disabled   | `var(--muted)` at 50%    | white at 50%      |

### 11.2 Checkbox — `🍏 Checkbox`

**Anatomy:**
- Box: 20×20pt · `var(--radius-sm)` corners

**States:**

| State     | Fill                  | Border              | Icon             |
|-----------|-----------------------|---------------------|------------------|
| Unchecked | transparent           | `var(--border)`     | —                |
| Checked   | `var(--primary)`      | `var(--primary)`    | white checkmark  |
| Indeterminate | `var(--primary)` | `var(--primary)`    | white dash       |
| Disabled  | `var(--muted)`        | `var(--border-subtle)` | —             |

### 11.3 Chip — `🍏 Chip`

**Component**: `🍏 Chip`

**Props:**

| Prop        | Type          | Default   | Options                      |
|-------------|---------------|-----------|------------------------------|
| `label`     | Text          | `Label`   | —                            |
| `has icon`  | Boolean       | `false`   | —                            |
| `icon`      | Instance Swap | —         | 16×16 leading icon           |
| `dismissible` | Boolean    | `true`    | Shows trailing `×`           |
| `style`     | Variant       | `outline` | `outline`, `solid`           |

**Styles:**

| Style   | Fill             | Border           | Text                          |
|---------|------------------|------------------|-------------------------------|
| Outline | `var(--card)`    | `var(--border)`  | `var(--foreground)`           |
| Solid   | `var(--accent)`  | none             | `var(--accent-foreground)`    |

- Shape: `var(--radius-button)` — full pill
- Label: `var(--text-label)` + `var(--font-weight-semibold)`
- Trailing `×`: `var(--muted-foreground)` · hover `var(--foreground)`

---

## 12. Indicators & Display

### 12.1 Avatars — `🍏 Avatar`

**Shape**: Circle

**Sizes:**

| Size | Diameter |
|------|----------|
| S    | 24px     |
| M    | 32px     |
| L    | 40px     |
| XL   | 56px     |

**Content variants:**
- **Initial** — 1–2 character initials · `var(--accent)` background · `var(--accent-foreground)` text
- **Icon** — generic person icon · `var(--muted)` background · `var(--muted-foreground)` icon
- **Photo** — user-supplied image, cropped to circle

### 12.2 Emblems

Squircle (rounded-square) container with a solid icon inside. Used for financial accounts, contacts, and categories.

- Background: `var(--accent)`
- Icon: `var(--primary)` · 24×24pt centered
- Sizes match Avatar size scale

### 12.3 Badges

Compact status pills. **Not** interactive.

| Variant | Background                  | Text Color          |
|---------|-----------------------------|---------------------|
| Warning | `var(--warning-subtle)`     | `var(--warning)`    |
| Danger  | `var(--destructive-subtle)` | `var(--destructive)`|
| Success | `var(--success-subtle)`     | `var(--success)`    |
| Info    | `var(--accent)`             | `var(--accent-foreground)` |
| Neutral | `var(--muted)`              | `var(--muted-foreground)` |

- Radius: `var(--radius)` — rounded rectangle
- Padding: `4px` vertical · `12px` horizontal
- Font: `var(--text-label)` + `var(--font-weight-regular)`

### 12.4 Text Status Indicators

Inline, non-pill status labels used in list rows and detail screens.

`INACTIVE` · `LOCKED` · `CANCELLED` · `BLOCKED` · `EXPIRED`

- Leading dot or icon · text right of icon
- Font: `13px` + `var(--font-weight-semibold)`
- Color: matches badge variant (Neutral → INACTIVE, Danger → BLOCKED/CANCELLED, etc.)

### 12.5 Context Menus (iOS 26)

Triggered by long-press on any interactive element.

**Behavior:**
1. Target element scales to `transform: scale(1.05)` — `150ms ease-in-out`
2. Surrounding content blurs (Liquid Glass, §1.1) to visually isolate the target
3. Floating action sheet appears above or below the target
4. Each action item: leading icon + label · `var(--text-base)` · `var(--foreground)`
5. Destructive actions: `var(--destructive)`
6. Dismiss: tap outside or swipe down

---

## 13. Feedback & Empty States

### 13.1 Activity Indicator — `🍏 Activity Indicator`

iOS-style rotating multi-spoke wheel (8 spokes at 45° intervals).

- Default color: `var(--primary)`
- On colored backgrounds: `var(--primary-foreground)`
- Animation: continuous clockwise rotation
- Sizes: 20×20 (inline) · 24×24 (standard) · 32×32 (full-screen)

### 13.2 Shimmer / Skeleton Loaders

Used during data fetching before content is available.

- **Shape** — matches the destination element's dimensions and radius exactly
- **Base color** — `var(--muted)`
- **Animation** — left-to-right gradient sweep (`var(--card)` highlight) · `1500ms` loop
- **Usage** — replace text lines, avatars, card content; never show a spinner and a skeleton simultaneously

### 13.3 Inline Alert Banners

**Anatomy:**
- Container: card layout · `var(--elevation-sm)` · `var(--radius-card)` corners
- Background: semantic subtle variant (e.g. `var(--warning-subtle)` for warnings)
- Top section: leading semantic icon + title (`var(--text-base)` + semibold) + optional body text
- Bottom section (optional): separated by 1px `var(--border-subtle)` · contains text action link (`var(--text-label)` + semibold · `var(--primary)`)

### 13.4 Full-Page Empty States

Used when a screen has no data: No Internet, No Transactions, Success, Error.

**Anatomy (vertically centered, full-screen):**

1. **Illustration** — large 3D or flat art · 200–280px width
2. **Title** — `var(--text-h3)` + `var(--font-weight-bold)` · `var(--foreground)` · centered
3. **Subtitle** — `var(--text-base)` + `var(--font-weight-regular)` · `var(--muted-foreground)` · centered · max 2 lines
4. **Primary action** — pill button (§7.1 Primary style) · optional
5. **Secondary action** — text link (§7.3) · below primary button · optional

---

## 14. Quick Reference — Component Mapping

| Use Case               | Component Name                  |
|------------------------|---------------------------------|
| Page header with tabs  | `🍏 Tab Header`                 |
| Navigation stack       | `🍏 Navigation Controller`      |
| Bottom tab bar         | `🍏  iOS26+/Tab Bar`            |
| Segmented filter tabs  | `🍏 Segmented Control`          |
| Icon-only action       | `🍏 Icon Button`                |
| Text / link action     | `🍏 Link`                       |
| Search field           | `🍏 Search Bar / Standalone`    |
| Multi-line text input  | `🍏 Text Area`                  |
| Phone number input     | `🍏 Input Phone`                |
| Password field         | `🍏 Input Password`             |
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
- Reference every `🍏` component by its **exact** name from the library
- Apply variants and states exclusively through component properties
- Use `var(--token)` for every color, font size, font weight, radius, and shadow — values live in `theme.css`
- Apply Liquid Glass material (§1.1) to all floating and sticky elements
- Implement **all** defined states (default, hover, focus, error, disabled) for every interactive component
- Respect 44×44pt minimum tap target size for all touch interactions
- Use `var(--sidebar-foreground)` for helper text and placeholder text

**Don't:**
- Hardcode any `#hex`, `rgb()`, `rgba()`, or raw `px` size that has a corresponding CSS variable in `theme.css`
- Detach library components or manually edit their internal layers
- Use `#9747FF` — it is an internal Figma annotation / template color, not a production token
- Combine `var(--text-sm)` or `var(--text-xs)` — these variables do not exist in `theme.css`
- Skip disabled or error states for interactive components
- Mix Liquid Glass material with opaque solid backgrounds on the same floating layer
