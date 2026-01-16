# 🛒 User Behavior & Purchase Strategy Analysis
**From Clickstream Data to Actionable Product Insights**

## Overview
This project analyzes user behavior at the **session level** to understand how users engage with an e-commerce platform and how those behaviors translate into **purchase decisions and spending patterns**.

Rather than optimizing surface-level metrics such as session duration, this analysis focuses on **behavioral engagement** and derives **practical product strategies** to increase purchase likelihood.

---

## Key Questions
1. **Who purchases?**
2. **Who spends more (among purchasers)?**
3. **How do different purchase styles (cheap-many vs. expensive-few) emerge?**
4. **What product strategies can meaningfully increase purchases?**

---

## Dataset
The dataset consists of simulated e-commerce clickstream data, including:

- **Sessions**: session start time, device, traffic source
- **Events**: page_view, add_to_cart, checkout, purchase
- **Orders & Order Items**: order totals, quantities, prices
- **Products**: price, cost, margin

All raw data is aggregated into a **session-level dataset**, reflecting real-world product analytics workflows.

---

## Methodology

### Session-Level Feature Engineering
Each session is transformed into a single analytical unit with:

**Time Features**
- `session_seconds`
- `first_event_delay_seconds`

**Engagement Features**
- `event_count`
- event-type counts (page_view, add_to_cart, checkout)

**Purchase Outcomes**
- `did_purchase`
- `amount_usd`
- `n_orders`

This produces a reusable **gold table** for behavioral analysis.

---

## Findings

### Q1. What drives purchase conversion?
**Result**
- Interaction intensity (`event_count`) is the strongest predictor of purchase.
- Session duration and early interaction timing show weak effects once engagement is controlled for.

**Insight**
> Users convert because they **actively engage**, not because they stay longer.

---

### Q2. What explains higher spending among buyers?
(Analysis restricted to purchasers only.)

**Result**
- Interaction count explains spending better than session duration.
- When controlling for engagement, longer session time is associated with **lower spending**, suggesting hesitation or distraction.

**Insight**
> Spending is driven by **engaged exploration**, not passive time on site.

---

### Q3. Cheap-many vs. expensive-few purchase styles
Buyers were segmented into:
- **Cheap-many**: multiple lower-priced purchases
- **Expensive-few**: fewer higher-priced purchases

**Result**
- These groups show **similar session duration and interaction volume**.
- Purchase style differences are driven primarily by **price selection**, not browsing intensity.

**Insight**
> Users behave similarly — they simply choose differently priced products.

---

## Strategic Implications

### 1. Optimize for engagement, not time
- Increasing session duration alone does not increase conversion or spend.
- Product strategy should focus on triggering **meaningful actions**, not prolonging sessions.

### 2. Convert passive time into active interaction
- Long idle periods are associated with lower spending.
- Contextual prompts and decision aids can densify engagement without extending sessions.

### 3. Segment UX by engagement level
- Low-engagement users benefit from guidance and reduced cognitive load.
- High-engagement users benefit from friction removal and faster checkout.

### 4. Do not rely on browsing mechanics to sell expensive items
- Purchase style is driven by price framing and value perception, not interaction volume.

---

## Example Experiment Proposal
**Hypothesis**  
Increasing interaction density (events per minute) increases conversion without increasing session duration.

**Intervention**
- Detect idle time between interactions.
- Trigger low-friction engagement prompts (compare, expand details, save).

**Success Metrics**
- Conversion rate
- Event count / events per minute
- Guardrail: session duration

---

## Conclusion
Across all analyses, **interaction intensity consistently outperforms time-based metrics** in explaining conversion and spending.

The central takeaway:
> **Design for interaction density, not time spent.**

This project demonstrates how behavioral analytics can move beyond description to generate **actionable product strategy**.

---

## Tools & Techniques
- Python (pandas, NumPy, scikit-learn)
- Logistic & linear regression
- Session-level feature engineering
- Behavioral interpretation & product strategy framing