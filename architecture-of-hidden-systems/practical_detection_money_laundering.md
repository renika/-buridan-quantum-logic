# Practical Detection of Money Laundering Through Data Overlay Structures

**Author:** Renê Luiz de Almeida
**Document Type:** Technical Appendix / Case Expansion
**Version:** 1.0
**Language:** English

---

## 1. Shift in Focus: From Transaction Events to Structural Patterns

Most AML (Anti-Money Laundering) systems today rely on **transactional anomaly detection** — looking at amount, timestamp, sender, and recipient. While useful, these models struggle to detect sophisticated laundering schemes that **mimic legal behavior at each isolated step**.

The **Overlay Model**, inspired by data network architectures, introduces a **structural approach**. It analyzes the *overall behavioral pattern* across entities and time, not just isolated values.

| Traditional AML Model                  | Overlay-Based Detection                             |
| -------------------------------------- | --------------------------------------------------- |
| Looks at one transaction               | Analyzes interlinked layers over time               |
| Asks for origin of funds               | Maps dispersal, timing, re-routing, layering        |
| Stops at valid CNPJs or legal accounts | Examines whether an entity acts as a dispersal node |

---

## 2. Step-by-Step Practical Detection

### 🧩 PHASE 1 — Insertion

* **Example:** R\$ 500,000 is deposited into a recently formed company.
* **Detection System Flags:**

  * Transaction out of expected behavior for that CNPJ or sector
  * No historical cash flow or operations
  * Entry point linked to crypto or informal deposits

➡ **Insertion flag triggered.**

---

### 🧩 PHASE 2 — Dispersal (Overlay Phase)

* Funds are quickly routed to multiple accounts labeled as "services," "consulting," or intermediaries.
* **System Identifies:**

  * Repeat patterns: Same recipient appears in other suspicious flows
  * Short time between in/out transactions ("pass-through" behavior)
  * Value splitting (e.g., R\$ 9,990 or R\$ 10,050) to avoid triggers
  * Usage of unregulated banks, crypto wallets, or opaque fintechs

➡ **Dispersal flag triggered. Overlay structure identified.**

---

### 🧩 PHASE 3 — Convergence (Reintegration)

* After multiple hops, the original value appears:

  * As real estate purchases
  * As investment into another company
  * As a vehicle or luxury item
* **Detection System Flags:**

  * Asset acquired inconsistent with declared income
  * Ultimate owner traced indirectly to original dispersal flow
  * Shell company or intermediary used to obscure final ownership

➡ **Convergence flag triggered. End-point inconsistent with clean origin.**

---

## 3. Tools That Enable This Model

* **Graph Database Analysis** (e.g., Neo4j, IBM i2): Maps relationships between accounts, legal entities, and behavior chains.
* **AI Clustering & Pattern Matching**: Detects recurring structural patterns such as insertion → dispersal → convergence.
* **Time-Series Monitoring**: Identifies irregular pacing across accounts (e.g., rapid in/out or slow funneling).
* **Supervised Reinforcement Learning**: Trains algorithms on labeled overlay behavior cases to identify new ones.

---

## 4. Practical Advantages Over Current AML Methods

| Benefit                | Description                                   |
| ---------------------- | --------------------------------------------- |
| Works preemptively     | Identifies patterns before a scandal erupts   |
| Cross-border capable   | Follows money even across jurisdictions       |
| Evolves over time      | AI refines pattern thresholds dynamically     |
| Auditable model        | Each flag has structured, explainable logic   |
| Retroactive capability | Can revisit past cases with new systemic lens |

---

## 5. Realistic Simulation Example

**Scenario:**
Company A receives R\$ 300,000 → sends to 4 vendors in 24 hours → one vendor is a crypto exchange → 2 weeks later, A’s owner buys a luxury car in another company’s name.

**Overlay Model Detection:**

* Phase 1: Sudden entry + inactive company → ⚠️
* Phase 2: Multiple quick dispersals → known overlay pattern → ⚠️
* Phase 3: Luxury asset with indirect connection to entry flow → ⚠️

**Result:** System detects *nonlinear flow* typical of laundering even though every individual step is "legal" on paper.

---

## 6. Why This Is New

Although tools like Chainalysis and FinCEN systems monitor suspicious activity, **none currently implement a systemic, overlay-based, layered behavioral model**. This proposal introduces:

* A three-phase structure (Insertion → Dispersal → Convergence)
* Application-agnostic detection logic (blockchain, fiat, or hybrid)
* Functional parity with network packet layering — **not yet used in AML detection.**

---

## Final Remark

This method transforms scattered legal fragments into detectable laundering patterns. It changes the game by turning systems of abuse into maps of traceable intent.

> “What was once invisible in isolation becomes visible in structure.”
