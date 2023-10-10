# Travel Reimbursement Discovery Findings 

## Landing Date

MVP Targeting Fall/Winter 2022


### Meetings & Decisions 
- [Meeting Notes](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/discovery/travel-reimbursement/meeting-notes.md)
- [Decision Register](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/discovery/travel-reimbursement/decision-register.md)

### Questions
- [Running List of Answers to Questions](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/discovery/travel-reimbursement/answers-to-questions.md)

### Research

#### Previous Research 
- [Final Presentation - 18F - VA Travel Reimbursement PA.pdf](https://github.com/department-of-veterans-affairs/va.gov-team/files/12822170/Final.Presentation.-.18F.-.VA.Travel.Reimbursement.PA.pdf)
- [Final Report - 18F Path Analysis on Beneficiary Travel Self-Service System (BTSSS).pdf](https://github.com/department-of-veterans-affairs/va.gov-team/files/12822171/Final.Report.-.18F.Path.Analysis.on.Beneficiary.Travel.Self-Service.System.BTSSS.pdf)
- [18F & VA Travel Reimbursement PA Mid-Point.pdf](https://github.com/department-of-veterans-affairs/va.gov-team/files/12822172/18F.VA.Travel.Reimbursement.PA.Mid-Point.pdf)

#### Primary Research Artifacts
- [Travel Reimbursement Findings from Interview with VA Bay Pines Healthcare System ](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/discovery/travel-reimbursement/bay-pines-interview-notes.md)<br>
- [Research Synthesis from Bay Pines (Mural)](https://app.mural.co/t/departmentofveteransaffairs9999/m/departmentofveteransaffairs9999/1677531778271/c07cb27bbf026415d07a1fc0ae39b972954ecf5c?sender=u37bb983bd3fc3cc00c7d3286)<br>
- [Travel Reimbursement Findings from Interview with VA Texas Valley Health Care](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/discovery/travel-reimbursement/tx-valley-interview-notes.md)
- [Research plan](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/research/veteran-facing/travel-reimbursement-mvp-remote-test/research-plan.md)<br>
- [Travel Reimbursement Veteran Remote Study Synthesis (Mural)](https://app.mural.co/t/departmentofveteransaffairs9999/m/departmentofveteransaffairs9999/1677531174556/4f4a8f04d34bde856e78d316e3b233b705714a3c?sender=u37bb983bd3fc3cc00c7d3286)
- [Research report (PDF)](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/research/veteran-facing/travel-reimbursement-mvp-remote-test/PCI%20Travel%20Reimbursement%20Research%20Report.pdf)
- [Research findings (Markdown)](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/checkin/research/veteran-facing/travel-reimbursement-mvp-remote-test/research-findings.md#recommendations)

### Design Artifacts
- [Initial user flow options (Sketch)](https://www.sketch.com/s/42a478e7-cb38-49e5-9500-9b21182873da/a/dlAA519)
- [Initial user flow diagrams for prototypes (Mural)](https://app.mural.co/t/vfscie8528/m/vfscie8528/1658844568873/93ba988aed6312d43533b8feaed365529b836332?sender=u83bc52d7fa73658f84f27755)
- [Prototype A](https://www.sketch.com/s/38819fc4-18ef-4958-a330-a699785301d6/prototype/a/3A3BBB6C-17C3-44B9-87A0-7C6B35EED3A1)
- [Prototype B](https://www.sketch.com/s/38819fc4-18ef-4958-a330-a699785301d6/prototype/a/79088E97-24E3-4453-99A2-2A982BA0D3FD)
- [Prototype C](https://www.sketch.com/s/38819fc4-18ef-4958-a330-a699785301d6/prototype/a/E31FD129-23BD-4CF3-AE44-8B1D88533FC6)
- [Prototype D (post-research study) (Sketch)](https://www.sketch.com/s/38819fc4-18ef-4958-a330-a699785301d6/prototype/a/1A834D3B-A6B1-4B5E-A0CB-9C11FF0238D5)
- [MVP Prototype (after Midpoint Review) (Abstract)](https://share.goabstract.com/3f25b4c0-4404-4079-a938-367f40c4903b)

## MVP Requirements 

- As a Veteran, During the check in flow, a Veteran can submit a claim for travel that is `round trip`, `mileage only` travel from their `home address` to the BTSSS system. 
- As a Veteran, I should be shown my Claim Number during check in so that I can track the claim in the BTSSS system. 
- As a Veteran, I should see this current claims list in the existing Travel Pay system. 
- As the Product team, we should able to track a claim through the whole system from end to end and determine `average time to paid`

## Current assumptions

- We are displaying the question for all users. 
- During the check in process, We have access to the Veterans ICN, the veterans home address and the facility address. 
- No staff facing enhancements are happening for MVP 
- Little flexibility in the BTSSS API, assumed  none until something is needed. 
- If a claim is submitted before an appoinment is checked out, the claim will go into manual review 

## Future Iterations Initiatives

- Asycnronous Claim Submission
- Veteran notifiction
- Performance Tweaks 
- Filter Eligilbity 
- Better feedback for veterans (textin/portal)
- Add more expenses to the claim
