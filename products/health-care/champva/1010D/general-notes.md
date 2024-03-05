# General Notes
General info, notes and miscellaneous 

### Programs
- IVC: Office of Integrated Veteran Care (merging of two offices - OVAC Office of Veterans Access to Care and the Office of Community Care)
- VBA: Veterans Benefits Administration
- VHA: Veterans Health Administration
- VFMP: Veteran and Family Member Program
- VR&E (or Chapter 31): Veteran Readiness and Employment

### Systems/Processes
- AVA: [Ask VA](https://ask.va.gov/) (online service where people can submit questions, concerns, recommendations, and upload documents to VA)
- CMP: Centralized Mail Portal
  - takes documents and routes them to various VBA (Veterans Benefits Administration) teams for processing
- CP&E: Claims Processing and Eligibility
  - Eligibility system where records are stored and decisions are made
- CRM: where tasks/requests from call center are created and tracked/routed
- CXM: health care clearinghouse/database
  - all CHAMPVA,  VFMP, Spina Bifida, Children of Women Vietnam Veterans claims go here
- DAPER: Document and process enabled repository (existing system that will be replaced by PEGA)
- DCDM: Document Control Data Management 
- EEV: eligibility, enrollment, verification
- PEGA: new document repository and management system that will replace DAPER
  - integration needs to be built still 
- VBMS: Veteran Benefit Management system
  - case management system for VBA (Veteran's name/phone number/address/Ch 31)
- VES: Veterans enrollment system
  - new enrollment system that won't be ready until sometime in 2025
  - (dev will begin in spring 2024 and plan to complete in spring 2025)
  - VHA version of VBMS
- VIS: Veteran Information System
- VISTA: Veterans Health Information Systems and Technology Architecture (VISTA)
  - instance of CP&E (where eligibility info is stored, service connected conditions); VBA system

 
### Key Decisions/Findings
- PEGA integration [decision record](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/health-care/champva/ADR-PEGA%20integration%20for%20CHAMPVA.md)
- 2/7/24 - Our recommendation for the longer term approach is for VBMS and VIS to communicate with each other (and to eliminate need for 10-7959f-1 FMP registration form altogether). For now we will focus on digitizing the form.
- 3/4/24 - 10-10d usability testing will be done in staging. 10-7959f-1 testing - looking into UXPin (CodePen involves too much coding, Figma licenses are too limited). [Decision matrix](https://app.mural.co/t/departmentofveteransaffairs9999/m/departmentofveteransaffairs9999/1709218659350/85e1a2c931eafd52734bc66235165d15bf08d582?sender=334959bc-2aad-4cce-a6be-76386587a1e8) for prototypes created by Lois.

### Miscellaneous
- New list and loop pattern being worked on by VFF team but not ready to use ('classic' will be used in usability testing as well as staging review and production). 
- Houseless/no address not really an existing pattern for this currently (may revisit this at a later point in time, but not part of initial effort for launch).
  
