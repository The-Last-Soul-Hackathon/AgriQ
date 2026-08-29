e-NAM already supports electronic payments, so simply adding UPI isn't innovative.

The research question is different:

> **When does the farmer actually consider a transaction financially safe?**
> 

Map:

```
Order
 ↓
Buyer commitment
 ↓
Goods loaded
 ↓
Goods delivered
 ↓
Weight confirmed
 ↓
Quality accepted
 ↓
Payment
```

### Adding features in payment

- Is payment advance?
- Same day?
- 2 days later?
- 7 days?
- Is there a dispute?
- Who decides final quantity?
- Who bears rejection risk?

### Product implication

Your transaction engine eventually needs:

**order → shipment → delivery confirmation → final settlement (like flipkart etc)**

rather than simply:

**order → payment**

its helps in trust build
