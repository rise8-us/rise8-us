# Engineering Practice Playbook

## What is an Engineer?
---

An engineer on a balanced team is responsible for the technical delivery of a product to the customer. They focus their time on building a secure, reliable, scalable, and maintainable product. The engineer brings a unique perspective to the team as they best understand the amount of work needed to build features. They also understand the impact technical debt can have on velocity. They work hand in hand with the product manager to buy down risks through backlog prioritization. The engineer also works with the designer to execute a design system and tease out technical pain points from the user. The engineer works with operations to optimize product delivery and support.

> “A team management philosophy that has people with a variety of skills and perspectives that support each other towards a shared goal.” - balancedteam.org

## Foundation
**Agile Manifesto Principles**

1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.  
1. Welcome changing requirements, even late in development. Agile processes harness change for the customer’s competitive advantage.
1. Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
1. Business people and developers must work together daily throughout the project.
1. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
1. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
1. Working software is the primary measure of progress.
1. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
1. Continuous attention to technical excellence and good design enhances agility.
1. Simplicity – the art of maximizing the amount of work not done – is essential.
1. The best architectures, requirements, and designs emerge from self-organizing teams.
1. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

### Rise8 Takes

- Enablement is a primary skillset we practice here at Rise8. Not only building the product but helping build the team's skillset to continue product development.
- Pair engineers with projects they love.
- Offer opportunities for engineers to grow and expand.
- Trust allows agile teams to communicate quickly and respond rapidly to changes as they emerge. Without sufficient trust, team members can waste effort and energy hoarding information, forming cliques, dodging blame, and covering their tracks.
  - Trust your team is making the best decisions with the information known at the moment, with or without your presence. You and your team have a common goal, there is more than one way to reach it.
- Technical facts and data overrule opinions and personal preferences.
- Use best practices and design patterns unless justified.
- Adheres to the team's code contract for styling.


## Discovery
---

### Build vs Buy Analysis

Engineers evaluate already existing options to include commercial or government.

TODO: Separate into groups (Build & Purchase/Use)


- Is there an offering that sufficently meets the team's requirements
- Build, operate, maintain, and upgrade cost Vs buy and licensing cost?
- Do we have the expertise to build?
- What is the learning curve/developer experience of the commercial products?
- Security requirements?
- Will new features be required, can they be added to the buy option?
- How much granular control of the system is necessary?
- Will the buy/FOSS option be maintained longterm
- Is the offering well documented/provide a satisfactory user experience?
- Time to market?


### Technology Stack

**We choose the right Tech stack for the problem space.**

**Here are a few things to consider when selecting tools and technologies**
  
1. Is training necessary? What is the learning curve? How much documentation is available? Is it good documentation?
1. Are the skills and knowledge required common, or is the technology very niche?
1. Is the technology mature enough to adopt?
1. What are the costs?
    - compute cost of a low level language
    - engineering wage difference between one language to another
    - tooling
1. Is there support for the technology within the current continuous integration process?
1. Can the technology be deployed to all environments?
1. Can the technology be managed in all environments?
1. Is the technology stack meeting security criteria and project constraints?
1. Does the technology stack performance, reliability, and maintainability satisfy the product's requirements?
1. Can the technology stack scale?


## Building an MVP
---

Proof of Concept >> Prototype >> MVP

### Proof of Concept

The goal of a Proof of Concept is for quick applied Technical Discovery to learn information to empower decision making. It can be comprised of pseudo-code, code-fragments, and/or diagrams that depict how the systems communicate. Outcome should be to validate & verify if feasible to accomplish, becomes the reference to for the prototype.

Should we use best practices when building a proof of concept?
  - Not required, but encouraged
  - Use as needed to explain the proposed concept

### Prototype

The goal of a Prototype is to demo limited functionality to end users in an ideal/sandbox environment and help teams evaluate risk. This becomes a candidate for the initial MVP. Code should follow best practices unless it would be a severe time sync to implement.

Should we use best practices when building a prototype?
- Should try to use best practices, unless severe time sink

What types of outcomes/information should the prototype produce?
- Technical discovery
- User traction/Customer feedback

### MVP

An MVP builds off of a Prototype to add in further functionality and error handling, and integrate with a production environment.

What defines an MVP?
- Full functionality
- Meets all acceptance criteria

Should we use best practices when building an MVP?
- Best practices are standardized and required


## Systems Design and Architecture
---

### Architecture - Marshall/JB

**[Example](https://playbook.obvious.in/2f06a1c7eaa542098251719a1f083d54)**  
*We will keep a collection of records for "architecturally significant" decisions: those that affect the structure, non-functional characteristics, dependencies, interfaces, or construction techniques.

An architecture decision record is a short text file in a format similar to an Alexandrian pattern. (Though the decisions themselves are not necessarily patterns, they share the characteristic balancing of forces.) Each record describes a set of forces and a single decision in response to those forces. Note that the decision is the central piece here, so specific forces may appear in multiple ADRs.

We will keep ADRs in the project repository under doc/arch/adr-NNN.md

We should use a lightweight text formatting language like Markdown or Textile.

ADRs will be numbered sequentially and monotonically. Numbers will not be reused.

If a decision is reversed, we will keep the old one around, but mark it as superseded. (It's still relevant to know that it was the decision, but is no longer the decision.)

We will use a format with just a few parts, so each document is easy to digest. The format has just a few parts.

Title These documents have names that are short noun phrases. For example, "ADR 1: Deployment on Ruby on Rails 3.0.10" or "ADR 9: LDAP for Multitenant Integration"

Context This section describes the forces at play, including technological, political, social, and project local. These forces are probably in tension, and should be called out as such. The language in this section is value-neutral. It is simply describing facts.

Decision This section describes our response to these forces. It is stated in full sentences, with active voice. "We will ..."

Status A decision may be "proposed" if the project stakeholders haven't agreed with it yet, or "accepted" once it is agreed. If a later ADR changes or reverses a decision, it may be marked as "deprecated" or "superseded" with a reference to its replacement.

Consequences This section describes the resulting context, after applying the decision. All consequences should be listed here, not just the "positive" ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team and project in the future.

The whole document should be one or two pages long. We will write each ADR as if it is a conversation with a future developer. This requires good writing style, with full sentences organized into paragraphs. Bullets are acceptable only for visual style, not as an excuse for writing sentence fragments. (Bullets kill people, even PowerPoint bullets.)*

### Domain Driven Design


### Design Patterns

### Supplemental Materials

- Security requirements - full process architecture diagram


### Technical Debt

Technical debt can be defined as aspects of our code that will slow down future development. Debt can be intentional or unintentional but must be managed. Incurring too much technical debt can lead to a reduction in productivity, maintainability and testability which in turn leads to unhappy employees and decreased organizational performance. Engineers are responsible for making technical debt visible. Here are a few ways to mitigate and manage technical debt in your products:

1. Keep a log of debt on your project for future conversations
1. Discuss during backlog grooming
1. Establish coding and documentation standards
1. Familiarize yourself with common design & architecture patterns
1. Be aware of new technologies

### Acceptance Criteria

Engineers can help the team by reviewing acceptance criteria before the sprint begins. The acceptance criteria should be clear and free of interpretation.


## Development
---

### Pointing and Scheduling work (Needs work and sync with PMs)

**Pointing**

All work should be pointed and labeled with the category. This allows you to see a break down of work and identify trends and make corrections when neccessary. Feature velocity is down, why? Oh we spent a lot of time on refactoring.  Why are we spending a large amount of time on refactoring, is it because we are rushing in new features?  Having this data is super helpful especially when doing retros.

The Product Manager discipline is sometimes only concerned with feature work pointing. Labeling the work allows you to pull out an accurate Feature velocity.

**Target ranges**

- 30% - 50% Feature
- 15% - 30% Innovation/Tech debt sometimes call chore
- 5% - 20% bug

*TODO define feature, bug Innovation/tech debt*

**Feature**
A feature is something that provides new capabibilties or improves end user experience.

**Innovation / Refactoring**
Innovation is proactive tech debt management.  Innovation work is time spent incorporating **new** libraries, patterns, or services to make the code base easier to maintain, scale, and or add features. Innovation work should be closely evaluated to ensure that it is a worth while return on investment; avoid innovating for the sake of innovation without providing any meaningful value.

Refactoring is an oppurtunity drive down existing technical debt, optimize, and re-architect the codebase so the code can remain simple, decoupled, easily read, and painlessly scaled. Engineers often complain about old programing languages as if the language is root problem when real problem is old messy code bases.

Engineers should not shy away from performing large scale refactors (agreed on by the team) that improve the applications performance, ease of use, and deployability. These refactors can range from UI changes to entire revisions of the database schema.

**Bug**
Any work being done to correct unexpected behaviors or faults that are inconsistent with the desired coded intent.

**NOTE**
Security is a fundamental part of software developemnt and as such can be characterized to fit in all three of the categories as needed.  In a high compliance environment where stories are created to address security controls from Compliance tool such as SD Elements the team may want a seprate category to cover this work.

### CI/CD Pipeline



### Continuous Integration

We believe CI is non-negotiable and must begin at the initial conception of development to ensure comprehensive software security, testing, and fast feedback on the main branch health. Furthermore it empowers the ability of the team to hold to agile practices.


### Continuous Delivery

We believe that any merge to main should be able to deploy to production. Merges should be self-contained and not dependant upon another branch.

## Testing
---

Building testing into our products provides us the confidence that we need to quickly deliver new features without the fear of breaking our products. The test pyramid depicts the types of test we can author along with the general distribution.


### Unit

The unit test is designed to test a small, singular component/function/method. The tests are easy to author and maintain and thus often represent the largest portion of tests within the code.


### Contract Testing

TDD for micro service architecture, contracts are written on what will be consumed and then consumers and producers are tested against these contracts.  Eliminates the need for test environments that have all services running and at a specific version.


### Integration

The integration test is designed to test between components. A typical example might be integrating with a database or a provided REST service. Integration tests require that you stand up not only your product but also the components with which you integrate. For this reason, they require more time and effort than unit tests. They often times are the second most frequently used test.


### End to End {#end-to-end}

The end to end test is designed to test through your stack starting at the front end. The tests require the most time and effort to write and maintain. For this reason, they often represent the smallest portion of your tests.

For further reading take a look at a the list of curated resources



* [https://martinfowler.com/articles/practical-test-pyramid.html](https://martinfowler.com/articles/practical-test-pyramid.html)


## Practices
---

Ceremonies

### Story Point

Engineers can help the team by helping to point stories. They can help estimate the amount or complexity of the work. Since engineers understand the work involved to fulfill a requirement,  they can ensure that stories are granular and right sized.

### Pair Programming

Pair programming is a development technique where two developers author software using the same computer. The computer is outfitted with two keyboards, two monitors and two mice. In a remote environment one user can share the screen with another via collaboration software such as [Zoom](https://zoom.us/). Pair programming has many benefits that include:



1. Knowledge sharing (both domain and technical knowledge)
2. Immediate code reviews
3. Improved interpersonal communication
4. Reduction in code defects

Here are few helpful hints when pairing:



1. Pairing can be tiring, take breaks often
2. Rotate pairs regularly. Each person brings something unique to the table which will improve the codebase as a whole. Swapping pairs also drives both knowledge sharing and alignment across the team.
3. Be open to new ideas and constructive criticism
4. Sometimes pairing might not be the best approach. Feel free to solo when it makes sense. But remember, committed code requires a peer review.





### Test Driven Development

Test Driven Development is software development practice. The process starts with authoring a failing test and then implementing the functionality required for the test to succeed. Often times referred to as “Red Green Refactor”, it consists of three distinct steps (red-green-refactor):



1. Author a failing test
2. Author just enough code for test to pass
3. Refactor


### Code Review

The primary purpose of code review is to make sure that the overall code health of the project's codebase is improving over time, and a series of trade-offs have to be balanced.

First, developers must be able to _make progress_ on their tasks. If you never submit an improvement to the codebase, then the codebase never improves. Also, if a reviewer makes it very difficult for _any_ change to go in, developers are disincentivized to improve in the future.

Second, the reviewer must ensure that each merge request is of such a quality that their codebase's overall health is not decreasing as time goes on. This can be tricky because codebases degrade through small decreases in code health over time, especially when a team is under significant time constraints and feel that they have to take shortcuts to accomplish their goals.

A reviewer has ownership and responsibility for the code they are reviewing. They want to ensure that the codebase stays consistent and maintainable.

Thus, we get the following rule as the standard we expect in code reviews:

In general, reviewers should favor approving a merge request once it is in a state where it improves the overall code health of the system being worked on, even if the merge request isn't perfect.

There are limitations to this, of course. For example, if a merge request adds a feature that the reviewer doesn't want in their system, then the reviewer can certainly deny approval even if the code is well-designed.

A key point here is that there is no such thing as "perfect" code—there is only _better_ code. Reviewers should not require the author to polish every tiny piece of a merge request before approving. Instead, the reviewer should balance out the need to make forward progress compared to the importance of the changes they are suggesting. Instead of seeking perfection, what a reviewer should seek is _continuous improvement_. A merge request that improves the maintainability, readability and understandability of the system shouldn't be delayed because it isn't "perfect."

Reviewers should _always_ feel free to leave comments expressing that something could be better, but if it's not very important, prefix it with something like "Nit: "to let the author know that it's just a point of polish that they could choose to ignore (Nit means nit-pick).



Note: Nothing in this document justifies checking in merge requests that _worsen_ the system's overall code health. The only time you would do that would be in an emergency.

- Aspects of software design are seldom a pure style issue or just a personal preference**.** They are based on underlying principles and should be weighed on those principles, not simply by subjective opinion. Sometimes there are a few valid options. If the author can demonstrate (either through data or based on solid engineering principles) that several approaches are equally good, the reviewer should accept the author's preference. Otherwise, the choice is dictated by standard principles of software design.
- If no other rule applies, then the reviewer may ask the author to be consistent with the current codebase, as long as that doesn't worsen the system's overall code health.
- On matters of style, the style guide is the absolute authority. Any purely style point (whitespace, etc.) not in the style guide is a personal preference. The style should be consistent with what is there. If there is no previous style, accept the author's style.

#### Mentoring

Code reviews can be an essential function for teaching developers something new about a language, a framework, or general software design principles. It's always OK to leave comments that help a developer learn something new. Sharing knowledge is part of improving the code health of a system over time. Just keep in mind that if your comment is purely educational but not critical to meeting the standards described in this document, prefix it with "Nit: "or otherwise indicate that the author doesn't need to resolve it in this merge request.


#### Resolving Conflicts

In any conflict on a code review, the first step should always be for the developer and reviewer to reach an agreement.

When coming to consensus becomes especially difficult, it can help to have a face-to-face meeting or a video conference between the reviewer and the author, instead of just trying to resolve the conflict through code review comments. (If you do this, though, make sure to record the discussion results as a comment on the merge request for future readers.)

If that doesn't resolve the situation, the most common way to resolve it would be to escalate. Often the escalation path is to a broader team discussion, having a Technical Lead weigh in, asking for a decision from a maintainer of the code, or asking an Eng Manager to help.

Don't let a merge request sit around because the author and the reviewer can't agree.

_This section was derived, with modifications, from [Google Engineering Practices Documentation](https://github.com/google/eng-practices)_


## Modern Applications


### Logging

As you ship your application into production you want to make sure that your logs can be processed and aggregated easily. Designing your application in this fashion will allow the platform to treat all application logs the same. Additionally, it allows for providing a base set of services your organization will need to support and operate your application. A few examples include, access to logs for debugging as well as setting up alerts for monitoring. The standard practice is to write log entries to stdout. For further information, check out the  [logs](https://12factor.net/logs) section on [12factor.net](https://12factor.net/)


### Configuration

Your application will exist in numerous environments including development, staging and production. For this reason, it is important that your application can be configured easily. Keep in mind that your application is likely to end up on a platform like Kubernetes where managing the lifecycle of an application is important. The standard practice is to expose configuration via granular environment variables. The configuration defines a contract with the tools that manages your application’s lifetime. For further information, check out the [config](https://12factor.net/config) section on [12factor.net](https://12factor.net/)


### Backing Services

As you build out your application, there will be a set of services you wish to consume. You should consider what services are needed and if they are provided as part of the platform offering. Configuring these services is as simple as adding environment variables to your configuration (see above). Listed below are common services:



1. Identity Management (ie Keycloak)
2. Databases (ie Relational, NoSQL)
3. Storage (ie S3, Minio, Volumes)
4. Message Queues (ie RabbitMQ, Kafka)
5. Email (ie SMTP)


### Monitoring

Monitoring your application will help you be successful. Monitoring can help you understand how your application is being used and by whom. Monitoring can help you understand whether your application is functioning. When you start building your application consider the following:



1. Are health endpoints available in my application? What engineering aspects should be part of the health endpoint? How are the health endpoints monitored?
2. Are there important product metrics to capture? Are there any technologies available to support metrics collection (ie Elasticsearch, Kibana, Grafana)?
3. Are there technologies available to support alerting?


### Additional Resources



* [https://12factor.net](https://12factor.net/)




### Recommended Reads



* [Clean Code by Robert C. Martin](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
* [Composing Software by Eric Elliot](https://www.amazon.com/Composing-Software-Exploration-Programming-Composition/dp/1661212565)
* [Design Patterns by Gang of Four](https://www.amazon.com/Design-Patterns-Object-Oriented-Addison-Wesley-Professional-ebook/dp/B000SEIBB8)
* [Pragmatic Programmer](https://www.amazon.com/Pragmatic-Programmer-Anniversary-Journey-Mastery/dp/B0833FBNHV/ref=sr_1_1?dchild=1&gclid=Cj0KCQiAst2BBhDJARIsAGo2ldUUR4IfnxCjch0ni9ici1HmmtCYjITL9ghoHWfJRZJjlTOXIRdR5DEaAiXrEALw_wcB&hvadid=241894030769&hvdev=c&hvlocphy=9008585&hvnetw=g&hvqmt=e&hvrand=15887975436101901235&hvtargid=kwd-131403882&hydadcr=16400_10303601&keywords=pragmatic+programmer&qid=1614290816&sr=8-1&tag=googhydr-20)
* [Event-Driven Microservices](https://www.oreilly.com/library/view/building-event-driven-microservices/9781492057888/)

<!-- Footnotes themselves at the bottom. -->
## Notes

[^1]:
Accelerate

[^2]:
Accelerate
