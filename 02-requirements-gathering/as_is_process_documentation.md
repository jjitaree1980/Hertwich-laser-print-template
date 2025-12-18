# As-Is Process Documentation
## Current Laser Print Layout Management Process

**Project:** Laser Print Template Layout Management System
**Document Owner:** Business Analyst
**Version:** 1.0
**Date:** 2025-12-18

---

## Process Overview

This document describes the current (as-is) process for managing laser print layouts for aluminum billet marking.

---

## High-Level Process Flow

```
Production Order → Manual Lookup → Data Selection → Format Data → Send to Hertwich → Verify → Proceed
```

---

## Detailed Process Steps

### 1. Production Order Received

**Actor:** Production Planning System
**Description:** A new production order is created in the Kubal system for aluminum billet production

**Inputs:**
- Customer name
- Product specifications (alloy, dimensions, quantity)
- Delivery requirements

**Outputs:**
- Production order record in Kubal

**Duration:** Automated (instant)

---

### 2. Operator Reviews Order

**Actor:** Production Operator
**Description:** Operator accesses production order and identifies customer

**Inputs:**
- Production order from Kubal

**Actions:**
- Log into Kubal system
- Navigate to production orders
- Open relevant order
- Note customer name

**Outputs:**
- Customer identification

**Duration:** 2-3 minutes

**Pain Points:**
- Multiple clicks required to find order
- Sometimes unclear which customer variant (if customer has subsidiaries)

---

### 3. Look Up Customer Layout Requirements

**Actor:** Production Operator or Supervisor
**Description:** Operator must find what layout/information the customer requires

**Current Methods (in order of usage):**
1. Check Excel spreadsheet (stored on shared drive)
2. Search email for customer requirements
3. Ask supervisor or colleague
4. Check customer contract (rare)

**Inputs:**
- Customer name

**Actions:**
- Open Excel file "Customer_Laser_Requirements.xlsx"
- Search for customer name
- Note which fields are required
- If not found, search emails or ask colleagues

**Outputs:**
- List of data fields to include in laser print

**Duration:** 10-15 minutes

**Pain Points:**
- **Major pain point** - time-consuming and error-prone
- Excel file not always up to date
- Multiple versions of the file exist
- New operators don't know where to look
- No consistency in how requirements are documented
- Some requirements only exist as "tribal knowledge"

---

### 4. Decision: Standard or Special Layout?

**Actor:** Production Operator
**Description:** Operator determines if customer needs standard or customized layout

**Decision Criteria:**
- If customer is in Excel list with specific requirements → Special layout
- If customer not in list → Standard layout
- If uncertain → Ask supervisor

**Duration:** 1-2 minutes

---

### 5. Select Data Fields to Include

**Actor:** Production Operator
**Description:** Based on customer requirements, operator determines which data fields to include

**Standard Layout Fields:**
- Logo
- Company name
- Charge number
- Alloy number
- Homogenization status and machine
- QR code (standard fields)

**Variations:**
- Some customers: Only alloy + batch number
- Some customers: Standard + ingot ID
- Some customers: Standard + ingot ID + length
- Custom customers: Various combinations

**Duration:** 3-5 minutes

**Pain Points:**
- Easy to forget a field
- No validation that selected fields match customer requirements
- Inconsistent interpretation of requirements

---

### 6. Extract Data from Kubal

**Actor:** Production Operator
**Description:** Operator manually queries or extracts required data from Kubal

**Data Sources in Kubal:**
- Customer table → Company name, customer code
- Production_Orders table → Charge number, dimensions, length
- Products table → Alloy number
- Production_Process table → Homogenization status, machine
- Inventory table → Ingot ID (if applicable)

**Actions:**
- Navigate to each relevant table/screen in Kubal
- Copy data values
- Paste into intermediate file or form

**Duration:** 8-10 minutes

**Pain Points:**
- Manual data entry prone to typos
- Data scattered across multiple screens
- Some data may not be updated yet (e.g., homogenization status)

---

### 7. Format Data for Hertwich

**Actor:** Production Operator
**Description:** Operator formats the data according to Hertwich system requirements

**Format Requirements:**
- CSV file or fixed-width text file (depending on setup)
- Specific field order
- Character limits per field
- QR code data must be comma-separated in specific order

**Actions:**
- Open template file or create new file
- Arrange data fields in required order
- Ensure proper formatting (no special characters, trim spaces)
- Generate or format QR code data string

**Duration:** 5-7 minutes

**Pain Points:**
- Manual formatting risk
- Easy to forget QR code field order
- Character limit violations not caught until printing
- No standard template used consistently

---

### 8. Send Data to Hertwich

**Actor:** Production Operator
**Description:** Operator transmits formatted data to Hertwich system

**Transmission Method:** [File upload / API call / Manual entry - depends on configuration]

**Actions:**
- Save formatted file
- Upload to Hertwich system or designated folder
- Verify transmission successful

**Duration:** 2-3 minutes

**Pain Points:**
- Occasional transmission failures (network issues)
- No confirmation of what Hertwich received
- No versioning or tracking of what was sent

---

### 9. Hertwich Performs Laser Printing

**Actor:** Hertwich System (External)
**Description:** Hertwich's laser printing equipment marks the billets according to transmitted data

**Duration:** Varies (per batch size)

**Pain Points:**
- No visibility into Hertwich process from our side
- Errors discovered only after printing

---

### 10. First Billet Verification

**Actor:** Production Operator or QA Inspector
**Description:** First billet from batch is visually inspected to verify laser print is correct

**Verification Checks:**
- All required fields present
- Data values correct
- QR code scannable
- Print quality acceptable

**Duration:** 5-10 minutes

**Outcomes:**
- **If correct:** Proceed with full batch
- **If incorrect:** Stop production, rework required

**Pain Points:**
- **Late error discovery** - errors found after printing
- Rework is time-consuming and costly
- Sometimes billet already moved to next process stage

---

### 11. Decision: Correct or Rework?

**Decision Criteria:**
- All customer requirements met → Proceed
- Missing field or wrong data → Rework

**If Rework Required:**
1. Identify root cause (wrong customer requirements? data error? transmission error?)
2. Correct data/configuration
3. Re-send to Hertwich
4. Re-print affected billets
5. Re-verify

**Rework Duration:** 30-60 minutes plus re-printing time

**Impact:**
- Production delay
- Material waste (if billets can't be re-marked)
- Customer delivery impact

---

### 12. Proceed with Batch

**Actor:** Production Team
**Description:** If first billet verified correct, proceed with full batch production

**Duration:** Per production schedule

---

## Process Metrics (Current State)

| Metric | Value |
|--------|-------|
| Average time per batch (layout config) | 30-45 minutes |
| Error rate (incorrect layouts) | ~10 errors per month |
| Rework time per error | 30-60 minutes |
| New customer onboarding time | 1-2 hours (first time) |
| Operator training time | 1-2 days |
| Number of manual steps | 8 steps |
| Number of systems/tools used | 3-4 (Kubal, Excel, Email, File system) |
| Data entry points (manual) | 6-8 fields |

---

## Current Systems and Tools

| System/Tool | Purpose | Issues |
|-------------|---------|--------|
| Kubal ERP | Production data storage | Data scattered, multiple screens |
| Excel Spreadsheet | Customer requirements storage | Not centralized, version control issues, not always updated |
| Email | Customer requirement communication | Unstructured, hard to search |
| Hertwich System | Laser printing execution | Limited visibility, no feedback loop |
| Shared Network Drive | File storage and transfer | No organization, no version control |

---

## Current Pain Points Summary

### High Severity (Must Fix)
1. **No centralized customer requirements** - scattered across Excel, emails, memory
2. **Manual lookup time-consuming** - 10-15 min per batch
3. **Late error discovery** - errors found after printing
4. **No validation** - errors not caught until production

### Medium Severity (Should Fix)
5. **Manual data extraction** - time-consuming, error-prone
6. **Inconsistent process** - varies by operator
7. **No audit trail** - can't trace what was sent when
8. **Poor new customer onboarding** - ad-hoc, inconsistent

### Low Severity (Nice to Fix)
9. **No process documentation** - operators rely on training and experience
10. **Limited Hertwich integration visibility** - black box

---

## Workarounds Currently Used

1. **Supervisor maintains "master" Excel file** - but not always used
2. **Operators create personal reference notes** - leads to inconsistency
3. **"Standard" customers assumed to use default** - but no formal definition of "standard"
4. **Double-check with colleague before first transmission** - informal peer review

---

## Stakeholder Quotes

**Production Supervisor:**
> "Every time we get a new customer, I have to create a Word document with their requirements and email it to the team. But operators still call me to confirm."

**Production Operator:**
> "I waste at least 20 minutes every batch looking up what the customer wants. Sometimes I'm not even sure I have the latest requirements."

**QA Manager:**
> "We catch errors during first-piece inspection, but by then the billet is already marked. If it's a critical field, we have to scrap it."

**Customer Service:**
> "Customers sometimes complain that the marking doesn't match what they requested. It's embarrassing and damages our reputation."

---

## Root Cause Analysis

### Why do layout errors occur?

**Root Causes:**
1. No single source of truth for customer requirements
2. Manual process with multiple handoffs
3. No validation before transmission
4. Inconsistent interpretation of requirements
5. Operator experience/knowledge dependency

### Why is the process so time-consuming?

**Root Causes:**
1. Manual lookup of customer requirements
2. Manual data extraction from multiple Kubal screens
3. Manual data formatting
4. No automation or system support

---

## Conclusion

The current process is **manual, time-consuming, error-prone, and not scalable**. Key improvement opportunities:

1. **Centralize** customer requirements in system
2. **Automate** layout selection based on customer
3. **Validate** data before transmission
4. **Integrate** with Kubal for automatic data extraction
5. **Standardize** process across all operators
6. **Track** audit trail for troubleshooting

---

**END OF DOCUMENT**
