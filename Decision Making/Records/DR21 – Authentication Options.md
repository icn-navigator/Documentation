
| **Status**     | #Pending                                             |
| -------------- | ---------------------------------------------------- |
| **Impact**     | #Medium                                              |
| **Driver/s**   | Alex                                                 |
| **Approver/s** | Matthew, Julian                                      |
| **Date**       | Sunday, September 29th                               |
| **Links**      | Client Sprint Feedback (Week 6), Sprint Review Notes |

## Background
The client confirmed that users may sign up using **Google or Facebook accounts** in addition to the standard email-based sign-up. This could improve onboarding flow and align with modern authentication expectations. However, the team has not yet committed to implementing social login, preferring to wait until the framework is stable.

## Relevant Data
- Email registration is already defined as the baseline.  
- Social sign-in (OAuth) would require external integration and extra setup.  
- The MVP goal is functionality first; authentication flexibility may follow later.  

## Options Considered
**Option 1: Email-only authentication**  
- Pro: Simplest implementation, fewer dependencies.  
- Con: Higher friction for some users, less convenience.  

**Option 2: Support Google and Facebook sign-in**  
- Pro: Familiar experience, reduces onboarding friction.  
- Con: Requires integration with external providers, slightly more complex.  

**Option 3: Decide later after framework setup (Chosen for now)**  
- Pro: Keeps focus on building core framework; allows flexibility to revisit.  
- Con: Authentication approach is not yet finalised.  

## Action Items
- Prioritise setting up baseline authentication framework (email).  
- Document requirements for Google and Facebook OAuth integration.  
- Revisit decision after initial framework is in place and development progress is clearer.  

## Outcome
The team decided to **defer the final decision on social authentication** until after the core framework is established.  
Email login will be implemented first, with Google/Facebook sign-in considered later depending on progress.
