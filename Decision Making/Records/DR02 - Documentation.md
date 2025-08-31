| **Status**   | #Complete           |
| ------------ | ------------------- |
| **Impact**   | #High               |
| **Driver**   | @Oliver and @Julian |
| **Approver** | @Everyone           |
| **Date**     | W1                  |
| **Links**    | [[W1 - Meeting 2]]  |

## Background

This project requires a centralised system for activities such as:
* Team management 
* Information sharing
* Planning
* Agile workflows
* Documentation

## Relevant Data

None of us have any experience with Confluence.

## Options Considered

### Confluence

**Positives:**
* Feature rich software
* Established industry standard
* Integration with other software (Jira, Figma)
* Has been used by past years to great success
* Entire spaces can be easily converted to a pdf for submission

**Negatives:**
* Relatively steep learning curve
* Arguably bloated software
* Potentially unnecessary for a small team
* Premium trial expires within a month then we have to pay
* Potentially harder for handover

### Markdown with Obsidian

**Positives:**
* Simple, easy to use
* Standardised file format is highly portable
* With tools such as [Jekyll](https://jekyllrb.com/) or [Obsidian Publish](https://obsidian.md/publish) can be deployed to a static website which would be especially useful for code documentation.
* Free (although shared vaults are not, we can just use GitHub for version control)

**Negatives:**
* Not as feature rich, doesn't provide specific support for Agile workflows
* Markdown has some limitations (styling is standardised)

## Action items

- [m] Check with Harry that using Markdown with Obsidian is acceptable

--- 

## Outcome

We will be using Markdown (with Obsidian) for documentation (both internal and for development)

The primary justification for not using Confluence was that it would add unnecessary friction that would slow us down. 