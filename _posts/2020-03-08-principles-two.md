---
layout: post
title:  "My Top Software Engineering Principles - Part Two: Cultural Guidelines"
categories: [Company Culture, Leadership]
excerpt_separator: <!--more-->
---

This post is the second in a three-part article discussing the core principles I follow when designing, developing and deploying applications for the iOS platform. In the first part of the article, I outlined some low-level concepts used to increase app stability and communication on a more technical level. In this next part, we are travelling up one level of abstraction, so to speak. The following are ideas that can be used on a team or company level to improve overall communication and engineer efficiency across the board.

 <!--more-->

If you haven't already taken the time to read the first part of this article, it's not entirely necessary, however, if you'd like some more context on my working style, it [might be worth reading](/principles-one).

Without further ado, here are my mid-level cultural principles:

## Agile Software Development Methodologies

[Agile](https://agilemanifesto.org){:target="_blank"} is a methodology for software development encompassing a series of core principles, utilised to create high-quality software and deliver value to project stakeholders faster than otherwise possible. There are two main "frameworks" which aim to formalise Agile Software Development into a structured template, called [Kanban](https://www.atlassian.com/agile/kanban){:target="_blank"} and [Scrum](https://www.atlassian.com/agile/scrum){:target="_blank"}. These two frameworks are mostly the same, however, I believe the key difference is in the way software is delivered.

Kanban is on a "continuous" basis, and releases are deployed simply when it's determined that value has been added to the product. Scrum, on the other hand, is split into time-blocked sprints, giving more time to deliver features, after which software releases are deployed regardless of what is included at that time.

I tend to prefer Scrum as an Agile process over Kanban, as I find it suits mobile application development far better. With TestFlight, iTunes Connect and the App Store review process, there is always a certain overhead when deploying an iOS app, and it's important to factor this time when planning work-loads at the beginning of a sprint.

Scrum simply facilitates this better - 2 weeks is a decent length of time to add some value to an application, and perform the release process. Any longer, and you compromise on the amount of data and crash reports you can collect from having your new release in the hands of users. Any shorter, and you will find yourself spending all your time dealing with deployment rather than adding concrete value to the product itself.

It's important to note that both Kanban and Scrum are simply templates for a team to adapt and use. Like anything in Software Engineering, it's important to know why frameworks, tools and products exist and understand the problem they are trying to solve - only then can you use these tools to their full potential.

## Asynchronous Communication

Hiring within the technology industry is hard, and companies are increasingly looking further afield to recruit talent, either with only a few remote employees or entire distributed teams such as Todoist and GitLab.

Working from home part-time is also becoming more popular, with many companies offering flexible working and a remote work policy, and employees visiting the office 1-2 times a week.

Working from home some of the time, or even entirely remotely can be amazing for fully concentrating and getting deep-work done, and also has a myriad of quality of life benefits, especially for those with children or accessibility issues.

This can come at a price however, as remote working undoubtedly makes communication more difficult, and without the correct processes in place, can cause problems. As an engineer who's worked in remote environments before, I've experienced these problems first hand, including a lack of communication across the team, and social isolation.

Through using asynchronous communication methods, and promoting a healthy culture of asynchronously at your company, a lot of these problems can be mitigated. Concepts include:

- Software: Correct usage of project management software such as [Jira](https://www.atlassian.com/software/jira){:target="_blank"} or design tools such as [Zeplin](https://zeplin.io){:target="_blank"} can update team members on progress automatically.
- Documentation: Have a set of high-level cultural guidelines your team or company can use to unify their behaviour and use as a reference for how to communicate internally.
- Video calling: Use high-quality video calling software such as [Zoom](https://zoom.us){:target="_blank"}, and make sure to have all the information necessary before the call. Take notes and update documentation after the call.
- Messaging: When using instant message clients such as [Slack](https://slack.com/){:target="_blank"}, take the time to write long, detailed messages with all the information the recipient might need to respond, and don't expect an immediate reply, they may be busy or even asleep in the case of time-zone differences.

These guidelines also have the advantage of improving knowledge transfer, as information is automatically documented or achieved when changing hands, which can also be a lifesaver when onboarding a new engineer.

## Coding Standards & Linting

The technology industry moves quickly, and iOS app development is no exception. Every year there are new frameworks released, Swift is updated and old API interfaces are deprecated. Coupled with changing business requirements, this all means your codebase will never be static, and any low-level documentation you choose to write for a project will quickly become outdated - and outdated documentation is even worse than no documentation at all!

Instead, your code should be self-documenting. In other words, It should be easy for someone jumping into your code to immediately understand how the different components react with each other, and the logic flow of each function or class. There are entire books written about code health, but a few main tips are:

- Group similar levels of abstraction together, both in code and architecture
- Choose simple, descriptive names for your types and files
- Don't overcomplicate your technical solutions - [You aren't gonna need it](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it){:target="_blank"}
- Don't do [unnecessary refactors](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming){:target="_blank"}), a working solution is better than no solution
- But also, [don't repeat yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself){:target="_blank"}, and refactor if something obviously needs a new level of abstraction
- Your code should not require comments unless it's doing something crazy that warrants further explanation 
- [Linting](https://github.com/realm/SwiftLint){:target="_blank"} can ensure all members of a team are unified on a coding style, enforcing certain coding standards and making code easier to read. Bear in mind some there will inevitably be disagreements on which linting rules to use within a project!

## High-Level Documentation

One type of documentation I truly believe is worth writing is high-level cultural guidelines. It's important as a team to have a shared understanding of your approach to problems and communication methods. It's almost like an informal contract, that everyone can refer to in case of ambiguity or disagreement.

Note this type of documentation is not written by solely the team leader, but is a collaboration of everyone's ideas and feelings, and will evolve with time. If everyone feels their voice is heard and they have a say in the culture of the team, I think it helps everyone feel more involved.

Another style of documentation worth writing is technical reference sheets for projects. An example of this could be a list of dependencies, tools and online platforms your team uses, and a short explanation for each (it's often easy for this information to be lost over time). You could also include short tutorials for the project including "Getting Started" or "How to Deploy a Build".

Another example of useful high-level documentation are design-docs for new features or large architectural improvements. This helps the team organise their thoughts, explain the value of the new feature improvement, and centralise knowledge.

## Pair Programming, Whiteboarding & Code Reviews

Software engineering is about much more than just coding, it's important to have a culture of discussion where everyone can have their voice heard, lessons can be shared and disagreements can be resolved.

Coding is inherently an intimate, high-concentration activity, and requires an environment where you can focus on the problem at hand, and the best possible solution.

I believe pair-programming has a lot of value when used as a teaching tool for more junior engineers, as it allows you to see their level of understanding and the way they approach a problem, rather than simply the outcome of the work through a pull request, later down the line when it becomes frustrating to make large changes.

When working with more senior engineers however, I believe it's best to trust their ability to solve the problem independently, in which case pair programming actually blocks productive thought and stifles creativity.

As an alternative, for highly complex tasks, I would suggest high-level whiteboarding sessions.

Provided every member of the team has performed their due diligence and is well-versed in the topic we are discussing, these whiteboarding sessions can be invaluable in approaching problems from alternate viewpoints, and creating novel solutions. Software Engineering is a creative endeavour, and I believe discussing tasks at a high conceptual level over a coffee and a whiteboard is more effective and pair-programming in this instance.

Another invaluable tool I use for mentorship is the use of frequent code reviews, giving validation of someone's work, with honest but constructive feedback. Code reviews also give the advantage of being an open platform, through which any team member can jump in and give feedback.

Because of the nature of written communication, sometimes it's easy to miscommunicate the tone you are trying to achive, resulting in misunderstandings or disagreements. To mitigate this, I use a system of emojis to signal my intent, as follows:

<ul style="list-style: none; padding: 0;">
<li>👍&ensp;I love this change! Good work.</li>
<li>❌&ensp;This needs changing, here is a suggestion.</li>
<li>❓&ensp;I need clarification on something</li>
<li>🔎&ensp;Nitpicking, you can change it or leave it as is</li>
<li>💭&ensp;Thinking out loud - Have you considered x?</li>
</ul>

## Conclusion

I hope you enjoying reading about the mid-level concepts I employ as part of my work to improve team efficiency. Having the right cultural guidelines in place can really make a difference in the motivation and efficiency of your team.

 In the next post, I will be focusing my the final five principles - these are much more conceptual and include Honesty, Sustainability and Inclusivity in technology.
