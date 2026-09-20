# 🍅 AI Perishability-Aware Routing

### The idea

Normal route optimization asks:

> **“What is the shortest or cheapest route?”**

AgriQ asks:

> **“What route can deliver the most perishable produce before its quality drops?”**

This makes the logistics engine **perishability-aware**, instead of optimizing only for distance or transportation cost.

---

## 🧠 Freshness Risk Score

For every shipment/order, AgriQ calculates a **Freshness Risk Score** based on factors such as:

* 🌱 **Crop type**
* ⏱️ **Harvest time**
* 🕐 **Estimated shelf life**
* 🌡️ **Temperature**
* 📍 **Distance**
* 🚚 **Expected transit time**
* 🚛 **Vehicle availability**

The system combines these factors to estimate how urgently the produce needs to be delivered.

---

## 📊 Example

| Produce             | Freshness Risk | Priority     |
| ------------------- | -------------: | ------------ |
| 🥬 Leafy vegetables |        **91%** | 🔴 Immediate |
| 🍅 Tomato           |        **63%** | 🟠 High      |
| 🥔 Potato           |        **18%** | 🟢 Normal    |

### How routing changes

Instead of simply selecting the route with the lowest transportation cost, the routing engine considers **freshness risk + delivery time + logistics cost**.

For example:

```text
                    ┌──────────────────────┐
                    │   Shipment Created   │
                    └──────────┬───────────┘
                               ↓
                    ┌──────────────────────┐
                    │ Freshness Risk Score │
                    └──────────┬───────────┘
                               ↓
              ┌────────────────┴────────────────┐
              ↓                                 ↓
       🔴 High Risk                       🟢 Low Risk
              ↓                                 ↓
    Prioritize faster route          Optimize mainly for cost
              │                                 │
              └────────────────┬────────────────┘
                               ↓
                    ┌──────────────────────┐
                    │ Optimized Route      │
                    │ + Delivery Priority │
                    └──────────────────────┘
```

---

## 🔗 Why this matters for AgriQ

This connects three important parts of the system:

**AI Forecasting → Perishability Analysis → Logistics Optimization**

```text
Market / Demand Data
        ↓
Demand Forecast
        ↓
Expected Orders
        ↓
Freshness Risk Score
        ↓
AI-Aware Route Optimization
        ↓
Faster / Smarter Delivery
        ↓
Reduced Spoilage & Food Waste
```

The goal is not simply to find the **shortest route**.

The goal is to find a route that balances:

* **Freshness**
* **Delivery time**
* **Transportation cost**
* **Vehicle availability**
* **Produce priority**

---

## 🚀 Hackathon Feasibility

**⭐⭐⭐⭐☆**

A prototype does **not** require real IoT sensors.

For the hackathon, temperature and other environmental values can be **simulated** or obtained from available weather/API data.

### Prototype

```text
Crop Data
   +
Harvest Time
   +
Shelf Life
   +
Simulated Temperature
   +
Route Distance / ETA
        ↓
Freshness Risk Model
        ↓
Priority Score
        ↓
OR-Tools / Routing Engine
        ↓
Recommended Route
```

### Future Integration

The same system could later integrate:

* 🌡️ IoT temperature sensors
* 📍 GPS vehicle tracking
* 🌦️ Weather APIs
* 🚚 Real-time vehicle availability
* 📦 Warehouse / FPO inventory data

This allows AgriQ to move from a **prototype freshness model** toward real-time, perishability-aware agricultural logistics.
