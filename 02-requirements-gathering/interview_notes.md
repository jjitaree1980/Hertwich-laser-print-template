# Interview Notes
## Laser Print Template Layout Management System

**Project Name:** Laser Print Template Layout Management System
**Document Owner:** Business Analyst
**Version:** 1.0

---

## Interview Log

| Interview # | Date | Interviewee | Role | Duration | Interviewer | Status |
|-------------|------|-------------|------|----------|-------------|--------|
| INT-001 | [TBD] | [Name] | Production Manager | 90 min | [BA Name] | Scheduled |
| INT-002 | [TBD] | [Name] | Production Supervisor | 60 min | [BA Name] | Scheduled |
| INT-003 | [TBD] | [Name] | Production Operator 1 | 45 min | [BA Name] | Scheduled |
| INT-004 | [TBD] | [Name] | Production Operator 2 | 45 min | [BA Name] | Scheduled |
| INT-005 | [TBD] | [Name] | Kubal System Administrator | 90 min | [BA Name] | Scheduled |
| INT-006 | [TBD] | [Name] | Customer Service Manager | 60 min | [BA Name] | Scheduled |
| INT-007 | [TBD] | [Name] | Quality Assurance Manager | 60 min | [BA Name] | Scheduled |
| INT-008 | [TBD] | [Name] | Hertwich Technical Contact | 90 min | [BA Name] | Scheduled |

---

## Interview #INT-001: Production Manager

**Interviewee:** [Name]
**Role:** Production Manager
**Date:** [TBD]
**Time:** [TBD]
**Duration:** 90 minutes
**Location/Method:** [Meeting room / Video call]
**Interviewer:** [BA Name]
**Note Taker:** [Name]

### Objectives
- Understand high-level business needs for layout management
- Identify pain points in current process
- Define success criteria
- Understand customer landscape and requirements diversity

### Current Process

**Q: Can you walk me through the current process for laser printing on billets?**

A: [Interview response to be captured here]

**Key Points:**
- [Point 1]
- [Point 2]
- [Point 3]

**Q: How do you currently manage different customer requirements?**

A: [Response]

**Key Points:**
- [Manually check customer specifications]
- [Reference customer contracts or order notes]
- [Coordinate with Customer Service for clarification]

### Pain Points

**Q: What are the biggest challenges with the current approach?**

A: [Response]

**Identified Pain Points:**
1. [Manual process is time-consuming]
2. [Risk of human error in layout selection]
3. [Difficult to track which customers have which requirements]
4. [New customer onboarding is complex]
5. [No standardized process]

**Q: Can you estimate how much time is spent on layout configuration per batch?**

A: [Response - estimated XX minutes per batch]

**Q: How often do layout errors occur?**

A: [Response - estimated XX errors per month]

### Customer Requirements

**Q: How many different customers do we serve with unique layout requirements?**

A: [Response - approximately XX customers, of which YY have unique requirements]

**Q: Can you categorize the types of customer requirements?**

A: [Response]

**Customer Categories Identified:**
1. **Standard Layout:** [Description - e.g., "Logo, company name, charge number, alloy, QR code"]
2. **Minimal Layout:** [Description - e.g., "Only alloy name and batch number"]
3. **Detailed Layout:** [Description - e.g., "Standard plus unique ingot ID and length"]
4. **Custom Layout:** [Description - e.g., "Completely customized format"]

**Q: What information fields are currently available for printing?**

A: [Response]

**Data Fields Inventory:**
- Logo of aluminum company
- Company name
- Charge number
- Homogenization status
- Homogenization machine
- Alloy number
- QR code (containing: charge number, company code, alloy code, dimension, length, homogenization status)
- Unique ingot ID (for some customers)
- Length (for some customers)
- [Other fields identified...]

**Q: Are there any customers with very unusual requirements?**

A: [Response - examples]

### Integration with Hertwich

**Q: How does the current integration with Hertwich work?**

A: [Response]

**Key Points:**
- [Data sent via [method - file/API/manual entry]]
- [Hertwich manages the actual laser printing]
- [We hold the data in Kubal system]
- [Current format/protocol]

**Q: What are the limitations or constraints with Hertwich integration?**

A: [Response]

### Future State Vision

**Q: What would an ideal system look like?**

A: [Response]

**Desired Features:**
- [Automatic layout selection based on customer order]
- [Easy configuration for new customers]
- [Visual preview of layout before sending to Hertwich]
- [Audit trail of layouts sent]
- [Other features...]

**Q: What are the must-have features vs. nice-to-have?**

A: [Response]

**Must-Have:**
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

**Nice-to-Have:**
1. [Feature 1]
2. [Feature 2]

### Success Criteria

**Q: How will you measure success of this project?**

A: [Response]

**Success Metrics:**
- Zero layout errors
- Configuration time reduced by XX%
- Easy new customer onboarding (< XX minutes)
- Production team satisfaction
- [Other metrics...]

**Q: What are the key dates or business drivers?**

A: [Response - any specific deadlines, seasonal factors, customer pressures]

### Risks and Concerns

**Q: What concerns do you have about this project?**

A: [Response]

**Concerns Raised:**
- [Production disruption during implementation]
- [Training time for team]
- [System reliability]
- [Integration complexity]

**Q: What would make this project fail in your view?**

A: [Response]

### Stakeholders

**Q: Who else should we talk to for requirements?**

A: [Response]

**Recommended Stakeholders:**
- [Name/Role - Production Supervisor for detailed workflow]
- [Name/Role - Customer Service for customer-specific requirements]
- [Name/Role - Quality team for compliance requirements]

### Additional Notes

[Any other important points, observations, or context captured during interview]

### Action Items

| # | Action Item | Owner | Due Date | Status |
|---|-------------|-------|----------|--------|
| 1 | [Provide list of all customers with layout requirements] | Production Manager | [Date] | Open |
| 2 | [Share example of customer contract showing layout specs] | Production Manager | [Date] | Open |
| 3 | [Arrange meeting with Hertwich contact] | Production Manager | [Date] | Open |

### Follow-up Questions

1. [Question that came up during interview requiring research]
2. [Clarification needed on specific point]

---

## Interview #INT-002: Production Supervisor

**Interviewee:** [Name]
**Role:** Production Supervisor
**Date:** [TBD]
**Time:** [TBD]
**Duration:** 60 minutes
**Location/Method:** [Meeting room / Video call]
**Interviewer:** [BA Name]

### Objectives
- Understand detailed workflow for laser print layout selection
- Identify step-by-step process
- Understand operator challenges
- Gather specific examples of errors or issues

### Detailed Workflow

**Q: Can you walk me step-by-step through how you prepare a batch for laser printing?**

A: [Response]

**Current Workflow Steps:**
1. [Step 1 - e.g., "Receive production order"]
2. [Step 2 - e.g., "Check customer name in order"]
3. [Step 3 - e.g., "Look up customer requirements in [location]"]
4. [Step 4 - e.g., "Manually configure layout"]
5. [Step 5 - e.g., "Send data to Hertwich"]
6. [Step 6 - e.g., "Verify first billet print"]

**Q: Where do you find customer layout requirements currently?**

A: [Response - spreadsheet, document, email, verbal knowledge?]

**Q: How long does this process typically take?**

A: [Response]

**Time Breakdown:**
- Looking up customer requirements: [XX min]
- Configuring layout: [XX min]
- Sending to Hertwich: [XX min]
- Verification: [XX min]
- **Total:** [XX min per batch]

### Error Scenarios

**Q: Can you describe a recent error or issue related to laser printing layouts?**

A: [Response - specific example]

**Example Error Case:**
- **What happened:** [Description]
- **Root cause:** [Why it happened]
- **Impact:** [What was the consequence]
- **How resolved:** [How it was fixed]
- **Prevention:** [How to prevent in future]

**Q: What are the most common types of errors?**

A: [Response]

**Common Errors:**
1. [Error type 1 - e.g., "Wrong data field included"]
2. [Error type 2 - e.g., "Forgot custom field for specific customer"]
3. [Error type 3 - e.g., "Used old customer requirements"]

### Data and Systems

**Q: What information do you need from Kubal system for laser printing?**

A: [Response]

**Data Requirements:**
- [Data field 1 and where it comes from in Kubal]
- [Data field 2 and where it comes from in Kubal]
- [Data field 3...]

**Q: Are there any data quality issues?**

A: [Response]

**Q: How do you handle special characters or formatting in data?**

A: [Response]

### New Customer Onboarding

**Q: What happens when a new customer comes in with specific layout requirements?**

A: [Response]

**Onboarding Process:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Q: How are new requirements documented and communicated?**

A: [Response]

### User Needs

**Q: What would make your job easier regarding layout management?**

A: [Response]

**Supervisor Needs:**
1. [Need 1]
2. [Need 2]
3. [Need 3]

**Q: What features or capabilities would you like to see?**

A: [Response]

**Q: How comfortable is your team with new systems?**

A: [Response - technology adoption readiness]

### Additional Notes

[Any other important points captured during interview]

### Action Items

| # | Action Item | Owner | Due Date | Status |
|---|-------------|-------|----------|--------|
| 1 | [Provide current customer requirements reference document] | Production Supervisor | [Date] | Open |
| 2 | [Share example production order] | Production Supervisor | [Date] | Open |

---

## Interview #INT-005: Kubal System Administrator

**Interviewee:** [Name]
**Role:** Kubal System Administrator
**Date:** [TBD]
**Time:** [TBD]
**Duration:** 90 minutes
**Location/Method:** [Meeting room / Video call]
**Interviewer:** [BA Name]

### Objectives
- Understand Kubal system architecture
- Identify data structures and availability
- Assess technical feasibility
- Define integration approach

### System Architecture

**Q: Can you give an overview of the Kubal system architecture?**

A: [Response]

**Key Points:**
- [System type - ERP, custom, etc.]
- [Database type]
- [Key modules]
- [Integration capabilities]

**Q: Where is production data stored in Kubal?**

A: [Response - database tables, structure]

**Relevant Data Tables:**
- [Table 1 - e.g., "Production_Orders"]
- [Table 2 - e.g., "Customers"]
- [Table 3 - e.g., "Products"]
- [Table 4...]

### Current Data Availability

**Q: What data fields are currently available in Kubal related to laser printing?**

A: [Response]

**Available Fields:**

| Field Name | Table/Location | Data Type | Example Value | Notes |
|------------|----------------|-----------|---------------|-------|
| Charge Number | [Table] | [Type] | "CH-12345" | |
| Company Name | [Table] | [Type] | "Acme Corp" | |
| Alloy Number | [Table] | [Type] | "6061" | |
| Homogenization Status | [Table] | [Type] | "Complete" | |
| [Field...] | | | | |

**Q: Are there any fields that would need to be added?**

A: [Response]

**New Fields Needed:**
- [Customer layout preference flag]
- [Layout template ID]
- [Other fields...]

### Current Hertwich Integration

**Q: How does Kubal currently send data to Hertwich system?**

A: [Response]

**Integration Details:**
- **Method:** [File transfer / API / Database link / Manual export]
- **Frequency:** [Real-time / Batch / On-demand]
- **Data Format:** [CSV / XML / JSON / Custom]
- **Protocol:** [FTP / HTTP / Database connection]

**Q: Can you show me a sample of data sent to Hertwich?**

A: [Response - sample file or format]

**Q: Are there any integration issues or limitations?**

A: [Response]

### Technical Feasibility

**Q: Is it feasible to add customer configuration tables to Kubal database?**

A: [Response]

**Q: What are the constraints or limitations we need to consider?**

A: [Response]

**Constraints:**
- [Database size limits]
- [Performance considerations]
- [Security requirements]
- [Backup/recovery procedures]

**Q: Can Kubal support dynamic layout configuration?**

A: [Response - technical approach discussion]

### Proposed Solution Discussion

**Q: [Present initial technical approach] - Is this feasible?**

A: [Response - feedback on approach]

**Technical Recommendations:**
- [Recommendation 1]
- [Recommendation 2]
- [Recommendation 3]

### Development and Testing

**Q: What environments are available for development and testing?**

A: [Response]

**Environments:**
- Development: [Details]
- Test: [Details]
- UAT: [Details]
- Production: [Details]

**Q: What is the deployment process for Kubal changes?**

A: [Response - deployment procedures, windows, approvals needed]

### Additional Notes

[Technical diagrams, screenshots, or other important information]

### Action Items

| # | Action Item | Owner | Due Date | Status |
|---|-------------|-------|----------|--------|
| 1 | [Provide database schema for relevant tables] | System Admin | [Date] | Open |
| 2 | [Share sample data export to Hertwich] | System Admin | [Date] | Open |
| 3 | [Set up access to development environment for BA/developers] | System Admin | [Date] | Open |

---

## Interview #INT-008: Hertwich Technical Contact

**Interviewee:** [Name - Hertwich]
**Role:** Hertwich Technical Contact
**Date:** [TBD]
**Time:** [TBD]
**Duration:** 90 minutes
**Location/Method:** Video call
**Interviewer:** [BA Name]
**Also attending:** [Technical Lead Name]

### Objectives
- Understand Hertwich system capabilities
- Define integration requirements
- Identify constraints and limitations
- Establish collaboration approach

### Hertwich System Overview

**Q: Can you explain how the laser printing system works?**

A: [Response]

**Q: What data do you currently receive from Kubal?**

A: [Response]

**Current Data Received:**
- [Data field 1]
- [Data field 2]
- [Data field 3...]

**Q: How is the data currently formatted?**

A: [Response - file format, structure, samples]

### Layout Capabilities

**Q: How flexible is the laser printing system for different layouts?**

A: [Response]

**Q: Are there any limitations on what can be printed or how it can be arranged?**

A: [Response]

**Constraints:**
- [Maximum characters per line]
- [Number of lines]
- [QR code size/position constraints]
- [Font limitations]
- [Other constraints...]

**Q: Can the system handle variable layouts per customer?**

A: [Response]

### Integration Requirements

**Q: What changes would be needed on Hertwich side to support customer-specific layouts?**

A: [Response]

**Hertwich Changes:**
- [Change 1 - if any]
- [Change 2 - if any]
- Or: No changes needed, can be handled through data format

**Q: What is the best way to specify layout information in the data feed?**

A: [Response - format recommendations]

**Recommended Approach:**
- [Layout specification method]
- [Data structure]
- [Examples]

**Q: Do you support layout templates or configuration files?**

A: [Response]

### Testing and Validation

**Q: How can we test integration changes without affecting production?**

A: [Response]

**Test Approach:**
- [Test environment availability]
- [Sample data approach]
- [Validation procedures]

**Q: What is your availability for integration testing?**

A: [Response - timing, contact person, process]

### Timeline and Constraints

**Q: Are there any planned changes or maintenance windows for Hertwich system?**

A: [Response]

**Q: What lead time do you need for any changes on your side?**

A: [Response]

**Q: What are your business constraints or peak periods we should avoid?**

A: [Response]

### Support and Communication

**Q: Who will be our primary contact for this integration project?**

A: [Response - contact details]

**Q: What is the best way to communicate technical questions?**

A: [Response - email, ticketing system, phone, etc.]

**Q: What documentation can you provide?**

A: [Response]

**Documentation Available:**
- [Integration specification]
- [API documentation]
- [File format specification]
- [Other docs...]

### Additional Notes

[Any other important points or technical details]

### Action Items

| # | Action Item | Owner | Due Date | Status |
|---|-------------|-------|----------|--------|
| 1 | [Provide current integration specification document] | Hertwich | [Date] | Open |
| 2 | [Share sample layout configuration files] | Hertwich | [Date] | Open |
| 3 | [Set up test environment access] | Hertwich | [Date] | Open |
| 4 | [Schedule technical deep-dive session] | Both teams | [Date] | Open |

---

## [Additional Interview Templates]

_Use the above template format for remaining interviews: INT-003, INT-004, INT-006, INT-007_

**Note:** Each interview should be documented in similar detail with:
- Objectives
- Questions and responses
- Key findings
- Action items
- Follow-up needs

---

## Interview Summary and Key Findings

### Overall Themes

**Pain Points Identified Across Interviews:**
1. [Theme 1 - e.g., "Manual process is major inefficiency"]
2. [Theme 2 - e.g., "No centralized customer requirements repository"]
3. [Theme 3 - e.g., "Error risk due to human factors"]
4. [Theme 4...]

### Requirements Emerging from Interviews

**High-Priority Requirements:**
1. [Requirement derived from interviews]
2. [Requirement derived from interviews]
3. [Requirement derived from interviews]

**Technical Insights:**
- [Technical finding 1]
- [Technical finding 2]

**Business Insights:**
- [Business finding 1]
- [Business finding 2]

### Stakeholder Alignment

**Areas of Agreement:**
- [Point of agreement across stakeholders]
- [Point of agreement across stakeholders]

**Areas of Divergence:**
- [Conflicting view or requirement - needs resolution]
- [Conflicting view or requirement - needs resolution]

### Next Steps

1. [Consolidate requirements from all interviews]
2. [Schedule validation workshop with key stakeholders]
3. [Document Business Requirements Document (BRD)]
4. [Follow up on all action items]

---

## Document Control

**Version History:**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-18 | [BA Name] | Initial template creation |
| 1.1 | [Date] | [BA Name] | Added INT-001 interview notes |
| 1.2 | [Date] | [BA Name] | Added INT-002 interview notes |

**Reminder:** Update this document after each interview is conducted.

---

**END OF DOCUMENT**
