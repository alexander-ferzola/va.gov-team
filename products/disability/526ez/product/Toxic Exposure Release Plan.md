
<!-- markdownlint-disable MD024 -->
# Release Plan: 526 Toxic Exposure [DRAFT]

# Purpose
The purpose of this document is to describe and align development teams and stakeholders on what will be delivered and when. It describes the features, enhancements, and fixes that will be included in each Toxic Exposure (TE) release along with identified timelines. It is a living document and serves as a communication tool for keeping stakeholders informed about the progress of TE.

# Background
In 2022, The Sergeant First Class Heath Robinson Promise to Address Comprehensive Toxics (PACT) Act was signed into law. The PACT Act is a new law that expands VA health care and benefits for Veterans exposed to burn pits and other toxic substances. This law helps the VA provide generations of Veterans—and their survivors— with the care and benefits they’ve earned and deserve.

The PACT Act 
* Expands and extends eligibility for VA health care for Veterans with toxic exposures and Veterans of the Vietnam, Gulf War, and post-9/11 eras
* Adds 20+ more presumptive conditions for burn pits, Agent Orange, and other toxic exposures
* Adds more presumptive-exposure locations for Agent Orange and radiation
* Requires VA to provide a toxic exposure screening to every Veteran enrolled in VA health care
* Helps us improve research, staff education, and treatment related to toxic exposures

Today, while Veterans can file disability compensation for conditions believed to be caused by toxic exposure on the paper version of the 21-526ez, they’re not able to file a TE claim at va.gov. This creates an unnecessary burden for the Veteran, who may have mental, physical, or other environmental challenges or disabilities that prevent or otherwise make it difficult for them to file a claim using the paper version of the 526 form.

# Overview
To make it easy for Veterans to file disability compensation claims resulting from the PACT Act via va.gov, we are adding a toxic exposure section to the 21-526ez Veterans Disability Compensation and Related Compensation Benefits form on VA.gov. This change brings the digital form at VA.gov into parity with the 526ez paper form on these exposure questions, and will enable Veterans to specify aspects of their service history that might qualify them for disability benefits related to toxic exposure.

Veterans will be able to complete the paper form equivalent of Section IV; questions 15a-15e 
- 15a: "Are you claiming any conditions related to toxic exposures?
- 15b: "Did you serve in any of the following gulf war hazard locations?"
- 15c: "Did you serve in any of the following Herbicide locations?"
- 15d: "Have you been exposed to any of the following?" and;
- 15e: "If you were exposed multuiple times, please provide all additional dates and locations of potential exposure."

We expect this change to:

[relative to form 526]: #

- Bring the online 526 form into compliance by being up to date with the 2022 paper form
- Reduce the number of letters sent to Veterans with requests for more information
- Reduce the amount of time to determine if the applicant is elegible for presumptive service connection based on toxic exposure
- Mantain or reduce abandonment rates

[relative to form EVSS to Lighthouse]: #

- Sucessfully migrate 526 submission infrastructure off EVSS
- Reduce or maintain existing submission errors
- Maintain % of submissions that use normal path
- Maintain or reduce uses of backup and failsafe path

Release plan user flow (coming soon).

## New Capabilities and Changes
In addition to adding TE sections to the digital form, this release also includes the following changes:

1. Migration of the EVSS submit endpoint to Lighthouse
2. Migration of the /generatePDF endpoint to Lighthouse for the backup submission path 
3. User Interface notifications for Veterans who have an IPF
4. A new checkbox and loop pattern for the Veteran-facing form logic
5. Transformation of the vets-website JSON data structure to be compatible with Lighthouse
6. Implementation of a Flipper feature flag that controls access to the TE feature
7. Handling of multiple exposures data to populate on the PDF in 15e
10. Implementation of updated logic for the new Lighthouse /submit endpoint

## Risks & Challenges
1. DBEX teams have developed this solution with the assumption that Lighthouse's Submit endpoint will be used for the production deployment of TE. If the Lighthouse /submit endpoint isn’t available by the end of June, DBEX teams will not re-pipe the TE solution to use EVSS async Submit endpoint. VA’s expectation is that TE solution is complete and ready by end of June. TE will leverage LH’s Submit endpoint when it's released into production.

## Use Cases
There are two use cases that we are considering for this release. For each, we plan to follow an incremental release strategy using established traffic percentages to incrementally route Veterans to the 526 form. We plan to use Flipper to control availabity for each use case. As Flipper controls access to the new form (via a conditional flag) the moment a Veteran starts a new claim, Veterans with an active session will not be directed to the new form.

### 1. New Applications
- Veterans who begin a new 526 form will be directed to complete the 2022 version of the 526 form, including the new Toxic Exposure section. These Veterans will not have an IPF, and may or may not have a previous Intent To File (ITF). Exact traffic targets have yet to be determined.

### 2. Veterans With an In Progress Form
- Veterans who have a 526 form in progress will be directed to complete the 2022 version of the 526 form, including the new Toxic Exposure section. Unlike New Applications, these Veterans will have an IPF and an ITF. Exact traffic targets have yet to be determined. 


## Timelines and Activities

| Phase | Milestone | Target Dates | Notes |
|---|---|---|---|
|1 |Gulf War exposures|May 21, 2024|On Track|
|2 |Herbicide & Hazards|June 04 2024|
|3 |Launch Preparation|June 18 2024|
|4 |New TE Applications|June 27 - 27 2024|
|5 |Veterans with an IPF|TBD||

# Release Process


| Phase | Description | Flipper Status | Form in Progress | Visible Form |
|---|---|---|---|---|
|4 | New TE Applications |On | No | 2022 |
|5 | Veterans with an IPF |On | Yes | 2022 |


 
1. Canary launch for LH Submit endpoint
2. Canary launch for LH generatePDF
3. Staggered live prod release of Submit for N Veterans
4. Monitor DD for errors & issues
5. if this goes well...
6. enable FF for TE for Veterans without an IPF
7. test in staging env before it goes to prod in daily deploy
8. let 10 records come through
9. turn it off, and inspect the data to ensure it's working
10. if it works
11. we continue incremental plan for the staggered release
12. 20%, 30%, 40%, etc.

POST
1. add TE pages to Google analytics in Domo (can we do this sooner?)
2. look at the count of sucessfull claim submissions




## Step 1: Development

[use this section to name the pieces of code we are touching and new capabilities we're delivering]

You'll need to create a feature toggle (or two) for any moderately or significantly changing feature. Follow the [best practices for creating feature toggles](https://depo-platform-documentation.scrollhelp.site/developer-docs/feature-toggles).


| Toggle name | Description |
| ----------- | ----------- |
| disability_526_toxic_exposure | Enables new pages, processing, and submission of toxic exposure claims |

## Step 2: Validation

Since we use a [continuous delivery](https://depo-platform-documentation.scrollhelp.site/developer-docs/deployment-process) model, once code is in the `main` branch, it will be deployed that day. 

Before enabling your feature toggle in production, you'll need to:

- [ ] Follow [best practices for QA](https://depo-platform-documentation.scrollhelp.site/developer-docs/qa-and-accessibility-testing).
- [ ] Have your team perform as much validation in staging as possible. Validation may be challenging for some teams and systems due to downstream requirements, but the staging system should mimic the production system as much as possible.
- [ ] Work any downstream or dependant systems proactively to ensure that the feature is ready for use once it hits production.
- [ ] Have a go/no go meeting with the team to ensure that the feature is ready for use and signed off by each discipline and your DEPO/OCTO contact. During this meeting, you'll need to:
  - [ ] review the plan with your DEPO/OCTO representative.
  - [ ] review the release plan with your team.

## Step 3: Production rollout
<!--
### Do I need a staged rollout?

**Yes**, a staged rollout is required unless you can confidently answer "yes" to all of the following:

- This change does not add substantial new functionality to VA.gov
- This change does not impact user flows through tasks
- This change does not affect traffic to backend services

*Example*: a change to a page's text content **could skip** staged rollout

*Example*: a minor visual redesign to a page that doesn't affect user flows **could skip** staged rollout

*Example*: adding a new field to an existing form **could skip** staged rollout

*Example*: a new feature on an existing application that creates new backend traffic **needs staged rollout**

*Example*: a significant change to how users navigate an existing form **needs staged rollout**

*Example*: a feature that will route significantly more users (and therefore more backend traffic) to an existing application **needs staged rollout**

#### Exceptions

Currently, [feature toggles](https://department-of-veterans-affairs.github.io/veteran-facing-services-tools/platform/tools/feature-toggles/) are the primary tool VSP provides for facilitating staged rollout. If feature toggles don't work for your use case, you can request an exception from staged rollout in Staging Review.

| Feature type | Possible with feature toggles? |
| --- | --- |
| New feature in existing application | Yes |
| New application | Yes |
| Static content changes | Doable but tricky |
| URL redirects | No |

DEPO VSP / OCTO leads can approve other exceptions to this requirement.
-->

### Define the Rollback process

Our PM and PO will monitor analytics. If something goes wrong, the engineering team will be on standby to disable the flippers and fall back to v1 of the form.

Rollback plan:
1. Team will monitor analytics for issues (failed submissions, traffic irregularies, unexpected errors).
2. Engineering disables flipper which hides the 2022 version of the form.
   - Users with in-progress v2022 sessions will finish out their v2022 session. If they start a new session, they will be redirected to the old version.
   - New users will be directed to the old of the form.

### Phase I: moderated production testing (also known as User Acceptance Testing, or UAT)
Production testing poses a risk, due to the downstream actions that submitting an application for disability benefits triggers. To migtigate the risk this poses, we will be doing extensive E2E testing in a staging environment.

#### Planning

- Desired date range or test duration: TBD
- Desired number of users: TBD
- How you'll recruit the right production test users: TBD
- How you'll conduct the testing: TBD
- How you'll give the test users access to the product in production w/o making it live on VA.gov: TBD

#### Results

- Number of users: TBD
- Number of bugs identified / fixed: TBD
- Was any downstream service affected by the change?: TBD
- Types of errors logged: TBD
- Any changes necessary based on the logs, feedback on user challenges, or VA challenges? [PICK_ONE]: TBD
- If yes, what: TBD

### Phase II: Staged Rollout (also known as unmoderated production testing)

We recommend that the rollout plan has X stages, each increasing the number of Veterans. This plan is a strongly recommended guideline but should only be deviated for precise reasons.

#### Rollout Planning

- Desired date range: TBD
- How will you make the product available in production while limiting the number of users who can find/access it: Flipper
- What metrics-based criteria will you look at before advancing rollout to the next stage ("success criteria")?:
  - Abandonment rate:
  - Submission volume:
  - Error rate: 
  - Pageviews
- Links to the dashboard(s) showing "success criteria" metrics:
  - TBD
- Who is monitoring the dashboard(s)?: DBEX Teams 1 and 2


### Stage A: Canary

*Test a small Veteran population to ensure any obvious bugs/edge cases are found.*

#### Planning

- Length of time: TBD
- Percentage of Users (and roughly how many users do you expect this to be): TBD

#### Results

- Number of unique users: TBD
- Metrics at this stage (per your "success criteria"): [FILL_IN] a list that includes KPIs listed in the [Rollout Planning](#rollout-planning) section
- Was any downstream service affected by the change?: No
- Types of errors logged:
  -  TBD
- What changes (if any) are necessarily based on the logs, feedback on user challenges, or VA challenges? TBD

### Stage B: X% of users

*Test a larger user population to ensure larger usage patterns expose no issues.*

#### Planning

- Length of time: TBD
- Percentage of Users (and roughly how many users do you expect this to be): TBD

#### Results

- Number of unique users: TBD
- Metrics at this stage (per your "success criteria"): [FILL_IN] a list that includes KPIs listed in the [Rollout Planning](#rollout-planning) section
- Was any downstream service affected by the change?: [PICK_ONE]: TBD
- Types of errors logged:
   - TBD
- What changes (if any) are necessarily based on the logs, feedback on user challenges, or VA challenges? TBD

### Stage C: X% of users

*Test a larger user population to ensure larger usage patterns expose no issues.*

#### Planning

- Length of time: TBD
- Percentage of Users (and roughly how many users do you expect this to be): TBD

#### Results

- Number of unique users: [FILL_IN]
- Metrics at this stage (per your "success criteria"): [FILL_IN] a list that includes KPIs listed in the [Rollout Planning](#rollout-planning) section
- Was any downstream service affected by the change?: [PICK_ONE]: TBD
- Types of errors logged:
   - TBD
- What changes (if any) are necessarily based on the logs, feedback on user challenges, or VA challenges? TBD

### Stage D: X% of users

*Test a larger user population to ensure larger usage patterns expose no issues.*

#### Planning

- Length of time: TBD
- Percentage of Users (and roughly how many users do you expect this to be): TBD

#### Results

- Number of unique users: [FILL_IN]
- Metrics at this stage (per your "success criteria"): [FILL_IN] a list that includes KPIs listed in the [Rollout Planning](#rollout-planning) section
- Was any downstream service affected by the change?: [PICK_ONE]: yes | no |  N/A
- Types of errors logged: [FILL_IN]
- What changes (if any) are necessarily based on the logs, feedback on user challenges, or VA challenges? [FILL_IN]

### Stage E: 100% of users

#### Planning

- Length of time: TBD
- Percentage of Users (and roughly how many users do you expect this to be): 100%

#### Results

- Number of unique users: [FILL_IN]
- Metrics at this stage (per your "success criteria"): [FILL_IN] a list that includes KPIs listed in the [Rollout Planning](#rollout-planning) section
- Was any downstream service affected by the change?: [PICK_ONE]: yes | no |  N/A
- Types of errors logged: [FILL_IN]
- What changes (if any) are necessarily based on the logs, feedback on user challenges, or VA challenges? [FILL_IN]

## Post Launch metrics

Continue to check in on the KPIs of your feature at periodic intervals to ensure everything is working as expected. We recommend one-week and one-month check-ins, but this is only minimal.

### 1-week results

- Number of unique users:
- Error rate:
- Abandonment rate:
- Time to complete:
- Sessions to complete
- Any issues with VA handling/processing?:  [PICK_ONE]: yes | no |  N/A
- Types of errors logged: [FILL_IN]
- Any changes necessary based on the logs, feedback on user challenges, or VA challenges? [PICK_ONE]: yes | no |  N/A
- If yes, what: [FILL_IN]

### 1-month results

- Number of unique users: [FILL_IN]
- Error rate:
- Abandonment rate:
- Time to complete:
- Sessions to complete
- Any issues with VA handling/processing?: [PICK_ONE]: yes | no |  N/A
- Types of errors logged: [FILL_IN]
- Any UX changes necessary based on the logs, feedback on user challenges, or VA challenges? [PICK_ONE]: yes | no |  N/A
- If yes, what: [FILL_IN]

## Post-launch Questions

*To be completed once you have gathered your initial set of data, as outlined above.*

1. How do the KPIs you gathered compare to your pre-launch definition(s) of "success"?
1. What qualitative feedback have you gathered from users or other stakeholders?
1. Which assumptions you listed in your product outline were/were not validated?
1. How might your product evolve now or in the future based on these results?
1. What technical tasks are needed to clean up (i.e., removal of feature toggles)?

## Phase One questions
Will we include or exclude Veterans who have an Intent To File (ITF)? What are the risks (if any) to this?

Phase Two Questions
- will we ship TE to Veterans who have an active session?

## Open Quesdtions for Post MVP
2. Open Questions: If users are in an active session, they will complete the v1 version of the form.
3. should we separate the MVP release and the IPF release on this page?
4. is there a specfic DD dashboard we could use to monitor the product performance of the release
5. Do we need to re-pipe LH to EVSS before the release? What is the decision on that?
