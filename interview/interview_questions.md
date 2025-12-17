# Interview Questions: Laser Print Layout Requirements

## Section 1: Current State (10 min)

### Q1: Show me the standard layout
**Ask:** "Can you show me what the current standard layout looks like? What information is printed now?"

**What to capture:**
- Photo or sketch of current layout
- List all fields currently printed
- Note the order/position of each field

---

### Q2: What's the problem?
**Ask:** "What problems are you facing with the current one-size-fits-all layout?"

**What to capture:**
- Specific customer complaints
- Which customers are unhappy
- Why they need different layouts

---

## Section 2: Layout Variations (20 min)

### Q3: How many different layouts?
**Ask:** "From the examples you prepared, how many different layout types do we actually need?"

**What to capture:**
- Count distinct layout patterns
- Group similar requests together
- Estimate: 3 templates? 5? 10?

**Follow-up:** "Can we group some customers together if their needs are similar?"

---

### Q4: Walk through each customer example
**Ask:** "Let's go through each customer example. For [Customer A], what exactly do they want?"

**What to capture for EACH customer:**
```
Customer: _______________
Layout Type: [Minimal/Standard/Detailed/Custom]

Fields INCLUDED:
☐ Company logo
☐ Company name  
☐ Charge number
☐ Homogenization status
☐ Alloy number
☐ Alloy name
☐ Batch number
☐ Ingot ID
☐ Length
☐ Dimension
☐ QR code
☐ Other: _______________

Fields EXCLUDED:
_______________

Special requirements:
_______________
```

**Repeat for each customer example they brought**

---

### Q5: Any unusual requests?
**Ask:** "Are there any weird or special requests that don't fit the normal pattern?"

**What to capture:**
- Edge cases (multi-language, extra large text, colors)
- One-off requests
- Requests you're not sure how to handle

---

## Section 3: Mandatory Fields (5 min)

### Q6: What MUST be on every billet?
**Ask:** "Are there any fields that must appear on every billet for safety, traceability, or regulations?"

**What to capture:**
- List of mandatory fields that cannot be removed
- Why they're mandatory (safety/legal/traceability)

---

### Q7: What about the QR code?
**Ask:** "Does the QR code content change by customer, or just the printed text?"

**What to capture:**
- Is QR code mandatory for all?
- Does QR content vary by customer?
- What's in the QR code minimum/maximum?

---

## Section 4: Data & System (10 min)

### Q8: Where does the data come from?
**Ask:** "In Kubal, where does each piece of information come from? Which tables or fields?"

**What to capture:**
```
Printed Field → Kubal Source
- Alloy number → [table.field]
- Charge number → [table.field]
- Customer name → [table.field]
- Homogenization status → [table.field]
- Ingot ID → [table.field]
- Length → [table.field]
```

---

### Q9: Is customer linked to orders?
**Ask:** "In Kubal, is the customer already connected to the production order? How do we know which customer an order is for?"

**What to capture:**
- Yes/No: customer field exists?
- Table/field name where customer is stored
- Is it reliable and always filled?

---

### Q10: How is data sent to Hertwich?
**Ask:** "How exactly do we send data to Hertwich now? File export? Manual entry? How long does it take?"

**What to capture:**
- Current process: Kubal → ??? → Hertwich
- File format or method
- Frequency (per billet? batch? daily?)
- Pain points in current process

---

## Section 5: Prioritization (10 min)

### Q11: Which customers are most important?
**Ask:** "If we can only support 3-5 layouts at first, which customers or layout types should we do first?"

**What to capture:**
- Priority 1: Must have (high volume or critical customer)
- Priority 2: Should have (important but can wait)
- Priority 3: Nice to have (low priority)

**Rank each customer/layout by:**
- Order volume
- Customer importance
- Urgency

---

### Q12: How often do requirements change?
**Ask:** "Do customers change their layout preferences often? Or is it set once and stable?"

**What to capture:**
- Frequency of layout changes per customer
- How changes are communicated
- Lead time needed for changes

---

## Section 6: Future & Growth (5 min)

### Q13: New customers
**Ask:** "How many new customers do you get per year? Will we need more layouts in the future?"

**What to capture:**
- Number of new customers per year
- Expected growth in layout complexity
- Trend: staying simple or getting more complex?

---

### Q14: Who manages this?
**Ask:** "If we build a system to manage layouts, who should be able to add or change them? Production? IT? Engineering?"

**What to capture:**
- User roles who need access
- Skill level (technical or non-technical users)
- Need for approval process?

---

## Section 7: Constraints (5 min)

### Q15: Physical limitations
**Ask:** "Are there any physical limits? Maximum print area? Size differences between billets?"

**What to capture:**
- Print area dimensions
- Billet size variations
- Position requirements (top/middle/bottom)
- Font size limitations

---

### Q16: Error handling
**Ask:** "What happens if wrong layout is printed? How do you catch it? Has it happened?"

**What to capture:**
- Current error rate
- Cost of mistakes
- How errors are caught
- Need for preview/verification step?

---

## Section 8: Success Definition (5 min)

### Q17: What would success look like?
**Ask:** "If this new system works perfectly, what would make your job easier?"

**What to capture:**
- Specific improvements they want
- Time saved
- Fewer errors
- Happier customers

---

## Summary Section (5 min)

### Q18: Final confirmation
**Review together:**
1. "So we identified [X] different layout types, is that correct?"
2. "The mandatory fields are [list], right?"
3. "Priority customers are [list], yes?"
4. "Anything we missed or need to clarify?"

---

## Post-Interview Checklist

After the interview, make sure you have:

☐ **Layout count:** How many distinct templates needed?

☐ **Customer mapping:** Which customer uses which layout?

☐ **Field list:** Complete list of all possible fields

☐ **Mandatory fields:** What must always appear

☐ **Data sources:** Kubal table.field for each element

☐ **Priority ranking:** Which layouts to build first

☐ **Edge cases:** Unusual requests documented

☐ **Integration point:** How data flows to Hertwich

☐ **Photos/sketches:** Visual examples of layouts

☐ **Success criteria:** What makes this project successful

---

## Expected Outcomes

By the end of this interview, you should be able to say:

**"We need [X] layout templates:"**
1. Template 1 (Minimal): Fields A, B, C - Used by Customers X, Y
2. Template 2 (Standard): Fields A, B, C, D, E - Used by Customers M, N, P
3. Template 3 (Detailed): All fields - Used by Customer Z
4. [etc.]

**"Exception cases:"**
- Customer ABC needs special handling because [reason]
- Multi-language requirement for Customer DEF

**"Implementation approach:"**
- Add `print_template_id` to customer master
- Create [X] template definitions
- Modify export to Hertwich to include template ID

**"Priority:"**
- Phase 1: Templates 1 & 2 (covers 80% of volume)
- Phase 2: Template 3 (remaining customers)
- Phase 3: Handle exceptions

---

## Quick Tips During Interview

✅ **DO:**
- Take lots of notes
- Sketch layouts as they describe them
- Ask "show me" instead of "tell me"
- Group similar requests together
- Confirm your understanding: "So what I'm hearing is..."

❌ **DON'T:**
- Jump to solutions too quickly
- Assume you understand without examples
- Skip documenting edge cases
- Forget to ask about data sources

---

**Time estimate:** 60-75 minutes total
