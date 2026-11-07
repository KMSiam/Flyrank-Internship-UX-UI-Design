# DESIGN.md — FlyCore Design System v1.0
**Project**: FlyCommerce OS · **Author**: K. M. Siam ([GitHub: @KMSiam](https://github.com/KMSiam))  
**Figma Workspace**: [FlyCore Master Design System (View Access)](https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access)

---

## 1. System Philosophy: "Velocity Through Clarity"

**FlyCore Design System** is an enterprise-grade, accessibility-first design foundation engineered for high-stakes, multi-channel supply chain operations. 

In e-commerce fulfillment, interface ambiguity causes missed carrier cutoffs, stockouts, and financial penalties. FlyCore is built on four core tenets:
1. **Zero Aesthetic Slop**: Every element serves an operational purpose. We reject low-density consumer whitespace and decorative glassmorphism in favor of high-contrast, glanceable data density.
2. **Deterministic Token Hierarchy**: Colors, typography, and spacing are strictly referenced through semantic variables—never hard-coded hexes.
3. **Ergonomic Multi-Modal Parity**: Seamless parity between desktop high-density grids (1440px) and rugged warehouse floor tablets (1024px with 48px+ touch targets).
4. **Explainable AI (XAI) Native**: Machine learning recommendations are always paired with inspectable mathematical formulas and human control governors.

---

## 2. Key Architecture Decisions & Rationales

```
┌────────────────────────────────────────────────────────────────────────┐
│                   FLYCORE ARCHITECTURE FOUNDATIONS                     │
├────────────────────┬───────────────────────────────────────────────────┤
│ 1. Color Engine    │ Semantic Functional Aliases (Light & Dark Mode)   │
│ 2. Typography      │ 1.250 Major Third Modular Scale with Tabular Nums │
│ 3. Spacing Grid    │ Strict 8-Point Spatial Rhythm (4px to 64px)       │
│ 4. Component Logic │ Category / Component / Variant / Size / State     │
└────────────────────┴───────────────────────────────────────────────────┘
```

### A. Semantic Color Tokens & WCAG Compliance
Colors are abstracted into functional roles rather than descriptive palettes (e.g., `action-primary-default` instead of `indigo-600`):
- **Surfaces**: `surface-canvas` (#F8FAFC / #0B0F17), `surface-card` (#FFFFFF / #161F30), `surface-raised` (Elevation 3).
- **Text**: `text-primary` (14.8:1 AAA contrast), `text-secondary` (7.2:1 AA contrast), `text-inverse` (#FFFFFF).
- **Feedback**: `feedback-success-text` (#15803D), `feedback-warning-text` (#B45309), `feedback-danger-text` (#B91C1C). Every status token pairs color with a distinct geometric shape (Hexagon, Triangle, Square) for color-blind accessibility.

### B. Mathematical Modular Typography (1.250 Major Third)
Anchored to **16px base ($1.0\text{rem}$)**:
- `Display-Hero` (38px / 800) · `Heading-1` (30px / 700) · `Heading-2` (24px / 700) · `Heading-3` (20px / 600)
- `Body-Large` (16px / 500) · `Body-Base` (14px / 400-500) · `Body-Small` (12px / 400) · `Caption-Mono` (11px / 600 `tnum`)
- *Tabular Numbers (`tnum`)*: Mandatory on all inventory tables to prevent visual jitter when numbers update dynamically.

### C. 8-Point Spatial System
- `space-050` (4px) · `space-100` (8px) · `space-150` (12px) · `space-200` (16px) · `space-300` (24px) · `space-400` (32px) · `space-600` (48px) · `space-800` (64px).
- Warehouse touch targets enforce a strict minimum height of **48px (Desktop)** and **54px (Tablet)**.

---

## 3. "How to Use This" (5-Minute Onboarding for New Designers)

1. **Never Detach a Component**: If an existing component does not meet your screen's layout requirement, request an extension or create a new variant on Page `05_Design System & Components`.
2. **Apply Tokens via Variables Panel**: Press `Shift + I` to insert components. When coloring frames or text, always bind to the local variables library (`surface-*`, `text-*`, `border-*`).
3. **Follow the Slash Hierarchy**: Name all new components using:  
   `Category / Component / Variant / Size / State` (e.g. `Button / Primary / Large / Default`).
4. **Inspect in Dev Mode**: Every component uses 100% responsive Figma Auto-Layout. Engineers can copy exact Tailwind CSS classes or CSS variables directly from Dev Mode.

---

## 4. How to Extend the System

When introducing a new component or token:
1. **Check the Contrast Ratio**: Ensure all new foreground/background pairs exceed **4.5:1 (WCAG AA)** for body text and **3.0:1** for UI components.
2. **Provide Light & Dark Mode Pairs**: Every new surface token must have an explicit Dark Mode counterpart in the variables collection.
3. **Document DOs and DON'Ts**: Every component added to the library must include at least one positive and one negative usage guideline.

---

## 5. Reusable AI Prompt Cheat Sheet (For System Expansion)

Use these calibrated system prompts in DeepSeek or Claude to generate future design system assets without hallucinated "slop":

```markdown
### Prompt 1: New Component Combinatorial Matrix Generator
"Act as a Principal Design System Architect. I need to create a new [Component Name, e.g. Notification Toast].
Define its attribute axes: [Type] x [Priority] x [State] x [Device].
Generate a complete markdown matrix listing every single variant following the strict naming convention:
'Category / Component / Variant / Size / State'.
Provide exact Figma Auto-Layout specifications (height, horizontal padding, vertical padding, border radius, and token bindings for surface, text, and border)."

### Prompt 2: WCAG-Compliant Semantic Token Generator
"Generate a semantic color palette for an enterprise e-commerce tool.
The palette must include: surface-canvas, surface-card, surface-raised, text-primary, text-secondary, border-default, border-focus, action-primary (default, hover, active, disabled), and feedback (success, warning, danger).
For every token, provide:
1. Light Mode Hex
2. Dark Mode Hex
3. Calculated WCAG Contrast Ratio against the surface canvas.
Reject any pairing below 4.5:1."
```
