| **Status**     | #InProgress                                                        |
| -------------- | ------------------------------------------------------------------ |
| **Impact**     | #High                                                              |
| **Driver/s**   | @Julian                                                            |
| **Approver/s** |                                                                    |
| **Date**       | Monday, September 1st                                              |
| **Links**      | Links to relevant research, pages, meetings, and related decisions |

## Background

In order to make the API (backend) functionality of ICN Navigator available to users, we must have a system in place to deploy the application where a persistent and publicly addressable instance can run.

Importantly, the choice for hosting must meet the client criteria of:
- Use a common hosting platform
- Simplicity (no overly complex and platform-specific infrastructure requirements)
As well as the implicit goal of extensibility and scalability.

## Relevant Data

To support this decision, here are some definitions/reminders for key terms:

* **CI/CD (Continuous Integration / Continuous Deployment):** A set of practices and tools that automatically test, build, and deploy code whenever changes are made. This reduces manual effort, catches errors earlier, and ensures new features can be delivered quickly and reliably.
* **VPS (Virtual Private Server):**  A VM provided by a cloud provider (e.g., AWS EC2) that acts like a dedicated server. It gives more flexibility and control than shared hosting, allowing us to install and configure the exact software stack we need. (See also: [AWS - What is VPS?](https://aws.amazon.com/what-is/vps/))
* **TLS (Transport Layer Security):**  (recall from Computer Systems!) - A protocol that runs on top of TCP to provide confidentiality and integrity for communication between a client and a server. 

## Options Considered

### Vercel (More generally: all-in-one hosting platforms)

>[!Info]
> See: <https://vercel.com/>

**Positives:**
- Incredibly easy configuration and initial deployment
- CI/CD is automatically handled
**Negatives:**
- Complete vendor lock-in
	- Deployment tailored for Vercel or Netlify is difficult to port to other providers (as it's typically configured in their web-app platform)
- Expensive to scale (and generally less control over cost)
	- These platforms act as a layer of abstraction over underlying cloud providers like AWS or GCP

### Custom VPS Hosting

>[!Info]
>See: 
>- [EC2](https://aws.amazon.com/ec2/)
>- [CodeDeploy](https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html)

**Positives:**
- Complete flexibility in hosting architecture
- Far less vendor lock-in
	-  Simple VPS configuration is applicable to all cloud providers and even in-house hosting
- Orders of magnitude cheaper for future scaling
**Negatives:**
- More initial effort in setting up
	- Need to manually configure TLS and CI/CD
- Slightly more complex than all-in-one solutions

An ideal minimal technology stack to meet the client criteria with a VPS hosting solution requires:
- VPS platform
- TLS management
- CI/CD integration

To ensure we utilise widely adopted and well documented systems, a good choice would be:
- AWS EC2 for the VPS platform
- TLS management with Let's Encrypt through CertBot
	- Cheap domain through popular registrar (e.g. NameCheap)
- CI/CD through AWS CodeDeploy

### Managed VPS Hosting (E.g. Render)

>[!Info]
> See: <https://render.com/platform>

**Positives:**
- Hybrid approach between 1st and 2nd option
	- Simplicity of the all-in-one serverless platform with some flexibility of custom VPS hosting
**Negatives:**
- Potentially less scalable than a custom system (cost and throughput-wise)

## Action items

Add action items to close the loop on open questions or concerns.

--- 
## Outcome

Summarise the outcome. 