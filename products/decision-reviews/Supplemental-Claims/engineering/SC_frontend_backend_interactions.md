# List of Frontend/Backend Interactions

## Get Contestable Issues

  Gets a list of contestable issues the veteran can choose from for this claim

| External System(s)   | # of occurences    | Responses  | Outcome / Message
| -------------------- | ------------------ | ---------- | --------- 
| Lighthouse           | 1 per submission   | 200        | Shows list of contestable issues
|                      |                    | Any other  | Error alert. <br> Header: We can't load your issues right now <br> Body: You can come back later, or if you'd like to add your issue manually, you can select "Add a new issue" to get started. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/cf41503b-68a3-40e9-8096-fb15f24f4b32)

## Intent to File (check) 

  Check Intent to File for veteran

| External System(s)   | # of occurences           | Responses                    | Outcome / Message
| -------------------- | ------------------------- | ---------------------------- | --------- 
| EVSS -> Lighthouse   | Always 1 per submission   | 200 with no active ITF       | Shows pending 'Submitting a new Intent to File...' [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/ea3f1a3d-7e1f-4d1d-aa1a-2b01d1d87568)
|                      |                           | 200 with existing active ITF | Success alert. <br> Header: You already have an Intent to File <br>Body: Our records show that you already submitted an Intent to File for disability compensation. Your Intent to File will expire on `date`. You'll need to file your claim by this date to receive payments starting from your effective date. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/d9a1953d-5cef-4d02-bd3c-1b4143976880)
|                      |                           | Any other                    | Error alert. <br> Header: We're sorry. Something went wrong on our end. <br> Body: We're sorry. Your Intent to File request didn't go through because something went wrong on our end. For help creating an Intent to File a Claim for Compensation, please call Veterans Benefits Assistance at 800-827, Monday through Friday, 8:00 a.m. to 9:00 p.m. ET. Or, you can fill out a VA Form 21-0996 and submit to: Department of Veterans Affairs Claims Intake Center PO Box 4444 Janesville, WI 53547-4444 [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/ba037938-7092-4e84-8722-001aebaf069d)
  
## Intent to File (create)
  
  File an Intent to File for veteran

| External System(s)   | # of occurences           | Responses                    | Outcome / Message
| -------------------- | ------------------------- | ---------------------------- | --------- 
| EVSS -> Lighthouse   | 0-1 per submission        | 200                          | Success alert. <br> Header: You already have an Intent to File <br>Body: Our records show that you already submitted an Intent to File for disability compensation. Your Intent to File will expire on `date`. You'll need to file your claim by this date to receive payments starting from your effective date. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/a71a5e88-d5a9-44b5-b3fb-5709e752bd8f)
|                      |                           | Any other                    | Error alert. <br> Header: We're sorry. Something went wrong on our end. <br> Body: We're sorry. Your Intent to File request didn't go through because something went wrong on our end. For help creating an Intent to File a Claim for Compensation, please call Veterans Benefits Assistance at 800-827, Monday through Friday, 8:00 a.m. to 9:00 p.m. ET. Or, you can fill out a VA Form 21-0996 and submit to: Department of Veterans Affairs Claims Intake Center PO Box 4444 Janesville, WI 53547-4444 [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/ba037938-7092-4e84-8722-001aebaf069d)

## Evidence Upload (before submission) 

  Putting user uploaded file into S3

| External System(s)   | # of occurences                            | Responses                        | Outcome / Message
| -------------------- | -------------------------------------------| -------------------------------- | --------- 
| AWS S3               | Any per submission, including 0 (optional  | 200                              | Prompt for document type [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/e7ab26df-9bf2-47d7-8727-f00c5667e99c)
|                      |                                            | 422 Locked PDF w/ wrong password | Inline error. <br> We can't unlock your PDF. Save your file without a password and try uploading it again. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/af4371a1-9b09-4865-96c2-da453646e613)
|                      |                                            | Any other                        | Inline error. <br> Header: We're sorry. We had a connection problem. Please try again. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/1dd28c24-eddb-49a4-86ae-36ced237047c)

## Overall Supplemental Claim Submission

  The overall submission over the claim

| External System(s)   | # of occurences           | Responses     | Outcome / Message
| -------------------- | ------------------------- | --------------| --------- 
| Lighthouse           | 1 per submission          | 200           | Redirect to confirmation page. <br> Success alert. <br> Header: Thank you for filing a Supplemental Claim <br> Body: When we've completed our review, we'll mail you a decision packet with the details of our decision. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/6533bb0f-37ef-42d8-a493-d6eb6e200cd4)
|                      |                           | 403 Forbidden | Error alert. <br> Header: Your decision review request didn't go through <br> Body: We're sorry. We're working to fix the problem, but it may take us a while. Please try again tomorrow. <br> If you're still having trouble submitting your request, call us at 800-698-2411 (TTY:711). We're here 24/7. Your in-progress ID is `ID number`. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/00945ee3-7a2d-4919-9403-5dfa3fa15859)
|                      |                           | Any other     | Error alert. <br> Header: We're sorry, there was an error connecting to VA.gov. <br> Body: Please check your internet connection and try again. [Screnshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/2fec9183-8f91-4497-bf27-eeb598b96bad)

## Save In Progress

  Saving of a users progress through the form

| External System(s)   | # of occurences           | Responses                    | Outcome / Message
| -------------------- | ------------------------- | ---------------------------- | --------- 
| N/A (only vets-api)  | Many per submission       | 200                          | Slim success alert. <br> We've saved your application. We saved it on `Date`, at `time`. Your application ID number is `ID number` [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/7f56ad4e-27f2-42f0-a4b3-ed6824125380)
|                      |                           | Any other                    | Slim error alert. <br> We're sorry. We're unable to connect to VA.gov. Please check that you're connected to the Internet, so we can save your application in progress. [Screenshot](https://github.com/department-of-veterans-affairs/va.gov-team/assets/37049625/2f1003f9-f390-4d80-bb4d-e3e7a2911407)
