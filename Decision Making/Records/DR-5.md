
| **Status**     | #InProgress                                                        |
| -------------- | ------------------------------------------------------------------ |
| **Impact**     | #High                                                              |
| **Driver/s**   | Julian Lewis                                                       |
| **Approver/s** |                                                                    |
| **Date**       | 30/08/2025                                                         |
| **Links**      | Links to relevant research, pages, meetings, and related decisions |

## Background

Our choice for backend language was shaped by three key requirements: familiarity, popularity, and performance.

Choosing a language the team is more familiar with (or has a shallow learning curve):
- Minimises time spent learning syntax and language features
- Permits better programming practice through established language knowledge

Choosing a language that is popular for the application is important to:
- Maximise the number of available resources for developing robust and proven software
- Increase the amount of tooling and developer libraries available
	- Reduces time spent "re-inventing the wheel"

Choosing an inherently performant language for the application is important for later stages of development when testing user experience, where higher level or domain-unoptimised languages may introduce delays that reduce software quality and UX.

## Relevant Data

Add any data or feedback the team should consider when making this decision.
## Options Considered

### Typescript + Node

**Positives:**
- Very widely used for writing API servers
- Simple language
- Moderate (compile-time) type safety
**Negatives:**
- Potentially un-intuitive runtime (using express for HTTP server)
- Half of team would have to learn Javascript/Typescript

### Rust + Axum

**Positives:**
- Extremely fast
- Completely enforced type (and memory) safety
- Minimal memory footprint, can be deployed anywhere
**Negatives:**
- Not as well supported as Node or Bun
- Most of team isn't familiar with Rust (which has quite a high learning curve)
- Lower level than Typescript, sacrifice development time for performance and safety

### Typescript + Bun

**Positives:**
- Very performant
- Rapidly growing support
- Cross-compatibility with Node
- Very simple runtime, servers are built with high-level ready-made library interfaces
**Negatives:**
- Half of team would have to learn Javascript/Typescript

## Action items

Add action items to close the loop on open questions or concerns.

--- 
## Outcome

We have decided to use the **Bun** runtime with **Typescript**.

