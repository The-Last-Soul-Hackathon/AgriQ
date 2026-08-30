# Net Realization — Explained Simply (with a real-data example)

## The one-line idea

> **Net Realization = what the farmer actually ends up with, after every real cost is subtracted from the buyer's offered price.**

The highest *offered* price is not always the best deal, because a buyer who offers more may also cost more to reach (transport) or deduct more (market fees, quality cuts). AgriQ's job is to compare buyers on **net realization**, not on the offered price alone.

## Simplified formula (MVP version)

The full algorithm (see `Buyers price =! profit to farmers.md` and the detailed net-realization spec) has 7 steps and handles shared trucks, transit loss, and confidence ranges. For an MVP, the core formula is:

```
Net Realization (₹/kg) = Buyer's Offered Price (₹/kg)
                          − Transport Cost (₹/kg)
                          − Market Fee / Commission (₹/kg)
                          − Quality Deduction (₹/kg, if applicable)
```

Everything on the right side must come from a real, labelled source — not a guess — so the app can show *why* it recommends a buyer, not just a number.

---

## Worked Example — using real onion mandi data

This example uses **actual historical mandi prices** from our dataset (`Agriculture_price_dataset.csv`), which mirrors AGMARKNET data. Distances are illustrative (a real farmer's location would come from the app), but the price and cost-rate inputs are real and sourced.

### Step 1: Real prices (from our dataset)

On **25 March 2025**, Nashik district recorded these real FAQ-grade onion modal prices:

| Market (acting as "Buyer") | Modal Price (₹/quintal) | Price (₹/kg) | Source |
|---|---|---|---|
| Lasalgaon (Niphad) | ₹1,400 | **₹14.00/kg** | `Agriculture_price_dataset.csv`, row: Maharashtra, Nashik, Lasalgaon(Niphad), Onion, FAQ, 25/3/2025 |
| Shivsiddha Govind Producer Co. | ₹1,525 | **₹15.25/kg** | Same dataset, same date |

At first glance, the second market/buyer looks better — it pays ₹1.25/kg more.

### Step 2: Real transport cost

Published road-freight benchmarks (mini-truck, small consignments) are roughly **₹15–₹25 per km** depending on vehicle size (industry rate cards, 2025–26). We use **₹20/km** here as a mid-range, labelled rate — in the real app this should be replaced by an actual transporter quote whenever one is available (see confidence-levels note below).

Assume a farmer moving **1,000 kg (1 tonne)** of onions:

| Buyer | Distance (assumed, for illustration) | Transport cost (₹20/km × distance) | Transport cost per kg |
|---|---|---|---|
| Lasalgaon (Niphad) | 8 km | ₹160 | ₹0.16/kg |
| Shivsiddha Govind | 80 km | ₹1,600 | ₹1.60/kg |

### Step 3: Real market fee

Maharashtra APMC market fee is typically **~1% of transaction value** (published APMC fee schedules, plus small supervision/weighing charges not included here for simplicity).

| Buyer | Market fee (1% of price) |
|---|---|
| Lasalgaon (Niphad) | 1% × ₹14.00 = ₹0.14/kg |
| Shivsiddha Govind | 1% × ₹15.25 = ₹0.15/kg |

### Step 4: Net Realization

| Buyer | Price | − Transport | − Market Fee | **= Net Realization** |
|---|---|---|---|---|
| Lasalgaon (Niphad) | ₹14.00 | −₹0.16 | −₹0.14 | **₹13.70/kg** ✅ |
| Shivsiddha Govind | ₹15.25 | −₹1.60 | −₹0.15 | ₹13.50/kg |

### Result

> Shivsiddha Govind *offered* ₹1.25/kg more. But because it is much farther away, the extra transport cost (₹1.44/kg more than Lasalgaon) outweighs the price advantage. **Lasalgaon actually leaves the farmer with ₹0.20/kg more.**

This is exactly the situation AgriQ is built to catch — a farmer comparing offers by eye would likely pick the higher price and lose money after transport.

---

## On quality deduction (important caution)

We separately analyzed our dataset for same-market, same-date price differences between **FAQ** (fair average quality) and **Non-FAQ** grade onions, across 7,634 real comparable pairs:

> **Non-FAQ grade sold for ~10.8% less than FAQ grade, on average, in the same market on the same day.**

This number is **real and data-derived**, but it must be labelled as an **estimate**, not an official fixed rate — there is no universal government table that says "Non-FAQ = 10.8% deduction." In the app, this should show as:

```
Estimated quality deduction: ~10.8% (based on historical price data, not an official rate)
Confidence: Medium
```

This matches the confidence-level framework already defined in the detailed net-realization spec (High / Medium / Low confidence per data point).

---

## Why this matters for the pitch

This worked example is useful evidence that:
1. The core AgriQ insight (highest price ≠ highest net return) is not just theoretical — it shows up in real mandi data.
2. Every number in the calculation traces back to a labelled source (dataset, published rate, or estimate) — nothing is invented.
3. The app should always show its *reasoning* ("Buyer B's price is lower, but transport savings make it the better deal"), not just a final recommendation.

**Sources used in this example:**
- `Agriculture_price_dataset.csv` — Maharashtra, Nashik district, Onion, FAQ grade, 25 March 2025 (Lasalgaon (Niphad) and Shivsiddha Govind Producer Company markets)
- Same dataset — FAQ vs Non-FAQ price comparison across 7,634 same-market/same-date pairs (Potato and Onion, all states, 2023–2025)
- Road-freight rate benchmark: ₹15–25/km for mini-truck/LCV agri transport (industry rate cards, 2025–26)
- Maharashtra APMC market fee: ~1% of transaction value (published APMC fee schedules)
