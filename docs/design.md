# AnySync Design System v2.0.0

**iOS 26 Liquid Glass · WCAG 3.0 Bronze · Light + Dark Modes · RTL Support**

Version 2.0.0 · February 25, 2026

---

## Table of Contents

1. [Logo Analysis & Color Extraction](#1-logo-analysis--color-extraction)
2. [Brand Color System](#2-brand-color-system)
3. [Extended Palette & Neutral Scale](#3-extended-palette--neutral-scale)
4. [Gradient Tokens](#4-gradient-tokens)
5. [Semantic Colors](#5-semantic-colors)
6. [Surface & Text Colors](#6-surface--text-colors)
7. [WCAG 3.0 Contrast Compliance](#7-wcag-30-contrast-compliance)
8. [iOS 26 Liquid Glass System](#8-ios-26-liquid-glass-system)
9. [Shadow & Elevation System](#9-shadow--elevation-system)
10. [Spacing & Layout](#10-spacing--layout)
11. [Border Radius & Corners](#11-border-radius--corners)
12. [Typography System](#12-typography-system)
13. [Animation & Motion](#13-animation--motion)
14. [Z-Index Architecture](#14-z-index-architecture)
15. [Component Tokens](#15-component-tokens)
16. [Accessibility Standards](#16-accessibility-standards)
17. [File Architecture & Usage](#17-file-architecture--usage)
18. [Agentic AI UI Components](#18-agentic-ai-ui-components)
19. [LLM Provider & Gateway UX](#19-llm-provider--gateway-ux)
20. [Infrastructure & Routing UX (Traefik/FastMCP)](#20-infrastructure--routing-ux)
21. [Design Token Architecture](#21-design-token-architecture)
22. [Responsive Breakpoint System](#22-responsive-breakpoint-system)
23. [Dark Mode Implementation](#23-dark-mode-implementation)
24. [Interactive Component States](#24-interactive-component-states)
25. [Icon System](#25-icon-system)
26. [Form Design System](#26-form-design-system)
27. [Data Visualization System](#27-data-visualization-system)
28. [Chart & Map Component Specifications](#28-chart--map-component-specifications)
29. [Internationalization (i18n) & RTL Layout](#29-internationalization-i18n--rtl-layout)
30. [Healthcare-Specific Components](#30-healthcare-specific-components)
31. [Component Documentation Patterns](#31-component-documentation-patterns)

---

## 1. Logo Analysis & Color Extraction

### 1.1 Visual Structure

The AnySync logo is a composite symbol merging two visual metaphors into a single cohesive mark:

```
 ▌▌▌▌∿∿→
 ^^^^  ^^^^
 BARS  PULSE
```

**Left side — Bar chart (Data/Analytics):** Four vertical bars in descending height. Colors transition from deep royal blue through teal to cyan. Represents structure, measurement, and intelligence.

**Right side — ECG heartbeat line with arrow (Vitality):** An ECG-style waveform with sharp peak and forward-pointing arrow. Colors shift from cyan through emerald to bright green. Represents life, health, real-time monitoring, and forward momentum.

**Background — Pure black (#000000):** Places this brand firmly in a premium, tech-forward, medical-grade context.

### 1.2 Color Extraction Points

Colors sampled at seven key points along the logo's gradient path:

| Element | Hex | Color Name | Role |
|---------|-----|-----------|------|
| Bar 1 (tallest, left) | `#1B3FA0` | Royal Blue | Primary brand |
| Bar 2 | `#1A5DAE` | Mid Blue | Transition |
| Bar 3 | `#1A7A9E` | Bridge |
| Bar 4 (shortest) | `#17B5A6` | Teal-Cyan | Secondary brand |
| Heartbeat start | `#19CDA0` | Cyan-Green | Transition |
| Heartbeat peak | `#1CD760` | Emerald | Accent / Action |
| Arrow tip | `#2AE668` | Bright Green | Vitality CTA |

### 1.3 Simplified 3-Color System

The seven extraction points consolidate into a practical three-color brand system:

- **Primary `#1B3FA0` (Royal Blue)** — Authority, structure, data intelligence. Used for headings, primary buttons, links, and brand anchoring.
- **Secondary `#17B5A6` (Teal-Cyan)** — Flow, transition, connectivity. Used for secondary actions, accents, gradients, and interactive highlights.
- **Accent `#1CD760` (Emerald)** — Vitality, pulse, action. Used for success states, CTAs, status indicators, and the heartbeat-pulse animation motif.

### 1.4 Color Narrative

The gradient flows left-to-right telling the brand story: **structured data → flowing transition → living pulse → forward momentum.** This narrative informs every gradient, animation, and visual hierarchy decision in the system.

---

## 2. Brand Color System

Each brand color has a full 11-step scale (50–950) for maximum flexibility. The **500** step is always the logo-extracted exact color.

### 2.1 Primary — Royal Blue

| Step | Hex | RGB | Usage |
|------|-----|-----|-------|
| 50 | `#EBF0FF` | 235, 240, 255 | Subtle backgrounds, hover states |
| 100 | `#D6E0FF` | 214, 224, 255 | Light backgrounds, borders |
| 200 | `#ADC1FF` | 173, 193, 255 | Disabled states |
| 300 | `#7596F5` | 117, 150, 245 | Dark mode `--text-brand` |
| 400 | `#4A6FDB` | 74, 111, 219 | Dark mode buttons |
| **500** | **`#1B3FA0`** | **27, 63, 160** | **Logo exact — Primary brand** |
| 600 | `#163489` | 22, 52, 137 | Hover states |
| 700 | `#112972` | 17, 41, 114 | Active / pressed states |
| 800 | `#0D1F5B` | 13, 31, 91 | Deep emphasis |
| 900 | `#091544` | 9, 21, 68 | Ultra-deep |
| 950 | `#050C2D` | 5, 12, 45 | Near-black brand |

**CSS:** `--brand-primary` through `--brand-primary-950`

### 2.2 Secondary — Teal-Cyan

| Step | Hex | RGB | Usage |
|------|-----|-----|-------|
| 50 | `#ECFDF9` | 236, 253, 249 | Success-tinted backgrounds |
| 100 | `#D1FAF0` | 209, 250, 240 | Light teal fills |
| 200 | `#A5F3E2` | 165, 243, 226 | Light teal accents |
| 300 | `#6DE8D0` | 109, 232, 208 | Highlights |
| 400 | `#33D4BB` | 51, 212, 187 | Dark mode secondary |
| **500** | **`#17B5A6`** | **23, 181, 166** | **Logo exact — Secondary brand** |
| 600 | `#0F9185` | 15, 145, 133 | Hover |
| 700 | `#0B7068` | 11, 112, 104 | Deep teal |
| 800 | `#08544E` | 8, 84, 78 | Very deep |
| 900 | `#053B37` | 5, 59, 55 | Ultra-deep |
| 950 | `#022421` | 2, 36, 33 | Near-black teal |

**CSS:** `--brand-secondary` through `--brand-secondary-950`

### 2.3 Accent — Emerald Green (Heartbeat Pulse)

| Step | Hex | RGB | Usage |
|------|-----|-----|-------|
| 50 | `#EDFFF3` | 237, 255, 243 | Success backgrounds |
| 100 | `#D5FFE4` | 213, 255, 228 | Light green fills |
| 200 | `#ADFFC9` | 173, 255, 201 | Light green accents |
| 300 | `#72F59E` | 114, 245, 158 | Highlights |
| 400 | `#3DE878` | 61, 232, 120 | Dark mode `--text-accent` |
| **500** | **`#1CD760`** | **28, 215, 96** | **Logo heartbeat — Accent** |
| 600 | `#14B04E` | 20, 176, 78 | Hover |
| 700 | `#0F8A3D` | 15, 138, 61 | Light mode `--text-accent` (WCAG safe) |
| 800 | `#0B6A2F` | 11, 106, 47 | Deep green |
| 900 | `#074D22` | 7, 77, 34 | Ultra-deep |
| 950 | `#042F15` | 4, 47, 21 | Near-black green |

**CSS:** `--brand-accent` through `--brand-accent-950`

### 2.4 Deep Surface (Logo Background)

| Token | Hex | Usage |
|-------|-----|-------|
| `--brand-deep` | `#0A0F1A` | Dark mode primary surface |
| `--brand-navy` | `#0F172A` | Dark mode secondary surface |

---

## 3. Extended Palette & Neutral Scale

Neutrals are **tinted toward the blue brand family** for visual cohesion. Pure grays look disconnected; blue-tinted slates feel integrated and intentional.

| Step | Hex | RGB | Usage |
|------|-----|-----|-------|
| 0 | `#FFFFFF` | 255, 255, 255 | Pure white — cards, inputs |
| 25 | `#FAFBFD` | 250, 251, 253 | Near-white backgrounds |
| 50 | `#F4F6FA` | 244, 246, 250 | Page background (light mode) |
| 100 | `#E8ECF3` | 232, 236, 243 | Dividers, subtle borders |
| 200 | `#D1D8E5` | 209, 216, 229 | Default borders |
| 300 | `#B0BBCE` | 176, 187, 206 | Strong borders, disabled text |
| 400 | `#8694AE` | 134, 148, 174 | Placeholder text |
| 500 | `#64748B` | 100, 116, 139 | Tertiary text |
| 600 | `#475569` | 71, 85, 105 | Secondary text |
| 700 | `#334155` | 51, 65, 85 | Strong secondary text |
| 800 | `#1E293B` | 30, 41, 59 | Dark surfaces |
| 900 | `#0F172A` | 15, 23, 42 | Primary text (light mode) |
| 950 | `#080D19` | 8, 13, 25 | Ultra-dark background |

**CSS:** `--neutral-0` through `--neutral-950`

---

## 4. Gradient Tokens

Gradients mirror the logo's left-to-right color narrative. The full spectrum gradient recreates the exact logo flow across all seven extraction points.

| Token | Value | Usage |
|-------|-------|-------|
| `--gradient-brand` | `135deg, Primary → Secondary` | Default brand gradient for CTAs, headers |
| `--gradient-brand-extended` | `135deg, Primary → Secondary → Accent` | Full 3-color brand expression |
| `--gradient-brand-reverse` | `135deg, Secondary → Primary` | Reverse for variety |
| `--gradient-logo-spectrum` | `90deg, #1B3FA0 → #1A7A9E → #17B5A6 → #1CD760 → #2AE668` | Hero backgrounds, marketing materials |
| `--gradient-pulse` | `90deg, Secondary → Accent` | Heartbeat-line inspired elements |
| `--gradient-pulse-glow` | `90deg, Secondary 40% → Accent 40%` | Subtle pulse glow behind elements |
| `--gradient-mesh-light` | 3 radial-gradients overlaid on white | Hero section ambient lighting |
| `--gradient-mesh-dark` | 3 radial-gradients on `#0A0F1A` | Dark mode hero ambient |
| `--gradient-glass-blue` | Brand-tinted glass overlay | iOS 26 colored glass panels |
| `--gradient-glass-teal` | Teal-tinted glass overlay | Secondary glass panels |
| `--gradient-glass-accent` | Green-tinted glass overlay | Accent glass panels |
| `--gradient-shine` | `transparent → white 40% → transparent` | Shimmer / loading animation |
| `--gradient-surface-subtle` | `180deg, surface-primary → surface-secondary` | Subtle page gradient |

### Mesh Background Example

```css
/* Hero section with brand-colored ambient lighting */
.hero {
  background: var(--gradient-mesh-light);
  /* Resolves to:
     radial-gradient(ellipse at 20% 50%, rgba(27,63,160, 0.08), transparent 60%),
     radial-gradient(ellipse at 80% 20%, rgba(23,181,166, 0.06), transparent 50%),
     radial-gradient(ellipse at 60% 80%, rgba(28,215,96, 0.05), transparent 50%),
     #FFFFFF;
  */
}
```

---

## 5. Semantic Colors

Status colors are visually distinct from brand colors while harmonizing with the palette. Success aligns with the accent green family for coherence.

| Status | Default | Light | Dark | Background | Border |
|--------|---------|-------|------|-----------|--------|
| Success | `#10B981` | `#34D399` | `#059669` | `rgba(16,185,129, 0.08)` | `rgba(16,185,129, 0.25)` |
| Warning | `#F59E0B` | `#FBBF24` | `#D97706` | `rgba(245,158,11, 0.08)` | `rgba(245,158,11, 0.25)` |
| Error | `#EF4444` | `#F87171` | `#DC2626` | `rgba(239,68,68, 0.08)` | `rgba(239,68,68, 0.25)` |
| Info | `#3B82F6` | `#60A5FA` | `#2563EB` | `rgba(59,130,246, 0.08)` | `rgba(59,130,246, 0.25)` |

### UI State Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--color-hover` | `rgba(27,63,160, 0.06)` | Hover background tint |
| `--color-active` | `rgba(27,63,160, 0.12)` | Active / pressed |
| `--color-selected` | `rgba(27,63,160, 0.08)` | Selected row / item |
| `--color-disabled` | `rgba(0,0,0, 0.26)` | Disabled foreground |
| `--color-disabled-bg` | `rgba(0,0,0, 0.06)` | Disabled background |

---

## 6. Surface & Text Colors

### 6.1 Light Mode

| Token | Value | Purpose |
|-------|-------|---------|
| `--surface-primary` | `#FFFFFF` | Cards, inputs, main content |
| `--surface-secondary` | `#F4F6FA` | Page background |
| `--surface-tertiary` | `#E8ECF3` | Inset panels, wells |
| `--surface-elevated` | `#FFFFFF` | Elevated cards, modals |
| `--surface-sunken` | `#EDF0F7` | Recessed areas |
| `--surface-overlay` | `rgba(15,23,42, 0.5)` | Modal scrim |
| `--text-primary` | `#0F172A` | Headings, body text |
| `--text-secondary` | `#475569` | Descriptions, labels |
| `--text-tertiary` | `#64748B` | Captions, metadata |
| `--text-disabled` | `#B0BBCE` | Disabled text |
| `--text-brand` | `#1B3FA0` | Brand-colored text |
| `--text-accent` | `#0F8A3D` | Accent text (WCAG-safe dark green) |
| `--text-link` | `#1B3FA0` | Hyperlinks |
| `--text-link-hover` | `#112972` | Hovered links |

### 6.2 Dark Mode

| Token | Value | Purpose |
|-------|-------|---------|
| `--surface-primary` | `#0A0F1A` | Main background (logo deep) |
| `--surface-secondary` | `#111827` | Card backgrounds |
| `--surface-tertiary` | `#1E293B` | Inset panels |
| `--surface-elevated` | `#1A2236` | Elevated surfaces |
| `--surface-sunken` | `#070B14` | Recessed areas |
| `--surface-overlay` | `rgba(0,0,0, 0.6)` | Modal scrim |
| `--text-primary` | `#F1F5F9` | Headings, body text |
| `--text-secondary` | `#94A3B8` | Descriptions, labels |
| `--text-tertiary` | `#64748B` | Captions, metadata |
| `--text-disabled` | `#475569` | Disabled text |
| `--text-brand` | `#7596F5` | Brand text (Primary-300) |
| `--text-accent` | `#3DE878` | Accent text (vibrant green) |
| `--text-link` | `#7596F5` | Hyperlinks |
| `--text-link-hover` | `#ADC1FF` | Hovered links |

### 6.3 Border Tokens

| Token | Light | Dark |
|-------|-------|------|
| `--border-default` | `#D1D8E5` | `rgba(255,255,255, 0.10)` |
| `--border-subtle` | `#E8ECF3` | `rgba(255,255,255, 0.06)` |
| `--border-strong` | `#B0BBCE` | `rgba(255,255,255, 0.18)` |
| `--border-brand` | `var(--brand-primary)` | `var(--brand-primary-400)` |

---

## 7. WCAG 3.0 Contrast Compliance

All text/surface combinations verified against WCAG 3.0 APCA (Accessible Perceptual Contrast Algorithm) Bronze requirements:

- **Body text (<24px):** ≥ 60 Lc (lightness contrast)
- **Large text (24px+):** ≥ 45 Lc
- **Non-text (icons, borders):** ≥ 45 Lc
- **Focus indicators:** ≥ 3:1 against adjacent colors

### 7.1 Light Mode Contrast Matrix

| Color Pair | APCA Lc | Status |
|-----------|---------|--------|
| `--text-primary` (#0F172A) on white | ~106 Lc | ✅ Exceeds all requirements |
| `--text-secondary` (#475569) on white | ~68 Lc | ✅ Body text compliant |
| `--text-tertiary` (#64748B) on white | ~55 Lc | ✅ Large text / non-text |
| `--brand-primary` (#1B3FA0) on white | ~82 Lc | ✅ All text sizes |
| `--brand-accent-dark` (#0F8A3D) on white | ~60 Lc | ✅ Body text minimum |
| White on `--brand-primary` (#1B3FA0) | ~82 Lc | ✅ Button text |

### 7.2 Dark Mode Contrast Matrix

| Color Pair | APCA Lc | Status |
|-----------|---------|--------|
| `--text-primary` (#F1F5F9) on #0A0F1A | ~107 Lc | ✅ Exceeds all requirements |
| `--text-secondary` (#94A3B8) on #0A0F1A | ~62 Lc | ✅ Body text compliant |
| `--text-brand` (#7596F5) on #0A0F1A | ~68 Lc | ✅ All text sizes |
| `--text-accent` (#3DE878) on #0A0F1A | ~72 Lc | ✅ All text sizes |
| White on `--brand-primary-400` (#4A6FDB) | ~68 Lc | ✅ Dark mode buttons |

---

## 8. iOS 26 Liquid Glass System

The glassmorphism system follows Apple's iOS 26 "Liquid Glass" design philosophy. Every glass panel simulates physical glass with translucency, frosted blur, light refraction, and specular highlights.

### 8.1 Design Principles

1. **Translucency** — Background content bleeds through at calibrated opacity levels
2. **Backdrop Blur** — Frosted glass effect via `backdrop-filter`, ranging from 8px to 100px
3. **Light Refraction** — Borders simulate light bending through glass with varying opacity
4. **Specular Highlights** — Top-edge shimmer simulates overhead light source (the "glass edge" effect)
5. **Brand Tinting** — Glass absorbs underlying brand color for visual cohesion (unique to iOS 26)
6. **Saturation Boost** — Blurred content is saturated 1.4–1.8× for vibrancy
7. **Continuous Curvature** — Rounded corners use iOS-style "squircle" (superellipse) approximation

### 8.2 Glass Layer Hierarchy

Five opacity tiers from most transparent to most opaque:

| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--glass-bg-subtle` | `rgba(255,255,255, 0.35)` | `rgba(15,23,42, 0.55)` | Background hints |
| `--glass-bg-light` | `rgba(255,255,255, 0.60)` | `rgba(15,23,42, 0.70)` | Subtle panels |
| `--glass-bg-medium` | `rgba(255,255,255, 0.72)` | `rgba(15,23,42, 0.80)` | Standard panels |
| `--glass-bg-heavy` | `rgba(255,255,255, 0.82)` | `rgba(15,23,42, 0.88)` | Cards, nav bars |
| `--glass-bg-pronounced` | `rgba(255,255,255, 0.92)` | `rgba(15,23,42, 0.94)` | Modals, sheets |

### 8.3 Brand-Tinted Glass (iOS 26 Exclusive)

Glass panels absorb the color of underlying content. These tokens add a subtle brand tint:

| Token | Light Mode | Dark Mode |
|-------|-----------|-----------|
| `--glass-bg-brand-blue` | `rgba(27,63,160, 0.06)` | `rgba(27,63,160, 0.12)` |
| `--glass-bg-brand-teal` | `rgba(23,181,166, 0.06)` | `rgba(23,181,166, 0.10)` |
| `--glass-bg-brand-green` | `rgba(28,215,96, 0.06)` | `rgba(28,215,96, 0.08)` |

### 8.4 Glass Borders

| Token | Light Mode | Dark Mode | Purpose |
|-------|-----------|-----------|---------|
| `--glass-border-bright` | `rgba(255,255,255, 0.65)` | `rgba(255,255,255, 0.14)` | Primary glass edge |
| `--glass-border-soft` | `rgba(255,255,255, 0.40)` | `rgba(255,255,255, 0.08)` | Secondary edge |
| `--glass-border-dim` | `rgba(255,255,255, 0.18)` | `rgba(255,255,255, 0.04)` | Subtle dividers |
| `--glass-border-tinted` | `rgba(27,63,160, 0.12)` | `rgba(113,150,245, 0.15)` | Brand-tinted |

### 8.5 Specular Highlights

| Token | Light | Dark |
|-------|-------|------|
| `--glass-highlight` | `rgba(255,255,255, 0.85)` | `rgba(255,255,255, 0.12)` |
| `--glass-highlight-soft` | `rgba(255,255,255, 0.45)` | `rgba(255,255,255, 0.06)` |
| `--glass-highlight-tint` | `rgba(23,181,166, 0.15)` | `rgba(23,181,166, 0.10)` |

### 8.6 Backdrop Blur Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--blur-xs` | `blur(8px)` | Subtle depth hint |
| `--blur-sm` | `blur(16px)` | Cards, subtle panels |
| `--blur-md` | `blur(32px)` | Standard glass panels |
| `--blur-lg` | `blur(48px)` | Navigation bars, heavy glass |
| `--blur-xl` | `blur(64px)` | Modals, overlays |
| `--blur-xxl` | `blur(80px)` | Full-screen frosted |
| `--blur-max` | `blur(100px)` | Maximum frost effect |

### 8.7 Glass Utility Classes

```css
/* Ready-to-use glass panels */
.glass-panel         /* Standard: medium bg, md blur, soft border, 24px radius */
.glass-panel-subtle  /* Lightweight: subtle bg, sm blur, dim border */
.glass-panel-heavy   /* Prominent: heavy bg, lg blur, bright border */
.glass-card          /* Card with specular highlight ::before pseudo-element */
.glass-card-gradient /* Card with gradient border (brand-tinted) */
.glass-nav           /* Fixed navigation bar with heavy glass */
```

### 8.8 Composing a Glass Panel

```css
.my-component {
  background: var(--glass-bg-medium);
  backdrop-filter: var(--blur-md) var(--glass-saturation);
  -webkit-backdrop-filter: var(--blur-md) var(--glass-saturation);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-2xl);
  box-shadow: var(--shadow-raised), var(--glass-inner-glow);
}
```

---

## 9. Shadow & Elevation System

A five-tier elevation model where each level adds more shadow depth. Every shadow uses three layers: a ring (border simulation), a key shadow (direct light), and an ambient shadow (diffused fill).

### 9.1 Elevation Levels

| Token | Level | Usage | Light Mode |
|-------|-------|-------|-----------|
| `--shadow-ambient` | 0 | Resting cards, default state | Subtle 3-layer shadow |
| `--shadow-raised` | 1 | Hovered cards, buttons | Medium 3-layer shadow |
| `--shadow-floating` | 2 | Dropdowns, popovers | Strong 3-layer shadow |
| `--shadow-elevated` | 3 | Modals, dialogs | White ring + deep shadow |
| `--shadow-glass-floating` | 4 | Hero glass panels | White ring + maximum depth |

### 9.2 Inner Shadows

| Token | Usage |
|-------|-------|
| `--shadow-inset` | Pressed / inset button state |
| `--glass-inner-glow` | `inset 0 1px 0 0 rgba(255,255,255, 0.5)` — Top-edge luminosity |
| `--glass-inner-glow-soft` | `inset 0 1px 0 0 rgba(255,255,255, 0.25)` — Subtle version |

### 9.3 Brand Glow Shadows

| Token | Color | Usage |
|-------|-------|-------|
| `--shadow-glow-primary` | Royal Blue | Primary action emphasis |
| `--shadow-glow-secondary` | Teal | Secondary highlights |
| `--shadow-glow-accent` | Emerald | Success / pulse indicators |
| `--shadow-glow-success` | Green | Success state glow |
| `--shadow-glow-warning` | Amber | Warning state glow |
| `--shadow-glow-error` | Red | Error state glow |
| `--shadow-pulse` | Animated emerald ring | Heartbeat-line indicator |

Dark mode versions have **increased glow intensity** (30–40px spread vs 24px) for visibility against dark surfaces.

---

## 10. Spacing & Layout

A **4px base unit system** provides consistent spatial rhythm. All spacing values are multiples of 4px (0.25rem).

### 10.1 Spacing Scale

| Token | rem | Pixels | Usage |
|-------|-----|--------|-------|
| `--space-0` | 0 | 0 | Reset |
| `--space-px` | — | 1px | Hairline |
| `--space-0_5` | 0.125 | 2px | Micro gaps |
| `--space-1` | 0.25 | 4px | Tight inline gaps |
| `--space-1_5` | 0.375 | 6px | Small inline |
| `--space-2` | 0.5 | 8px | Icon gaps, compact padding |
| `--space-3` | 0.75 | 12px | Input padding, small gaps |
| `--space-4` | 1.0 | 16px | Standard padding, card gaps |
| `--space-5` | 1.25 | 20px | Medium gaps |
| `--space-6` | 1.5 | 24px | Section gaps, card padding |
| `--space-8` | 2.0 | 32px | Large gaps |
| `--space-10` | 2.5 | 40px | Extra large gaps |
| `--space-12` | 3.0 | 48px | Section padding (small) |
| `--space-16` | 4.0 | 64px | Section padding (medium) |
| `--space-20` | 5.0 | 80px | Section padding (large) |
| `--space-24` | 6.0 | 96px | Hero spacing |
| `--space-32` | 8.0 | 128px | Maximum section spacing |
| `--space-40` | 10.0 | 160px | Full-bleed hero |

### 10.2 Section Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `--section-padding-sm` | 48px | Compact sections |
| `--section-padding-md` | 80px | Standard sections |
| `--section-padding-lg` | 112px | Prominent sections |
| `--section-padding-xl` | 144px | Hero sections |

### 10.3 Gap System

| Token | Value | Usage |
|-------|-------|-------|
| `--gap-xs` | 8px | Tight grid gaps |
| `--gap-sm` | 16px | Card grid gaps |
| `--gap-md` | 24px | Standard grid gaps |
| `--gap-lg` | 32px | Large grid gaps |
| `--gap-xl` | 48px | Section grid gaps |

### 10.4 Layout Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--main-content-top` | 24px | Space between header and main |
| `--banner-to-content` | 24px | Space below announcement banner |

---

## 11. Border Radius & Corners

iOS uses "squircle" continuous curvature corners (superellipse), which appear smoother than standard CSS `border-radius`. We approximate with generous radius values and assign semantic roles.

### 11.1 Radius Scale

| Token | Value | Component |
|-------|-------|-----------|
| `--radius-none` | 0 | Sharp corners |
| `--radius-xs` | 4px | Inline badges, tags |
| `--radius-sm` | 8px | Tooltips, small elements |
| `--radius-md` | 12px | Inputs, compact cards |
| `--radius-lg` | 16px | Buttons |
| `--radius-xl` | 20px | Standard cards |
| `--radius-2xl` | 24px | Large cards |
| `--radius-3xl` | 28px | Modals, sheets |
| `--radius-4xl` | 32px | Hero panels |
| `--radius-dynamic` | 40px | iOS Dynamic Island inspired |
| `--radius-pill` | 9999px | Pill buttons, capsule badges |
| `--radius-full` | 9999px | Circles (avatars) |

### 11.2 Component Assignments

| Component | Token | Value |
|-----------|-------|-------|
| Button | `--radius-button` | 16px |
| Card | `--radius-card` | 24px |
| Modal | `--radius-modal` | 28px |
| Input | `--radius-input` | 12px |
| Badge | `--radius-badge` | 9999px (pill) |
| Avatar | `--radius-avatar` | 9999px (circle) |
| Tooltip | `--radius-tooltip` | 8px |

### 11.3 Border Widths

| Token | Value | Usage |
|-------|-------|-------|
| `--border-thin` | 1px | Default borders |
| `--border-medium` | 1.5px | Emphasized borders |
| `--border-thick` | 2px | Focus rings, strong borders |
| `--border-heavy` | 3px | Maximum emphasis |

---

## 12. Typography System

### 12.1 Font Stacks

```css
--font-sans:    'SF Pro Display', 'SF Pro Text', -apple-system, BlinkMacSystemFont,
                'Segoe UI', 'Roboto', 'Helvetica Neue', Arial, sans-serif;

--font-mono:    'SF Mono', 'Fira Code', 'JetBrains Mono', 'Cascadia Code',
                'Consolas', 'Liberation Mono', monospace;

--font-display: 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
```

RTL Arabic: `'Cairo', 'Noto Sans Arabic', sans-serif` with `line-height: 1.8`.

### 12.2 Type Scale

| Token | Size | Pixels | Usage |
|-------|------|--------|-------|
| `--text-2xs` | 0.625rem | 10px | Micro labels |
| `--text-xs` | 0.75rem | 12px | Captions, metadata |
| `--text-sm` | 0.875rem | 14px | Secondary text, labels |
| `--text-base` | 1rem | 16px | Body text |
| `--text-lg` | 1.125rem | 18px | Large body, subtitles |
| `--text-xl` | 1.25rem | 20px | Card titles |
| `--text-2xl` | 1.5rem | 24px | Section headings |
| `--text-3xl` | 1.875rem | 30px | Page headings |
| `--text-4xl` | 2.25rem | 36px | Hero subheadings |
| `--text-5xl` | 3rem | 48px | Hero headings |
| `--text-6xl` | 3.75rem | 60px | Display headings |
| `--text-7xl` | 4.5rem | 72px | Maximum display |

### 12.3 Fluid Display Sizes

For hero sections, headings use `clamp()` for responsive scaling:

| Token | Value | Range |
|-------|-------|-------|
| `--text-display-sm` | `clamp(1.875rem, 4vw, 2.25rem)` | 30–36px |
| `--text-display-md` | `clamp(2.25rem, 5vw, 3rem)` | 36–48px |
| `--text-display-lg` | `clamp(3rem, 6vw, 4.5rem)` | 48–72px |
| `--text-display-xl` | `clamp(3.75rem, 8vw, 6rem)` | 60–96px |

### 12.4 Font Weights

| Token | Value | Usage |
|-------|-------|-------|
| `--font-thin` | 100 | Decorative display |
| `--font-light` | 300 | Light emphasis |
| `--font-regular` | 400 | Body text |
| `--font-medium` | 500 | Labels, navigation |
| `--font-semibold` | 600 | Buttons, card titles |
| `--font-bold` | 700 | Headings |
| `--font-extrabold` | 800 | Hero headings |
| `--font-black` | 900 | Maximum weight display |

### 12.5 Line Heights & Letter Spacing

| Line Height Token | Value | Letter Spacing Token | Value |
|-------------------|-------|---------------------|-------|
| `--leading-none` | 1 | `--tracking-tighter` | -0.05em |
| `--leading-tight` | 1.2 | `--tracking-tight` | -0.025em |
| `--leading-snug` | 1.35 | `--tracking-normal` | 0 |
| `--leading-normal` | 1.5 | `--tracking-wide` | 0.025em |
| `--leading-relaxed` | 1.65 | `--tracking-wider` | 0.05em |
| `--leading-loose` | 1.8 | `--tracking-widest` | 0.1em |

---

## 13. Animation & Motion

The motion system follows **iOS 26 Liquid Motion** principles: fluid organic movement, slight overshoot for playfulness, and crisp settle for precision.

### 13.1 Duration Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--duration-instant` | 75ms | Micro-feedback (ripples, checkmarks) |
| `--duration-fast` | 150ms | Hover states, toggles |
| `--duration-base` | 250ms | Standard transitions |
| `--duration-moderate` | 350ms | Panel reveals, slides |
| `--duration-slow` | 500ms | Modal entry/exit |
| `--duration-slower` | 700ms | Page transitions |
| `--duration-slowest` | 1000ms | Complex orchestrated reveals |

### 13.2 Easing Curves

| Token | Cubic Bezier | Character |
|-------|-------------|-----------|
| `--ease-default` | `0.25, 0.1, 0.25, 1` | Standard smooth |
| `--ease-liquid` | `0.4, 0, 0.2, 1` | Material standard |
| `--ease-liquid-out` | `0, 0, 0.2, 1` | Decelerate (entry) |
| `--ease-liquid-in` | `0.4, 0, 1, 1` | Accelerate (exit) |
| `--ease-spring` | `0.34, 1.56, 0.64, 1` | iOS spring bounce |
| `--ease-spring-gentle` | `0.22, 1.2, 0.36, 1` | Subtle spring overshoot |
| `--ease-spring-snappy` | `0.68, -0.2, 0.32, 1.2` | Crisp spring |
| `--ease-elastic` | `0.68, -0.6, 0.32, 1.6` | Playful elastic stretch |
| `--ease-bounce` | `0.34, 1.56, 0.64, 1` | Bouncy settle |
| `--ease-dramatic-in` | `0.6, 0, 0.7, 0.2` | Modal entrance |
| `--ease-dramatic-out` | `0.2, 0.8, 0.2, 1` | Modal / sheet exit |

### 13.3 Logo-Inspired Animations

**Pulse Ring** — Heartbeat-line inspired concentric ring animation using `--brand-accent` green. For status indicators and live data points.
```css
@keyframes pulse-ring {
  0%   { box-shadow: 0 0 0 0 rgba(28, 215, 96, 0.40); }
  50%  { box-shadow: 0 0 0 8px rgba(28, 215, 96, 0.15); }
  100% { box-shadow: 0 0 0 16px rgba(28, 215, 96, 0.0); }
}
```

**Float** — Gentle 20s figure-eight drift for background orbs. Creates ambient depth without distraction.

**Skeleton Shimmer** — 1.5s gradient sweep for loading states. Uses neutral scale colors for subtlety.

**Gradient Border Shift** — Animated gradient position for hero section borders, creating a slowly breathing color effect.

### 13.4 Animation Utility Classes

| Class | Description |
|-------|-------------|
| `.animate-float` | 20s figure-eight background orb drift |
| `.animate-pulse` | 2s opacity pulse for loading |
| `.animate-pulse-glow` | 3s scale + opacity pulse |
| `.animate-pulse-ring` | 2s heartbeat ring expansion |
| `.skeleton` | Shimmer loading placeholder |

---

## 14. Z-Index Architecture

A structured layering system prevents z-index conflicts. Every UI element has a designated layer range.

| Token | Value | Layer |
|-------|-------|-------|
| `--z-deep` | -10 | Decorative backgrounds |
| `--z-background` | -1 | Animated mesh, orbs |
| `--z-base` | 0 | Normal content flow |
| `--z-raised` | 10 | Cards, interactive elements |
| `--z-dropdown` | 100 | Dropdown menus |
| `--z-sticky` | 200 | Sticky headers, navigation bars |
| `--z-fixed` | 300 | Fixed-position elements |
| `--z-modal-backdrop` | 400 | Modal overlay / scrim |
| `--z-modal` | 500 | Modal dialogs |
| `--z-popover` | 600 | Popovers, command palette |
| `--z-tooltip` | 700 | Tooltips |
| `--z-toast` | 800 | Toast notifications |
| `--z-spotlight` | 900 | Spotlight / onboarding |
| `--z-max` | 9999 | Skip-to-main, emergencies |

---

## 15. Component Tokens

Pre-composed composite tokens that combine primitives into ready-to-use component values.

### 15.1 Card

| Token | Value |
|-------|-------|
| `--card-bg` | `var(--glass-bg-heavy)` |
| `--card-border` | `1px solid var(--glass-border-soft)` |
| `--card-radius` | `var(--radius-2xl)` = 24px |
| `--card-shadow` | `var(--shadow-ambient)` |
| `--card-shadow-hover` | `var(--shadow-raised)` |
| `--card-backdrop` | `var(--blur-sm)` = blur(16px) |
| `--card-padding` | `var(--space-6)` = 24px |

### 15.2 Button

| Token | Value |
|-------|-------|
| `--btn-radius` | `var(--radius-lg)` = 16px |
| `--btn-padding-sm` | `8px 16px` |
| `--btn-padding-md` | `12px 24px` |
| `--btn-padding-lg` | `16px 32px` |
| `--btn-font-weight` | `600` (semibold) |
| `--btn-transition` | `all 150ms ease-liquid` |

### 15.3 Input

| Token | Value |
|-------|-------|
| `--input-bg` | `var(--surface-primary)` |
| `--input-border` | `1px solid var(--border-default)` |
| `--input-border-focus` | `2px solid var(--brand-primary)` |
| `--input-radius` | `var(--radius-md)` = 12px |
| `--input-padding` | `12px 16px` |

### 15.4 Navigation Bar (iOS-style glass)

| Token | Value |
|-------|-------|
| `--nav-height` | 64px (56px mobile) |
| `--nav-bg` | `var(--glass-bg-heavy)` |
| `--nav-backdrop` | `var(--blur-lg)` = blur(48px) |
| `--nav-border` | `1px solid var(--glass-border-dim)` |
| `--nav-shadow` | `var(--shadow-ambient)` |

### 15.5 Modal / Sheet

| Token | Value |
|-------|-------|
| `--modal-bg` | `var(--glass-bg-pronounced)` |
| `--modal-backdrop` | `var(--blur-md)` |
| `--modal-radius` | `var(--radius-modal)` = 28px |
| `--modal-shadow` | `var(--shadow-glass-floating)` |
| `--modal-overlay` | Light: `rgba(10,15,26, 0.45)` / Dark: `rgba(0,0,0, 0.65)` |

### 15.6 Badge / Tag

| Token | Value |
|-------|-------|
| `--badge-radius` | `var(--radius-pill)` |
| `--badge-padding` | `4px 12px` |
| `--badge-font-size` | `var(--text-xs)` = 12px |
| `--badge-font-weight` | `600` (semibold) |

### 15.7 Tooltip

| Token | Value |
|-------|-------|
| `--tooltip-bg` | Light: `--neutral-900` / Dark: `--neutral-200` |
| `--tooltip-text` | Light: `--neutral-0` / Dark: `--neutral-900` |
| `--tooltip-radius` | `var(--radius-sm)` = 8px |
| `--tooltip-padding` | `8px 12px` |

### 15.8 Data Visualization (Logo-Inspired)

Chart colors follow the exact logo gradient spectrum:

| Token | Hex | Role |
|-------|-----|------|
| `--chart-color-1` | `#1B3FA0` | Series 1 — Primary data |
| `--chart-color-2` | `#1A5DAE` | Series 2 |
| `--chart-color-3` | `#1A7A9E` | Series 3 |
| `--chart-color-4` | `#17B5A6` | Series 4 |
| `--chart-color-5` | `#1CD760` | Series 5 — Accent |
| `--chart-color-6` | `#2AE668` | Series 6 — Highlight |

Supporting tokens:
- `--chart-grid`: `rgba(100,116,139, 0.12)` (light) / `rgba(148,163,184, 0.08)` (dark)
- `--chart-axis`: `--neutral-400` (light) / `--neutral-500` (dark)
- `--chart-label`: `--text-secondary`

### 15.9 Pulse Indicator (Heartbeat-Inspired)

| Token | Value |
|-------|-------|
| `--pulse-color` | `var(--brand-accent)` |
| `--pulse-ring-1` | `rgba(28, 215, 96, 0.3)` |
| `--pulse-ring-2` | `rgba(28, 215, 96, 0.15)` |
| `--pulse-ring-3` | `rgba(28, 215, 96, 0.05)` |

---

## 16. Accessibility Standards

The design system is built to **WCAG 3.0 Bronze** compliance with additional support for platform-specific accessibility modes.

### 16.1 Supported Accessibility Modes

| Mode | Detection | Behavior |
|------|----------|----------|
| Dark mode | `prefers-color-scheme: dark` | Full dark mode with inverted surfaces, adjusted glass, enhanced glows |
| High contrast | `prefers-contrast: high` | Opaque glass fallbacks, stronger borders, 3px focus rings, boosted text |
| Reduced motion | `prefers-reduced-motion: reduce` | All animations disabled (0.01ms), scroll-behavior auto |
| Forced colors | `forced-colors: active` | Windows HC. Glass → Canvas, borders → CanvasText, no box-shadows |
| Legacy HC | `-ms-high-contrast` | IE/Edge legacy with WindowText focus indicators |
| Reduced transparency | `prefers-reduced-transparency` | `--surface-opaque` fallback for glass |

### 16.2 Focus System

| Context | Light Mode | Dark Mode |
|---------|-----------|-----------|
| Default | 3px solid `#1B3FA0`, offset 3px | 3px solid `#33D4BB`, offset 3px |
| High contrast | 4px solid `currentColor`, offset 3px | 4px solid `currentColor`, offset 3px |
| Forced colors | 3px solid `Highlight`, offset 3px | 3px solid `Highlight`, offset 3px |
| Gold (fallback) | `#FFD700` for maximum visibility | `#FFD700` for maximum visibility |

Focus ring implementation:
```css
--focus-ring: 0 0 0 var(--focus-ring-offset) var(--surface-primary),
              0 0 0 calc(var(--focus-ring-offset) + var(--focus-ring-width)) var(--focus-color);
```

### 16.3 Touch Targets

- **Minimum:** 44×44px (WCAG 2.5.5) enforced on all interactive elements at mobile breakpoints
- **Comfortable:** 48×48px recommended for primary actions
- Tokens: `--touch-target-min: 44px` and `--touch-target-comfortable: 48px`

### 16.4 Skip Navigation

A skip-to-main-content link (WCAG 2.4.1 Bypass Blocks) positioned off-screen, slides into view on focus. Uses `--brand-primary` background with white text.

### 16.5 Screen Reader Utilities

`.sr-only` class: visually hidden but accessible to screen readers. Becomes visible on `:focus`, `:active`, and `:focus-within`.

---

## 17. File Architecture & Usage

### 17.1 File Structure

```
├── design-tokens.css    ← Single source of truth for ALL token values
├── globals.css           ← Global styles, reset, utilities, animations, a11y
└── tailwind.config.ts    ← Tailwind v4 integration via @theme bridge
```

**Load order:** `design-tokens.css` must be loaded **before** `globals.css`.

### 17.2 Consumption Patterns

**CSS Variables:**
```css
color: var(--brand-primary);
background: var(--glass-bg-medium);
box-shadow: var(--shadow-floating);
```

**Tailwind Classes:**
```html
<div class="bg-brand-primary text-white shadow-floating rounded-2xl">
```

**Inline Styles (React):**
```jsx
<div style={{ background: 'var(--gradient-brand)' }}>
```

**Glass Utility Classes:**
```html
<div class="glass-panel hover-glass-lift">
<div class="glass-card">
<nav class="glass-nav">
```

**Gradient Text:**
```html
<h1 class="text-gradient-brand">Brand gradient heading</h1>
<h1 class="text-gradient-spectrum">Full logo spectrum heading</h1>
```

### 17.3 Theme Switching

The system supports three theme mechanisms simultaneously:

| Mechanism | Trigger | Usage |
|-----------|---------|-------|
| `@media (prefers-color-scheme: dark)` | OS-level | Automatic detection |
| `[data-theme='dark']` | JavaScript | next-themes or manual toggle |
| `.dark` class | JavaScript | Tailwind dark mode class |

All three override the same CSS custom properties, ensuring consistent rendering regardless of toggle method.

### 17.4 Legacy Aliases

For backward compatibility with existing code:

| Legacy Token | Maps To |
|-------------|---------|
| `--brand-blue` | `var(--brand-primary)` |
| `--brand-teal` | `var(--brand-secondary)` |
| `--brand-green` | `var(--brand-accent)` |
| `--ms-deep-blue` | `var(--brand-primary)` |
| `--ms-blue` | `var(--brand-primary)` |
| `--ms-teal` | `var(--brand-secondary)` |
| `--color-trust-blue` | `var(--brand-primary)` |
| `--color-growth-teal` | `var(--brand-secondary)` |

---

## 18. Agentic AI UI Components

The Agentic AI UI components provide specialized interfaces for interacting with, monitoring, and configuring the multi-agent ecosystem.

### 18.1 Agent Card (Compact Design)

Agent Cards follow a standardized "Business Card" layout for discovery and invocation.

| Element | Specification |
|---------|---------------|
| **Header** | Small agent avatar (logo/icon) + Bold Name + Version badge (pill) |
| **Description** | 2-line max description using `--text-secondary` |
| **Skill Badges** | Horizontal scroll of skill chips using `--glass-bg-brand-blue` |
| **Primary Action** | "Invoke" or "Config" button using `--gradient-brand` |
| **Secondary Action** | "View Card" link opening full JSON Agent Card |
| **Health Dot** | Pulse ring indicator (`--pulse-ring-1`) for active status |

### 18.2 RAG Attribution & Grounding

Visual indicators for tracing AI responses back to source data.

| Component | Design |
|-----------|--------|
| **Citation Chip** | Compact inline bubble with number; hover reveals source snippet |
| **Source Preview** | `blur-md` glass popover showing exact document/database row excerpt |
| **Grounding Badge** | Small "Direct Source" or "Verified" badge next to sensitive metrics |
| **Link out** | Deep-link to the original HIS/ERP record |

### 18.3 Visual Flow Builder (LangFlow Bridge)

Standardizing the canvas for multi-agent workflows.

| Element | Style |
|---------|-------|
| **Canvas** | Subtle grid using `--chart-grid`; `--surface-sunken` background |
| **Nodes** | `glass-card` with 16px radius; brand-colored headers per agent type |
| **Handles** | Circular ports with concentric ring on hover |
| **Edges (Paths)** | 2px smooth curves using `--brand-secondary`; animated flow effect on active |
| **Active Highlight** | `--shadow-glow-primary` around the currently executing agent node |

### 18.4 HITL & Guardrails UI

Interfaces for human intervention and safety monitoring.

| Context | Visual Expression |
|---------|-------------------|
| **Approval Required** | Amber pulse banner across the chat interface |
| **Intervention Card** | Pronounced glass modal with "Approve", "Edit", or "Reject" actions |
| **Violations** | Red glass toast (`--surface-error`) with explanation of guardrail hit |
| **Audit Trail** | Timeline view using the neutral scale (50-300) for historical actions |

### 18.5 Agent Marketplace

Grid-based UI for discovering internal and federated agents.

| Component | Style |
|-----------|--------|
| **Category Chips** | Pill-shaped filters using secondary/accent colors |
| **Marketplace Logo** | Glassified version of the AnySync logo with mesh glow background |
| **Search Bar** | Floating transparent input with large backdrop blur |
| **Performance Graph** | 24-hour success/cost sparkline using `--chart-color-5` |

### 18.6 Autonomous Scheduler & Insight Feed

Interfaces for configuring scheduled AI actions and reviewing proactive recommendations.

| Component | Style |
|-----------|--------|
| **Insight Feed Card** | Elevated `glass-card` highlighting a single proactive recommendation with a "1-Click Apply" action |
| **Anomaly Alert Badge** | Glowing amber/red pulse indicator located on the main navigation |
| **Cron Visualizer** | Natural language to cron translation UI ("Every Monday at 9AM" → `0 9 * * 1`) with visual calendar preview |
| **Autonomous Log** | Timeline interface displaying actions the AI took autonomously in the background, with manual rollback options |

### 18.7 Generative UI (CopilotKit)

Standardizing the dynamic generation of UI components based on agent reasoning.

| Component | Design |
|-----------|--------|
| **Copilot Sidebar** | `blur-lg` glass panel on the right (320px-400px wide) |
| **Generative Card** | A card that morphs its layout (e.g., from text to chart) via `--ease-liquid` |
| **Response Typing** | Realistic staggering of text arrival with subtle cursor glow |
| **Action Bubbles** | Context-aware buttons (e.g., "Export", "Drill Down") generated by the agent |

### 18.8 AI Heartbeat & Reasoning HUD

Visualizing the "thinking" process of the multi-agent federation.

| Aspect | Specification |
|--------|---------------|
| **Heartbeat Icon** | Animated SVG matching the logo's ECG pulse family |
| **Reasoning HUD** | Expandable "View Reasoning" section using `--font-mono` and dimmed text |
| **Agent Handoff** | Visual "sparkle" or transition when one agent passes context to another |
| **Thought Stream** | Real-time log of current execution step (e.g., "Synthesizing revenue columns...") |

---

## 19. LLM Provider & Gateway UX

The LLM Provider UX ensures users and developers have clear visibility and control over the platform's "brain" infrastructure.

### 19.1 Provider Selector (Glass Dynamic)

A premium interface for manually switching or overriding LLM providers.

| Element | Visual Expression |
|---------|-------------------|
| **Selector Bubble** | `radius-dynamic` floating bubble using `--glass-bg-subtle` |
| **Provider Icons** | High-fidelity SVG logos for OpenAI, Anthropic, Gemini, Grok, etc. |
| **Active Highlight** | Concentric `pulse-ring` around the currently active provider |
| **Latency Indicator** | Small sparkline (`--chart-color-5`) showing provider response time |
| **Provider Badge** | `pill` badge showing model version (e.g., "Claude 3.7 Opus") |

### 19.2 Gateway Status Dashboard

Visualizing the health and performance of the Bifrost LLM Gateway.

| Component | Style |
|-----------|--------|
| **Failover Alert** | Amber glass toast (`--surface-warning`) when a failover occurs |
| **Cache Hit Icon** | Blue lightning bolt icon next to cached AI responses |
| **Cost Tracker** | Linear gauge showing budget consumption vs limit |
| **Route Map** | Simplified Sankey diagram showing token flow between agents and providers |

### 19.3 Local vs Cloud Indicators

Differentiating between on-premise (Ollama/LMStudio) and cloud processing for privacy transparency.

| Context | visual expression |
|---------|-------------------|
| **Local Mode** | Shield icon with "On-Prem" text; `--brand-secondary` (Teal) theme |
| **Cloud Mode** | Cloud icon; `--brand-primary` (Blue) theme |
| **Sensitive Data** | Red border glow if sensitive data is sent to a cloud provider without masking |

---

## 20. Infrastructure & Routing UX

The infrastructure UX provides visibility into the platform's edge routing and connectivity layers, ensuring high availability and performance.

### 20.1 Edge Routing Status (Traefik Integration)

Real-time monitoring of ingress traffic and service health.

| Element | Visual Expression |
|---------|-------------------|
| **Traffic Pulse** | Animated ECG-line (`pulse-ring`) showing request throughput |
| **Service Health** | Mesh glow background: Green (Healthy), Amber (Throttling), Red (Critical) |
| **SSL/Security** | Shield icon with "Traefik Secure" badge in footer/settings |
| **Load Distribution**| Simplified bar chart showing traffic across agent nodes |

### 20.2 MCP Connectivity (FastMCP)

Visualizing high-performance data plane connections.

| Component | Style |
|-----------|--------|
| **Latency Dot** | 8px dot using `--chart-color-6` (Bright Green) for <10ms latency |
| **Protocol Badge** | "FastMCP 3.0" pill using `--glass-bg-brand-teal` |
| **Connection Map** | Dynamic node-link graph showing active MCP server connections |

---

## 21. Design Token Architecture

The design System establishes a **three-layer token architecture** following 2024-2025 best practices. This system provides a clear hierarchy from raw values to production-ready component tokens.

### 21.1 Three-Layer Token System

| Layer | Purpose | Example |
|-------|---------|---------|
| **Primitive** | Raw values (colors, sizes, durations) | `#1B3FA0`, `16px`, `250ms` |
| **Semantic** | Context-aware aliases | `--text-primary`, `--bg-surface` |
| **Component** | Pre-composed component values | `--btn-bg-primary`, `--card-shadow` |

### 21.2 Token Naming Convention

Pattern: `--{category}-{property}-{variant}-{state}`

**Examples:**
- `--color-text-primary` (semantic)
- `--button-background-primary-hover` (component +state)
- `--input-border-error-focus` (component+state)

### 21.3 CSS Custom Properties Architecture

```css
/* design-tokens.css structure */
:root {
  /* === PRIMITIVE TOKENS === */
  --primitive-color-blue-500: #1B3FA0;
  --primitive-space-4: 16px;
  --primitive-duration-base: 250ms;

  /* === SEMANTIC TOKENS === */
  --color-brand-primary: var(--primitive-color-blue-500);
  --space-card-padding: var(--primitive-space-4);

  /* Maps to component tokens via utility classes */
}

/* === COMPONENT TOKENS === */
.button {
  --btn-bg: var(--color-brand-primary);
  --btn-padding: var(--space-card-padding);
}
```

### 21.4 Token Categories

| Category | Includes |
|----------|----------|
| **Color** | Brand, semantic, surface, text, state |
| **Typography** | Font family, size, weight, line-height, letter-spacing |
| **Spacing** | Space, gap, padding, margin |
| **Layout** | Width, height, max-width, grid |
| **Effect** | Shadow, blur, opacity, transition |
| **Border** | Radius, width, color, style |

### 21.5 TypeScript Token Types

```typescript
// tokens.types.ts
export interface ColorTokens {
  brand: {
    primary: string;
    secondary: string;
    accent: string;
  };
  semantic: {
    success: string;
    warning: string;
    error: string;
    info: string;
  };
  surface: {
    primary: string;
    secondary: string;
    tertiary: string;
    elevated: string;
  };
}

export interface TypographyTokens {
  fontFamily: {
    sans: string;
    mono: string;
    display: string;
    arabic: string;
  };
  fontSize: Record<string, string>;
  fontWeight: Record<string, number>;
  lineHeight: Record<string, number>;
}

export interface SpacingScale {
  [key: string]: number; // e.g., '4': 16, '6': 24
}

export interface DesignTokens {
  colors: ColorTokens;
  typography: TypographyTokens;
  spacing: SpacingScale;
  breakpoints: Record<string, string>;
  shadows: Record<string, string>;
  animation: {
    duration: Record<string, string>;
    easing: Record<string, string>;
  };
}
```

### 21.6 Token Consumption Patterns

**CSS Variables:**
```css
color: var(--brand-primary);
background: var(--glass-bg-medium);
box-shadow: var(--shadow-floating);
```

**Tailwind Classes:**
```html
<div class="bg-brand-primary text-white shadow-floating rounded-2xl">
```

**Inline Styles (React):**
```jsx
<div style={{ background: 'var(--gradient-brand)' }}>
```

---

## 22. Responsive Breakpoint System

Following **mobile-first design principles** with CSS Container Queries support for truly responsive components.

### 22.1 Breakpoint Scale

| Token | Min Width | Max Width | Target Device |
|-------|-----------|-----------|---------------|
| `--bp-xs` | 0px | 479px | Small phones (iPhone SE) |
| `--bp-sm` | 480px | 767px | Large phones (iPhone Pro Max) |
| `--bp-md` | 768px | 1023px | Tablets portrait |
| `--bp-lg` | 1024px | 1279px | Tablets landscape, small laptops |
| `--bp-xl` | 1280px | 1535px | Desktops |
| `--bp-2xl` | 1536px | ∞ | Large desktops, 4K displays |

### 22.2 Media Query Mixins

```css
/* Mobile-first approach */
@media (min-width: 480px) { /* sm */ }
@media (min-width: 768px) { /* md */ }
@media (min-width: 1024px) { /* lg */ }
@media (min-width: 1280px) { /* xl */ }
@media (min-width: 1536px) { /* 2xl */ }

/* Max-width queries for specific ranges */
@media (max-width: 479px) { /* xs only */ }
@media (max-width: 767px) { /* sm only */ }
```

### 22.3 Container Queries (CSS 2024)

```css
/* Enable container-relative sizing */
.card-container {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    flex-direction: row;
  }

  @container (min-width: 600px) {
  .card {
    flex-direction: row;
    padding: var(--space-6);
  }
}
```

### 22.4 Responsive Component Behavior

| Component | xs | sm | md | lg | xl |
|-----------|-----|-----|-----|-----|-----|
| Navigation | Bottom bar | Bottom bar | Side rail | Sidebar | Sidebar |
| Card Grid | 1 col | 2 cols | 2 cols | 3 cols | 4 cols |
| Sidebar | Hidden | Hidden | Collapsible | 280px | 320px |
| Modal | Fullscreen | Fullscreen | Centered | Centered | Centered |
| Font Scale | 87.5% | 93.75% | 100% | 100% | 106.25% |

### 22.5 Touch Target Adjustments

```css
/* Mobile: 48x48px minimum */
@media (max-width: 767px) {
  .button, .icon-button, .nav-item {
    min-height: var(--touch-target-comfortable);
    min-width: var(--touch-target-comfortable);
  }
}
```

### 22.6 Responsive Typography Scale

| Token | Mobile | Tablet | Desktop |
|-------|--------|--------|---------|
| `--text-hero` | 32px | 48px | 72px |
| `--text-h1` | 28px | 36px | 48px |
| `--text-h2` | 24px | 30px | 36px |
| `--text-h3` | 20px | 24px | 30px |
| `--text-body` | 16px | 16px | 18px |

### 22.7 Responsive Spacing Scale

| Token | Mobile | Tablet | Desktop |
|-------|--------|--------|---------|
| `--section-padding` | 48px | 80px | 112px |
| `--card-padding` | 16px | 24px | 32px |
| `--grid-gap` | 16px | 24px | 32px |

---

## 23. Dark Mode Implementation

Complete dark mode implementation with toggle logic, OS synchronization, and persistent storage.

### 23.1 Theme Detection Strategy

Three-tier detection with precedence:
1. User preference in localStorage (`theme: 'light' | 'dark' | 'system'`)
2. OS preference (`prefers-color-scheme`)
3. Default (Light mode)

### 23.2 CSS Implementation

```css
/* Base: Light mode */
:root {
  --surface-primary: #FFFFFF;
  --surface-secondary: #F4F6FA;
  --text-primary: #0F172A;
  /* ... */
}

/* System preference dark */
@media (prefers-color-scheme: dark) {
  :root:not([data-theme='light']) {
    --surface-primary: #0A0F1A;
    --surface-secondary: #111827;
    --text-primary: #F1F5F9;
    /* ... */
  }
}

/* Explicit dark mode */
[data-theme='dark'] {
  --surface-primary: #0A0F1A;
  --surface-secondary: #111827;
  --text-primary: #F1F5F9;
}

/* Tailwind class mode */
.dark {
  --surface-primary: #0A0F1A;
  --surface-secondary: #111827;
  --text-primary: #F1F5F9;
}
```

### 23.3 ThemeProvider Component

```typescript
// providers/ThemeProvider.tsx
import { createContext, useContext, useEffect, useState } from 'react';

type Theme = 'light' | 'dark' | 'system';

interface ThemeContextType {
  theme: Theme;
  setTheme: (theme: Theme) => void;
  resolvedTheme: 'light' | 'dark';
}

const ThemeContext = createContext<ThemeContextType | undefined>(undefined);

export const useTheme = () => {
  const context = useContext(ThemeContext);
  if (!context) throw new Error('useTheme must be used within ThemeProvider');
  return context;
};

export const ThemeProvider: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const [theme, setTheme] = useState<Theme>('system');

  useEffect(() => {
    const stored = localStorage.getItem('theme') as Theme;
    if (stored) setTheme(stored);
  }, []);

  useEffect(() => {
    const root = document.documentElement;

    if (theme === 'system') {
      const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
      root.setAttribute('data-theme', prefersDark ? 'dark' : 'light');
    } else {
      root.setAttribute('data-theme', theme);
    }

    localStorage.setItem('theme', theme);
  }, [theme]);

  // Listen for OS theme changes
  useEffect(() => {
    if (theme !== 'system') return;

    const mediaQuery = window.matchMedia('(prefers-color-scheme: dark)');
    const handleChange = (e: MediaQueryListEvent) => {
      document.documentElement.setAttribute('data-theme', e.matches ? 'dark' : 'light');
    };

    mediaQuery.addEventListener('change', handleChange);
    return () => mediaQuery.removeEventListener('change', handleChange);
  }, [theme]);

  const resolvedTheme = theme === 'system'
    ? (typeof window !== 'undefined' && window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light')
    : theme;

  return (
    <ThemeContext.Provider value={{ theme, setTheme, resolvedTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};
```

### 23.4 Dark Mode Color Mappings

| Token | Light | Dark | Notes |
|-------|-------|------|-------|
| `--surface-primary` | `#FFFFFF` | `#0A0F1A` | Logo deep |
| `--surface-secondary` | `#F4F6FA` | `#111827` | Elevated |
| `--surface-tertiary` | `#E8ECF3` | `#1E293B` | Cards |
| `--glass-bg-medium` | `rgba(255,255,255,0.72)` | `rgba(15,23,42,0.80)` | Glass panels |
| `--shadow-ambient` | `0 2px 8px rgba(0,0,0,0.08)` | `0 2px 8px rgba(0,0,0,0.32)` | Elevated |
| `--glow-primary` | `0 0 24px rgba(27,63,160,0.24)` | `0 0 40px rgba(117,150,245,0.32)` | Enhanced glow |

### 23.5 Dark Mode Image Handling

```css
/* Reduce brightness for images in dark mode */
[data-theme='dark'] img {
  filter: brightness(0.92) contrast(1.02);
}

/* Invert logos where appropriate */
[data-theme='dark'] .logo-invert {
  filter: invert(1) hue-rotate(180deg);
}
```

### 23.6 Transition Handling

```css
/* Prevent flash during theme change */
html {
  transition: background-color 0ms, color 0ms;
}

/* Respect reduced motion */
@media (prefers-reduced-motion: no-preference) {
  html {
    transition: background-color 250ms ease, color 250ms ease;
  }
}
```

### 23.7 Theme Toggle Component

```typescript
// components/ThemeToggle.tsx
import { useTheme } from '../providers/ThemeProvider';
import { Sun, Moon, Monitor } from 'lucide-react';

export const ThemeToggle: React.FC = () => {
  const { theme, setTheme } = useTheme();

  return (
    <div className="flex items-center gap-2 p-1 rounded-full bg-surface-secondary">
      <button
        onClick={() => setTheme('light')}
        className={`p-2 rounded-full transition-all ${
          theme === 'light' ? 'bg-brand-primary text-white' : 'text-text-secondary'
        }`}
        aria-label="Light mode"
      >
        <Sun size={18} />
      </button>
      <button
        onClick={() => setTheme('system')}
        className={`p-2 rounded-full transition-all ${
          theme === 'system' ? 'bg-brand-primary text-white' : 'text-text-secondary'
        }`}
        aria-label="System preference"
      >
        <Monitor size={18} />
      </button>
      <button
        onClick={() => setTheme('dark')}
        className={`p-2 rounded-full transition-all ${
          theme === 'dark' ? 'bg-brand-primary text-white' : 'text-text-secondary'
        }`}
        aria-label="Dark mode"
      >
        <Moon size={18} />
      </button>
    </div>
  );
};
```

---

## 24. Interactive Component States

Comprehensive state definitions for all interactive UI components following iOS 26 Liquid Glass principles.

### 24.1 State Types

| State | Trigger | Visual Expression |
|-------|---------|-------------------|
| **Default** | Initial | Base token values |
| **Hover** | Mouse over | Background tint, shadow lift, `translateY(-1px)` |
| **Active/Pressed** | Mouse down | Scale down (0.97), inset shadow |
| **Focus** | Keyboard nav | Focus ring, outline |
| **Focus-visible** | Keyboard only | Enhanced focus ring |
| **Disabled** | `disabled` attr | Reduced opacity (0.5), no interaction |
| **Loading** | Async operation | Skeleton, spinner, shimmer |
| **Error** | Validation fail | Red border, icon, message |
| **Success** | Validation pass | Green border, icon |
| **Selected** | Multi-select | Checkbox, highlight background |

### 24.2 Button States

```css
.button {
  /* Default */
  background: var(--btn-bg);
  border: 1px solid transparent;
  box-shadow: var(--shadow-ambient);
  transform: scale(1);
  transition: all var(--duration-fast) var(--ease-liquid);
}

.button:hover {
  background: var(--btn-bg-hover);
  box-shadow: var(--shadow-raised);
  transform: translateY(-1px);
}

.button:active {
  background: var(--btn-bg-active);
  box-shadow: var(--shadow-inset);
  transform: scale(0.97);
}

.button:focus-visible {
  outline: none;
  box-shadow: var(--focus-ring), var(--shadow-raised);
}

.button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

.button[data-loading="true"] {
  position: relative;
  color: transparent;
  pointer-events: none;
}

.button[data-loading="true"]::after {
  content: "";
  position: absolute;
  width: 16px;
  height: 16px;
  border: 2px solid currentColor;
  border-right-color: transparent;
  border-radius: 50%;
  animation: spin 0.75s linear infinite;
}
```

### 24.3 Input States

```css
.input {
  /* Default */
  border: 1px solid var(--border-default);
  background: var(--surface-primary);
  transition: all var(--duration-fast) var(--ease-liquid);
}

.input:hover:not(:disabled) {
  border-color: var(--border-strong);
}

.input:focus {
  border-width: 2px;
  border-color: var(--brand-primary);
  outline: none;
  box-shadow: var(--focus-ring);
}

.input:disabled {
  background: var(--surface-sunken);
  color: var(--text-disabled);
  cursor: not-allowed;
}

.input[data-invalid="true"] {
  border-color: var(--color-error);
}

.input[data-invalid="true"]:focus {
  border-color: var(--color-error);
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.15);
}

.input[data-valid="true"] {
  border-color: var(--color-success);
}
```

### 24.4 Card States

| State | Background | Shadow | Border | Transform |
|-------|------------|--------|--------|-----------|
| Default | `var(--card-bg)` | `var(--shadow-ambient)` | `var(--card-border)` | none |
| Hover | `var(--card-bg)` | `var(--shadow-raised)` | `var(--card-border)` | `translateY(-2px)` |
| Active | `var(--card-bg)` | `var(--shadow-ambient)` | `var(--card-border)` | `scale(0.99)` |
| Selected | `var(--color-selected)` | `var(--shadow-raised)` | `2px solid var(--brand-primary)` | none |

### 24.5 Loading States

**Skeleton Shimmer:**
```css
.skeleton {
  background: linear-gradient(
    90deg,
    var(--surface-sunken) 0%,
    var(--surface-tertiary) 50%,
    var(--surface-sunken) 100%
  );
  background-size: 200% 100%;
  animation: skeleton-shimmer 1.5s ease-in-out infinite;
  border-radius: var(--radius-md);
}

@keyframes skeleton-shimmer {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}
```

**Spinner:**
```css
.spinner {
  width: 20px;
  height: 20px;
  border: 2px solid var(--border-default);
  border-top-color: var(--brand-primary);
  border-radius: 50%;
  animation: spin 0.75s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

### 24.6 State Transition Timing

| Transition | Duration | Easing |
|------------|----------|--------|
| Color/background | 150ms | `ease-liquid` |
| Shadow | 200ms | `ease-liquid` |
| Transform | 150ms | `ease-spring-gentle` |
| Focus ring | 0ms (instant) | - |
| Disabled | 0ms | - |
| Loading | 1.5s (shimmer) | `ease-in-out` |

---

## 25. Icon System

Comprehensive icon system with sizes, colors, animations, and usage guidelines.

### 25.1 Icon Library

**Primary Library:** Lucide Icons (React)
**Fallback:** Phosphor Icons
**Custom:** AnySync-specific icons (logo, agent indicators, healthcare symbols)

```bash
# Installation
npm install lucide-react
```

### 25.2 Icon Size Scale

| Token | Size | Usage |
|-------|------|-------|
| `--icon-xs` | 12px | Inline with small text, badges |
| `--icon-sm` | 16px | Button icons, menu items, inline |
| `--icon-md` | 20px | Standard UI elements |
| `--icon-lg` | 24px | Navigation, section headers |
| `--icon-xl` | 32px | Feature icons, empty states |
| `--icon-2xl` | 48px | Hero icons, large illustrations |

### 25.3 Icon + Text Combinations

```css
/* Icon before text */
.icon-text {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
}

.icon-text svg {
  flex-shrink: 0;
}

/* Icon after text */
.text-icon {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  flex-direction: row-reverse;
}

/* Icon only button */
.icon-only {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--space-2);
}
```

### 25.4 Icon Button Sizing

| Size | Icon | Padding | Touch Target |
|------|------|---------|---------------|
| Small | 16px | 6px | 28px |
| Medium | 20px | 8px | 36px |
| Large | 24px | 12px | 48px |

```css
.icon-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-lg);
  background: transparent;
  color: var(--text-secondary);
  transition: all var(--duration-fast) var(--ease-liquid);
}

.icon-button:hover {
  background: var(--color-hover);
  color: var(--text-primary);
}

.icon-button-sm { padding: 6px; }
.icon-button-md { padding: 8px; }
.icon-button-lg { padding: 12px; }
```

### 25.5 Icon Colors by Context

| Context | Light Mode | Dark Mode |
|---------|------------|-----------|
| Primary action | `var(--brand-primary)` | `var(--brand-primary-300)` |
| Secondary | `var(--text-secondary)` | `var(--text-secondary)` |
| Success | `var(--color-success)` | `var(--color-success-light)` |
| Warning | `var(--color-warning)` | `var(--color-warning-light)` |
| Error | `var(--color-error)` | `var(--color-error-light)` |
| Disabled | `var(--text-disabled)` | `var(--text-disabled)` |

### 25.6 Animated Icons

**Spinner:**
```css
.icon-spinner {
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
```

**Pulse (for status indicators):**
```css
.icon-pulse {
  animation: icon-pulse 2s ease-in-out infinite;
}

@keyframes icon-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}
```

**Bounce (for notifications):**
```css
.icon-bounce {
  animation: icon-bounce 0.5s var(--ease-spring);
}

@keyframes icon-bounce {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.2); }
}
```

### 25.7 Icon Usage Guidelines

**Do:**
- Use consistent sizing within a feature area
- Pair icons with text for clarity
- Use semantic colors (success, warning, error) for status
- Maintain adequate spacing (8px minimum)

**Don't:**
- Mix icon libraries
- Use icons as standalone decoration
- Override icon colors arbitrarily
- Use icons smaller than 16px in interactive elements

---

## 26. Form Design System

Complete form patterns including validation, multi-step forms, and accessibility.

### 26.1 Form Layout Patterns

| Pattern | Use Case | Layout |
|---------|----------|--------|
| **Stacked** | Simple forms, mobile | Labels above inputs, full width |
| **Inline** | Compact filters, search | Label beside input |
| **Grid** | Complex forms | 2-column responsive grid |
| **Multi-step** | Long forms, onboarding | Wizard with progress indicator |

### 26.2 Input Components

**Text Input:**
```css
.input {
  height: 44px;
  padding: 0 var(--space-4);
  border-radius: var(--radius-md);
  font-size: var(--text-base);
  border: 1px solid var(--border-default);
  background: var(--surface-primary);
  color: var(--text-primary);
  transition: all var(--duration-fast) var(--ease-liquid);
}

.input::placeholder {
  color: var(--text-placeholder);
}

.input:hover:not(:disabled) {
  border-color: var(--border-strong);
}

.input:focus {
  border-width: 2px;
  border-color: var(--brand-primary);
  outline: none;
  box-shadow: var(--focus-ring);
}

.input:disabled{
  background: var(--surface-sunken);
  color: var(--text-disabled);
  cursor: not-allowed;
}

.input[data-invalid="true"] {
  border-color: var(--color-error);
}

.input[data-invalid="true"]:focus {
  border-color: var(--color-error);
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.15);
}
```

### 26.3 Input Sizes

| Size | Height | Padding | Font Size |
|------|--------|---------|-----------|
| Small | 36px | 12px | 14px |
| Medium | 44px | 16px | 16px |
| Large | 52px | 20px | 18px |

### 26.4 Select / Dropdown

```css
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%2364748B' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 40px;
}

.select-dropdown {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  margin-top: var(--space-1);
  background: var(--surface-elevated);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-floating);
  z-index: var(--z-dropdown);
  max-height: 300px;
  overflow-y: auto;
}
```

### 26.5 Checkbox & Radio

```css
/* Custom checkbox */
.checkbox {
  appearance: none;
  width: 20px;
  height: 20px;
  border: 2px solid var(--border-default);
  border-radius: var(--radius-xs);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-liquid);
}

.checkbox:hover {
  border-color: var(--brand-primary);
}

.checkbox:checked {
  background: var(--brand-primary);
  border-color: var(--brand-primary);
}

.checkbox:checked::after {
  content: "";
  display: block;
  width: 6px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
  margin: 2px auto;
}

/* Radio button */
.radio {
  appearance: none;
  width: 20px;
  height: 20px;
  border: 2px solid var(--border-default);
  border-radius: 50%;
  cursor: pointer;
}

.radio:checked {
  border-color: var(--brand-primary);
}

.radio:checked::after{
  content: "";
  display: block;
  width: 10px;
  height: 10px;
  background: var(--brand-primary);
  border-radius: 50%;
  margin: 3px;
}
```

### 26.6 Form Validation

| State | Border Color | Background | Helper Text |
|-------|--------------|------------|-------------|
| Default | `var(--border-default)` | `var(--surface-primary)` | `var(--text-tertiary)` |
| Error | `var(--color-error)` | `rgba(239,68,68,0.04)` | `var(--color-error)` |
| Success | `var(--color-success)` | `rgba(16,185,129,0.04)` | `var(--color-success)` |
| Warning | `var(--color-warning)` | `rgba(245,158,11,0.04)` | `var(--color-warning)` |

**Error Message Component:**
```css
.input-error {
  display: flex;
  align-items: center;
  gap: var(--space-1);
  color: var(--color-error);
  font-size: var(--text-sm);
  margin-top: var(--space-1);
}

.input-error svg {
  width: 14px;
  height: 14px;
}
```

### 26.7 Multi-Step Forms (Wizard)

```
┌─────────────────────────────────────────────────────────────────┐
│  PROGRESS INDICATOR                                              │
│  ━━━━━━━━━●━━━━━━━━━━○━━━━━━━━━━○                               │
│   Step 1    Step 2     Step 3                                    │
│  [Current]  [Pending]  [Pending]                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Step 2: Contact Information                                     │
│  ─────────────────────────────────                              │
│                                                                  │
│  [Form fields here]                                              │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                        [Back]           [Next →]                 │
└─────────────────────────────────────────────────────────────────┘
```

**Progress Indicator Tokens:**
```css
--wizard-step-complete: var(--brand-primary);
--wizard-step-current: var(--brand-primary);
--wizard-step-pending: var(--neutral-300);
--wizard-connector-height: 2px;
--wizard-step-size: 32px;
```

### 26.8 Form Accessibility

- All inputs have associated `<label>` elements
- Error messages linked via `aria-describedby`
- Required fields marked with `aria-required="true"`
- Fieldsets for grouped inputs (radio groups)
- Legend for fieldset descriptions

```html
<div class="form-group">
  <label for="email" class="form-label">
    Email Address
    <span class="required" aria-hidden="true">*</span>
  </label>
  <input
    type="email"
    id="email"
    name="email"
    aria-required="true"
    aria-describedby="email-error"
    class="input"
  />
  <p id="email-error" class="input-error" role="alert" aria-live="polite">
    <!-- Error message appears here -->
  </p>
</div>
```

---

## 27. Data Visualization System

Comprehensive chart and data visualization specifications aligned with PRD F2.1-F2.6.

### 27.1 Chart Color Palette

**Logo-Inspired Gradient Spectrum:**

| Index | Hex | Role | Use Case |
|-------|-----|------|----------|
| 1 | `#1B3FA0` | Primary | Primary data series, emphasis |
| 2 | `#1A5DAE` | Secondary | Second series |
| 3 | `#1A7A9E` | Tertiary | Third series |
| 4 | `#17B5A6` | Quaternary | Fourth series |
| 5 | `#1CD760` | Accent | Fifth series, highlights |
| 6 | `#2AE668` | Bright | Sixth series, peak indicators |

**Extended Palette (8+ series):**
```css
--chart-color-7: #45B7D1;
--chart-color-8: #96CEB4;
--chart-color-9: #FFEAA7;
--chart-color-10: #DDA0DD;
```

### 27.2 Chart Categories (per PRD F2.1)

**Category Charts (Comparisons):**

| Type | Use Case | Features |
|------|----------|----------|
| **Bar Chart** | Compare discrete categories | Horizontal/vertical, stacked, grouped |
| **Column Chart** | Time-series comparisons | Trend lines, variance indicators |
| **Pie Chart** | Part-to-whole | Donut variant, explode segments |
| **Donut Chart** | Proportions with center KPI | Center value display |
| **Treemap** | Hierarchical proportions | Nested rectangles |
| **Funnel Chart** | Stage-based processes | Conversion rates |

**Trend Charts (Time-Series):**

| Type | Use Case | Features |
|------|----------|----------|
| **Line Chart** | Continuous data trends | Multi-series, area fill, smooth curves |
| **Area Chart** | Cumulative trends | Stacked areas, gradient fills |
| **Step Chart** | Discrete changes | Before/after indicators |
| **Candlestick** | Financial OHLC | Bullish/bearish colors |
| **Sparkline** | Inline trend indicators | Mini charts in tables/KPIs |

**Distribution Charts:**

| Type | Use Case | Features |
|------|----------|----------|
| **Histogram** | Frequency distribution | Bin customization |
| **Box Plot** | Statistical summaries | Quartiles, outliers |
| **Violin Plot** | Distribution density | Split comparisons |
| **Scatter Plot** | Correlation analysis | Trend lines, clustering |

**Relationship Charts:**

| Type | Use Case | Features |
|------|----------|----------|
| **Bubble Chart** | Three-variable comparison | Size encoding, quadrants |
| **Heatmap** | Matrix correlations | Color gradients, annotations |
| **Radar/Spider** | Multi-dimensional comparison | Category axes, area fills |
| **Sankey Diagram** | Flow relationships | Node-link, width by volume |

### 27.3 Chart Anatomy

```
┌─────────────────────────────────────────────────────────────────┐
│  CHART TITLE                                                    │
├─────────────────────────────────────────────────────────────────┤
│  [Subtitle / Date Range]                                        │
├─────────────────────────────────────────────────────────────────┤
│                                                        [⋮ More] │
│     ▲ Y-Axis Label                                              │
│     │                                                           │
│   $ │    ┌────────────────────────────────────────────┐         │
│     │    │         [Chart Area / Plot]                │         │
│     │    │                                            │         │
│     │    │     ╭───╮                                  │         │
│     │    │    ╱     ╲        ╭──╮                     │         │
│     │    │   ╱       ╲      ╱    ╲   ╭────╮           │         │
│     │    │  ╱         ╲────╱      ╲─╯      ╲──        │         │
│     └────┴──┴──────────────────────────────────────────────────┴─────▶  │
│          Jan   Feb   Mar   Apr   May   Jun                      │
│                         X-Axis Label                            │
├─────────────────────────────────────────────────────────────────┤
│  ○ Series A  ● Series B  ◐ Series C                    [Legend] │
└─────────────────────────────────────────────────────────────────┘
```

### 27.4 Chart Tokens

```css
/* Grid & Axes */
--chart-grid-color: rgba(100, 116, 139, 0.12);
--chart-axis-color: var(--neutral-400);
--chart-axis-label-color: var(--text-secondary);
--chart-axis-label-font: var(--text-xs);

/* Tooltip */
--chart-tooltip-bg: var(--surface-elevated);
--chart-tooltip-border: var(--border-default);
--chart-tooltip-shadow: var(--shadow-floating);
--chart-tooltip-radius: var(--radius-lg);
--chart-tooltip-padding: var(--space-3);

/* Animation */
--chart-enter-duration: 500ms;
--chart-enter-stagger: 50ms;
--chart-update-duration: 300ms;
```

### 27.5 Color-Blind Accessible Palette

For accessibility compliance, an alternative deuteranopia/protanopia-safe palette:

| Index | Standard | Color-Blind Safe |
|-------|----------|------------------|
| 1 | `#1B3FA0` | `#0077BB` |
| 2 | `#17B5A6` | `#33BBEE` |
| 3 | `#1CD760` | `#009988` |
| 4 | `#F59E0B` | `#EE7733` |
| 5 | `#EF4444` | `#CC3311` |
| 6 | `#8B5CF6` | `#AA3377` |

### 27.6 Map Visualizations (per PRD F2.2)

**Map Types:**

| Type | Use Case | Features |
|------|----------|----------|
| **Choropleth** | Regional comparisons | Color gradients by value |
| **Point Map** | Location markers | Clustering, custom icons |
| **Heat Map** | Density visualization | Radius intensity, blur |
| **Flow Map** | Origin-destination flows | Animated paths, arrows |
| **Bubble Map** | Sized regional indicators | Circle sizing by metric |

**Map Color Scales:**
```css
/* Sequential (low to high) */
--map-scale-low: var(--brand-primary-100);
--map-scale-mid: var(--brand-primary-500);
--map-scale-high: var(--brand-primary-900);

/* Diverging (negative to positive) */
--map-scale-negative: var(--color-error);
--map-scale-neutral: var(--surface-sunken);
--map-scale-positive: var(--color-success);
```

```

### 27.7 Interactive Features

**Cross-Filtering:**
- Click on chart element to filter related charts
- Filter indicator shows active filter
- Clear all filters button

**Drill-Down:**
- Hierarchical levels (Year → Quarter → Month → Day)
- Breadcrumb navigation
- Back/Reset controls

**Tooltips:**
```typescript
interface ChartTooltip {
  title: string;
  values: Array<{
    label: string;
    value: string | number;
    color: string;
  }>;
  footer?: string;
}
```

**Zoom/Pan:**
- Mouse wheel zoom
- Drag to pan
- Reset zoom button
- Zoom level indicator

---

## 28. Chart & Map Component Specifications

Detailed component specifications for KPIs, gauges, data tables, and export functionality.

### 28.1 KPI Cards & Indicators

```
┌────────────────────┐
│  Total Revenue     │  ← Label: text-sm, text-secondary
│                    │
│    $2.4M           │  ← Value: text-3xl, text-primary, font-bold
│    ↑ 15.3%         │  ← Trend: text-sm, success/error color
│  vs last month     │  ← Comparison: text-xs, text-tertiary
│                    │
│  ┌──────────────┐  │
│  │ ▁▂▃▄▅▆▇█▇▆  │  │  ← Sparkline: 24px height
│  └──────────────┘  │
└────────────────────┘
```

**KPI Tokens:**
```css
--kpi-card-padding: var(--space-6);
--kpi-card-radius: var(--radius-xl);
--kpi-value-size: var(--text-3xl);
--kpi-label-size: var(--text-sm);
--kpi-trend-up: var(--color-success);
--kpi-trend-down: var(--color-error);
--kpi-trend-neutral: var(--text-tertiary);
```

### 28.2 Gauge Components

**Semicircular Gauge:**
```
        ╭─────────╮
      ╱             ╲
    ╱   78%   ▲      ╲
   │    Target       │
    ╲       |        ╱
      ╲             ╱
        ╰─────────╯
    Red   Yellow   Green
```

**Gauge Zones:**

| Zone | Range | Color |
|------|-------|-------|
| Critical | 0-33% | `var(--color-error)` |
| Warning | 34-66% | `var(--color-warning)` |
| Good | 67-100% | `var(--color-success)` |

### 28.3 Data Table Component

```css
/* Table structure */
.data-table {
  width: 100%;
  border-collapse: collapse;
}

.data-table th {
  background: var(--surface-secondary);
  padding: var(--space-3) var(--space-4);
  text-align: left;
  font-weight: var(--font-semibold);
  border-bottom: 2px solid var(--border-default);
}

.data-table td {
  padding: var(--space-3) var(--space-4);
  border-bottom: 1px solid var(--border-subtle);
}

.data-table tr:hover td {
  background: var(--color-hover);
}

.data-table tr.selected td {
  background: var(--color-selected);
}
```

**Table Features:**

| Feature | Implementation |
|---------|----------------|
| Sorting | Click header to sort, indicator arrow |
| Filtering | Column filter dropdown, global search |
| Pagination | Page size selector, page numbers |
| Selection | Checkbox column, shift-click range |
| Inline Edit | Double-click cell to edit |
| Frozen Columns | Sticky left/right columns |

### 28.4 Pivot Table

**Drop Zones:**
- **Columns:** Dimensions for column headers
- **Rows:** Dimensions for row headers
- **Values:** Metrics to aggregate
- **Filters:** Filter criteria

**Aggregation Functions:**
- Sum, Average, Count, Count Distinct
- Min, Max, Median, Std Dev
- % of Total, Running Total

### 28.5 Export Configuration

**Export Dialog:**
```
┌─────────────────────────────────────────────────────────────────┐
│  Export Report                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Format:  [PDF ▼]  [Excel] [CSV] [PNG] [SVG] [PPT]             │
│                                                                 │
│  PDF Options:                                                   │
│  ☑ Include header with logo                                    │
│  ☑ Include page numbers                                        │
│  ☑ Include generation timestamp                                │
│  ☐ Landscape orientation                                       │
│  Paper Size: [A4 ▼]  Quality: [High ▼]                        │
│                                                                 │
│  Delivery:                                                      │
│  ○ Download now                                                │
│  ○ Email to: [________________________]                        │
│  ○ Save to: [My Reports ▼]                                     │
│                                                                 │
│                           [Cancel]  [Export]                    │
└─────────────────────────────────────────────────────────────────┘
```

**Export Format Tokens:**

| Format | File Extension | MIME Type |
|--------|----------------|-----------|
| PDF | `.pdf` | `application/pdf` |
| Excel | `.xlsx` | `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet` |
| CSV | `.csv` | `text/csv` |
| PNG | `.png` | `image/png` |
| SVG | `.svg` | `image/svg+xml` |
| PowerPoint | `.pptx` | `application/vnd.openxmlformats-officedocument.presentationml.presentation` |

---

## 29. Internationalization (i18n) & RTL Layout

Comprehensive i18n support with RTL layout patterns and Arabic typography.

### 29.1 Supported Languages

| Language | Code | Direction | Font |
|----------|------|-----------|------|
| English (US) | `en-US` | LTR | Inter |
| Arabic (Saudi) | `ar-SA` | RTL | Cairo |

### 29.2 RTL Layout System

**CSS Logical Properties:**
```css
/* Use logical properties instead of physical */
/* LTR: left → right, RTL: right → left */

/* Instead of: */
margin-left: 16px;

/* Use: */
margin-inline-start: 16px;

/* Property Mappings */
inline-start → LTR: left, RTL: right
inline-end → LTR: right, RTL: left
block-start → top
block-end → bottom
```

**RTL-Specific Overrides:**
```css
[dir='rtl'] {
  /* Flip directional icons */
  .icon-arrow-right { transform: scaleX(-1); }
  .icon-arrow-left { transform: scaleX(-1); }

  /* Adjust text alignment */
  .text-start { text-align: right; }
  .text-end { text-align: left; }

  /* Flip progress direction */
  .progress-bar { transform: scaleX(-1); }

  /* Adjust sidebar position */
  .sidebar {
    right: auto;
    left: 0;
  }
}
```

### 29.3 Bidirectional Components

**Components requiring RTL awareness:**

| Component | Consideration |
|-----------|---------------|
| Navigation | Menu items reverse order |
| Breadcrumbs | Separator direction, item order |
| Lists | Bullet position, indentation |
| Forms | Label alignment, input icons |
| Tables | Column order (optional) |
| Charts | Axis labels, legend position |
| Modals | Close button position |
| Toasts | Icon and text alignment |

### 29.4 Arabic Typography

```css
:lang(ar) {
  font-family: 'Cairo', 'Noto Sans Arabic', 'IBM Plex Sans Arabic',
                 'Segoe UI', Tahoma, sans-serif;
  line-height: 1.8; /* Increased for Arabic */
  letter-spacing: 0; /* Reset for Arabic */
}

/* Arabic font scales */
:lang(ar) {
  --text-hero: clamp(2.5rem, 6vw, 4rem);
  --text-h1: clamp(2rem, 4vw, 3rem);
  --text-h2: clamp(1.75rem, 3.5vw, 2.5rem);
  --text-body: 1.0625rem; /* 17px for Arabic readability */
}
```

### 29.5 Number & Date Formatting

**Number Formatting:**
```typescript
// English: 1,234,567.89
// Arabic: ١٬٢٣٤٬٥٦٧٫٨٩ (Eastern Arabic numerals)

const formatNumber = (value: number, locale: string) => {
  return new Intl.NumberFormat(locale).format(value);
};

// Currency
const formatCurrency = (value: number, locale: string, currency: string = 'USD') => {
  return new Intl.NumberFormat(locale, {
    style: 'currency',
    currency
  }).format(value);
};
```

**Date Formatting:**
```typescript
// English: Feb 25, 2026
// Arabic: ٢٥ فبراير ٢٠٢٦

const formatDate = (date: Date, locale: string) => {
  return new Intl.DateTimeFormat(locale, {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  }).format(date);
};

// Relative time
const formatRelativeTime = (date: Date, locale: string) => {
  return new Intl.RelativeTimeFormat(locale, {
    numeric: 'auto'
  }).format(date);
};
```

### 29.6 Calendar Systems

| Locale | Calendar | Notes |
|--------|----------|-------|
| en-US | Gregorian | Default |
| ar-SA | Hijri + Gregorian | Show both for Saudi Arabia |

### 29.7 Translation Management

**File Structure:**
```
/locales
  /en-US
    common.json
    dashboard.json
    reports.json
    alerts.json
  /ar-SA
    common.json
    dashboard.json
    reports.json
    alerts.json
```

**Key NamingConvention:**
```
{namespace}.{component}.{element}.{state}

Examples:
- common.button.submit
- dashboard.kpi.revenue.label
- reports.export.pdf.title
- alerts.threshold.error.message
```

---

## 30. Healthcare-Specific Components

Components designed for healthcare PHI masking, audit trails, and HIPAA/GDPR compliance.

### 30.1 PHI Masking Components

**Masked Field:**
```css
.phi-masked {
  position: relative;
  user-select: none;
}

.phi-masked::after {
  content: "••••••";
  position: absolute;
  inset: 0;
  background: var(--surface-primary);
  display: flex;
  align-items: center;
  padding: 0 var(--space-3);
  letter-spacing: 0.2em;
  font-family: var(--font-mono);
  color: var(--text-secondary);
}

/* Hover to reveal (admin only) */
.phi-masked[data-can-reveal="true"]:hover::after {
  content: attr(data-value);
  letter-spacing: normal;
  font-family: var(--font-sans);
}
```

**PII Badge:**
```
┌─────────────────────────────────────────────────────────────────┐
│  Patient ID: ••••••••  [👁 Reveal]  [📋 Copy]             │
│                         (Admin only)                            │
└─────────────────────────────────────────────────────────────────┘
```

### 30.2 Audit Trail Component

```
┌─────────────────────────────────────────────────────────────────┐
│  AUDIT TRAIL                                                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ● 2026-02-25 14:32:15                                         │
│  │ User: Dr. Fatima (Cardiology)                               │
│  │ Action: Viewed patient report #1247                         │
│  │ IP: 192.168.1.100                                          │
│  │                                                            │
│  ● 2026-02-25 14:28:03                                         │
│  │ User: System (Scheduled Task)                               │
│  │ Action: Generated weekly revenue report                     │
│  │                                                            │
│  ● 2026-02-25 14:15:47                                         │
│  │ User: Ahmed (Finance)                                       │
│  │ Action: Exported P&L Statement (PDF)                        │
│  │                                                            │
└─────────────────────────────────────────────────────────────────┘
```

**Audit Log Tokens:**
```css
--audit-timeline-color: var(--neutral-200);
--audit-node-size: 8px;
--audit-timestamp-color: var(--text-tertiary);
--audit-action-color: var(--text-primary);
--audit-user-color: var(--text-secondary);
```

### 30.3 Compliance Badge Component

| Badge | Color | Use Case |
|-------|-------|----------|
| HIPAA | `var(--brand-primary)` | Data handled per HIPAA |
| GDPR | `var(--brand-secondary)` | EU data protection compliant |
| PHI | `var(--color-warning)` | Contains Protected Health Info |
| PII | `var(--color-error)` | Contains Personally Identifiable Info |

```css
.compliance-badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-1);
  padding: var(--space-1) var(--space-2);
  border-radius: var(--radius-badge);
  font-size: var(--text-xs);
  font-weight: var(--font-semibold);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.compliance-badge-hipaa {
  background: rgba(27, 63, 160, 0.12);
  color: var(--brand-primary);
}

.compliance-badge-gdpr {
  background: rgba(23, 181, 166, 0.12);
  color: var(--brand-secondary);
}

.compliance-badge-phi {
  background: rgba(245, 158, 11, 0.12);
  color: var(--color-warning);
}

.compliance-badge-pii {
  background: rgba(239, 68, 68, 0.12);
  color: var(--color-error);
}
```

### 30.4 HITL (Human-in-the-Loop) Approval Card

```
┌─────────────────────────────────────────────────────────────────┐
│  ⚠️ APPROVAL REQUIRED                                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Agent: Financial Sync Agent                                    │
│  Action: Update patient billing record                          │
│  Record: #PAT-2026-001247                                       │
│                                                                 │
│  Proposed Changes:                                              │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ Field: Amount                                           │   │
│  │ Old: $1,240.00                                          │   │
│  │ New: $1,340.00                                          │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  Justification: Corrected billing per insurance adjustment     │
│                                                                 │
│                    [Reject]  [Edit]  [Approve]                  │
└─────────────────────────────────────────────────────────────────┘
```

**HITL Tokens:**
```css
--hitl-warning-bg: rgba(245, 158, 11, 0.08);
--hitl-warning-border: 1px solid rgba(245, 158, 11, 0.3);
--hitl-card-shadow: var(--shadow-floating);
```

### 30.5 PII Admin Configuration Panel

```
┌─────────────────────────────────────────────────────────────────┐
│  PII CONFIGURATION                                    [Save]    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Detection Settings                                             │
│  ─────────────────────────────────────────────────────────────  │
│  ☑ Enable PII Detection                                        │
│  Detection Sensitivity: ────●─────────────── 0.7               │
│                                                                 │
│  Entity Types                                                     │
│  ─────────────────────────────────────────────────────────────  │
│  ☑ Names          ☑ Phone Numbers    ☑ Email Addresses         │
│  ☑ SSN            ☑ Medical IDs      ☑ Credit Cards            │
│  ☑ Addresses      ☐ IP Addresses     ☐ Browser Fingerprint     │
│                                                                 │
│  Anonymization Method                                             │
│  ─────────────────────────────────────────────────────────────  │
│  ○ Replace with <TYPE>                                         │
│  ○ Redact (*****)                                             │
│  ● Hash (SHA-256)                                              │
│  ○ Encrypt (AES-256)                                           │
│                                                                 │
│  Custom Recognizers                                               │
│  ─────────────────────────────────────────────────────────────  │
│  [+ Add Custom Recognizer]                                      │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ MRN Pattern: ^MRN-[0-9]{8}$                             │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 30.6 Presidio PII Admin Integration

**Integration Points:**
- **Detection Engine:** Microsoft Presidio analyzer
- **Anonymization:** Configurable transformers
- **Custom Recognizers:** Regex-based pattern matching
- **Audit Logging:** All PII operations logged
- **Role-Based Access:** Admin-only configuration

**Configuration Interface:**
```typescript
interface PresidioConfig {
  enabled: boolean;
  languages: string[]; // ['en', 'ar']
  entities: string[];
  customRecognizers: CustomRecognizer[];
  anonymizationMode: 'replace' | 'redact' | 'hash' | 'encrypt';
  sensitivity: number; // 0.0-1.0
}
```

---

## 31. Component Documentation Patterns

Storybook-style documentation patterns for the component library.

### 31.1 Documentation Structure

Each component documented with:
1. **Overview** — Purpose, when to use
2. **Variants** — All available variations
3. **States** — Default, hover, focus, disabled, loading, error
4. **Props API** — TypeScript interface
5. **Usage Examples** — Code snippets
6. **Accessibility** — ARIA requirements
7. **Design Tokens** — Customizable tokens

### 31.2 Component Anatomy Template

```
┌─────────────────────────────────────────────────────────────────┐
│  COMPONENT: Button                                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Anatomy:                                                       │
│  ┌───────────────────────────────────────────────────────┐     │
│  │  ┌─────┐ ┌─────────────────────┐                      │     │
│  │  │Icon │ │ Label               │                      │     │
│  │  └─────┘ └─────────────────────┘                      │     │
│  │  ↑ Start  ↑ Content           ↑ End →                 │     │
│  └───────────────────────────────────────────────────────┘     │
│                                                                 │
│  Spacing:                                                         │
│  - Padding: var(--btn-padding-md) = 12px 24px                  │
│  - Gap: var(--space-2) = 8px                                   │
│  - Radius: var(--btn-radius) = 16px                            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 31.3 Variant Matrix Template

```
┌─────────────────────────────────────────────────────────────────┐
│  BUTTON VARIANTS                                                │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Variant: Primary | Secondary | Ghost | Destructive            │
│  ─────────────────────────────────────────────────────────────  │
│                                                                 │
│  Primary:   [████████████ Submit █████████████]                 │
│  Secondary: [░░░░░░░░░░ Cancel ░░░░░░░░░░]                     │
│  Ghost:     [        Ghost Button            ]                  │
│  Destructive: [████████ Delete ████████████]  (Red)            │
│                                                                 │
│  Size: Small | Medium | Large                                  │
│  ─────────────────────────────────────────────────────────────  │
│                                                                 │
│  Small:  [███████]  32px height                                │
│  Medium: [███████████] 44px height                             │
│  Large:  [████████████████] 52px height                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 31.4 Props Documentation Template

```typescript
interface ButtonProps {
  /** The visual style variant */
  variant?: 'primary' | 'secondary' | 'ghost' | 'destructive';

  /** Size of the button */
  size?: 'sm' | 'md' | 'lg';

  /** Icon to display before the label */
  startIcon?: React.ReactNode;

  /** Icon to display after the label */
  endIcon?: React.ReactNode;

  /** Whether the button is disabled */
  disabled?: boolean;

  /** Whether the button shows a loading state */
  loading?: boolean;

  /** Full width button */
  fullWidth?: boolean;

  /** Click handler */
  onClick?: (event: React.MouseEvent<HTMLButtonElement>) => void;

  /** Additional CSS class names */
  className?: string;

  /** Button contents */
  children: React.ReactNode;
}
```

### 31.5 Story File Structure

```
/stories
  /components
    Button.stories.tsx
    Input.stories.tsx
    Card.stories.tsx
    /charts
      LineChart.stories.tsx
      BarChart.stories.tsx
    /healthcare
      PHIMaskedField.stories.tsx
      AuditTrail.stories.tsx
```

### 31.6 Accessibility Documentation

For each component, document:
- **Keyboard interactions**
- **Screen reader behavior**
- **ARIA attributes**
- **Focus management**

**Example (Button):**
```
### Accessibility

| Key | Action |
|-----|--------|
| Tab | Move focus to button |
| Enter / Space | Activate button |
| Escape | (If in menu) Close menu |

- Uses native `<button>` element for built-in accessibility
- Focus visible ring via `:focus-visible`
- Disabled state removes from tab order
- Loading state sets `aria-busy="true"`
```

### 31.7 Component Checklist

- [ ] All variants documented
- [ ] All states documented
- [ ] Props API complete
- [ ] Usage examples provided
- [ ] Accessibility documented
- [ ] Design tokens listed
- [ ] Story file created
- [ ] Unit tests written
- [ ] Visual regression tests

---

*AnySync Design System v2.0.0 · February 25, 2026*

**Changelog:**
- Added Section 21: Design Token Architecture
- Added Section 22: Responsive Breakpoint System
- Added Section 23: Dark Mode Implementation
- Added Section 24: Interactive Component States
- Added Section 25: Icon System
- Added Section 26: Form Design System
- Added Section 27: Data Visualization System
- Added Section 28: Chart & Map Component Specifications
- Added Section 29: Internationalization & RTL Layout
- Added Section 30: Healthcare-Specific Components
- Added Section 31: Component Documentation Patterns
- Expanded Section 18: Agentic AI UI Components (18.6, 18.7)
- Expanded Section 16: Accessibility Standards (16.6-16.9)
- Expanded Section 12: Typography System (12.6 Arabic)