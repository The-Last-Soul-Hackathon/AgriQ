# AgriQ: Buyer Selection Through Verified Net Realization

## 1. Objective

AgriQ should not recommend a buyer based only on the highest quoted price.

The correct question is:

> Which buyer gives this farmer or FPO the highest realistic amount after transport, commission, handling, storage, quality adjustment, wastage and payment-related conditions?

This amount should be called **Net Realization**, not profit. Profit would also require cultivation costs such as seeds, fertilizer, labour and irrigation. AgriQ initially calculates the amount realized from the sale transaction itself.

### Existing market systems

eNAM already supports market access, online bidding, quality assaying and electronic payments. Its official objective is to improve price discovery using actual demand and supply.

Therefore, AgriQ should **not** be positioned as another mandi-price or farmer-marketplace application.

### AgriQ's actual gap

eNAM helps farmers discover market prices. AgriQ helps farmers decide **which selling option will leave them with the highest realistic net amount.**

---

## 2. Trusted Data Sources

AgriQ must separate official data from user-provided and estimated data.

| Data required | Preferred source | Use in AgriQ | Reliability |
|---|---|---|---|
| Mandi minimum, maximum and modal prices | AGMARKNET dataset via data.gov.in | Reference market price | Official |
| Maharashtra mandi prices and arrivals | MSAMB market-price portal | Maharashtra-specific market comparison | Official |
| Quality parameters | eNAM commodity-quality documents | Determine quality range and required parameters | Official |
| Transport cost | Actual transporter quotation or FPO invoice | Calculate route-specific logistics cost | Transaction-based |
| Commission and market fees | Maharashtra APMC Act, rules, by-laws and actual receipts | Calculate applicable deductions | Regulatory/transaction-based |
| Buyer offer price | Verified buyer or FPO entry | Compare actual selling options | User-verified |
| Quality deduction | Buyer settlement records and assaying reports | Estimate financial impact of quality | Transaction-based |
| Wastage or rejected quantity | Delivery weighment and settlement records | Estimate actual saleable quantity | Transaction-based |
| Retail price | Department of Consumer Affairs Price Monitoring System | Show farmer-consumer price spread | Official context only |

The official data.gov.in mandi dataset provides daily wholesale minimum, maximum and modal prices generated from AGMARKNET.

MSAMB publishes Maharashtra market-wise commodity prices and arrivals. However, a clearly documented public MSAMB developer API was not found, so AgriQ should support CSV/manual import or obtain formal access instead of depending on unstable scraping.

### Important data limitations

**Transport data**

A Maharashtra-specific, official, route-wise farm-transport tariff was not found. NITI Aayog provides a broad Indian road-freight benchmark of approximately ₹2.5 per tonne-km, but this is **not** a fixed Maharashtra rate for mini-trucks, tempos or tractor-trailers.

Priority order for transport cost data:
1. Actual transporter quotation
2. FPO historical invoice
3. Verified buyer pickup quotation
4. Historical route average
5. Broad benchmark — only as an explicitly labelled estimate

**Quality deductions**

eNAM publishes quality specifications. For example, onion parameters include limits for defects such as cuts and double splitting, while soybean parameters include moisture, oil content, foreign matter and damaged seeds.

However, AgriQ should **not** assume a fixed table such as "Range 2 = 10% deduction, Range 3 = 20% deduction." A universal official deduction table was not found. Quality classification and financial deduction must be treated as **separate data points**.

---

## 3. Net-Realization Algorithm

### Step 1: Standardize every buyer offer

Before comparing buyers, convert every offer into the same structure:

- Crop, Variety, Quality/grade, Quantity
- Price unit, Price basis
- Pickup location, Delivery location
- Payment terms
- Who pays transport, who pays commission
- Minimum order quantity
- Expected deductions

The **price basis** must be identified: Farm-gate price / Mandi-gate price / Delivered price / Warehouse price / Accepted-quality price / Estimated price.

A ₹28/kg *delivered* offer cannot be directly compared with a ₹30/kg *farm-gate* offer until transport and other costs are normalized.

### Step 2: Estimate accepted quantity

The farmer may load one quantity but receive payment for a lower quantity because of transit loss, spoilage, rejected produce, quality-based reduction, weight differences, or sorting/grading loss.

```
Q_accepted = Q_loaded × (1 − L_transit) × (1 − R_rejection)
```
- `Q_loaded` = quantity initially dispatched
- `L_transit` = expected transit loss percentage
- `R_rejection` = expected rejection percentage

If actual delivery weighment is available, use the actual accepted quantity instead of an estimate.

### Step 3: Calculate gross revenue

```
Gross Revenue = Q_accepted × P_buyer
```
- `Q_accepted` = accepted quantity
- `P_buyer` = buyer's price per kg or quintal

### Step 4: Calculate transport cost

For a dedicated vehicle:

```
C_transport = C_vehicle + C_toll + C_loading + C_unloading + C_waiting + C_packing
```

If the transporter gives a per-kilometre rate:

```
C_vehicle = C_base + (R_km × D_total)
```
- `C_base` = fixed vehicle charge
- `R_km` = rate per kilometre
- `D_total` = actual route distance, including applicable return travel

Do **not** automatically use one-way distance. Always confirm whether the quote includes: empty return, loaded return, toll, waiting, loading/unloading, and multiple collection stops.

### Step 5: Allocate shared transport

If several farmers share one vehicle:

```
C_farmer = (Q_farmer / Q_truck) × C_total_truck
```

**Example:**
- Total truck quantity: 10,000 kg
- Farmer's quantity: 2,000 kg
- Total truck cost: ₹15,000
- `C_farmer = (2,000 / 10,000) × 15,000 = ₹3,000`

### Step 6: Add all deductions

```
C_total = C_transport + C_commission + C_market_fee + C_handling 
        + C_packing + C_storage + C_quality + C_wastage + C_other
```

Maharashtra market fees and commission-related charges are governed through the state's APMC framework and applicable market rules. The exact charge may vary by market and transaction type, so AgriQ should use market-specific rules or actual settlement receipts rather than one universal percentage.

### Step 7: Calculate net realization

```
Net Realization = Gross Revenue − Total Deductions

Net Realization per kg = Net Realization / Q_loaded
```

**Important:** Divide by the originally **loaded** quantity, not only the accepted quantity. This ensures that wastage and rejection reduce the farmer's real per-kg result.

---

## 4. Illustrative Comparison

*The following example is illustrative, not an official market quotation.*

Assume: Crop = Onion, Quantity = 10,000 kg, Location = Maharashtra

| Buyer | Gross price | Transport | Other deductions | Net realization |
|---|---|---|---|---|
| A | ₹30/kg | ₹7/kg | ₹1/kg | ₹22/kg |
| B | ₹28/kg | ₹2.50/kg | ₹1/kg | **₹24.50/kg** |
| C | ₹32/kg | ₹8/kg | ₹1/kg | ₹23/kg |

**Result:** Buyer C offers the highest gross price, but Buyer B provides the highest net realization.

AgriQ should recommend Buyer B and explain:

> "Buyer B's gross offer is ₹2/kg lower than Buyer C's, but its logistics cost is ₹5.50/kg lower. The expected farmer net realization is ₹1.50/kg higher."

This explanation is more valuable than displaying a black-box recommendation.

---

## 5. Feasibility and Trust Checks

AgriQ should not recommend a buyer only because the calculated net amount is high. First, remove or flag infeasible buyers.

### Feasibility filters

A buyer should be considered eligible only if:
- Required quantity is available
- Buyer accepts the crop and variety
- Quality requirements are achievable
- Buyer has a valid pickup or delivery location
- Transport is available
- Minimum order quantity is satisfied
- Payment terms are acceptable
- Delivery deadline is realistic
- No major unresolved payment dispute exists

### Trust information

Show the following **separately** from the financial calculation:
- Buyer verification status
- Number of completed transactions
- Average payment time
- Rejection frequency
- Quantity-dispute history
- Quality-dispute history
- Previous settlement records

Do **not** subtract an invented "trust penalty" from the price. If evidence is insufficient, display:

```
Net realization: ₹24.50/kg
Payment reliability: Unknown
Recommendation confidence: Medium
```

---

## 6. Confidence and Uncertainty

Every calculated result should show its data quality.

**High confidence:** Actual buyer quotation, actual transporter invoice, actual delivery weighment, actual settlement record, official market or quality data.

**Medium confidence:** FPO historical route average, verified buyer's previous transaction, similar crop-lot settlement data.

**Low confidence:** Broad national transport benchmark, user-entered approximate deduction, predicted quality deduction without transaction history, price forecast.

### Avoid false precision

If transport is estimated between ₹2–3/kg and quality deduction between ₹0.50–1/kg, show a range:

```
Expected net realization: ₹23.50–₹25.00/kg
```

If two buyers' ranges overlap, AgriQ should say:

> "No statistically clear winner. Obtain a current transporter quote or buyer settlement confirmation."

This is more trustworthy than always selecting one buyer.

---

## 7. Recommended MVP

AgriQ should begin with:
- One crop, preferably onion
- Maharashtra markets such as Nashik/Lasalgaon and nearby markets
- One or two FPOs
- Three to five verified buyer offers
- Actual transporter quotations
- Historical FPO settlement data
- AGMARKNET/data.gov.in market prices
- eNAM quality parameters
- A transparent calculation sheet

### MVP workflow

```
FPO creates crop lot
        ↓
Buyer offers are added
        ↓
AGMARKNET/MSAMB reference prices are displayed
        ↓
Transport and other costs are entered
        ↓
Quality and accepted quantity are recorded
        ↓
Net realization is calculated
        ↓
Buyers are ranked after feasibility checks
        ↓
FPO selects buyer
        ↓
Delivery and final settlement are recorded
```

### Recommended output format

```
Recommended buyer: Buyer B

Expected gross price: ₹28/kg
Expected transport: ₹2.50/kg
Expected other deductions: ₹1/kg
Expected net realization: ₹24.50/kg

Payment reliability: Medium
Data confidence: High

Recommendation reason:
Highest verified net realization after logistics and deductions.
```

---

## 8. Final USP

> AgriQ does not simply show farmers the highest market price. It calculates and explains the highest realistic net realization after logistics, deductions, quality, quantity and settlement conditions.

This is the difference between **price discovery** and a **profitable selling decision**.

Do not claim that AgriQ replaces eNAM. A stronger and more credible statement is:

> "AgriQ uses official market information from systems such as AGMARKNET, eNAM and MSAMB, then adds transaction-level logistics and settlement data to answer the question that price-discovery systems alone do not answer: which buyer will leave this farmer with the highest realistic net amount?"
