### Problem Statement

> **Farmers often lack timely, understandable and actionable market information, which can lead to selling at a less favourable market, time or price.**
> 

The key question is not whether mandi prices are available — **they clearly are**. The research question is whether existing systems convert this information into a **personalized, cost-aware selling decision** for an individual farmer.

### 1. What Government Systems Already Solve

| Government System | What it already provides | What this means for PS 26132 |
| --- | --- | --- |
| **e-NAM** | National electronic market connecting APMCs, with online trading and price discovery. Its farmer app also provides nearby mandi prices and directions; the current e-NAM network covers markets across 23 states and 4 UTs. (eNAM) | 🔴 **Basic price discovery and mandi comparison are already solved.** |
| **Agmarknet / Agmarknet 2.0** | Real-time market price and arrival information. As of Dec. 2025, the government reported **4,367 mandis** linked to Agmarknet. (Press Information Bureau) | 🔴 **Real-time price + arrivals are already solved at national scale.** |
| **Kisan Suvidha** | Market prices along with weather, advisories and other farmer services. Government documentation explicitly lists market-price information as a core feature. (Press Information Bureau) | 🔴 **Basic farmer price-information access is already solved.** |
| **State agriculture/mandi portals** | Several states provide commodity-wise mandi prices, including minimum, maximum/modal prices and arrivals. For example, Rajasthan's current portal publishes mandi-wise commodity prices and arrivals. (Raj Kisan Rajasthan) | 🔴 **State-level price lookup is also widely available.** |

### Government conclusion

The basic information pipeline already exists:

**Mandi → Price + Arrival Data → Farmer**

So we **cannot** build PS 26132 around:

> ❌ “Farmers don't have access to mandi prices.”
> 

That gap has largely been addressed.

---

### 2. What Private / Startup / Global Systems Already Solve

## Indian platforms

market is not empty.

Platforms and services such as **RML/Reuters Market Light**, AgMart and other agricultural information platforms have historically provided farmers with localized market-price information, advisories and related agricultural information.

The important point is:

> **Price information as a service is not new in India.**
> 

RML, for example, has been providing localized agricultural information to farmers for many years.

So:

**Live price + SMS/app + crop information cannot be your main innovation.**

## Global systems

This problem is also old internationally.

For example:

- **Esoko** has used mobile/SMS channels to provide agricultural market-price information to farmers in Africa.
- **M-Farm** in Kenya provided farmers with price information through SMS and also supported group selling/buying.

Therefore:

> ❌ “We are the first to give farmers market prices through their phones.”
> 

would not be defensible.

---

### **3. The More Important Question: What Happens AFTER the Farmer Gets the Price?**

This is where PS 26132 becomes more interesting.

Imagine:

### Farmer has 100 quintals of wheat.

The system shows:

| Mandi | Current Price |
| --- | --- |
| Mandi A | ₹2,450/q |
| Mandi B | ₹2,560/q |
| Mandi C | ₹2,520/q |

A normal price application says:

> **Mandi B has the highest price.**
> 

But that does **not** necessarily mean Mandi B is the best option.

The farmer still needs to know:

- How far is Mandi B?
- How much will transportation cost?
- Is the price actually achievable for their quality?
- Is the mandi currently receiving large arrivals?
- Will there be deductions?
- Does the farmer have storage if they wait?
- Is the crop perishable?
- What is the local MSP, if applicable?
- Is today's higher price likely to continue?
- Will waiting cost more than the expected price increase?

This produces a different problem:

> **Price information ≠ selling decision.**
> 

### 4. Existing Systems vs Proposed Decision Layer

| **Layer** | **Government** | **Private / Global** | **Research Status** |
| --- | --- | --- | --- |
| Live mandi prices | e-NAM, Agmarknet, Kisan Suvidha | RML, other agri platforms | 🔴 **Solved** |
| Historical prices | Agmarknet and other market databases | Various agricultural platforms | 🔴 **Solved** |
| Mandi comparison | e-NAM nearby mandi prices | Private market-information platforms | 🔴 **Solved** |
| Market arrivals | Agmarknet/e-NAM | Some private platforms | 🔴 **Solved** |
| Price trends | Government market databases | Various analytics platforms | 🔴 **Solved** |
| “Highest price nearby” | Already possible through existing data | Common comparison feature | 🔴 **Not unique** |
| Basic “sell now / wait” prediction | Forecasting research and pilots exist | Some agri-tech/analytics products | 🟡 **Existing, but less universally deployed** |
| Transport-adjusted selling decision | Not clearly established as a standard farmer-facing government feature in the sources reviewed | Not clearly established as a universal feature | 🟢 **Potential gap** |
| Price + transport + storage + spoilage + MSP combined decision | No clear integrated government feature identified | No clear universal implementation identified | 🟢 **Strong potential gap** |
| Personalized “Where should I sell?” recommendation | Price comparison exists, but a complete net-realization decision is not clearly established | Some market-linkage platforms approach this, but scope varies | 🟢 **Worth validating** |
| Personalized “Sell now vs wait” based on farmer-specific constraints | Forecasting exists, but this is not the same as a complete farmer-specific decision | Exists in parts/pilots | 🟡 **Potential gap** |
| Actionable decision through vernacular voice/SMS | Information services exist | SMS-based agricultural information is well established globally | 🟡 **Delivery exists; decision intelligence is the opportunity** |

## 5. The Actual Gap We Should Investigate

The gap is **NOT**:

> “Farmers don't know mandi prices.”
> 

That is already heavily addressed.

The better gap is:

> **Farmers receive market information, but the information is not necessarily converted into a personalized net-realization decision based on their crop, quantity, location, transportation cost, storage ability, MSP and expected price movement.**
> 

In other words:

### Existing systems

**“Mandi A = ₹2,500/q”**

### Proposed decision layer

**“For YOUR 50 quintals, Mandi A gives the best expected net realization after transport, and selling today is preferable to waiting.”**

That's a much more meaningful distinction.

### 6. The Product Concept

## **MandiWise — Farmer Selling Decision Engine**

Instead of replacing e-NAM or Agmarknet, the product would **use their data**.

### Input

Farmer provides:

- Crop
- Quantity
- Location
- Current storage availability
- Optional quality/grade
- Vehicle/transport information

### System collects

**Live market data**

↓

**Nearby mandi prices**

↓

**Market arrivals**

↓

**Historical price trends**

↓

**Transport distance/cost**

↓

**MSP where applicable**

↓

**Storage/spoilage constraints**

↓

**Price prediction**

### Then produces one simple answer:

> **Recommended Action**
> 
> 
> 🟢 **Sell at Mandi B**
> 
> Expected price: ₹2,560/q
> 
> Estimated transport: ₹120/q
> 
> Expected net realization: ₹2,440/q
> 
> Current alternative: ₹2,380/q
> 
> **Recommendation: Sell now**
> 

Or:

> **Wait**
> 
> 
> Prices are showing an upward trend.
> 
> Estimated potential improvement: ₹150/q
> 
> Your crop can safely be stored for ~7 days.
> 
> **Recommendation: Wait 3–4 days and reassess.**
> 

---

### 7. The Key Difference

Your system should move through this chain:

```
                 EXISTING SYSTEMS
                       ↓
             Live market information
                       ↓
              Price comparison
                       ↓
              Historical trends
                       ↓
                Farmer sees data

                 YOUR LAYER
                       ↓
              Farmer's situation
                       +
              Market information
                       +
              Transport cost
                       +
              Storage constraints
                       +
              MSP / price floor
                       +
              Expected price movement
                       ↓
             NET REALIZATION
                       ↓
          ┌────────────┴────────────┐
          ↓                         ↓
       SELL NOW                  WAIT
          ↓                         ↓
     Mandi X                  Reassess later
```

---

### 8. Important Research Finding

There is another important lesson from existing agricultural information systems:

**Giving farmers more information does not automatically guarantee better selling outcomes.**

So simply making another dashboard with 20 graphs would be weak.

The product should focus on:

> **Information → Interpretation → Recommendation → Action**
> 

rather than:

> **Information → More information → More charts**
> 

That is the stronger product direction.

---

# 9. What We Should NOT Claim

Don't write:

❌ “No system provides mandi prices.”

❌ “No system compares mandis.”

❌ “No system predicts prices.”

❌ “Nobody has built AI for agricultural price prediction.”

❌ “Farmers currently have no market information.”

All of these are too easy to disprove.

Instead:

> **“Existing systems provide extensive market information and price data, but the opportunity is to transform fragmented market signals into a farmer-specific selling decision that considers net realization and practical constraints.”**
> 

---

# 10. Potential India-Specific Gap

This is where I would position the SIH idea.

### Global / existing ecosystem

Many individual components already exist:

**Price data → Market comparison → Forecasting → Agricultural advisory**

### India

India has **very strong public market-data infrastructure** through e-NAM, Agmarknet and related systems.

But your research can investigate whether these datasets are being turned into a **single farmer-specific decision layer** that answers:

> **“Given MY crop, MY quantity, MY location and MY constraints, where and when should I sell to maximize my expected net realization?”**
> 

That is much narrower and more defensible.

---

# Final Conclusion — SIH26132

### **PS 26132 is NOT an unsolved price-information problem.**

Government systems such as **e-NAM, Agmarknet and Kisan Suvidha already provide large-scale access to mandi prices, arrivals, nearby-market information and market data.**

Private and international platforms have also demonstrated agricultural price-information services for years.

Therefore:

> **“Live mandi prices + trends” = 🔴 Solved**
> 

> **“Basic price prediction” = 🟡 Existing / researched**
> 

But there is a more promising decision-level opportunity:

> **Market data → farmer-specific economics → net realization → actionable selling recommendation**
> 

The potential gap is not **finding the highest mandi price**, but determining the **best practical selling decision** after considering factors such as transportation cost, quantity, storage/spoilage constraints, MSP and expected price movement.

### **The product direction**

> **Build a decision layer on top of existing agricultural market data rather than another mandi-price app.**
> 

**Input:**

Crop + quantity + location + farmer constraints

↓

**Data:**

Live prices + arrivals + trends + transport + MSP + forecast

↓

**Decision:**

> **“Sell at Mandi X today”**
> 

or

> **“Wait 3 days and reassess.”**
>
