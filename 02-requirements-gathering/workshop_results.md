# Workshop Results
## Laser Print Template Layout Management System

**Project:** Laser Print Template Layout Management System
**Document Owner:** Business Analyst
**Version:** 1.0
**Date:** 2025-12-18

---

## Workshop Results Summary

This document consolidates key findings and outputs from all requirements gathering workshops.

---

## Workshop #1 Results: Current State Process Mapping

**Date Conducted:** [TBD]
**Participants:** [List names]
**Facilitator:** [BA Name]

### As-Is Process Map

_[Process map diagram to be inserted here - photo of whiteboard or digital version]_

**Process Steps Identified:**
1. Production order received in Kubal system
2. Operator reviews order details and identifies customer
3. Operator looks up customer layout requirements (Excel spreadsheet or memory)
4. Decision point: Standard or special layout?
5. Operator manually selects which data fields to include
6. Data extracted from multiple Kubal tables
7. Data formatted according to Hertwich requirements
8. Data sent to Hertwich via [file transfer/API/method]
9. Hertwich performs laser printing
10. First billet inspected by operator or QA
11. If incorrect, rework required; if correct, batch proceeds

**Key Decision Points:**
- Is this a known customer or new customer?
- Standard layout or custom layout?
- Is all required data available in Kubal?
- Does layout require QA approval?

### Pain Points Identified and Ranked

| Rank | Pain Point | Impact | Frequency | Severity | Votes |
|------|------------|--------|-----------|----------|-------|
| 1 | Manual lookup of customer requirements (multiple sources) | Time waste, errors | Every batch | High | 8 |
| 2 | No centralized customer requirements repository | Confusion, outdated info | Ongoing | High | 7 |
| 3 | Manual data selection and formatting | Time waste | Every batch | Medium | 6 |
| 4 | No validation before sending to Hertwich | Late error discovery | ~10/month | High | 6 |
| 5 | Inconsistent process (varies by operator) | Quality variation | Ongoing | Medium | 5 |
| 6 | New customer onboarding is ad-hoc | Delays, confusion | Monthly | Medium | 4 |
| 7 | No audit trail of what was printed | Traceability issues | Ongoing | Low | 2 |

### Time Analysis

**Current Process Time Breakdown:**
- Looking up customer requirements: 10-15 minutes
- Selecting and extracting data from Kubal: 8-10 minutes
- Formatting data for Hertwich: 5-7 minutes
- Sending to Hertwich: 2-3 minutes
- Verification: 5-10 minutes
- **Total:** 30-45 minutes per batch

**Annual Impact:**
- ~50 batches per week × 52 weeks = 2,600 batches/year
- 30 min average × 2,600 = 1,300 hours/year
- **Opportunity:** 70% reduction = 910 hours saved annually

### Data Sources Inventory

| Data Element | Current Source | Format | Quality | Issues |
|--------------|----------------|--------|---------|--------|
| Customer layout requirements | Excel spreadsheet + emails | Unstructured | Poor | Not centralized, version issues |
| Customer name | Kubal: Customers table | Text | Good | None |
| Charge number | Kubal: Production_Orders | Alphanumeric | Good | None |
| Alloy number | Kubal: Products | Alphanumeric | Good | None |
| Company code | Kubal: Customers | Alphanumeric | Good | None |
| Homogenization status | Kubal: Production_Process | Text | Fair | Sometimes delayed update |
| Homogenization machine | Kubal: Equipment | Text | Good | None |
| Dimensions | Kubal: Products | Numeric | Good | None |
| Length | Kubal: Production_Orders | Numeric | Good | None |
| Unique Ingot ID | Kubal: Inventory (if used) | Alphanumeric | Fair | Only for some customers |

### Key Insights
1. **No single source of truth** for customer requirements - scattered across spreadsheet, emails, and tribal knowledge
2. **Operator dependency** - different operators have different approaches
3. **Late error detection** - errors found after printing, costly to fix
4. **Manual, repetitive work** - significant time spent on non-value-added tasks
5. **Scalability challenge** - current approach won't scale with growing customer base

---

## Workshop #2 Results: Customer Requirements Analysis

**Date Conducted:** [TBD]
**Participants:** [List names]
**Facilitator:** [BA Name]

### Customer Inventory

**Total Customers Analyzed:** [XX customers]
**Customers with Unique Requirements:** [YY customers]

### Customer Layout Categories Defined

**Category 1: Standard Layout (~60% of customers)**
- Logo
- Company name
- Charge number
- Alloy number
- Homogenization status
- QR code (standard fields: charge number, company code, alloy code, dimension, length, homogenization)

**Category 2: Minimal Layout (~20% of customers)**
- Alloy name
- Batch/Charge number
- QR code (minimal fields: charge number, alloy code)

**Category 3: Detailed Layout (~15% of customers)**
- All standard fields PLUS:
- Unique ingot ID
- Length (printed as text in addition to QR code)
- Dimension details
- Production date
- QR code (extended fields)

**Category 4: Custom Layout (~5% of customers)**
- Customer-specific field combinations
- Special formatting requirements
- Examples: [Specific customer examples]

### Data Field Requirements Matrix

| Data Field | Standard | Minimal | Detailed | Custom | Source |
|------------|----------|---------|----------|--------|--------|
| Logo | ✓ | ✗ | ✓ | Varies | Static file |
| Company name | ✓ | ✗ | ✓ | Varies | Kubal |
| Charge number | ✓ | ✓ | ✓ | Varies | Kubal |
| Alloy number | ✓ | ✓ | ✓ | ✓ | Kubal |
| Homogenization status | ✓ | ✗ | ✓ | Varies | Kubal |
| Homogenization machine | ✓ | ✗ | ✓ | Varies | Kubal |
| Unique ingot ID | ✗ | ✗ | ✓ | Varies | Kubal |
| Length (text) | ✗ | ✗ | ✓ | Varies | Kubal |
| Dimension | ✗ | ✗ | ✓ | Varies | Kubal |
| Production date | ✗ | ✗ | ✓ | Varies | Kubal |
| QR code | ✓ | ✓ | ✓ | ✓ | Generated |

### Customer-to-Category Mapping

_[Sample - to be completed with actual customer names]_

**Standard Layout:** Customer A, Customer B, Customer C, ...
**Minimal Layout:** Customer X, Customer Y, ...
**Detailed Layout:** Customer M, Customer N, ...
**Custom Layout:** Customer Z (special requirements: ...)

---

## Workshop #3 Results: Future State Design

**Date Conducted:** [TBD]
**Participants:** [List names]
**Facilitator:** [BA Name]

### To-Be Process Map

_[Process map diagram to be inserted - shows automated flow]_

**Simplified Process Steps:**
1. Production order received
2. **System automatically identifies customer**
3. **System automatically selects layout configuration**
4. **System extracts required data from Kubal**
5. **System validates data completeness and format**
6. **System transmits to Hertwich with layout config**
7. Laser printing performed
8. First billet verification
9. Proceed with batch

**Key Improvements:**
- Automatic layout selection (eliminates manual lookup)
- Built-in validation (catches errors early)
- Centralized configuration (single source of truth)
- Audit trail (full traceability)

**Time Savings Projected:**
- Manual lookup: Eliminated (~12 min)
- Data selection: Automated (~8 min)
- Formatting: Automated (~6 min)
- **New process time:** <10 minutes
- **Savings:** ~70% reduction

### System Capability List (Prioritized using MoSCoW)

**Must Have:**
1. Customer layout configuration storage
2. Automatic layout selection based on customer
3. Configurable data field selection per layout
4. Data extraction from Kubal
5. Data validation before transmission
6. Integration with Hertwich
7. User interface for configuration management
8. Default layout for customers without specific config
9. Error handling and user notifications
10. Basic audit trail (what layout was used for which batch)

**Should Have:**
1. Layout preview before sending to Hertwich
2. Approval workflow for new/modified layouts
3. Search and filter for customer configurations
4. Detailed audit trail (who changed what when)
5. Configuration change history
6. Manual override capability
7. Role-based access control
8. Online help/tooltips

**Could Have:**
1. Layout usage reporting/analytics
2. Advanced field positioning and formatting
3. Automated alerts for missing customer configurations
4. Duplicate/copy configuration feature
5. Export/import configuration capability

**Won't Have (this release):**
1. Mobile app
2. Customer self-service portal
3. Automated contract parsing
4. Real-time Hertwich printing status
5. Predictive analytics

### User Workflow Designs

**Workflow 1: Configure New Customer Layout**
1. User logs into system
2. Navigate to "Customer Configuration"
3. Click "Add New Customer"
4. Enter customer name (or select from Kubal)
5. Select layout template (Standard/Minimal/Detailed/Custom)
6. Select/deselect data fields
7. Preview layout
8. Save configuration
9. (Optional) Submit for approval
10. Configuration activated

**Workflow 2: Process Production Order (Automated)**
1. Production order created in Kubal
2. System automatically identifies customer
3. System retrieves customer layout configuration
4. System extracts required data fields
5. System validates data
6. System sends to Hertwich
7. Operator notified of success
8. (If error) Operator notified, takes corrective action

**Workflow 3: Manual Override**
1. Operator reviews automatic layout selection
2. Clicks "Override Layout"
3. Selects different layout or modifies fields
4. Enters reason for override
5. Confirms override
6. Override logged in audit trail

### Draft Wireframes

_[Wireframe sketches to be inserted - can be photos of flip chart drawings or digital mockups]_

**Key Screens Identified:**
1. Customer Configuration List (search, filter, add new)
2. Configuration Editor (select fields, preview)
3. Production Order Processing (auto-selection display, override option)
4. Audit Trail View (history of configurations and usage)

---

## Workshop #4 Results: Integration Requirements

**Date Conducted:** [TBD]
**Participants:** [List names]
**Facilitator:** [Technical Lead Name]

### Current Integration Architecture

**Method:** [File transfer / API / Database link]
**Protocol:** [FTP / SFTP / HTTP / Direct DB]
**Frequency:** [Real-time / Batch / On-demand]
**Data Format:** [CSV / XML / JSON / Fixed-width]

**Current Data Elements Sent:**
- [List current data fields sent to Hertwich]

**Current Issues:**
- [Issue 1 if any]
- [Issue 2 if any]

### Enhanced Integration Design

**Proposed Approach:**
- Maintain current integration protocol
- Add layout configuration metadata to data transmission
- Include field selection indicators
- Enhance error handling and retry logic

**New Data Elements to Include:**
- Layout template ID
- Field inclusion flags (which fields to print)
- Layout version/timestamp
- Override indicator (if manual override used)

**Error Handling:**
- Pre-transmission validation (data completeness, format)
- Transmission confirmation from Hertwich
- Retry logic (3 attempts with exponential backoff)
- Error notification to operator
- Failed transmission logging

### Integration Test Scenarios

| Scenario ID | Scenario Description | Expected Result |
|-------------|---------------------|-----------------|
| INT-001 | Send standard layout for known customer | Successful transmission, correct layout |
| INT-002 | Send minimal layout for customer | Successful transmission, correct layout |
| INT-003 | Send detailed layout with all fields | Successful transmission, correct layout |
| INT-004 | Customer with no configuration (default layout) | Successful transmission, default layout used |
| INT-005 | Missing required data field | Error caught, transmission prevented, user notified |
| INT-006 | Invalid data format | Error caught, transmission prevented, user notified |
| INT-007 | Hertwich system unavailable | Retry logic invoked, user notified |
| INT-008 | Manual override layout | Successful transmission, override logged |
| INT-009 | Concurrent transmissions (load test) | All successful, no data corruption |
| INT-010 | New customer first-time transmission | Successful with appropriate validation |

### Technical Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Obtain Hertwich API/integration documentation | Hertwich Contact | [Date] | Open |
| Confirm Hertwich can accept layout metadata | Hertwich Contact | [Date] | Open |
| Design database schema for layout config | System Admin | [Date] | Open |
| Define data validation rules | System Admin + BA | [Date] | Open |
| Create integration test environment | System Admin | [Date] | Open |

---

## Consolidated Key Findings

### Top Requirements from All Workshops
1. Centralized customer layout configuration repository
2. Automatic layout selection eliminating manual lookup
3. Data validation before transmission to catch errors early
4. User-friendly configuration interface
5. Maintain Hertwich integration reliability
6. Audit trail for compliance and troubleshooting
7. Support for standard, minimal, detailed, and custom layouts
8. Preview capability before production use

### Critical Success Factors
1. Zero layout errors after go-live
2. 70% reduction in configuration time
3. Easy adoption by production team
4. Reliable Hertwich integration
5. Scalable to support growing customer base

### Risk Mitigation Needs
1. Thorough testing with Hertwich integration
2. Comprehensive training for production team
3. Phased rollout with parallel run option
4. Clear error messages and troubleshooting guides
5. Backup manual process during transition

---

## Next Steps

Based on workshop results:
1. ✅ Complete Business Requirements Document (BRD)
2. ✅ Obtain BRD approval from stakeholders
3. → Proceed to Analysis & Design phase
4. → Develop Functional Requirements Specification (FRS)
5. → Create detailed UI designs based on wireframes
6. → Define database schema
7. → Design integration enhancement

---

## Document Control

**Version History:**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | [Date] | [BA Name] | Initial draft after Workshop #1 |
| 0.2 | [Date] | [BA Name] | Added Workshop #2 results |
| 0.3 | [Date] | [BA Name] | Added Workshop #3 results |
| 1.0 | 2025-12-18 | [BA Name] | Added Workshop #4 results, finalized |

---

**END OF DOCUMENT**
