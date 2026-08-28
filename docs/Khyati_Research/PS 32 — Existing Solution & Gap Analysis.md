KHYATI PROJECT INFO:- 

***

### Problem Statement

> **Farmers often face long waiting times, lack of information regarding procurement schedules, and uncertainty about procurement status.**
> 

1. What Government MSP Systems Already Solve?

| Government system | What it already provides | What this means for PS 32 |
| --- | --- | --- |
| **HPAPPP — Himachal Pradesh** | Online farmer registration, procurement-centre selection, token/slot generation, date-wise slot availability, token rescheduling, procurement and payment tracking. Farmers can reschedule a token subject to slot availability. (HPAPP) | **Slot booking/rescheduling is already solved.** |
| **Kapas-Kisan — CCI** | Farmer registration, procurement-centre scheduling/slot mechanisms, procurement/payment status and notifications. | **Basic scheduling and status tracking are not new.** |
| **e-Uparjan — Madhya Pradesh** | Procurement scheduling, SMS notification of the date/place to bring produce, procurement-centre processing, payment and transportation management. (India.gov.in) | **Schedule + notification + procurement tracking already exist.** |
| **West Bengal e-Paddy** | Farmer scheduling, schedule changes/rescheduling and explicit handling of no-shows. Farmers who miss their scheduled date can schedule again after that date. (e-Paddy Procurement) | **No-show/rescheduling is also not a new concept.** |

### Government conclusion

The basic PS-32 problems have already been **partially digitized**:

**Registration → Slot → Schedule → Procurement → Status → Payment**

2. What Private / Startup / Global Systems Already Solve?

### GrainQueue — Global

GrainQueue is specifically built for grain elevators and provides:

- live truck/tractor count
- estimated waiting time
- Open / Closed / Hold status
- delivery-slot reservation
- live queue visibility for farmers

It is therefore **very relevant** to PS 32 from an operational perspective.

**Conclusion:**

“ We cannot claim **"live queue/ETA doesn't exist."**

### GrainFlow — Global

GrainFlow goes even further.

It provides:

- real-time truck counting
- queue and wait-time measurement
- lane-level status
- throughput tracking
- congestion alerts
- farmer-facing live queue information
- capacity-aware scheduling
- operator dashboards
- APIs that can feed live yard data into existing farmer apps.

This is important because it means:

 **"Nobody connects physical grain-yard conditions with farmer information"**

would also be too strong.

GrainFlow is already very close to the **operational/physical-flow side** of what we were imagining.

### Indian AgriTech startups

These are solving **different layers** of agriculture:

| Startup | Main focus | Relevance to PS 32 |
| --- | --- | --- |
| **Ninjacart** | B2B agricultural marketplace + supply-chain/fulfilment | Solves commercial produce movement, not public MSP-yard scheduling. (UP Planning Department) |
| **DeHaat** | Farmer services, marketplace, supply-chain/market linkages | Different problem from managing government MSP-yard queues. (Manage) |
| **AgriBazaar** | Digital marketplace connecting farmers, traders, enterprises and governments + logistics | Market access/trading rather than physical MSP-centre queue coordination. (Manage) |
| **Bijak** | B2B agricultural commodity marketplace | Commercial trading rather than government procurement-centre operations. (App Store) |
| **Arya.ag** | Warehousing, post-harvest storage, finance and market linkages | Post-harvest/storage/market-access problem, not MSP-yard queue control. (WRI India) |
| **WayCool** | Supply-chain procurement through collection centres and links to commercial buyers | Private supply-chain coordination, not public MSP procurement. (ICRIER) |

### what Private Startups Actually Do

- **B2B Agri-Marketplaces (AgriBazaar, Bijak, DeHaat):** They bypass government MSP mandis entirely. They connect private buyers with private sellers for direct commercial trade. They handle online bidding, digital receipts, and payment settlements.
- **Cold-Chain & Perishable Supply Chains (Ninjacart, WayCool):** They focus on fruits and vegetables, managing private collection centers and micro-pickup windows. They do not operate in government MSP grain mandis.
- **Grain Storage & Warehousing (Arya.ag):** They track warehouse storage capacity and post-harvest grain collateral. They do not manage physical tractor/truck queues or gate entries at public MSP procurement yards.
- **Commercial Elevator Tech (e.g., GrainQueue - US):** GrainQueue allows private grain elevators in foreign markets to display live truck counts and issue 30-minute skip-the-line passes. It operates in private corporate supply chains abroad, not in public government MSP yards in India handling government-mandated procurement.

 **Question**:- so if these startups are that good and just bypass govt. MSP  mandis  makes things direct yet flexible then why would people use our or even govt.  **procurement  system?**

Private startups "bypassing" the government system works well for high-margin open-market trades, but farmers still flock to government MSP procurement yards for crucial economic reasons:

### Why Farmers MUST Use the Government MSP System

- **Guaranteed Floor Price (No Middlemen Exploitation):** Private buyers and local traders often purchase crops well below the Minimum Support Price (MSP) during peak harvest seasons. Government agencies guarantee a fixed rate (e.g., ₹2,425/quintal for wheat), shielding farmers from market price drops.
- **Direct Benefit Transfer (DBT):** Government procurement deposits payments directly into the farmer's Aadhaar-linked bank account without middleman commissions or delays.
- **Scale of Purchasing:** Private AgriTech startups focus primarily on high-margin perishables (fruits/vegetables) or specialized crops. They lack the capital and warehouse capacity to purchase millions of tons of staple food grains (paddy, wheat, pulses) during seasonal harvests.

### Why Farmers Will Use Your Solution

Farmers do not want to abandon government MSP procurement—they want to avoid spending **3 to 7 days sitting in a physical tractor line at the mandi**.

```
  TRADITIONAL METHOD                      YOUR OPERATIONAL ENGINE
┌───────────────────────────────┐       ┌───────────────────────────────┐
│ Farmer arrives at 9:00 AM     │       │ Disruption on site at 9:15 AM │
│ Weighing scale breaks down    │       │ System recalculates wait time │
│ Farmer waits in line 8 hours  │       │ Push SMS: "Depart at 1:30 PM" │
│ Sells at MSP (Loses whole day)│       │ Farmer stays home, saves fuel │
└───────────────────────────────┘       └───────────────────────────────┘
```

#### Core Benefits Provided to Farmers

- **Prevents Wasteful Travel:** Sends dynamic SMS updates telling farmers exactly when to leave home based on real-time mandi speeds, saving time and fuel.
- **Eliminates Unplanned Delays:** Provides visibility into live gate queues, scale processing speeds, and yard disruptions before traveling to the site.
- **Protects MSP Realization:** Enables farmers to sell at guaranteed government MSP rates without sacrificing days of lost labor waiting in physical lines.

Your system bridges the gap by optimizing **ground-level logistics** for government MSP procurement yards, ensuring farmers can access guaranteed prices without suffering through physical congestion.

but the statement that these startups **"bypass government MSP mandis entirely"** is too absolute.

Better:

> **Indian AgriTech platforms primarily address commercial agricultural trade, market linkage, logistics, storage or private supply chains rather than the operational management of government MSP procurement-centre arrivals.**
> 

3. Now Put Everything Together

cleanest version of table so far 🙂:-

| **Operational Layer** | **Government MSP Systems** | **Private / Global Systems** | **Status of PS 32 Gap** |
| --- | --- | --- | --- |
| **Registration / Slot Booking** | HPAPPP, e-Uparjan, Kapas-Kisan etc. already provide this. | Common in logistics. | 🔴 **Solved** |
| **Rescheduling** | HPAPPP and West Bengal e-Paddy explicitly support rescheduling. (HPAPP) | Common in appointment/logistics systems. | 🔴 **Solved** |
| **Procurement Status / Notifications** | e-Uparjan provides SMS notification and procurement/payment information. (India.gov.in) | Common in logistics platforms. | 🔴 **Solved** |
| **Live Queue / ETA** | Not consistently evident as a farmer-facing feature across the government systems reviewed. | GrainQueue and GrainFlow already provide this. (GrainQueue) | 🔴 **Not unique** |
| **Yard / Facility Monitoring** | Government systems monitor procurement operations, but public documentation varies in how deeply physical yard conditions are exposed to farmers. | GrainFlow provides real-time yard/lane monitoring and throughput. (GrainFlow) | 🟡 **Already exists globally** |
| **Capacity-Aware Scheduling** | Government systems use scheduled/token capacity. | GrainFlow explicitly offers capacity-aware scheduling. (GrainFlow) | 🟡 **Already exists globally** |
| **Physical Disruption Handling** | Government portals have administrative mechanisms for changing tokens/schedules and procurement procedures. | GrainFlow/other commercial systems address operational disruptions and yard conditions. | 🟡 **Not proven unique** |
| **Disruption → Affected Scheduled Farmers → Automated Response** | **No strong evidence found in the systems reviewed of this exact end-to-end workflow.** | Global systems come closer operationally, but the reviewed evidence does not establish this exact workflow for Indian public MSP procurement. | 🟡 **Potential gap — requires validation** |
| **Public MSP Multi-Centre Coordination** | Centre selection/rescheduling exists. | Commercial logistics can balance facilities, but they operate in different contexts. | 🟡 **Potential gap — requires validation** |
| **Complete Operational Coordination Engine** | Existing systems solve many individual administrative functions. | GrainFlow demonstrates a sophisticated commercial grain-yard operations layer. (GrainFlow) | 🟡 **Potentially interesting, but NOT proven unsolved** |

Existing government and commercial systems address different components of prxocurement and yard operations. Government platforms provide scheduling, rescheduling, procurement tracking and notifications, while commercial grain-yard platforms such as GrainQueue and GrainFlow provide live queue, ETA, yard visibility and capacity-aware scheduling. The research gap therefore cannot be claimed at the level of any individual feature. The remaining area to validate is whether these operational signals are integrated into an end-to-end disruption-response workflow specifically for Indian public MSP procurement, where a physical disruption is linked to its impact on already-scheduled farmers and generates coordinated corrective actions.

# Actual Research Status

### 🟢 Clearly already solved (globally)

- Farmer registration
- Slot/token booking
- Centre selection
- Basic scheduling
- Rescheduling
- Procurement status
- Payment tracking
- Notifications
- Live queue
- ETA
- Commercial grain-yard monitoring

### 

### **India-Specific Operational Coordination Gap**

**Global systems already solve many individual components → but the opportunity is to adapt them into one workflow for Indian public MSP procurement.**

**Physical disruption at MSP centre**

↓

**Real-time impact on centre capacity**

↓

**Identify affected scheduled farmers**

↓

**Predict delay / congestion**

↓

**Recommend action: delay / reschedule / nearby centre**

↓

**Notify farmer + operator**

> **Focus:** Not inventing a new queue system, but creating an **India-specific operational coordination layer** that connects live procurement-centre conditions with scheduled farmer movement.
> 

### Conclusion — PS 32

**PS 32 is not an unsolved problem at the basic level.** Government systems already handle registration, slot/token booking, rescheduling, procurement status, notifications and payments. Private/global systems also demonstrate live queues, ETA, yard monitoring and capacity-aware scheduling.

Therefore, **we should NOT position our solution as a new booking, queue or ETA platform.**

The only potentially valuable direction identified in our research is the **integration layer**:

> **Physical disruption at an Indian public MSP procurement centre → real-time change in operational capacity → identify affected scheduled farmers → predict the impact → recommend corrective action → notify the farmer and operator.**
> 

However, our research **does not prove that this workflow is globally unsolved**. Commercial systems such as GrainFlow already solve several closely related operational functions. What remains potentially differentiating is **adapting and integrating these capabilities specifically around the workflows, constraints and multi-centre structure of Indian public MSP procurement.**

### Final verdict

**PS 32: 🟡 Medium / Risky**

- **Do not claim:** “No existing system solves this.”
- **Do not build:** another slot-booking / queue / ETA app.
- 🟡 **Potential opportunity:** India-specific **MSP Operational Coordination Layer**.
- ⚠️ **Before choosing PS 32:** you still need stronger evidence that Indian public procurement systems actually lack this disruption-to-farmer-response workflow.

**If your goal is maximum confidence for SIH, I would NOT call PS 32 a clearly proven gap yet.** It is a **potentially good engineering problem, but a weakly proven innovation gap** based on the research you currently have.

nah add an angle that in gobal ps is alsmost solved but in inda these are the gaps dont add reschedualling this as it is already offered like conclusion based on my research

## Conclusion — PS 32

Our research shows that **PS 32 is largely solved at the basic and global operational level**. Government MSP platforms already provide registration, slot/token booking, rescheduling, procurement tracking and notifications, while global commercial systems already demonstrate live queues, ETA, yard monitoring and capacity-aware scheduling.

Therefore, **PS 32 should not be presented as a problem of “creating a better booking or queue system.”**

However, the research indicates an **India-specific operational gap**: these global operational capabilities are not clearly established as an integrated solution within **Indian public MSP procurement centres**, where government procurement has its own workflows, scale, multiple centres, seasonal surges and on-ground constraints.

The potential opportunity is therefore:

> **To adapt proven global operational-flow concepts to Indian MSP procurement and connect real-time centre conditions—such as equipment failure, reduced processing capacity, unexpected arrivals and centre-level congestion—to the movement of farmers scheduled for procurement.**
> 

### In simple terms

**Global:**

Individual pieces of the problem are already being solved.

**India:**

Government systems are strong in **procurement administration**, but the research did not identify an equivalent integrated **operational-flow layer** combining live centre conditions with farmer movement at public MSP yards.

### What this means for our product

We should **not build another booking/rescheduling portal.**

The product should focus on:

**Live centre condition → operational impact → affected farmer flow → recommended operational action**

For example:

> **Scale failure → capacity drops → backlog predicted → upcoming farmers affected → system recommends operational action.**
> 

### Final research position

**PS 32 is not a completely unsolved problem.**

But there is a **potential India-specific implementation gap** between existing government procurement administration and the advanced operational-flow systems demonstrated globally.

 ***idea, built on that gap:***

**"Mandi Pulse"** — an operational coordination layer that sits on top of existing MSP portals (HPAPPP/e-Uparjan/Kapas-Kisan), not a replacement for them.

- Yard side: cheap sensor/camera input (or even manual operator toggle if hardware is out of scope for a hackathon) flags disruptions — scale down, truck backlog, gate pass bottleneck, weather.
- Engine: cross-references the disruption against farmers already scheduled/slotted for that centre in the next N hours.
- Output: auto-generates a recommendation (wait, delay departure, reroute to nearby centre with capacity) and pushes it via SMS/app to affected farmers *and* flags it to the centre operator's dashboard.
- Differentiator for judges: it explicitly doesn't reinvent booking — it's the missing "glue" layer, which is a stronger, more defensible pitch than "we built a queue app" (judges researching prior art will find GrainFlow/e-Uparjan in five minutes, so owning that comparison upfront is a strength, not a weakness).

**[   HPAPPP definitely solves scheduling/rescheduling in India.** So we need to be precise.

HPAPPP lets a farmer select a mandi + date, generate a token, and **reschedule the mandi/date up to 2 days before the scheduled date, subject to slot availability**. It also lets officials change/add slots.

But that's **not the same thing** as what we were discussing.

### The distinction

**HPAPPP:**

> “I can't go on my scheduled date → I want to change my date/mandi.”
> 

**Mandi Pulse:**

> “My slot is today, but something changed at the mandi *right now* → the system detects the operational impact and tells me what I should do.”
> 

Example:

```
Farmer's slot
10:30 AM
     ↓
10:00 AM
Scale #2 breaks
     ↓
Centre capacity drops
     ↓
Mandi Pulse calculates impact
     ↓
Your 10:30 slot is affected
     ↓
"Don't leave yet.
Expected processing delay: 2h"
```

So **do NOT claim:**

> ❌ “India doesn't have procurement rescheduling.”
> 

HPAPPP proves that wrong.

Instead say:

> **“Indian MSP portals already provide advance slot scheduling and rescheduling. The proposed system explores a different operational layer: responding to changes in actual procurement-centre conditions after farmers have been scheduled.”**
> 

And one more important correction: **HPAPPP's public documentation does not prove that it automatically connects a live equipment/processing disruption to the affected farmers' schedules.** Its documented functionality covers token availability, scheduling/rescheduling, additional tokens and operational procurement management.  ]

Basically **Mandi Pulse existing government portals ko replace nahi karega**. Ye unke upar ek **extra operational layer** hoga.

### Simple example

Maan lo farmer ka slot **10:30 AM** hai.

Existing portal bolta hai:

> **“Your slot: 10:30 AM, Centre A.”**
> 

Ab actual mandi mein:

**10:00 AM → Scale #2 kharab ho gaya.**

Isse centre ki processing speed half ho gayi.

### Existing system

Portal ko bas pata hai:

> Farmer ka slot = 10:30 AM
> 

Lekin ground par kya ho raha hai, uska effect farmer ke scheduled arrival se automatically connect nahi hota.

### Mandi Pulse

**1. Mandi se signal aaya**

> 🔴 Scale #2 Down
> 

Ye signal aa sakta hai:

- operator ke simple button se
- sensor se
- camera/monitoring system se

Hackathon ke liye **manual operator toggle bhi enough hai**. Sensors compulsory nahi hain.

**2. Engine calculation karega**

System dekhega:

> Current processing capacity ↓
> 
> 
> Existing queue ↑
> 
> Next 3 hours mein scheduled farmers = 42
> 
> Expected backlog = 25 farmers
> 

**3. Ab system affected farmers identify karega**

Example:

> Khyati — 10:30 AM ❗ Affected
> 
> 
> Ravi — 11:00 AM ❗ Affected
> 
> Aman — 2:30 PM ✅ Probably unaffected
> 

**4. Farmer ko actionable information milegi**

Instead of farmer unnecessarily mandi pahunch jaaye:

> ⚠️ **Centre A is currently operating below normal capacity.**
> 
> 
> Your 10:30 AM arrival may be delayed.
> 
> **Recommended: arrive at 12:00–12:20 PM.**
> 

Ya agar situation serious hai:

> **Centre A is heavily congested. Nearby Centre B currently has available capacity.**
> 

---

### Toh actual product kya hai?

Think of it like this:

```
Existing MSP Portal
        ↓
Booking / Token / Procurement / Payment
        │
        ▼
   MANDI PULSE
   "Operational Glue"
        │
        ├── Live disruption
        ├── Processing capacity
        ├── Current arrivals
        ├── Scheduled farmers
        └── Centre status
                ↓
        Impact Prediction
                ↓
        Recommended Action
                ↓
     ┌──────────┴──────────┐
     ↓                     ↓
 Farmer                 Operator
 "When should I       "What should
  come?"               I do?"
```

### **Sabse important point**

Tum ye **claim nahi kar rahe**:

> ❌ “We invented online booking.”
> 
> 
> ❌ “We invented live queues.”
> 
> ❌ “We invented ETA.”
> 
> ❌ “We invented rescheduling.”
> 

Ye sab already exist karte hain in different systems.

Tumhara pitch hai:

> **“Existing systems tell farmers when they are scheduled. Mandi Pulse tells them what to do when the actual mandi situation changes.”**
> 

Aur **Mandi Pulse ka role exactly wahi “glue” hai**:

**ground reality → operational impact → scheduled farmers → actionable response.**

Isi wajah se judges ko tum existing portals ke competitor ke instead **existing infrastructure ke upar ka coordination layer** dikha sakte ho.
