# Engineering Practice Playbook

## Team Composition


### Engineer

The engineer is responsible for the technical delivery of a product to the customer. They focus their time on building a secure, reliable, scalable and maintainable product. The engineer brings a unique perspective to the team as they best understand the amount of work needed to build out features. They also understand the impact technical debt can have on velocity. They work hand in hand with the product manager to buy down risks through backlog prioritization. The engineer also works with the designer to execute a design system as well as tease out technical pain points from the user. The engineer works with operations to optimize product delivery and  support.


### Designer


### Product Manager


## Values


### Collaboration

Collaboration improves software delivery performance, organizational performance and job satisfaction[^1]. Working with someone to reach a common goal has many benefits to include:



1. Opens new communication channels
2. Quicker alignment
3. Brings unique perspectives and better solutions
4. Improves efficiency


### Trust

Collaboration improves software delivery performance, organizational performance and job satisfaction[^2]

Trust your team is making the best decisions with the information known at the moment, with or without your presence. You and your team have a common goal, there is more than one way to reach it.


### Courage


### Mission Driven


## Discovery


### Build vs Buy Analysis

Engineers can evaluate already existing options to include commercial or government.


### Prototypes

Engineers can build disposable prototypes in order to burn down any risk and help inform team.


## Product Planning


### Technical Debt

Technical debt can be defined as aspects of our code that will slow down future development. Debt can be intentional or unintentional but must be managed. Incurring too much technical debt can lead to a reduction in productivity, maintainability and testability which in turn leads to unhappy employees and decreased organizational performance. Engineers are responsible for making technical debt visible. Here are a few ways to mitigate and manage technical debt in your products:



1. Keep a log of debt on your project for future conversations
2. Discuss during backlog grooming
3. Establish coding and documentation standards
4. Familiarize yourself with common design & architecture patterns
5. Be aware of new technologies


### Story Point

Engineers can help the team by helping to point stories. They can help estimate the amount or complexity of the work. Since engineers understand the work involved to fulfill a requirement,  they can ensure that stories are granular and right sized.


### Acceptance Criteria

Engineers can help the team by reviewing acceptance criteria before the sprint begins. The acceptance criteria should be clear and free of interpretation.


## Development


### Technology Stack

Selecting the right technology stack is important. Teams perform better when they have control of the tools and technologies. Here are a few things to consider when selecting tools and technologies:



1. Is training necessary?
2. Are the skills and knowledge required common, or is the technology very niche?
3. Is the technology mature enough to adopt?
4. Are there any costs?
5. Is there support for the technology within the current continuous integration process?
6. Can the technology be deployed to all environments?
7. Can the technology be managed in all environments?


### Continuous Integration

Continuous integration is a process that automates aspects of software development.


### Testing

Building testing into our products provides us the confidence that we need to quickly deliver new features without the fear of breaking our products. The test pyramid depicts the types of test we can author along with the general distribution.


#### Unit

The unit test is designed to test a small, singular component. The tests are easy to author and maintain and thus often represent the largest portion of tests within the code.


#### Contract Testing

TDD for micro service architecture, contracts are written on what will be consumed and then consumers and producers are tested against these contracts.  Eliminates the need for test environments that have all services running and at a specific version.


#### Integration

The integration test is designed to test between components. A typical example might be integrating with a database or a provided REST service. Integration tests require that you stand up not only your product but also the components with which you integrate. For this reason, they require more time and effort than unit tests. They often times are the second most frequently used test.


#### End to End {#end-to-end}

The end to end test is designed to test through your stack starting at the front end. The tests require the most time and effort to write and maintain. For this reason, they often represent the smallest portion of your tests.

For further reading take a look at a the list of curated resources



* [https://martinfowler.com/articles/practical-test-pyramid.html](https://martinfowler.com/articles/practical-test-pyramid.html)


## Practices

Ceremonies


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

Test Driven Development is software development practice. The process starts with authoring a failing test and then implementing the functionality required for the test to succeed. Often times referred to as ???Red Green Refactor???, it consists of three distinct steps (red-green-refactor):



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

A key point here is that there is no such thing as "perfect" code???there is only _better_ code. Reviewers should not require the author to polish every tiny piece of a merge request before approving. Instead, the reviewer should balance out the need to make forward progress compared to the importance of the changes they are suggesting. Instead of seeking perfection, what a reviewer should seek is _continuous improvement_. A merge request that improves the maintainability, readability and understandability of the system shouldn't be delayed because it isn't "perfect."

Reviewers should _always_ feel free to leave comments expressing that something could be better, but if it's not very important, prefix it with something like "Nit: "to let the author know that it's just a point of polish that they could choose to ignore (Nit means nit-pick).



Note: Nothing in this document justifies checking in merge requests that _worsen_ the system's overall code health. The only time you would do that would be in an emergency.


#### Mentoring

Code reviews can be an essential function for teaching developers something new about a language, a framework, or general software design principles. It's always OK to leave comments that help a developer learn something new. Sharing knowledge is part of improving the code health of a system over time. Just keep in mind that if your comment is purely educational but not critical to meeting the standards described in this document, prefix it with "Nit: "or otherwise indicate that the author doesn't need to resolve it in this merge request.


#### Principles



* Technical facts and data overrule opinions and personal preferences.
* On matters of style, the style guide is the absolute authority. Any purely style point (whitespace, etc.) not in the style guide is a personal preference. The style should be consistent with what is there. If there is no previous style, accept the author's style.
* Aspects of software design are seldom a pure style issue or just a personal preference**.** They are based on underlying principles and should be weighed on those principles, not simply by subjective opinion. Sometimes there are a few valid options. If the author can demonstrate (either through data or based on solid engineering principles) that several approaches are equally good, the reviewer should accept the author's preference. Otherwise, the choice is dictated by standard principles of software design.
* If no other rule applies, then the reviewer may ask the author to be consistent with the current codebase, as long as that doesn't worsen the system's overall code health.


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

Your application will exist in numerous environments including development, staging and production. For this reason, it is important that your application can be configured easily. Keep in mind that your application is likely to end up on a platform like Kubernetes where managing the lifecycle of an application is important. The standard practice is to expose configuration via granular environment variables. The configuration defines a contract with the tools that manages your application???s lifetime. For further information, check out the [config](https://12factor.net/config) section on [12factor.net](https://12factor.net/)


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
