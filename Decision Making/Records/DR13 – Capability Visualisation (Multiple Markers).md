
| **Status**     | #InProgress                                                    |
| -------------- | -------------------------------------------------------------- |
| **Impact**     | #Medium                                                        |
| **Driver/s**   | Matthew                                                        |
| **Approver/s** | Oliver, Alex                                                   |
| **Date**       | Saturday, September 21st                                       |
| **Links**      | Client Sprint Feedback (Week 6), Common Q&A (Capability Types) |

## Background
The client highlighted that **a single company can hold multiple capabilities** (e.g., manufacturing, supplying, servicing). Therefore, it is inaccurate to represent a company with only one colour, icon, or simple distinguisher. Visualisation must support multiple attributes without oversimplification.

## Relevant Data
- Companies can be manufacturers, service providers, and suppliers at once.  
- Capability types include designer, project manager, retailer, etc.  
- Current datasets support many-to-many relationships between organisations and capabilities.  

## Options Considered
**Option 1: One icon/colour per company**  
- Pro: Simpler UI.  
- Con: Misrepresents companies with multiple roles.  

**Option 2: Multiple icons/markers per company (Chosen)**  
- Pro: Accurate, reflects complex company roles.  
- Con: Requires careful visual design to avoid clutter.  

**Option 3: Aggregate capability into one “primary” type**  
- Pro: Cleaner presentation.  
- Con: Oversimplifies data and loses important details.  

## Action Items
- Implement visual design that allows attaching multiple icons/colours to one company.  
- Explore layered icons, composite markers, or tooltips.  
- Test readability at different zoom levels.  

## Outcome
The team decided to **support multiple capability markers per company**.  
This ensures **accuracy** in representing company roles while preserving usability through thoughtful design.
