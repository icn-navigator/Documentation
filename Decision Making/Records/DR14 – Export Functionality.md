
| **Status**     | #Planned                                                             |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #Medium                                                              |
| **Driver/s**   | Zoy                                                                  |
| **Approver/s** | Julian, Matthew                                                      |
| **Date**       | Sunday, September 22nd                                               |
| **Links**      | Client Sprint Feedback (Week 6), Feature Prioritisation Doc          |

## Background
During sprint discussions, the client emphasised the importance of **sharing and exporting features**. Users should be able to export company data for analysis or reporting, with support for multiple formats such as Excel and PDF. This functionality aligns with the research and reporting needs of industry and government users.

## Relevant Data
- Basic tier: limited export (Excel/PDF basic info).  
- Plus/Premium tiers: extended exports (revenue, certifications, local content).  
- Export formats must remain consistent with ICN Victoria’s data standards.  

## Options Considered
**Option 1: No export functionality**  
- Pro: Simpler implementation.  
- Con: Fails to meet client expectations; reduces usability.  

**Option 2: Single export format (Excel only)**  
- Pro: Minimal implementation effort.  
- Con: Not flexible, excludes PDF use cases.  

**Option 3: Support multiple export formats (Excel and PDF) (Chosen)**  
- Pro: Flexible and useful across different contexts.  
- Con: Requires additional implementation effort.  

## Action Items
- Define export scope for each tier (Basic/Plus/Premium).  
- Implement export options in Excel and PDF.  
- Ensure exported files comply with ICN Victoria’s branding and format standards.  

## Outcome
The team decided to **support multiple export formats (Excel and PDF)**.  
This balances usability and client needs, and provides flexibility for both free and subscription-based tiers.
