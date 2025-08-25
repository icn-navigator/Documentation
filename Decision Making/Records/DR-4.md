
| **Status**     | #InProgress                                                        |
| -------------- | ------------------------------------------------------------------ |
| **Impact**     | #High / #Medium / #Low                                             |
| **Driver/s**   | @Matthew Wang                                                      |
| **Approver/s** | @Everyone                                                          |
| **Date**       | Monday, August 25th                                                |
| **Links**      | Links to relevant research, pages, meetings, and related decisions |

## Background

There aren't many choices for frontend languages, but there is one obvious important decision - Plain JavaScript or TypeScript?
## Relevant Data

* Some of the team (Zoy, Alex) have had no experience with either JavaScript or TypeScript
* Everyone has had an experience with at least one strongly typed language (C)
* 
## Options Considered

### JavaScript (JS)

JavaScript is a dynamic, interpreted language that runs in browsers, enabling devs to manipulate HTML, manage events, and create interactive elements.

**Positives:**
* Easier to learn
* Ideal for quick scripting and prototyping
* It's ubiquity ensures it can run (almost) anywhere
* Vast ecosystem of libraries (millions of packages see [npm](https://www.npmjs.com/))
* Can still scale well with disciplined coding practices

**Negatives:**
* No type system
* Does not scale (although, can still be effective in larger projects with disciplined coding practices)
### TypeScript (TS)

TypeScript is a superset of JavaScript, adding static typing and advanced features to the language. 

**Positives:**
* Compiled to JavaScript so can run anywhere JS does
* **Type system**
	* Fewer bugs
	* More predictable / readable code
	* Easier scaling to larger projects
* Features like interfaces, generics
* Strong tooling integrations - better intelligent suggestions (improves developer productivity)

**Negatives:**
* Steeper learning curve (requires understanding of typing) 
* Must to compile to JS before code execution
* A bit more setup required

Discuss alternate options and their positives and negatives.
## Action items

- [ ] Seek further feedback from all developers involved in frontend code (likely the whole team) to see what they are the most comfortable with

--- 
## Outcome

TypeScript.