# FlyCommerce OS: Capstone Impact Project Summary

**Track**: UX/UI Design · **Code**: UX (Capstone Impact Project) · **Workload**: 24h · **Week**: 7–8  
**Candidate**: K. M. Siam ([GitHub: @KMSiam](https://github.com/KMSiam) · [LinkedIn: linkedin.com/in/kmsiam](https://linkedin.com/in/kmsiam))  
**Project**: **FlyCommerce OS** (Predictive Multi-Channel E-Commerce Fulfillment & Inventory Hub)  
**Target Audience**: Incoming designers & product teams needing an instant, honest, artifact-heavy onboarding summary.

---

## 1. Project Snapshot

```
┌────────────────────────────────────────────────────────────────────────┐
│                        PROJECT SNAPSHOT AT A GLANCE                    │
├─────────────────────┬──────────────────────────────────────────────────┤
│ Focus Area          │ Omnichannel E-Commerce Inventory Triage &        │
│                     │ Predictive Rebalancing (Shopify, TikTok, Amazon)│
├─────────────────────┼──────────────────────────────────────────────────┤
│ Core Problem        │ A 42-minute batch sync lag between marketplaces  │
│                     │ causes overselling during viral demand spikes,    │
│                     │ inflicting $180k/yr in fines and stockouts.      │
├─────────────────────┼──────────────────────────────────────────────────┤
│ What We Built       │ An AI-native inventory operating system with     │
│                     │ high-density real-time tables, an explainable AI │
│                     │ rebalance governor, and tablet warehouse modes.  │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Outcome 1           │ System Usability Scale (SUS) jumped from         │
│ (Usability)         │ 71.5 to 89.0 (Grade A+ Excellent / Top 5%).      │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Outcome 2           │ Time-to-Execute Stock Balancing dropped by 72%   │
│ (Efficiency)        │ (from 3 minutes 12 seconds to 54 seconds).       │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Outcome 3           │ 100% WCAG 2.1 AA/AAA compliance across all views │
│ (Accessibility)     │ with zero detached design system components.     │
└─────────────────────┴──────────────────────────────────────────────────┘
```

---

## 2. Week-by-Week Journey Map (Deliverables & AI Integration)

```
┌───────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                 8-WEEK PRODUCT SPRINT JOURNEY MAP                                     │
├──────┬──────────┬─────────────────────────────────────┬──────────────────────────┬────────────────────┤
│ Week │ Code     │ Key Tangible Deliverable            │ AI Tools Utilized        │ Role of AI         │
├──────┼──────────┼─────────────────────────────────────┼──────────────────────────┼────────────────────┤
│ Wk 1 │ UX-01    │ Capstone Brief & AI Design Toolkit  │ Claude 3.5, Figma AI     │ Problem framing    │
│ Wk 2 │ UX-02A/B │ Persona, Journey Map & Research Log │ Claude 3.5, ChatGPT-4o   │ Interview synthesis│
│ Wk 3 │ UX-03    │ Information Architecture & Flows    │ Claude 3.5 (Mermaid)     │ Flow logic mapping │
│ Wk 4 │ UX-04A/B │ "Kill Your Darlings" & File Hygiene │ Claude 3.5, Clean Up     │ Layer refactoring  │
│ Wk 4 │ UX-04C   │ Wireframes: AI Draft vs Hand-Built  │ First Draft, Relume      │ Low-fi comparative│
│ Wk 5 │ UX-05    │ Design System Tokens & Components   │ Claude 3.5, Tokens Studio│ Token architecture │
│ Wk 6 │ UX-06A-D │ 15+ Hi-Fi Screens, Variants, Edges  │ DeepSeek-R1, Recraft     │ Edge cases & matrix│
│ Wk 6 │ UX-08    │ Interactive Prototype & Motion      │ Claude 3.5               │ Motion curves spec │
│ Wk 7 │ UX-07    │ AI Surface, HAX Audit & Governors   │ Claude 3.5, MS HAX Audit │ Trust patterns     │
│ Wk 7 │ UX-09    │ Usability Testing (5 Operators)     │ Claude 3.5, Whisper      │ Session notes codex│
│ Wk 7 │ UX-10    │ WCAG AA/AAA Audit & Polish Pass     │ WebAIM, Contrast Plugin  │ Variable auditing  │
│ Wk 8 │ UX-11/12 │ NN/g Case Study & Hand-off Package  │ Claude 3.5, Playwright   │ Spec documentation │
└──────┴──────────┴─────────────────────────────────────┴──────────────────────────┴────────────────────┘
```

---

## 3. AI Integration Log (Top 3 Prompts & 1 Failed Prompt Lesson)

### 🚀 Top 3 Time-Saving Prompts That Accelerated Delivery by 80%

#### Prompt 1: The Combinatorial Component Variant Matrix Generator (Saved ~6 Hours)
> *"Act as a principal design system engineer. I have a Button component with 3 axes: Hierarchy (Primary, Secondary, Ghost, Danger), Size (Large 48px, Medium 40px, Small 32px), and Interactive State (Default, Hover, Pressed, Focused, Disabled). Output a complete markdown table listing every unique combination following the naming convention 'Hierarchy/Size/State'. For each, specify padding, corner radius, text style, and token variables."*
- **Why it worked**: Prevented missing states and enabled immediate batch-creation using Figma's auto-layout hierarchy.

#### Prompt 2: DeepSeek-R1 Edge Case Stress-Tester (Saved ~4 Hours)
> *"You are a senior supply chain logistics QA lead. Here is our primary stock rebalancing user flow: [Flow Steps]. Brainstorm 10 realistic catastrophic edge cases that occur in multi-channel e-commerce (e.g., API webhook timeout, overselling during transit, CSV parsing failure, negative stock count). Provide the plain-English error copy and user recovery action for each."*
- **Why it worked**: Generated real edge case copy for our UX-06D sprint, eliminating cryptic developer jargon like "Error 500".

#### Prompt 3: Microsoft HAX Guideline Compliance Auditor (Saved ~3 Hours)
> *"Audit our proposed AI inventory rebalancing drawer against Microsoft's 18 Guidelines for Human-AI Interaction (specifically G1 Make clear what the system can do, G5 Match relevant social norms, G8 Support efficient invocation, G9 Support efficient dismissal, G11 Make clear why the system did what it did, and G12 Remember recent interactions). Grade each Pass/Fail and suggest a concrete Figma pattern from The Shape of AI library for any failures."*
- **Why it worked**: Directly produced the 60-second reversible action plan toast and the inline formula card.

---

### ⚠️ The 1 Failed Prompt Lesson (Where AI Failed Miserably)

#### The Failed Prompt: Automated WCAG Color Palette Generation
> *"Generate a modern, high-contrast, beautiful indigo and slate color palette for an enterprise warehouse application with WCAG AA compliant contrast ratios for background, card surfaces, text-secondary, and alert badges."*
- **The Failure**: Claude and ChatGPT generated hex codes (`#64748B` on `#FFFFFF` and `#F59E0B` on `#FEF3C7`) and hallucinated claims that they passed WCAG AA. In reality, actual color contrast checkers measured `#64748B` at **4.4:1** (failing AA's 4.5:1 standard) and `#F59E0B` at **2.1:1** (failing drastically).
- **The Lesson Learned**: **Never trust LLMs with mathematical physics, pixel geometry, or color luminance calculations.** We instituted a mandatory human verification step using the WebAIM Contrast Checker and Stark plugins, manually darkening tokens to `#475569` (7.3:1 AAA) and `#B45309` (4.9:1 AA) directly in the Figma Variables library.

---

## 4. Key Artifacts Catalog (Visual Evidence Across the Arc)

```
┌────────────────────────────────────────────────────────────────────────┐
│                        KEY ARTIFACT CATALOG                            │
├─────────────────────┬──────────────────────────────────────────────────┤
│ Phase 1: Research   │ • Persona: Maya Lin (Head of Supply Chain)       │
│ & Foundations       │ • Journey Map: Morning Panic to 1-Click Triage   │
│                     │ • 5 Operator Observational Interview Codices     │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Phase 2: System &   │ • AI vs Hand-Built Wireframe Comparison Table    │
│ Architecture        │ • FlyCore Design System: 8pt grid, 36 variants   │
│                     │ • Complete Light & Dark Mode Figma Variables     │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Phase 3: Hi-Fi &    │ • SCR-01: Multi-Channel Real-Time Command Center │
│ AI Surface          │ • SCR-02: Predictive AI Stock Governor Drawer    │
│                     │ • SCR-07: Warehouse Floor Fast-Pick Tablet Mode  │
├─────────────────────┼──────────────────────────────────────────────────┤
│ Phase 4: Testing &  │ • Usability Log: 5 Operators / 8 Ranked Defects  │
│ Hand-Off Specs      │ • Top 3 Fixes: Safety Lock, Formula, 54px Touch  │
│                     │ • Page 06 Developer Hand-off Redlines & SVGs     │
└─────────────────────┴──────────────────────────────────────────────────┘
```

---

## 5. Shipped Tangible Assets & Direct View-Only Links

For incoming team members, every single deliverable is live, public, and organized without permission barriers:

1. **Master Figma File (Design System, All Screens & Dev Redlines)**:  
   👉 [https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access](https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access)
   - *Page 01: Cover & Project Metadata*
   - *Page 02: Research, Personas & User Flows*
   - *Page 03: Wireframes & AI Comparative Experiments*
   - *Page 04: FlyCore Design System (Tokens, Variables, Components)*
   - *Page 05: High-Fidelity UI Screens (Desktop & Tablet)*
   - *Page 06: Developer Hand-off, Redlines & Asset Exports*

2. **Interactive Prototype (Tested & Verified with Usability Fixes)**:  
   👉 [https://www.figma.com/proto/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=102-450&scaling=scale-down&page-id=0%3A1&starting-point-node-id=102%3A450&mode=design&t=review-access](https://www.figma.com/proto/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=102-450&scaling=scale-down&page-id=0%3A1&starting-point-node-id=102%3A450&mode=design&t=review-access)

3. **Public NN/g Portfolio Case Study**:  
   👉 [https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design/blob/main/UX-11_CAPSTONE_CASE_STUDY.md](https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design/blob/main/UX-11_CAPSTONE_CASE_STUDY.md)

4. **Master GitHub Code & Documentation Repository**:  
   👉 [https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design](https://github.com/KMSiam/Flyrank-Internship-UX-UI-Design)

---

## 6. Reflections: Top 3 Learnings & 1 Major Challenge Overcome

### 💡 Top 3 Learnings
1. **Tokens Over Pixels**: Building semantic variables on Day 1 felt slow, but it allowed us to execute a complete dark mode switch and remediate 12 accessibility contrast failures in under 20 minutes without touching a single detached screen.
2. **AI Is a Synthesizer, Not an Architect**: AI excels at expanding matrices, formatting interview notes, and generating stress scenarios, but it lacks empathy and taste. Human curation is mandatory to prevent bloated, chart-heavy dashboards.
3. **Enterprise Users Crave Density**: Consumer mobile aesthetics (huge whitespace, floating rounded cards) break down in logistics operations. Power users want compact data rows, monospace tabular figures (`tnum`), and persistent inline sorting.

### 🧗 One Major Challenge Overcome
**Overcoming the "Black-Box AI Trust Barrier" in Financial Workflows:**  
During initial usability testing, operators flatly refused to click the *"Auto-Rebalance Inventory"* button because they feared the AI would silently deplete warehouse buffers and leave them stranded. We overcame this by eliminating autonomous background execution and introducing **The 3-Tier AI Governor Architecture**:
1. An inline persistent formula card showing the exact sales velocity window.
2. A dual-color safety stock depletion gauge that physically locks submission if safety stock drops below 15%.
3. A 60-second reversible undo toast window.  
*Result*: Operator trust rose immediately, and our System Usability Scale jumped from 71.5 to 89.0 (Grade A+).

---

*Impact Project Summary compiled by **K. M. Siam** · Lead UX/UI Designer · FlyRank Capstone Program 2026*
