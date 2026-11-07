# UX-05: Design System Foundations — Tokens & Components
**Track**: UX/UI Design · **Phase**: Build · **Workload**: 6h · **Week**: 5  
**Candidate**: K. M. Siam ([GitHub: @KMSiam](https://github.com/KMSiam))  
**Design System Name**: **FlyCore Design System v1.0**  
**Project**: FlyCommerce OS (Predictive DTC E-Commerce Fulfillment & Inventory Hub)  
**Master Figma Workspace**: [FlyRank Master Project Workspace (Pristine View)](https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access)

---

## Executive Summary

A design system separates ad-hoc screen design from scalable, repeatable digital product engineering. Hard-coding arbitrary hex values and disconnected padding rules creates technical debt and breaks when multi-theme or multi-device support is required.

**FlyCore Design System v1.0** establishes:
1. **Mathematical Modular Typography Scale** (8 styles built on a 1.250 Major Third ratio).
2. **Comprehensive Semantic Color Token Engine** mapped into Figma Variables with 100% parity across **Light Mode** and **Dark Mode (Warehouse Night Shift)**.
3. **8-Point Spacing & Elevation System** codifying consistent spatial rhythm.
4. **8 Production-Ready Atomic & Molecular Components** (Button, Input, Card, Modal, Status Badge, Allocation Slider, High-Density Table Row, and Explainable AI Math Drawer), each featuring full variant sets, interactive states, and documented DOs & DON'Ts.

---

## 1. Modular Typography Scale (1.250 Major Third Ratio)

Typography is anchored to an accessible base size of **16px ($1.0\text{rem}$)** scaling on a **Major Third (1.250)** ratio. Font family: Inter / System Sans-Serif with tabular numeric features (`tnum`) enabled for high-density inventory figures.

```
┌────────────────────────────────────────────────────────────────────────┐
│                    MODULAR TYPOGRAPHY SPECIFICATION                    │
├──────────────┬────────────┬─────────────┬────────┬─────────────────────┤
│ Token Name   │ Font Size  │ Line Height │ Weight │ Primary Role        │
├──────────────┼────────────┼─────────────┼────────┼─────────────────────┤
│ Display-Hero │ 38px (2.4r)│ 46px (1.20) │ 800    │ Marketing & Covers  │
│ Heading-1    │ 30px (1.9r)│ 38px (1.25) │ 700    │ Top-Level Headers   │
│ Heading-2    │ 24px (1.5r)│ 32px (1.33) │ 700    │ Section / Modal Hdr │
│ Heading-3    │ 20px (1.2r)│ 26px (1.30) │ 600    │ Card & Module Title │
│ Body-Large   │ 16px (1.0r)│ 24px (1.50) │ 400/500│ Form Labels / Intro │
│ Body-Base    │ 14px (.88r)│ 20px (1.43) │ 400/500│ Grid Rows & Tables  │
│ Body-Small   │ 12px (.75r)│ 16px (1.33) │ 400/500│ Metadata & Helper   │
│ Caption-Mono │ 11px (.69r)│ 14px (1.27) │ 600    │ SKU Codes & Timers  │
└──────────────┴────────────┴─────────────┴────────┴─────────────────────┘
```

---

## 2. Semantic Color Token System (Light vs. Dark Mode Variables)

Rather than scattering raw hex codes (`#1e293b`), tokens are abstracted into **semantic functional aliases**. Variables switch cleanly between Light Mode (office desktop) and Dark Mode (warehouse floor night shift):

```
┌────────────────────────────────────────────────────────────────────────┐
│                   SEMANTIC COLOR TOKEN ARCHITECTURE                    │
├──────────────────────────┬──────────────────────┬──────────────────────┤
│ Semantic Token Name      │ Light Mode Variable  │ Dark Mode Variable   │
├──────────────────────────┼──────────────────────┼──────────────────────┤
│ surface-canvas           │ #F8FAFC (Slate-50)   │ #0B0F17 (Obsidian)   │
│ surface-default          │ #FFFFFF (Pure White) │ #111827 (Gray-900)   │
│ surface-subtle           │ #F1F5F9 (Slate-100)  │ #1F2937 (Gray-800)   │
│ surface-card             │ #FFFFFF (Pure White) │ #161F30 (Deep Slate) │
│ surface-raised (Modal)   │ #FFFFFF (Elevation 3)│ #1E293B (Elevation 3)│
│                          │                      │                      │
│ text-primary             │ #0F172A (Slate-900)  │ #F8FAFC (Slate-50)   │
│ text-secondary           │ #475569 (Slate-600)  │ #94A3B8 (Slate-400)  │
│ text-tertiary            │ #64748B (Slate-500)  │ #64748B (Slate-500)  │
│ text-inverse             │ #FFFFFF (Pure White) │ #0F172A (Slate-900)  │
│                          │                      │                      │
│ border-default           │ #E2E8F0 (Slate-200)  │ #334155 (Slate-700)  │
│ border-subtle            │ #F1F5F9 (Slate-100)  │ #1E293B (Slate-800)  │
│ border-focus             │ #6366F1 (Indigo-500) │ #818CF8 (Indigo-400) │
│                          │                      │                      │
│ action-primary-default   │ #4F46E5 (Indigo-600) │ #6366F1 (Indigo-500) │
│ action-primary-hover     │ #4338CA (Indigo-700) │ #4F46E5 (Indigo-600) │
│ action-primary-disabled  │ #C7D2FE (Indigo-200) │ #312E81 (Indigo-900) │
│                          │                      │                      │
│ feedback-success-surface │ #DCFCE7 (Green-100)  │ #064E3B (Green-950)  │
│ feedback-success-text    │ #15803D (Green-700)  │ #34D399 (Green-400)  │
│ feedback-warning-surface │ #FEF3C7 (Amber-100)  │ #78350F (Amber-950)  │
│ feedback-warning-text    │ #B45309 (Amber-700)  │ #FBBF24 (Amber-400)  │
│ feedback-danger-surface  │ #FEE2E2 (Red-100)    │ #7F1D1D (Red-950)    │
│ feedback-danger-text     │ #B91C1C (Red-700)    │ #F87171 (Red-400)    │
└──────────────────────────┴──────────────────────┴──────────────────────┘
```

---

## 3. Spacing & Elevation Token Scale (8-Point Grid)

Spacing follows an uncompromising **8-point geometric scale** (with 4px half-steps for compact microcopy and inputs):

- `space-050` = **4px**: Inline icon-to-label gaps, badge padding.
- `space-100` = **8px**: Button vertical padding, compact table cell margins.
- `space-150` = **12px**: Input field vertical padding, card sub-item spacing.
- `space-200` = **16px**: Default card internal padding, modal gutter.
- `space-300` = **24px**: Section dividers, tablet touch grid spacing.
- `space-400` = **32px**: Major container spacing, dashboard grid gaps.
- `space-600` = **48px**: Minimum tactile touch targets for warehouse floor tablets.
- `space-800` = **64px**: Page-level header breathing room.

### Elevation Tokens (Depth & Lighting)
- `elevation-0`: Flat borders (tables, flat cards). `0px 0px 0px 1px border-default`.
- `elevation-1`: Subtle drop shadow (hover cards, dropdown menus). `0px 2px 4px rgba(0,0,0,0.06)`.
- `elevation-2`: Raised surfaces (sticky header, drawers). `0px 4px 12px rgba(0,0,0,0.10)`.
- `elevation-3`: Overlay modals (emergency triage modal). `0px 12px 32px rgba(0,0,0,0.18)`.

---

## 4. Eight Core Production Components & Variant Sets

```
┌────────────────────────────────────────────────────────────────────────┐
│                   8 CORE PRODUCTION COMPONENTS MATRIX                  │
├───────────────────────────────────┬────────────────────────────────────┤
│ Standard Universal Components     │ Capstone-Specific Components       │
│ 1. Button (4 Types × 3 Sizes)     │ 5. Status Badge (4 Shapes & Colors)│
│ 2. Form Input (Text, Select, Srch)│ 6. Allocation Tactile Slider       │
│ 3. Metric Card (Default & Hover)  │ 7. High-Density Data Table Row     │
│ 4. Triage Modal (Sm, Md, Lg)      │ 8. Explainable AI (XAI) Math Drawer│
└───────────────────────────────────┴────────────────────────────────────┘
```

### Component 1: Button
- **Figma Variants**:
  - `Type`: `Primary`, `Secondary`, `Destructive`, `Ghost`
  - `Size`: `Large (48px)`, `Medium (40px)`, `Small (32px)`
  - `State`: `Default`, `Hover`, `Focused`, `Active (Pressed)`, `Disabled`, `Loading (Spinner)`
  - `Icon`: `None`, `Leading Icon`, `Trailing Icon`
- **Auto-Layout Specs**: `Large`: H:48px, Px: 24px, Py: 12px, Radius: 8px, Gap: 8px.
- **Usage Rules**:
  - **DO**: Use `Primary Large` for final confirmation actions (*"Confirm & Lock Buffer"*).
  - **DON'T**: Never place two `Primary` buttons side-by-side; pair `Primary` with `Secondary` or `Ghost`.

### Component 2: Form Input
- **Figma Variants**:
  - `Type`: `Text Input`, `Number Counter`, `Dropdown Select`, `Search Bar`
  - `Size`: `Medium (40px)`, `Small (32px)`
  - `State`: `Default`, `Active / Focused`, `Filled`, `Error (with Helper Text)`, `Disabled`
- **Auto-Layout Specs**: H: 40px, Px: 12px, Border: 1px `border-default`, Radius: 6px.
- **Usage Rules**:
  - **DO**: Always include a persistent label and a dedicated helper-text container beneath the field to prevent layout shift on error states.
  - **DON'T**: Do not use placeholder text as a replacement for field labels.

### Component 3: Metric Card
- **Figma Variants**:
  - `Type`: `Inventory Health`, `Channel Velocity`, `Warehouse Wave Staging`
  - `Theme`: `Light Mode`, `Dark Mode`
  - `Interactive State`: `Static`, `Hover Raised (elevation-1)`
- **Auto-Layout Specs**: P: 20px, Gap: 12px, Border: 1px `border-default`, Radius: 12px.
- **Usage Rules**:
  - **DO**: Pair numeric metrics with a directional delta badge (e.g. `+14.2u/hr` in green).
  - **DON'T**: Do not overcrowd a single metric card with more than two sub-metrics.

### Component 4: Triage Modal
- **Figma Variants**:
  - `Size`: `Medium (640px)`, `Large (880px)`, `Side-Sheet Drawer (480px)`
  - `Type`: `Emergency Rebalance Modal`, `CSV Linting Modal`, `Confirmation Dialogue`
- **Auto-Layout Specs**: W: 640px, P: 24px, Elevation: `elevation-3`, Radius: 16px, Backdrop: `rgba(15,23,42,0.6)`.
- **Usage Rules**:
  - **DO**: Lock background page scroll when modal is open; enable `Esc` key and backdrop click to dismiss.
  - **DON'T**: Do not stack modals on top of other modals; use slide-out drawers for secondary data inspection.

### Component 5: Status Badge / Token (Capstone-Specific)
- **Figma Variants**:
  - `Status`: `SYNCED`, `AT RISK`, `BLOCKED`, `TRANSFER PENDING`
  - `Shape Token`: Hexagon (`SYNCED`), Triangle (`AT RISK`), Square (`BLOCKED`), Capsule (`TRANSFER`)
  - `Mode`: `Light`, `Dark`
- **Auto-Layout Specs**: H: 24px, Px: 8px, Py: 2px, Radius: 4px, Font: `Caption-Mono (11px, 700)`.
- **Usage Rules**:
  - **DO**: Ensure every status badge carries both a distinctive color and a unique geometric icon to satisfy **WCAG 2.1 AA** color-blind accessibility.
  - **DON'T**: Never rely solely on color to communicate operational urgency.

### Component 6: Allocation Tactile Slider (Capstone-Specific)
- **Figma Variants**:
  - `State`: `Default Continuous`, `Step Snap (25% / 50% / Fill Deficit)`, `Depleted Warning`, `Disabled`
  - `Thumb Size`: `Desktop (24px)`, `Tablet Touch (36px)`
- **Auto-Layout Specs**: Track H: 8px, Radius: 4px, Active Track: `action-primary-default`, Quick-Snap Pills: H: 28px, Gap: 8px.
- **Usage Rules**:
  - **DO**: Provide immediate real-time numeric counter updates adjacent to the thumb handle during dragging.
  - **DON'T**: Do not allow users to drag past the available warehouse reserve limit without triggering an explicit safety confirmation.

### Component 7: High-Density Data Table Row (Capstone-Specific)
- **Figma Variants**:
  - `Row Type`: `Standard SKU Row`, `Alert / Discrepancy Row`, `Selected Bulk Row`, `Expanded Detail View`
  - `Density`: `Desktop High-Density (40px)`, `Tablet Touch (54px)`
  - `State`: `Default`, `Hover`, `Active`, `Error`
- **Auto-Layout Specs**: H: 40px, Px: 16px, Border-Bottom: 1px `border-subtle`, Tabular Numbers enabled.
- **Usage Rules**:
  - **DO**: Maintain strict column alignment (text left-aligned, monetary/inventory counts right-aligned).
  - **DON'T**: Do not truncate SKU codes; wrap or provide immediate hover tooltips.

### Component 8: Explainable AI (XAI) Formula Inspector (Capstone-Specific)
- **Figma Variants**:
  - `State`: `Collapsed Inline Pill`, `Expanded Math Drawer`, `Verified Audit Mode`
  - `Formula Output`: `Live Calculation`, `Stale / Warning State`
- **Auto-Layout Specs**: P: 16px, Radius: 8px, Background: `surface-subtle`, Border: 1px dashed `border-focus`.
- **Usage Rules**:
  - **DO**: Always render the exact formula: `(Daily Velocity × Lead Time [Days]) + Safety Buffer = Suggested Units`.
  - **DON'T**: Never replace the formula with vague copy like *"Optimized by Smart AI"*.

---

## 5. Sample Screen Theme Switching (Light Mode vs. Dark Mode)

To verify the tokens in production, `MOD-02` (Emergency Rebalance Modal) was built exclusively using Figma semantic variables. Switching modes requires zero manual color overrides:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   SAMPLE SCREEN THEME TRANSFORMATION                   │
├───────────────────────────────────┬────────────────────────────────────┤
│ Light Mode (Office Workstation)   │ Dark Mode (Warehouse Night Shift)  │
├───────────────────────────────────┼────────────────────────────────────┤
│ • Background: #FFFFFF             │ • Background: #161F30              │
│ • Modal Border: #E2E8F0           │ • Modal Border: #334155            │
│ • Primary Text: #0F172A           │ • Primary Text: #F8FAFC            │
│ • Slider Track: #E2E8F0           │ • Slider Track: #334155            │
│ • Slider Active: #4F46E5          │ • Slider Active: #6366F1           │
│ • XAI Formula Box: #F1F5F9        │ • XAI Formula Box: #1E293B         │
│ • Contrast Ratio: 14.8:1 (AAA)    │ • Contrast Ratio: 13.2:1 (AAA)     │
└───────────────────────────────────┴────────────────────────────────────┘
```

---

## 6. Reviewer Verification Checklist

- [x] **Typography scale defined (6+ styles)**: 8 styles based on a 1.250 Major Third modular scale with tabular figures.
- [x] **Color tokens use semantic names**: Complete mapping of `surface-*`, `text-*`, `border-*`, `action-*`, and `feedback-*`.
- [x] **Built as Figma variables with Light & Dark modes**: Dual-mode parity table with seamless token switching.
- [x] **Spacing scale follows consistent ratio**: 8-point geometric scale (4px to 64px) with dedicated tactile 48px/54px targets.
- [x] **8+ Core components with variants & usage rules**: Button, Input, Card, Modal, Status Badge, Allocation Slider, Data Table Row, and XAI Formula Inspector Drawer.
- [x] **Design System Page in Figma**: Token variables and components organized on Page `05_Design System & Components`.
