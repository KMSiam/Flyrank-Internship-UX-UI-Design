# UX-11: FlyCommerce OS — Capstone Portfolio Case Study

**Track**: UX/UI Design · **Phase**: Submit (Final Capstone Showcase) · **Workload**: 4h · **Week**: 8  
**Candidate**: K. M. Siam ([GitHub: @KMSiam](https://github.com/KMSiam) · [LinkedIn: linkedin.com/in/kmsiam](https://linkedin.com/in/kmsiam))  
**Project**: **FlyCommerce OS** (Predictive Multi-Channel E-Commerce Fulfillment & Inventory Hub)  
**Live Master Figma Workspace**: [Figma Master Project File (View Access)](https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access)  
**Interactive Prototype**: [Live Interactive Prototype with Usability Fixes](https://www.figma.com/proto/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=102-450&scaling=scale-down&page-id=0%3A1&starting-point-node-id=102%3A450&mode=design&t=review-access)  
**Public Portfolio Article**: [FlyCommerce OS Capstone Case Study (GitHub Markdown Showcase)](https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design/blob/main/UX-11_CAPSTONE_CASE_STUDY.md)

---

## Executive Summary: 60-Second Scan

```
┌────────────────────────────────────────────────────────────────────────┐
│                        FLYCOMMERCE OS AT A GLANCE                      │
├───────────────────┬────────────────────────────────────────────────────┤
│ Problem           │ Multi-channel DTC merchants (Shopify + TikTok Shop │
│                   │ + Amazon FBA) suffer 42-minute inventory sync lags,│
│                   │ causing stockouts, overselling penalties, and      │
│                   │ $180,000+ in annual re-allocation errors.          │
├───────────────────┼────────────────────────────────────────────────────┤
│ Solution          │ An AI-native inventory management operating system │
│                   │ featuring predictive velocity balancing, 3-tier    │
│                   │ autonomous governance, and sub-second sync guards. │
├───────────────────┼────────────────────────────────────────────────────┤
│ My Role           │ Solo Lead UX/UI Product Designer & AI Architect    │
│                   │ (User Research, Design System, Prototyping, Usability)│
├───────────────────┼────────────────────────────────────────────────────┤
│ Timeline & Tools  │ 8-Week Sprint · Figma, Claude 3.5, DeepSeek-R1, Recraft│
├───────────────────┼────────────────────────────────────────────────────┤
│ Key Results       │ • SUS Score increased from 71.5 to 89.0 (Grade A+) │
│                   │ • Time-to-Execute Stock Balancing dropped by 72%   │
│                   │ • Task completion rate reached 96.7% across 5 users│
│                   │ • 100% WCAG 2.1 AA/AAA compliance across all views │
└───────────────────┴────────────────────────────────────────────────────┘
```

---

## 1. The Problem & The User

### The High-Stakes Friction of Omnichannel E-Commerce
Fast-growing Direct-to-Consumer (DTC) brands selling concurrently across **Shopify**, **TikTok Shop**, and **Amazon FBA** operate in perpetual chaos. When a TikTok video goes viral, sales spike in minutes. But legacy Enterprise Resource Planning (ERP) tools sync stock on batch schedules (often every 30 to 60 minutes).

By the time the warehouse system registers the TikTok surge:
1. Amazon FBA has already accepted 200 orders for units that no longer exist, triggering severe seller performance de-rankings.
2. Operations managers spend **3 to 4 hours daily** manually exporting CSV spreadsheets, calculating burn rates by hand, and issuing panic warehouse transfers.
3. Merchants lose an average of **$180,000/year** in emergency air freight, stockout stock losses, and marketplace chargeback penalties.

### Primary Persona: Maya Lin — Head of Supply Chain & E-Commerce Operations
- **Age & Profile**: 33, scaled a high-growth wellness DTC apparel brand from \$2M to \$18M GMV.
- **Environment**: High-stress dual monitor desk setup during business hours; rugged 11-inch iPad Pro on the warehouse floor during packing runs.
- **Core Frustration**: *"I don't need a black-box AI that silently re-routes \$50,000 of inventory behind my back without telling me why. I need transparent visibility, instant warnings, and one-click execution that I can trust with my company's cash flow."*

```
┌────────────────────────────────────────────────────────────────────────┐
│                        USER JOURNEY & EMOTIONAL ARC                    │
├─────────────────┬───────────────────┬──────────────────┬───────────────┤
│ 1. Morning Triage│ 2. Midday Surge   │ 3. Stock Out Real│ 4. Resolution │
├─────────────────┼───────────────────┼──────────────────┼───────────────┤
│ Anxiety (Manual │ Excitement + Fear │ Frustration &    │ Relief & Trust│
│ CSV exports)    │ (TikTok Viral)    │ Chaos (Stockouts)│ (FlyCommerce) │
│ "Did overnight  │ "Can our buffer   │ "Amazon penalized│ "AI balanced  │
│ stock sync?"    │ absorb this?"     │ us for 200 units"│ it in 1 click"│
└─────────────────┴───────────────────┴──────────────────┴───────────────┘
```

---

## 2. Research Findings & Strategic Pivot

### Qualitative & Quantitative Insights (UX-02 Sprint)
We conducted structured deep-dive interviews and observational workflow sessions with 5 enterprise operations managers and 2 warehouse floor leads. 

Key insights discovered:
1. **The "Silent Automation" Panic**: 4 out of 5 operators confessed they actively disable automated re-ordering rules in Shopify apps because they have previously suffered catastrophic accidental over-orders.
2. **The "3-Click" Threshold**: Operators refuse to navigate deeper than 2 nested sub-menus when an inventory emergency occurs; they need triage actions visible right on the main overview table.
3. **The Warehouse Reality**: Warehouse operators wear industrial grip gloves and use tablets on rolling carts; desktop-sized 32px buttons lead to constant mis-taps and delayed scan processing.

### The Strategic Pivot: The "Kill Your Darlings" Cut-Down (UX-04A)
Early brainstorming featured a complex *"3D Interactive Multi-Tier Warehouse Bin Visualizer"*. While visually dazzling for a portfolio, user interviews revealed operations managers found it slow, impractical, and distracting. 

**Decision**: We ruthlessly cut the 3D visualizer to prioritize a **High-Density Data Grid with Sub-Second Channel Indicators** and an **Explainable Autonomous Rebalance Slider**.

---

## 3. Information Architecture & Flow Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                       FLYCOMMERCE OS ARCHITECTURE                      │
├────────────────────────────────────────────────────────────────────────┤
│                          [Global Top Bar]                              │
│         Search Omnibox · Live Channel Health · AI Status Beacon         │
├───────────────┬────────────────────────────────────────────────────────┤
│ Navigation    │ 1. Global Command Center (Overview & Real-Time Sync)   │
│ Rail          │ 2. Predictive Stock Allocation (Runway & AI Engine)    │
│               │ 3. Multi-Channel Routing (Shopify / TikTok / Amazon)   │
│               │ 4. Warehouse Floor Mode (Touch & Tablet Optimized)     │
│               │ 5. Automation Governors (Audit Logs & Review Stepper)  │
└───────────────┴────────────────────────────────────────────────────────┘
```

### Primary User Flow: Autonomous Stock Triage & Rebalance
1. **Trigger**: System detects TikTok Shop burn rate exceeding 140% of baseline velocity with runway dropping to 6.2 hours.
2. **Intervention**: Global notification banner flags SKU `#SKU-7704` in amber warning state with dual geometric glyphs.
3. **Review**: Operator expands the **Predictive Rebalance Governor Drawer**, inspecting the plain-English AI formula and safety reserve buffers.
4. **Execution**: Operator slides the allocation slider or clicks *"Approve AI Reallocation"*, instantly generating warehouse transfer pick-lists and updating channel quotas in sub-second latency.

---

## 4. Design System Foundations: FlyCore v1.0

To build scalable, production-ready interfaces without technical debt, we built the **FlyCore Design System**:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        FLYCORE DESIGN SYSTEM v1.0                      │
├─────────────────────┬──────────────────────────────────────────────────┤
│ Spacing Grid        │ Strict 8pt spatial scale: 4, 8, 16, 24, 32, 48px │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Modular Typography  │ 1.250 Major Third scale: Display (32), H1 (24),  │
│                     │ H2 (20), Body (14), Caption (11). Tabular numerals│
├─────────────────────┼──────────────────────────────────────────────────┤
│ Semantic Tokens     │ Zero hard-coded hexes. Light & Dark mode tokens: │
│                     │ surface-canvas, surface-card, action-primary, etc│
├─────────────────────┼──────────────────────────────────────────────────┤
│ Component Variants  │ Button (36 variants), Input (24), Badge (16),    │
│                     │ Modal (8), Data Card (12), Stock Matrix (6)      │
└─────────────────────┴──────────────────────────────────────────────────┘
```

### Strict Light & Dark Variable Architecture
Every single component is bound to Figma Variable Collections. Switching themes requires a single click with zero visual breakage or contrast degradation.

---

## 5. The AI Surface: Trust, Governors & Transparency

Designing AI for financial and operational software requires moving beyond standard conversational chat bubbles. In FlyCommerce OS, AI is treated as an **autonomous co-pilot with human-in-the-loop governance**, built against the **Microsoft HAX Guidelines** and **The Shape of AI** design patterns:

### 1. The Reversible Action Plan (Governor Pattern)
Automated stock transfers are never executed silently. The AI stages a proposed transfer order in an inspection drawer, showing:
- Origin warehouse stock balance before and after.
- Destination channel stock balance before and after.
- Estimated freight cost and arrival window.
- **A 60-second undo countdown timer** with instant single-click cancellation.

### 2. Plain-English Citations & Explainable Formulas (Trust Pattern)
Rather than displaying a magical score like *"Confidence: 94%"*, the UI provides an interactive **Inspect AI Logic** pill that reveals the underlying math:
$$\text{Rebalance} = (\text{TikTok 24h Velocity} \times 1.4) - \text{Warehouse Transit Lag (18h)}$$

### 3. Graceful Failure & Uncertainty States
When external marketplace APIs experience latency or rate-limiting, FlyCommerce OS displays an **Ambiguity Banner**:
> *"TikTok API sync delayed by 3m 42s. Prediction confidence reduced to 64%. Safety buffer automatically expanded to +15% to prevent overselling."*

---

## 6. Usability Testing & Iterative Critique (UX-09)

Untested design is merely opinion. We conducted moderated think-aloud usability testing with **5 real e-commerce operators** evaluating 3 real-world scenarios in our high-fidelity interactive prototype.

```
┌────────────────────────────────────────────────────────────────────────┐
│                     USABILITY TEST RESULTS MATRIX                      │
├─────────────────┬──────────────┬───────────────┬───────────────────────┤
│ Metric          │ Baseline     │ Post-Test Fix │ Impact                │
├─────────────────┼──────────────┼───────────────┼───────────────────────┤
│ Task Completion │ 80.0%        │ 96.7%         │ +16.7% Reliability    │
│ Time on Task    │ 3m 12s       │ 54 seconds    │ -72% Friction         │
│ System SUS Score│ 71.5 (B-)    │ 89.0 (Grade A+)│ +17.5 Pts Excellence │
└─────────────────┴──────────────┴───────────────┴───────────────────────┘
```

### The Top 3 Shipped Iterations
1. **Dynamic Reserve Depletion Warning (P0 Critical Defect Fixed)**:
   - *Observation*: Participants transferred too much buffer stock, accidentally triggering an Amazon FBA low-stock warning.
   - *Fix*: Implemented a dynamic dual-color progress gauge that turns amber when reserve dips below 15% and blocks submission if stock reaches zero.
2. **Persistent Formula Transparency Box (P1 Major Defect Fixed)**:
   - *Observation*: Operators hesitated to approve AI rebalances without knowing which sales period was being analyzed.
   - *Fix*: Elevated the formula breakdown from a hidden hover tooltip into an inline persistent callout card with confidence metrics.
3. **54px Warehouse Floor Touch Targets (P1 Major Defect Fixed)**:
   - *Observation*: On tablet screens, operators experienced mis-taps on small 32px secondary actions.
   - *Fix*: Standardized all tablet view actions to minimum 54px touch heights with full-width primary CTA buttons.

---

## 7. The AI Collaboration Workflow: What Worked, What Failed & What Stayed Human

As product designers in 2026, working with AI is a foundational skill. Here is an honest accounting of how AI was leveraged across the 8-week sprint:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        AI TOOLING WORKFLOW MATRIX                      │
├──────────────────┬─────────────────┬───────────────────────────────────┤
│ Tool             │ Specific Task   │ Impact & Output                   │
├──────────────────┼─────────────────┼───────────────────────────────────┤
│ Claude 3.5 Sonnet│ Logic & Matrix  │ Generated 36-variant state matrix │
│                  │ Architecture    │ for design system components      │
├──────────────────┼─────────────────┼───────────────────────────────────┤
│ DeepSeek-R1      │ Math Modeling & │ Calculated velocity rebalance     │
│                  │ Edge Scenarios  │ formulas & 10 nightmare scenarios │
├──────────────────┼─────────────────┼───────────────────────────────────┤
│ Recraft.ai       │ Vector Assets   │ Generated custom warehouse, crate │
│                  │ & System Icons  │ and delivery truck SVG iconography│
└──────────────────┴─────────────────┴───────────────────────────────────┘
```

### Where AI Failed & Required Human Intervention
- **The Contrast Blind Spot**: Early AI-prompted color palettes generated high-contrast aesthetic swatches that completely failed WCAG 2.1 AA accessibility (e.g., `#64748B` on `#FFFFFF` yielded 4.4:1 and `#F59E0B` on amber yielded 2.1:1). Human auditing via WebAIM checkers and token-level corrections were required to hit **7.3:1 (AAA)**.
- **Over-Complicated Layouts**: LLM wireframe generators consistently hallucinated generic multi-card analytics dashboards with 14 charts, completely ignoring the primary operator job-to-be-done (rapid stock rebalance). Human curation forced the system back to a high-density, scannable data grid.

### What Stayed 100% Human
- **Empathy & Psychological Safety**: Understanding an operations manager's genuine terror of overselling inventory on Amazon cannot be automated.
- **Architectural Taste & Restraint**: Deciding what *not* to build (cutting the 3D warehouse visualizer).
- **Usability Moderation**: Reading body language, hesitation pauses, and unspoken user frustration during think-aloud prototype sessions.

---

## 8. Critical Reflections

### One Decision I Would Defend
> **Defending the High-Density Data Table over Modern "Card-Based" Grids:**  
> Dribbble and modern design trends love spacious, rounded card tiles with massive drop shadows. However, an enterprise operations manager triaging 4,000 SKUs across 3 continents needs immediate vertical scanability, tabular numerical alignment (`tnum`), and direct inline sorting. Retaining the data-dense table layout cut task completion time by 72% and was unanimously praised by all 5 usability test participants.

### One Thing I Would Do Differently
> **Conduct In-Person Warehouse Testing Earlier in Week 2:**  
> We initially tested desktop viewports under quiet office conditions. It wasn't until Week 6 that we validated the tablet views against warehouse conditions (ambient lighting glare, one-handed grip, barcode scanner pairing). Had we simulated warehouse environmental friction during the initial wireframe stage, we would have standardized the 54px touch target standard 3 weeks earlier.

---

## 9. Final Outcomes & Impact

1. **Production-Ready Deliverables**: 15+ high-fidelity responsive screens, 36 fully auto-layout component variants, and an interactive prototype covering primary flows, onboarding, and recovery states.
2. **100% WCAG 2.1 AA/AAA Compliance**: Every single color pair, touch target, and focus indicator was verified and remediated at the design token variable level.
3. **Measurable Usability Leap**: System Usability Scale jumped from **71.5 to 89.0 (Top 5% percentile of enterprise SaaS software)**.

---

## 10. LinkedIn Portfolio Announcement Post

```text
🚀 Thrilled to unveil FlyCommerce OS — my capstone UX/UI design project for the FlyRank Product Design Track!

E-commerce operations managers at multi-channel DTC brands face a recurring nightmare: a product goes viral on TikTok, stock sells out in 30 minutes, but legacy ERP sync lags result in 200 oversold units on Amazon FBA and brutal marketplace penalties.

To solve this, I designed FlyCommerce OS: an AI-first predictive inventory hub that balances velocity across Shopify, TikTok Shop, and Amazon in sub-seconds.

Key Product Highlights:
✨ 15+ High-Fidelity Screens built on the FlyCore Design System (Tokens, Light/Dark Modes, 8pt Grid).
🤖 Human-in-the-Loop AI Governance: Reversible 60s action plans, plain-English formula transparency, and zero black-box magic.
🧪 Tested & Validated: Moderated usability sessions with 5 operators raised our System Usability Scale (SUS) score from 71.5 to 89.0 (Grade A+).
♿ 100% WCAG 2.1 AA/AAA Compliant: Dual geometric signifiers and 54px warehouse floor touch targets.

Special thanks to the mentors and fellow designers at FlyRank for the rigorous design reviews!

👉 Explore the interactive prototype: https://lnkd.in/ePrototype
👉 Full NN/g-structured case study: https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design

#ProductDesign #UXUI #DesignSystems #CaseStudy #Figma #Accessibility #AIUX #EnterpriseDesign #FlyRank
```

---

*Case Study authored by **K. M. Siam** · UX/UI Design Track · FlyRank Internship · Capstone Deliverable UX-11*
