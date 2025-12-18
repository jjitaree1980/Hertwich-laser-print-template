# Interview Questions Template
## Laser Print Template Layout Management System

**Document Owner:** Business Analyst
**Version:** 1.0
**Date:** 2025-12-18

---

## Interview Preparation Checklist

Before each interview:
- ☐ Review stakeholder's role and background
- ☐ Customize questions to stakeholder's perspective
- ☐ Schedule 60-90 minutes
- ☐ Send agenda 24 hours in advance
- ☐ Prepare note-taking method
- ☐ Review project charter and scope
- ☐ Prepare any visual aids or examples

---

## General Opening Questions (All Stakeholders)

1. Can you describe your role and responsibilities related to the laser printing process?
2. How long have you been in this role?
3. What is your understanding of this project?
4. What are your expectations for this project?

---

## Questions for Production Manager

### Current State
1. Can you walk me through the current laser print layout management process from start to finish?
2. How many production batches do you process per day/week/month?
3. How do you currently track which customers have which layout requirements?
4. Where are customer layout requirements documented today?

### Pain Points
5. What are the biggest challenges with the current approach?
6. Approximately how much time is spent on layout configuration per batch?
7. How often do layout errors occur? What's the typical impact?
8. Can you describe a recent error or issue? What was the root cause?
9. What happens when you get a new customer with specific requirements?

### Customer Landscape
10. How many different customers do you serve?
11. How many of those have unique layout requirements?
12. Can you categorize the types of customer requirements? (e.g., standard, minimal, detailed)
13. What information fields are currently available for laser printing?
14. What's the most unusual or complex customer requirement you've encountered?

### Future State
15. What would an ideal solution look like from your perspective?
16. What features are absolutely essential (must-have)?
17. What features would be nice to have but not critical?
18. How will you measure success of this project?
19. What are your concerns or risks about this project?

### Timeline and Resources
20. Are there any critical dates or deadlines we should be aware of?
21. Who from your team can participate in requirements workshops and testing?
22. Are there any seasonal factors or busy periods we should avoid?

---

## Questions for Production Supervisor / Operators

### Detailed Workflow
1. Can you walk me step-by-step through how you prepare a batch for laser printing?
2. How do you know which layout to use for a specific customer?
3. Where do you look up customer requirements?
4. What systems or tools do you use in this process?
5. How long does each step typically take?

### Data and Systems
6. What information do you need from the Kubal system?
7. Are there any data quality issues or missing data you encounter?
8. How do you handle special characters or formatting in the data?
9. How is data sent to Hertwich currently?

### Error Scenarios
10. What types of errors are most common?
11. Can you describe a recent error? How was it discovered and resolved?
12. How do you verify the layout is correct before printing?
13. What happens if an error is discovered after printing?

### User Needs
14. What would make your job easier regarding layout management?
15. What frustrates you most about the current process?
16. How comfortable are you with learning new systems/software?
17. What features or capabilities would you like to see in a new system?
18. How do you prefer to be trained on new systems?

### New Customer Onboarding
19. What happens when a new customer is added? Who communicates the requirements?
20. How are new requirements documented and shared with the team?
21. How long does it typically take to onboard a new customer?

---

## Questions for Kubal System Administrator

### System Architecture
1. Can you provide an overview of the Kubal system architecture?
2. What database system does Kubal use?
3. Where is production and customer data stored in Kubal?
4. What are the key tables and data structures related to production orders?

### Data Availability
5. What data fields are currently available in Kubal related to laser printing?
6. Are there any fields that would need to be added to support this project?
7. How is customer information currently stored and managed?
8. What is the data model for production orders?

### Current Integration
9. How does Kubal currently integrate with the Hertwich system?
10. What is the data exchange method? (API, file transfer, database, manual)
11. What is the data format sent to Hertwich?
12. Can you provide a sample of data sent to Hertwich?
13. Are there any integration issues or limitations?
14. How is the integration monitored?

### Technical Feasibility
15. Is it feasible to add new tables to the Kubal database for layout configuration?
16. What are the constraints or limitations we need to consider?
17. Can Kubal support dynamic configuration-based data extraction?
18. What is the database size and performance capability?
19. Are there any security requirements we need to follow?

### Development and Testing
20. What environments are available? (Dev, Test, UAT, Prod)
21. What is the deployment process for Kubal changes?
22. What testing is required before production deployment?
23. What is the change management process?
24. Are there any planned system upgrades or changes?

### Integration Recommendations
25. What approach would you recommend for implementing this functionality?
26. Are there any existing similar features in Kubal we can leverage?
27. What documentation is available for Kubal database and APIs?

---

## Questions for Customer Service Manager

### Customer Requirements
1. How do you currently capture customer layout requirements?
2. Where do these requirements typically come from? (Contracts, verbal, email?)
3. How are customer requirements communicated to the production team?
4. How often do customer requirements change?
5. Do you have a process for documenting customer-specific needs?

### Customer Landscape
6. Can you provide examples of different customer layout requirements?
7. Which customers have the most complex requirements?
8. Are there any patterns or commonalities in customer requirements?
9. How many new customers are onboarded per month/year?

### Process Improvement
10. What challenges do you face in managing customer requirements today?
11. How would you like to see customer requirements managed in the future?
12. Would you need access to configure customer layouts yourself?
13. How should requirement changes be handled?

---

## Questions for Quality Assurance Manager

### Quality Requirements
1. What quality standards apply to laser printing?
2. What is the current quality verification process?
3. How are layout errors detected?
4. What is the impact of a layout error on quality?

### Approval and Validation
5. Should new or modified customer layouts require QA approval?
6. What validation should be performed before a layout is used in production?
7. What audit or traceability requirements exist?
8. How long should layout configuration history be retained?

### Testing
9. What testing would you recommend for this new system?
10. What acceptance criteria should be met before go-live?
11. How should we validate that layouts are correct?
12. What UAT involvement would you like from QA team?

---

## Questions for Hertwich Technical Contact

### System Capabilities
1. Can you explain how the Hertwich laser printing system works?
2. What data do you currently receive from our Kubal system?
3. How is the data currently formatted?
4. What is the integration protocol or method?

### Layout Flexibility
5. How flexible is the laser printing system for different layouts?
6. Are there limitations on what can be printed or how it can be arranged?
7. Can the system handle variable layouts per customer?
8. What are the constraints? (character limits, lines, formatting, etc.)

### Integration Changes
9. What changes would be needed on Hertwich side to support customer-specific layouts?
10. What is the best way to specify layout configuration in the data feed?
11. Do you support layout templates or configuration files?
12. Can you provide integration specifications or API documentation?

### Testing and Timeline
13. How can we test integration changes without affecting production?
14. What is your availability for integration testing?
15. What lead time do you need for any changes on your side?
16. Are there any planned maintenance or upgrades we should know about?

### Support
17. Who will be our primary contact for integration questions?
18. What documentation can you provide?
19. What are your business constraints or peak periods we should avoid?

---

## Closing Questions (All Stakeholders)

1. Is there anything else you think we should know?
2. Are there any other stakeholders we should speak with?
3. Do you have any questions for me?
4. Can we follow up with you if we have additional questions?
5. Would you be willing to review the requirements once documented?

---

## Interview Best Practices

**During the Interview:**
- Start with easier, general questions to build rapport
- Use open-ended questions to encourage detailed responses
- Listen actively and take thorough notes
- Ask follow-up questions for clarification
- Capture specific examples and quantifiable data
- Note any documents or artifacts mentioned
- Confirm understanding by summarizing key points

**After the Interview:**
- Document notes within 24 hours while fresh
- Identify action items and follow-ups
- Share summary with interviewee for validation
- Extract requirements and add to requirements register
- Follow up on any requested documents or information

---

## Interview Notes Template

**Interviewee:** [Name]
**Role:** [Title]
**Date:** [Date]
**Time:** [Time]
**Duration:** [Duration]
**Interviewer:** [Your Name]
**Note Taker:** [Name if different]

### Key Points Captured
- [Point 1]
- [Point 2]

### Requirements Identified
- [Requirement 1]
- [Requirement 2]

### Pain Points
- [Pain point 1]
- [Pain point 2]

### Action Items
| Action | Owner | Due Date |
|--------|-------|----------|
| [Item] | [Name] | [Date] |

### Follow-up Questions
- [Question 1]

---

**END OF DOCUMENT**
