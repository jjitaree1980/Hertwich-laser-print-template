# Interview Notes: Laser Print Layout Requirements

**Date:** _______________  
**Attendees:** _______________  
**Duration:** _______________

---

## Section 1: Current State (10 min)

### Q1: Show me the standard layout
**Question:** "Can you show me what the current standard layout looks like? What information is printed now?"

**Notes:**
- Current fields printed:
  - [ ] 
  - [ ] 
  - [ ] 
- Field order/position:
- Sketch/photo:

---

### Q2: What's the problem?
**Question:** "What problems are you facing with the current one-size-fits-all layout?"

**Notes:**
- Customer complaints:
- Which customers unhappy:
- Why different layouts needed:

---

## Section 2: Layout Variations (20 min)

### Q3: How many different layouts?
**Question:** "From the examples you prepared, how many different layout types do we actually need?"

**Notes:**
- Estimated template count: _____ templates
- Can group similar customers: Yes / No
- Grouping possibilities:

---

### Q4: Walk through each customer example
**Question:** "Let's go through each customer example. For [Customer A], what exactly do they want?"

**Customer 1:**
```
Customer name/code: _______________
Layout type: [ ] Minimal  [ ] Standard  [ ] Detailed  [ ] Custom

Fields INCLUDED:
[ ] Company logo
[ ] Company name  
[ ] Charge number
[ ] Homogenization status
[ ] Alloy number
[ ] Alloy name
[ ] Batch number
[ ] Ingot ID
[ ] Length
[ ] Dimension
[ ] QR code
[ ] Other: _______________

Fields EXCLUDED:
_______________

Special requirements:
_______________

Sketch:
```

**Customer 2:**
```
Customer name/code: _______________
Layout type: [ ] Minimal  [ ] Standard  [ ] Detailed  [ ] Custom

Fields INCLUDED:
[ ] Company logo
[ ] Company name  
[ ] Charge number
[ ] Homogenization status
[ ] Alloy number
[ ] Alloy name
[ ] Batch number
[ ] Ingot ID
[ ] Length
[ ] Dimension
[ ] QR code
[ ] Other: _______________

Fields EXCLUDED:
_______________

Special requirements:
_______________

Sketch:
```

**Customer 3:**
```
Customer name/code: _______________
Layout type: [ ] Minimal  [ ] Standard  [ ] Detailed  [ ] Custom

Fields INCLUDED:
[ ] Company logo
[ ] Company name  
[ ] Charge number
[ ] Homogenization status
[ ] Alloy number
[ ] Alloy name
[ ] Batch number
[ ] Ingot ID
[ ] Length
[ ] Dimension
[ ] QR code
[ ] Other: _______________

Fields EXCLUDED:
_______________

Special requirements:
_______________

Sketch:
```

**Additional customers:** (continue as needed)

---

### Q5: Any unusual requests?
**Question:** "Are there any weird or special requests that don't fit the normal pattern?"

**Notes:**
- Edge cases:
  - Multi-language:
  - Extra large text:
  - Colors:
  - Other:
- One-off requests:
- Unclear requests:

---

## Section 3: Mandatory Fields (5 min)

### Q6: What MUST be on every billet?
**Question:** "Are there any fields that must appear on every billet for safety, traceability, or regulations?"

**Notes:**
- Mandatory fields:
  1. _______________ (Reason: _______________)
  2. _______________ (Reason: _______________)
  3. _______________ (Reason: _______________)
  4. _______________ (Reason: _______________)

---

### Q7: What about the QR code?
**Question:** "Does the QR code content change by customer, or just the printed text?"

**Notes:**
- QR code mandatory for all: Yes / No
- QR content varies by customer: Yes / No
- QR code minimum content:
- QR code maximum content:

---

## Section 4: Data & System (10 min)

### Q8: Where does the data come from?
**Question:** "In Kubal, where does each piece of information come from? Which tables or fields?"

**Notes:**
| Printed Field | Kubal Table | Kubal Field |
|---------------|-------------|-------------|
| Alloy number | | |
| Charge number | | |
| Customer name | | |
| Homogenization status | | |
| Ingot ID | | |
| Length | | |
| Dimension | | |
| Batch number | | |
| Other: | | |

---

### Q9: Is customer linked to orders?
**Question:** "In Kubal, is the customer already connected to the production order? How do we know which customer an order is for?"

**Notes:**
- Customer field exists in order: Yes / No
- Table name: _______________
- Field name: _______________
- Always filled: Yes / No / Sometimes
- Notes:

---

### Q10: How is data sent to Hertwich?
**Question:** "How exactly do we send data to Hertwich now? File export? Manual entry? How long does it take?"

**Notes:**
- Current process: Kubal → _______________ → Hertwich
- File format: _______________
- Frequency: [ ] Per billet  [ ] Per batch  [ ] Daily  [ ] Other: _______________
- Time required: _______________
- Pain points:

---

## Section 5: Prioritization (10 min)

### Q11: Which customers are most important?
**Question:** "If we can only support 3-5 layouts at first, which customers or layout types should we do first?"

**Notes:**

**Priority 1 (Must have):**
- Customer/Layout: _______________
- Reason: _______________
- Volume: _______________

**Priority 2 (Should have):**
- Customer/Layout: _______________
- Reason: _______________
- Volume: _______________

**Priority 3 (Nice to have):**
- Customer/Layout: _______________
- Reason: _______________
- Volume: _______________

---

### Q12: How often do requirements change?
**Question:** "Do customers change their layout preferences often? Or is it set once and stable?"

**Notes:**
- Change frequency: [ ] Often  [ ] Sometimes  [ ] Rarely  [ ] Never
- How changes communicated:
- Lead time needed:

---

## Section 6: Future & Growth (5 min)

### Q13: New customers
**Question:** "How many new customers do you get per year? Will we need more layouts in the future?"

**Notes:**
- New customers per year: _______________
- Expected growth: [ ] Increase  [ ] Stay same  [ ] Decrease
- Complexity trend: [ ] More complex  [ ] Stay same  [ ] Simpler

---

### Q14: Who manages this?
**Question:** "If we build a system to manage layouts, who should be able to add or change them?"

**Notes:**
- User roles needing access:
  - [ ] Production
  - [ ] IT
  - [ ] Engineering
  - [ ] Other: _______________
- Skill level: [ ] Technical  [ ] Non-technical  [ ] Mixed
- Approval process needed: Yes / No

---

## Section 7: Constraints (5 min)

### Q15: Physical limitations
**Question:** "Are there any physical limits? Maximum print area? Size differences between billets?"

**Notes:**
- Print area dimensions: _______________
- Billet size variations:
- Position requirements: [ ] Top  [ ] Middle  [ ] Bottom  [ ] Flexible
- Font size limitations:

---

### Q16: Error handling
**Question:** "What happens if wrong layout is printed? How do you catch it? Has it happened?"

**Notes:**
- Current error rate: _______________
- Cost of mistakes: _______________
- How errors caught:
- Need preview/verification: Yes / No

---

## Section 8: Success Definition (5 min)

### Q17: What would success look like?
**Question:** "If this new system works perfectly, what would make your job easier?"

**Notes:**
- Specific improvements wanted:
- Time saved: _______________
- Error reduction: _______________
- Customer satisfaction impact:

---

## Summary & Confirmation (5 min)

### Q18: Final confirmation
**Review together:**

**Layout Templates Needed:**
1. Template name: _______________ 
   - Fields: _______________
   - Used by customers: _______________
   
2. Template name: _______________ 
   - Fields: _______________
   - Used by customers: _______________
   
3. Template name: _______________ 
   - Fields: _______________
   - Used by customers: _______________

**Mandatory Fields (Cannot be removed):**
- _______________
- _______________
- _______________

**Priority Customers:**
1. _______________
2. _______________
3. _______________

**Exception Cases:**
- _______________
- _______________

**Anything missed?**
- _______________

---

## Post-Interview Checklist

Verify you captured:

- [ ] **Layout count:** How many distinct templates needed?
- [ ] **Customer mapping:** Which customer uses which layout?
- [ ] **Field list:** Complete list of all possible fields
- [ ] **Mandatory fields:** What must always appear
- [ ] **Data sources:** Kubal table.field for each element
- [ ] **Priority ranking:** Which layouts to build first
- [ ] **Edge cases:** Unusual requests documented
- [ ] **Integration point:** How data flows to Hertwich
- [ ] **Photos/sketches:** Visual examples of layouts
- [ ] **Success criteria:** What makes this project successful

---

## Implementation Summary

**Final Requirements:**

**Template count:** _______________ templates

**Template definitions:**
```
Template 1 (_______________):
- Fields: _______________
- Used by: _______________

Template 2 (_______________):
- Fields: _______________
- Used by: _______________

Template 3 (_______________):
- Fields: _______________
- Used by: _______________
```

**Exception cases:**
- _______________
- _______________

**Implementation approach:**
- [ ] Add `print_template_id` field to customer master table
- [ ] Create ___ template definitions in system
- [ ] Modify export to Hertwich to include template ID
- [ ] Other: _______________

**Phased rollout:**
- Phase 1: _______________ (covers ___% of volume)
- Phase 2: _______________
- Phase 3: _______________

---

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| | | | |
| | | | |
| | | | |

---

## Next Steps

- [ ] Review notes and finalize requirements
- [ ] Create template mockups
- [ ] Present to stakeholders
- [ ] Plan database changes
- [ ] Coordinate with Hertwich team
- [ ] Define timeline
- [ ] Other: _______________

---

**Interview completed by:** _______________  
**Notes reviewed by:** _______________  
**Date:** _______________