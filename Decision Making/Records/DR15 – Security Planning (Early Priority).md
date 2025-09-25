
| **Status**     | #Planned                                                             |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #High                                                                |
| **Driver/s**   | Oliver                                                               |
| **Approver/s** | Zoy, Alex                                                            |
| **Date**       | Monday, September 23rd                                               |
| **Links**      | Client Sprint Feedback (Week 6), Sprint Review Notes                 |

## Background
The client stressed that **security features must not be left until the end of development**. As an enterprise-level product, Navigator requires early security planning to protect sensitive company data and ensure compliance with organisational policies.

## Relevant Data
- ICN Victoria manages company profiles; maintaining data integrity is critical.  
- Potential users include government and industry, requiring strong trust and security.  
- Delaying security could result in vulnerabilities and rework later.  

## Options Considered
**Option 1: Implement security at the final stage**  
- Pro: Faster to prototype.  
- Con: Risky, may expose vulnerabilities and create costly rework.  

**Option 2: Plan security from the start (Chosen)**  
- Pro: Enterprise-grade approach, reduces risk, aligns with client priority.  
- Con: Requires additional upfront planning.  

## Action Items
- Define authentication and authorisation strategy (email, Google/Facebook sign-in).  
- Identify sensitive data requiring encryption and secure storage.  
- Integrate security checks into CI/CD pipeline.  
- Document security strategy for client review.  

## Outcome
The team decided to **plan and integrate security from the early stages of development**.  
This ensures the Navigator platform meets enterprise standards and builds user trust.
