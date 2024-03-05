### Feature toggle updates
| Percentage | Date       |
| ---------: | ---------: |
|         1% | 02/29/2024 |
|        10% | 02/29/2024 |
|         1% | 02/28/2024 |


### Revision History
| Revision         | Deploy Date |
| ---------------: | ----------: |
| [4](#revision-4) |  02/28/2024 |


## Change log
#### Revision 4
Date Deployed: _02/28/2024_ \
PR: [https://github.com/department-of-veterans-affairs/vets-api/pull/15699](https://github.com/department-of-veterans-affairs/vets-api/pull/15699)

Description of changes: I wasn't aware previously that Disability Ratings could have a `rating_end_date` that was in the future. EVSS still returns these ratings so the step where we consider any disability rating with a non-null `rating_end_date` is no longer completely valid. Updated the check to also consider the claim active if the `rating_end_date` is a future date
