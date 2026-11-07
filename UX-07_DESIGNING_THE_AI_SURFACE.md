# UX-07: Designing the AI Surface — Chat, Agents, and Trust
**Track**: UX/UI Design · **Phase**: Build+ · **Workload**: 5h · **Week**: 5/7  
**Candidate**: K. M. Siam ([GitHub: @KMSiam](https://github.com/KMSiam))  
**Design System**: **FlyCore Design System v1.0**  
**Project**: FlyCommerce OS (Predictive DTC E-Commerce Fulfillment & Inventory Hub)  
**Master Figma Workspace**: [FlyRank Master Project Workspace (Pristine View)](https://www.figma.com/file/r7K8x9pL4mN2qS/FlyRank-UX-UI-Design-Capstone?type=design&node-id=0%3A1&mode=design&t=review-access)

---

## Executive Summary

In 2026, product designers are no longer hired simply to use AI tools for mockups; they are hired to **architect the AI product surface itself**. In high-stakes enterprise logistics, blind AI automation causes catastrophic financial loss and warehouse halts, while conversational chatbots introduce unacceptable typing latency during crises. 

This assignment deliberately architects the AI surface for **FlyCommerce OS**:
1. **Interaction Model Justification**: Selecting a **Proactive Autonomous Agent with Staged Human-in-the-Loop Review**, rigorously argued against conversational chat and unconstrained autopilot models.
2. **Four Named Patterns from "The Shape of AI" Library**: Implementing two Governors (*Action Plan* and *Interactive Verification Controls*) and two Trust Builders (*Explainable Formula Disclosure* and *Contextual Data Citations & Caveats*).
3. **Dedicated Failure & Uncertainty Mode Design**: Visualizing what the operator sees when the model encounters anomalous viral spikes, displaying split-scenario branch modeling rather than generic error banners.
4. **Microsoft HAX Audit**: Benchmarking against 8 of Microsoft's 18 Guidelines for Human-AI Interaction with transparent evaluation of honest failures and planned architectural mitigations.

---

## 1. Interaction Model Choice & Architectural Justification

```
┌────────────────────────────────────────────────────────────────────────┐
│                   INTERACTION MODEL TRADE-OFF ANALYSIS                 │
├───────────────────┬──────────────────────┬─────────────────────────────┤
│ Model Considered  │ Operational Friction │ Suitability for FlyCommerce │
├───────────────────┼──────────────────────┼─────────────────────────────┤
│ 1. Conversational │ High typing latency; │ REJECTED                    │
│    Chatbot Panel  │ non-deterministic    │ (Fails Elena's &lt;90s goal) │
├───────────────────┼──────────────────────┼─────────────────────────────┤
│ 2. Full Autopilot │ Catastrophic error   │ REJECTED                    │
│    (No Human Loop)│ risk; zero trust     │ (Rejected by 68% operators) │
├───────────────────┼──────────────────────┼─────────────────────────────┤
│ 3. Proactive Agent│ Sub-second scanning; │ SELECTED & ARCHITECTED      │
│    + Staged Review│ 100% human authority │ (Optimal Trust & Velocity)  │
└───────────────────┴──────────────────────┴─────────────────────────────┘
```

### The Chosen Model: Proactive Autonomous Agent with Staged Human Review
FlyCommerce OS implements a background surveillance agent that monitors multi-channel sales velocity (Shopify, TikTok Shop, Amazon FBA) against warehouse inventory webhooks. When an inventory deficit threat is predicted (<48h runway), the agent does not silently mutate database records; instead, it compiles a **Staged Action Plan** and surfaces a non-intrusive alert requiring explicit human verification before state execution.

### Why the Conversational Chatbot Alternative Was Rejected
- **The Alternative**: A floating chatbot drawer (e.g. *"Ask AI: 'Rebalance my stock'"*).
- **Why It Fails in Production**:
  1. *Typing Latency*: During an active out-of-stock crisis, an operator does not have the cognitive bandwidth to compose natural language prompts.
  2. *Non-Deterministic Hallucination*: Natural language parsing can misinterpret SKU variants (e.g. confusing `GLOW-01-V1` with `GLOW-01-REFILL`).
  3. *Lack of Spatial Glanceability*: A chat stream buries tabular multi-channel quantities inside wordy text bubbles. Operators need high-density tables and tactile sliders, not small talk.

### Why Full Autopilot Was Rejected
- **The Alternative**: Autonomous AI execution with zero human confirmation.
- **Why It Fails in Production**:
  1. As established in **UX-02 (Finding 2)**, 68% of operators abandon automated tools that execute purchase orders without consent.
  2. External variables (unannounced influencer promos, unrecorded supplier holiday shutdowns, manual warehouse holds) exist outside the model's training context. Human sign-off is the essential safety valve.

---

## 2. Four Named Patterns from "The Shape of AI" Library

```
┌────────────────────────────────────────────────────────────────────────┐
│                  SHAPE OF AI: IMPLEMENTED PATTERNS                     │
├───────────────────────────────────┬────────────────────────────────────┤
│ Category 1: Governors (Control)   │ Category 2: Trust Builders         │
├───────────────────────────────────┼────────────────────────────────────┤
│ 1. Action Plan (Staged Execution) │ 3. Explainable Formula Disclosure  │
│ 2. Interactive Verification Slider│ 4. Telemetry Citations & Caveats   │
└───────────────────────────────────┴────────────────────────────────────┘
```

### Pattern 1: Action Plan (Governor Pattern)
- **Shape of AI Definition**: The AI decomposes a complex high-level recommendation into discrete, sequential, human-verifiable steps prior to execution.
- **Implementation in FlyCommerce OS (MOD-02)**:
  Before executing a multi-channel buffer lock, the agent displays an explicit 3-step execution plan:
  ```
  ┌─ AGENT STAGED ACTION PLAN ──────────────────────────────────────────┐
  │ [x] Step 1: Reserve 150 units from Wholesale Pool (650u -> 500u)    │
  │ [x] Step 2: Push virtual inventory lock to TikTok Shop API (+150u)  │
  │ [x] Step 3: Transmit pre-validated pick manifest to Marcus at 3PL    │
  └─────────────────────────────────────────────────────────────────────┘
  ```
- **Governor Mechanism**: The user can toggle individual steps on or off. If Elena wants to allocate stock to TikTok but delay the warehouse physical pick-wave until tomorrow morning, she unchecks Step 3 with one click.

### Pattern 2: Interactive Verification & Threshold Controls (Governor Pattern)
- **Shape of AI Definition**: Physical interface controls that allow the user to modify, clamp, or constrain the AI's proposal with real-time feedback.
- **Implementation in FlyCommerce OS**:
  - The AI suggests allocating **136 units** based on hourly velocity.
  - The UI presents a **Tactile Allocation Slider** bounded by hard threshold limits.
  - **The Safety Lock Governor**: If Elena drags the slider beyond 75% of the total wholesale reserve pool, the slider turns red and locks into place, requiring an explicit checkbox confirmation: *"Acknowledge wholesale reserve drop below 150 units"*.
- **Governor Mechanism**: Prevents catastrophic single-click over-allocation.

### Pattern 3: Explainable Formula Disclosure (Trust Builder Pattern)
- **Shape of AI Definition**: Exposing the underlying mathematical logic and variable weights that produced the AI's suggestion.
- **Implementation in FlyCommerce OS (MOD-01)**:
  Instead of a black-box badge saying *"AI Recommended: 150 Units"*, clicking the info token expands the **Inspectable Math Drawer**:
  $$\text{Suggested PO} = (\text{Current Hourly Velocity [14.2u]} \times \text{Safety Window [48h]}) + \text{Lead Time Buffer [18u]} = 136\text{ Units}$$
- **Trust Mechanism**: Directly satisfies Priya's core requirement from UX-02 (*"If it's a black box, I revert to Excel"*). Transparent math fosters algorithmic trust.

### Pattern 4: Telemetry Citations & Environmental Caveats (Trust Builder Pattern)
- **Shape of AI Definition**: Explicitly disclosing the data recency, origin, and environmental assumptions behind recommendations, accompanied by known risks.
- **Implementation in FlyCommerce OS**:
  - **Data Citations**: Every recommendation lists its source telemetry:
    - *Source 1: Shopify Plus API (Webhook synced 42 seconds ago).*
    - *Source 2: TikTok Shop Seller Center (Sales velocity trailing 7 days).*
    - *Source 3: Apex 3PL WMS (Physical warehouse cycle count verified Oct 28).*
  - **Environmental Caveat**: A visible amber warning pill:
    - *⚠️ Vendor Caveat: Supplier Factory Blackout in 18 days for Lunar New Year. 14-day safety buffer automatically appended.*

---

## 3. Dedicated AI Failure & Uncertainty Mode Architecture

Standard applications fail by throwing a generic red toast: *"Error: Model failed."* In an intelligent supply chain, uncertainty is not a crash—it is an **ambiguity state** that must be surfaced to human judgment.

### The Uncertainty Trigger Scenario: The Viral Spike Anomaly
At 10:15 AM, sales velocity for SKU `GLOW-01` jumps from its normal $2.1\text{ units/hr}$ to $34.5\text{ units/hr}$ ($16\times\text{ spike}$). 
The AI model cannot determine whether this represents:
1. **Scenario A (Organic Viral Growth)**: A permanent demand shift requiring a \$50,000 emergency overseas factory purchase order.
2. **Scenario B (Transient Flash Spike)**: A short-lived TikTok reel that will exhaust within 6 hours, where a massive PO would cause catastrophic deadstock capital lockup.

### The Uncertainty Surface Interface (SCR-04 / MOD-05)
```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ ⚠️ AI UNCERTAINTY NOTICE: HIGH-VOLATILITY SALES ANOMALY DETECTED                [X]   │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ Confidence Score: 48% (Below Automated Action Threshold of 85%)                        │
│ Telemetry: Sales velocity surged 16x in the last 45 minutes on TikTok Shop.           │
│                                                                                        │
│ THE MODEL CANNOT SAFELY DETERMINE FUTURE VELOCITY. CHOOSE MITIGATION STRATEGY:         │
│                                                                                        │
│ ┌─ SCENARIO A: TRANSIENT FLASH SPIKE (Low Risk) ─┐ ┌─ SCENARIO B: SUSTAINED SURGE (Cap)──┐ │
│ │ Assumption: Influencer trend dies in 6-12h.   │ │ Assumption: Multi-week viral surge. │ │
│ │ • Reallocate 150 buffer units from Wholesale. │ │ • Reallocate 300 units from FBA.    │ │
│ │ • Do NOT issue international supplier PO.     │ │ • Issue Emergency Air-Freight PO.   │ │
│ │ Expected Capital at Risk: $0 (Internal Shift) │ │ Expected Capital at Risk: $24,500   │ │
│ │ [ SELECT SCENARIO A ]                         │ │ [ SELECT SCENARIO B ]               │ │
│ └───────────────────────────────────────────────┘ └─────────────────────────────────────┘ │
│                                                                                        │
│ Or declare marketing context: [ "This is an unannounced TikTok Creator collaboration ▼" ] │
│ [ Dismiss Warning ]                                     [ Manually Configure Buffer ]   │
└────────────────────────────────────────────────────────────────────────────────────────┘
```
- **Why This Builds Trust**: The system admits its epistemic limits (*"Confidence: 48%"*), outlines the trade-offs of both interpretations, and hands strategic agency back to the human founder.

---

## 4. Microsoft HAX Guidelines Audit (Human-AI Interaction)

We audited FlyCommerce OS against 8 of Microsoft's 18 Human-AI Interaction Guidelines, recording honest failures and planned architectural fixes:

```
┌────────────────────────────────────────────────────────────────────────┐
│                     MICROSOFT HAX AUDIT SCORECARD                      │
├──────────────────────────────────────┬─────────┬───────────────────────┤
│ Guideline Evaluated                  │ Status  │ Audit Finding         │
├──────────────────────────────────────┼─────────┼───────────────────────┤
│ G1: Make clear what system can do    │ ✅ PASS │ Scoped to inventory   │
│ G2: Make clear how well it can do it │ ✅ PASS │ Confidence % shown    │
│ G4: Show contextually relevant info  │ ✅ PASS │ XAI math drawer       │
│ G8: Support efficient dismissal      │ ✅ PASS │ 1-click toast dismiss │
│ G9: Support efficient correction     │ ✅ PASS │ Tactile slider edit   │
│ G11: Make clear why system acted     │ ✅ PASS │ Formula transparency  │
│ G10: Scope services when in doubt    │ ⚠️ FAIL │ Planned Fix: Branching│
│ G13: Learn from user behavior        │ ⚠️ FAIL │ Planned Fix: Memory   │
└──────────────────────────────────────┴─────────┴───────────────────────┘
```

### Detailed Evaluation of the 8 Guidelines

#### Phase 1: Initially
- **G1: Make clear what the system can do (Score: PASS)**:
  - *Evidence*: The dashboard onboarding explicitly scopes the agent's jurisdiction: *"Monitors multi-channel stock sync, flags stockout risks, and calculates rebalance plans. Does not execute financial purchase orders without manual confirmation."*
- **G2: Make clear how well the system can do what it can do (Score: PASS)**:
  - *Evidence*: Every recommendation displays an explicit confidence metric (e.g. *"94% Confidence — Based on 14-day steady sales telemetry"*).

#### Phase 2: During Interaction
- **G4: Show contextually relevant information (Score: PASS)**:
  - *Evidence*: MOD-02 presents relevant telemetry (live channel balances, factory blackouts, hourly velocity) adjacent to the interaction point without requiring menu navigation.
- **G8: Support efficient dismissal (Score: PASS)**:
  - *Evidence*: All proactive warning toasts and AI recommendation cards include an instantaneous single-click `[ Dismiss ]` button that mutes alerts for 4 hours.

#### Phase 3: When Wrong
- **G9: Support efficient correction (Score: PASS)**:
  - *Evidence*: When the AI suggests allocating 136 units, the user is never trapped in a binary accept/reject box. The tactile slider allows the operator to adjust the value to 100 units in under 2 seconds.
- **G10: Scope services when in doubt (Score: HONEST FAIL -> PLANNED FIX)**:
  - *Honest Fail*: In early prototypes, when sales velocity spiked wildly, the AI defaulted to calculating an exaggerated reorder quantity, overwhelming the user with high numbers.
  - *Planned Fix*: Implemented the **Split-Scenario Uncertainty Modal** (Scenario A vs. Scenario B). When confidence drops below 70%, the agent refuses to make a single recommendation and forces a human context declaration.
- **G11: Make clear why the system did what it did (Score: PASS)**:
  - *Evidence*: Pattern 3 (Explainable Formula Drawer) exposes the exact formula `(Velocity × Lead Time) + Safety Buffer`.

#### Phase 4: Over Time
- **G13: Learn from user behavior (Score: HONEST FAIL -> PLANNED FIX)**:
  - *Honest Fail*: If Elena repeatedly overrides the AI's 15% safety buffer and manually sets 25% on TikTok Shop, the system currently forgets this preference on the next incident.
  - *Planned Fix*: Architecture will introduce an **Adaptive Memory Token Engine**: after 3 consecutive manual overrides of the same magnitude, the agent prompts: *"Notice: You frequently apply a 25% buffer to TikTok Shop. Would you like to set 25% as your default rule?"*.

---

## 5. Reviewer Verification Checklist

- [x] **Interaction model choice argued against an alternative**: Autonomous proactive agent with staged human review justified; conversational chatbot and full autopilot rejected with concrete production reasons.
- [x] **4+ named patterns from The Shape of AI implemented**:
  - Governor 1: *Action Plan* (Staged 3-step execution plan).
  - Governor 2: *Interactive Verification Controls* (Tactile slider with 75% safety lock).
  - Trust Builder 1: *Explainable Formula Disclosure* (Inspectable math formula).
  - Trust Builder 2: *Telemetry Citations & Caveats* (Source recency and factory blackout warning).
- [x] **Failure & uncertainty states designed**: High-volatility anomaly modal displaying split-scenario branch modeling (Transient Flash vs. Sustained Surge) with explicit confidence scores.
- [x] **Microsoft HAX audit covers 8 guidelines**: Honest failures documented for G10 (Scope services) and G13 (Learn from behavior) with actionable planned fixes.
- [x] **Figma Deliverable Link**: Dedicated AI surface section on Page `04_Hi-Fi UI`.
