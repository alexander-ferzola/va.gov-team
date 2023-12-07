# Vaccines User Acceptance Testing Cases 12/7/23 

## Use case 1: As a user I can view my list of vaccines.
### Setup:
User should have at least two pages of vaccines in their record.
### Steps:
1. Navigate to the Vaccines page
2. Verify that pagination works properly
3. Verify that the same vaccines that have been logged in the EHR appear in the list, and that all data fields have been translated correctly.
﻿
## Use case 2: As a user I can print my list of vaccines.
### Setup:
User should have at least two pages of vaccine data in their record.
### Steps:
1. On the vaccines page, select Print this list
2. Verify that the browser opens a print dialog
3. If available, select Print to PDF or Microsoft XPS Document Write to verify that the page is formatted properly
4. Verify that all the expected data is included and matches the logged in user’s data:
   - Identifying information
   - Vaccine data
   - Date and time stamps
﻿
## Use case 3: As a user I can generate and view a PDF of my list of vaccines
### Setup:
User should have at least two pages of vaccine data in their record.
### Steps:
1. On the vaccines page, select Download PDF of this list
2. Verify that the browser’s download feature provides the ability to open or save a PDF
3. Select the option to view
4. Verify that the PDF opens for viewing
5. Verify that the PDF is formatted properly
6. Verify that all the expected data is included and matches the logged in user’s data.
   - Identifying information
   - Vaccines data
   - Date and time stamps
## Use case 4: As a user I can download and save a PDF of my list of vaccines.
### Setup:
User should have at least two pages of vaccine data in their record.
### Steps:
1. On the vaccines page, select Download PDF of this list
2. Verify that the browser’s download feature provides the ability to open or save a PDF
3. Select the option to print
4. Save the PDF locally
5. Open the PDF
6. Verify that the PDF is formatted correctly
7. Verify that all the expected data is included and matches the logged in user’s data.
   - Identifying information
   - Vaccines data
   - Date and time stamps
﻿
## Use case 5: As a user I can view details about my vaccines
### Setup:
User should have at least one vaccine in their record.
### Steps:
1. On the vaccines page, click the name of a vaccine
2. Verify that the detail page for the vaccine is displayed
3. Verify that data that has been logged in the EHR for a vaccine appears in the details for that vaccine: name, date administered, location administered, and any notes entered by the provider

﻿
## Use case 6: As a user I can print information about a single vaccine
### Setup:
User should have at least one vaccine in their record.
### Steps:
1. On the vaccine details page, select Print this page
2. Verify that the browser opens a print dialog
3. If available, select Print to PDF or Microsoft XPS Document Write to verify that the page is formatted properly
4. Verify that all the expected data is included and matches the logged in user’s data.
   - Identifying information
   - Vaccines data
   - Date and time stamps
﻿
## Use case 7: As a user I can generate and view a PDF of a single vaccine
### Setup:
User should have at least one vaccine in their record.
### Steps:
1. On the vaccine details page, select Download PDF of this list
2. Verify that the browser’s download feature provides the ability to open or save a PDF
3. Select the option to view
4. Verify that the PDF opens for viewing
5. Verify that the PDF is formatted properly
6. Verify that all the expected data is included and matches the logged in user’s data.
   - Identifying information
   - Vaccines data
   - Date and time stamps
﻿
## Use case 8: As a user I can download and save a PDF of a single vaccine
### Setup:
1. User should have at least one vaccine in their record.
### Steps:
1. On the vaccine details page, select Download PDF of this list
2. Verify that the browser’s download feature provides the ability to open or save a PDF
3. Select the option to print
4. Save the PDF locally
5. Open the PDF
6. Verify that the PDF is formatted correctly
7. Verify that all the expected data is included and matches the logged in user’s data.
   - Identifying information
   - Vaccines data
   - Date and time stamps
﻿
## Use case 9: As a user I do not want to see data that was erroneously entered into my record
### Setup:
User should have at least one vaccine that was "entered in error"
### Steps:
1. Navigate to the Vaccines page
2. Verify that the vaccine flagged as "entered in error" does not appear 
