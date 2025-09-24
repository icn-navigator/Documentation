
| **Status**     | #Complete                                         |
| -------------- | ------------------------------------------------- |
| **Impact**     | #High                                             |
| **Driver/s**   | Julian                                            |
| **Approver/s** | Oliver                                            |
| **Date**       | Monday, September 16th                            |
| **Links**      | Client Sprint Feedback (Week 6), Meeting Notes W6 |

## Background
ICN Victoria clarified that company profile information is **owned and managed by ICN Victoria**. Companies themselves cannot create or edit their profiles. All updates must go through ICN Victoria’s systems and processes. This ensures data accuracy, compliance, and a single source of truth.

## Relevant Data
- Profiles include company name, services, contact details, certifications, and tags.  
- ICN Victoria is the trusted custodian of these details.  
- Client feedback explicitly stated companies should not be allowed to self-edit.  

## Options Considered
**Option 1: Allow company self-service editing**  
- Pro: Easier for companies to keep data up to date.  
- Con: Risk of inconsistency, duplicate data, and reduced quality control.  

**Option 2: ICN Victoria controls all profile data (Chosen)**  
- Pro: Maintains data integrity and client governance.  
- Con: Companies must submit feedback requests to update their info.  

## Action Items
- Implement read-only company profile views in the Navigator app.  
- Feedback or update requests will be routed to ICN Victoria, not companies.  
- Document this constraint in system architecture and onboarding materials.  

## Outcome
The team has decided that **ICN Victoria retains full ownership and editing rights** for all company profiles. The Navigator platform will only provide **read-only access** to this data, ensuring integrity and alignment with client requirements.
