# Research Plan for Health Enrollment (1010) 1010EZR, October 2023

## Background
The Health Benefits Update Form (10-10EZR) is a new online version of a currently paper-only form. It's used to update personal, insurance, or financial information for Veterans currently enrolled in health care benefits. Most commonly, this looks like adding or removing a dependent or updating income information. We will be usability testing the MVP version of the new online form to ensure it meets the needs of VA.gov users. The form contains 4 sections, and for MVP, must be completed and submitted in its entirety to be processed.
The four main sections are:
- Veteran information
- Household financial information
- Insurance information
- Review
This MVP effort will go through the collaboration cycle and this study will happen post the midpoint review. 

### What problem is your product trying to solve?
Veterans who want to provide updates to their personal information for increasing or maintaining their health benefits are burdened with the manual processes of calling VA, mailing in a paper form and/or visiting a facility. This is driven by the lack of an online experience and pathway to provide these updates at a more convenient time and place for the Veteran. For Veterans who must provide these updates annually, the burden is multiplied. More information available in the [product outline - 10-10EZR Health Benefits Update form](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/application/va-application/EZ(R)%20Update%20Capabilities/10-10EZR%20Product%20Brief%20(standalone%20form).md)).

### Where is your product situated on VA.gov?
The product will live in the My Health section of VA.gov, but also be referenced by other static, informational pages on VA.gov, outside of the My Health section.

### What is Veterans’ familiarity with this tool?
This is a new product and form, although the first version of this form will be very similar to the 10-10EZ.

### OCTO Priorities 

The [OCTO objectives](https://github.com/department-of-veterans-affairs/va.gov-team/tree/master/strategy#readme) that this research supports are:

Increase 
- Completion rate of online transactions
- Usage of digital, self-service tools
- Percent of applications submitted online (vs. paper)
- Enhance Veterans’ personalized online experience
- Fast-track disability claims, starting with PACT Act claims


### Veteran Journey
This product fits into the [Veteran journey](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/platform/design/va-product-journey-maps/Veteran%20Journey%20Map.pdf) during the areas:

- Getting out
- Starting up
- Taking care of myself

## Research Goals	
- Goal 1: **Pre-filled information** - Test the usability of the prefilled form fields to see if Veterans understand what information needs to be updated, that the information is prefilled and information can be changed.
- Goal 2: **Financial information update** - Test the usability of the Household/financial information section of the form to see if Veterans understand what they need to provide since that section is never prefilled.
- Goal 3: **Financial information update notification** - Determine how a Veteran knows or would like to know they need to update the household/financial section.

### Outcome
These learnings will allow us to evaluate for additional gaps during the rollout of new form to production. The findings and recommendations will be categorized as to if there are any blockers and what can be addressed in future interations.

### Research questions
#### Goal 1: **Pre-filled information** - Test the usability of the prefilled form fields to see if Veterans understand what information needs to be updated, that the information is prefilled and information can be changed.

- Do participants understand that information is prefilled?
- Are the alerts about pre-filled information at the beginning of each section effective and understandable for participants?
- Do participants understand that they can change the information that's pre-filled?
- What is the impact on participants who need to update only one section of the form vs. more than one section of the form?

#### Goal 2: **Financial information update** - Test the usability of the household/financial information section of the form to see if Veterans understand what they need to provide since that section is never pre-filled.

- Do participants understand that they need to provide updated financial information?
- Do the participants understand the impact of not providing an update?
- Do the pariticipants struggle because this section isn't prefilled as opposed to other sections?

#### Goal 3: **Disability rating and financial updates** - Determine how disability ratings affect a Veteran's understanding of the financial updates section.

- How do participants approach the financial update section when they have a low disability rating (under 10 percent)?
- How do participants approach the financial update section when they have a high disability rating (above 50 percent)?
- How do participants want to be notified that they need to update their financial information?
- Do participants know what they need to do after encoutering the intro page on the form?
- Can participants find the landing page with more information, if prompted? 

### Hypothesis
- Participants will understand that information is prefilled and be able to update and submit the information.
- Participants may be frustrated if they want to only update one section of the form vs. multiple sections because they will have to go through the form linearly.
- Participants will understand they need to update financial information.
- Participants will understand how not providing an update to financial information will impact their benefits.
- Participants with a lower disability rating will be more familar with the need to keep financial information updated to keep their benefits.
- Participants will know what they need to do based on the intro page on the form.

## Methodology	
- Usability testing - appropriate for evaluative research
- User acceptance testing (UAT) - required before product release

### Location
- Remote, moderated via Zoom.

### Research materials
For moderated usability tests: 
- [Link to conversation guide](products/health-care/application/va-application/research/2023-10-EZR MVP Usability/conversation-guide.md)
- [Link to prototype](url goes here) TBD - either we will test on staging or potentially use a CodePen prototype.
- [Link to recruitment ticket]() TBD

## Recruitment	

### Recruitment approach
Our intended audience for this research are Veterans and we will be using and leveraging Perigean to recruit participants.

**Veterans: Requesting 10**

Which inclusive research strategies are you leveraging for this study? OCTO recommends using a lean maximum variation strategy for most studies. Refer to the resources above to learn more. Read this [introduction to inclusive research](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/teams/vsa/accessibility/research/introduction.md) and use the [recruitment checker (google sheets)](https://docs.google.com/spreadsheets/d/1pq7TSHZonfpzAQBJj6B2geGHlNUwZEs4DzEvxcRgu0o/edit?usp=sharing) to understand OCTO's targets for inclusivity.

### Recruitment criteria
List the total number and type (Veterans, caregivers, etc.) of participants for this study. 

**Primary criteria (must-haves)**
- All must be currently enrolled in VA health care benefits
- At least 2 are using a mobile device during the session
- A mix of disability ratings (from 10%-100%)
- Diverse mix of age ranges
- No more than 1 participant with a Bachelor's degree or higher
- At least 2 participants who are Black
- At least 2 participants who are Hispanic 

For all:
- Have you seen a healthcare provider in a VA medical center or other VA healthcare facility in the last 12 months? _Response options: yes or no (Answering yes would qualify the participant.)_
OR
- Are you currently enrolled in VA health care benefits? _Response options: yes or no (Answering yes would qualify the participant.)_

For recruiting 2 mobile users:
- Are you able to join the Zoom session from a smart phone such as a Samsung Galaxy or Apple iPhone? Any kind of smart phone will work, as long as it connects to the internet.  _Response options: yes or no (Answering yes would qualify the participant.)_

**Secondary criteria (nice-to-haves)**
What criteria would strengthen your results? 

## Timeline
Please submit artifacts for [Research Review](https://depo-platform-documentation.scrollhelp.site/collaboration-cycle/Research-review.1781891143.html) 8-9 days prior to the first planned research day for remote studies so Perigean can begin recruiting one week prior. Perigean requires 2+ weeks for in-person. 

### Prepare
When will the thing you are testing be finalized? Ideally it's ready a week before testing begins and has also been through a [Midpoint review](https://depo-platform-documentation.scrollhelp.site/collaboration-cycle/Midpoint-review.1781039167.html).

A pilot session is required. Please indicate the date and name of a mock participant for a pilot session. 
* Pilot participant email: TBD
* Date and time of pilot session: TBD

### Research sessions
* Planned dates of research: **November 6 - November 13**

### Length of sessions
* Session length: 1 hour
* Buffer time between sessions: 1 hour
* Maximum Sessions per day: 3

### Availability

| **Team Availability** | **Time (ET)** 	|
| --------------------- | --------------------- |
| November xx, 2023  	|  11am - 5pm ET 	|
| November xx, 2023   	|  11am - 5pm ET 	|
| November xx, 2023   	|  11am - 4pm ET 	|
| November xx, 2023   	|  10am - 4pm ET 	|
| November xx, 2023   	|  10am - 4pm ET 	|
| November xx, 2023  	|  11am - 5pm ET 	|
| November xx, 2023   	|  11am - 5pm ET 	|
| November xx, 2023   	|  11am - 4pm ET 	|
| November xx, 2023   	|  10am - 4pm ET 	|
| November xx, 2023   	|  10am - 4pm ET 	|

## Team Roles	
Please list the people who will be serving in each role. **Include the primary phone number for moderator and the emails for moderator, notetaker, accessibility specialist, and observers. If you need Perigean to take notes for you, indicate that next to Notetaker** 	
- Moderator: Katelyn Caillouet, Jessica Stump, Hieu Vo	
- Research guide writing and task development: Katelyn Caillouet (katelyn.caillouet@agile6.com)
- Participant recruiting & screening: Perigean	
- Project point of contact: Moderators
- Note-takers: Perigean, 10-10 Team
- Participant(s) for pilot test: TBD
- Accessibility specialist (for sessions where support for assistive technology may be needed):	
- Observers: TBD
