---
layout: post
title:  "My Top 15 Software Engineering Principles Part 2: CREATE A NEW TITLE"
categories: [Foo, Bar]
excerpt_separator: <!--more-->
---

This post is the second in a three-part article discussing the core principles I follow when designing, developing and deploying applications for the iOS platform. In the first part of the article, I outlined some low-level concepts used to increase app stability and communication on a more technical level. In this next part, we are travelling up one level of abstraction, so to speak. The following are ideas that can be used on a team or company level to improve overall communication and engineer efficiency across the board.

If you haven't already taken the time to read the first part of this article, it's not entirely necessary, however if you'd like some more context on my working style, it might be worth reading (LINK)

Without further ado, here are my mid-level principles:

## Agile Software Development Methodologies

Agile is a methodology for software development encompassing a series of core principles, utilised to create high-quality software and deliver value to project stakeholders faster than otherwise possible. There are two main "frameworks" which aim to formalise Agile Software Development into a structured template, called Kanban and Scrum. These two frameworks are mostly the same, however I believe the key difference is in the way software is delivered.

Kanban is on a "continuous" basis, and releases are deployed simply when it's determined that value has been added to the product. Scrum on the other hand, is split into time-blocked sprints, giving more time to deliver features, after which software releases are deployed regardless of what is included at that time.

I tend to prefer Scrum as an Agile process over Kanban, as I find it suits mobile application development far better. With TestFlight, iTunes Connect and the Apple review process, There is always a certain overhead when deploying an iOS app, and it's important to factor this time when planning work-loads at the beginning of a sprint.

Scrum simply facilitates this better - 2 weeks is a decent length of time to add some value to an application, and perform the release process. Any longer, and you compromise on the amount of data and crash reports you can collect from having your new release in the hands of users. Any shorter, and you will find yourself spending all your time dealing with deployment rather than adding concrete value to the product itself.

It's important to note that both Kanban and Scrum are simply templates for a team to adapt and use. Like anything in Software Engineering, it's important to know why frameworks, tools and products exist and understand the problem they are trying to solve - only then can you use these tools to their full potential.

// CONTINUE HERE

## Asynchronous Communication Standards

Hiring for technology roles is hard, and companies are now looking futher afield to recruit talent, and having employees that work 100% remotely. Many companies are also allowing their employees to work from home 2-3 days a week at home.

Working remotly or out the office can be great for deep working, and has many other advantages for quality of life and flexibility, however it does make communication harder. As someone who's worked in remote environments before, I know first hand how difficult communication can be, as well as other issues such as isolation and lack of social contact.

There are things we can do to make communication in remote sitatuions easier though, through proper use of asyncronous communication methods. Jumping onto a video call is fine, but disrupts work flow and is often unnessecary. Using the correct tools such as project management software, design sharing tools such as Zeplin, and writing high-level documentation can all help. Another trick is to treat messaging clients such as Slack and Google hangouts a little more like email - take real time to consider your messages and any questions you might ask, providing all the nessecary information and bearing in mind the reader may not be present at the time.

This also has the advantage of increasing knowldge transfer between employees, and automatically archiving all important information passing through hands, which is a lifesaver when onboarding a new engineer.

All in all, remote work can be hard, but taking an asyncronous-frist approach can really help in mititage potential misscommunications or fidelity loss.


## Coding Standards & Linting

The technology industry moves quickly, and iOS is no exception. Every year there are new frameworks released, Swift sytax is introduced and old API calls are deprecated. Coupled with changing business requirements,this means your codebase will never be static, and any low-level documentation you choose to write for a project will quickly become outdated - and outdated documentaton is even worse than no documentation!

Instead, your code should be self-documenting i.e. It should be easy for someone new reading your code to immediatly understand how different components reference each other and the logic flow of a function. There are entire books written about code health, but generally make sure to group similar levels of abstraction together, choose intelligent, descriptive names for your types and don't overcomplicate things because you can [LINK RULE OF THREE]. Comments are generally not nessecary unless your code is doing something really crazy that warrants external explaination.

Linting [LINK] can also be used to ensure all members of a team are unified on a coding style, enforcing certain coding standards and making code easier to read. Bear in mind there are diminishing returns on linting however, and some flexibility in coding style is inevitable, and enforcing too much may slow engineers down without much benefit.

https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)

## High-Level Documentation

One type of documentation I truly believe is worth writing is high-level cultural guidelines. It's important as a team to ahve a shared understanding of your approach to problems and communication methods. It's almost like an informal contract, that everyone can refer to in case of ambiguity or conflict.

Note this type of documentaiton is not written by solely the team leader, but is a collaboration of everyones ideals and feelings. If everyone feels their voice is heard and they have a say in the culture of the team, I think it helps everyone feel more involved.

Another style of documentation worth writing are technical refernece sheets for projects, and short tutorials on how to get started and perform actions. An example of this could be a list of dependencies, tools and online platforms your team uses, and a short explaination for each (it's often easy for this information to be lost). Another example is a "getting started" document or "how to deploy".

## Pair Programming & Code Reviews

Software engineering is about much more than just coding, it's important to have a culture of disucssion where everyone can have their voice heard, lessons can be shared and conflicts can be resolved.

Coding is inherinetly an intimate, involved experience, and requires an envinonrment where you can concentrate on the problem at hand, and the best way to solve this. While pair-programming can have some benefit in assessing someones ability to solve a task, or provide insight into the way someone approaces a problem, I often feel as though it blocks actual productive thought, and stifles creativity.

My suggested alternative would be to host high-level whiteboarding sessions surrounding an issue. Provided everyone has done their due diligence and is well-versed in the topic we are discussions, whiteboarding sessons can be invaluable in apporaching problems from alternative viewpoints and coming up with novel solutions. I would much rather discuss an issue or feature over coffee and a notepad than hunched over a laptop.

Another good alternative to pair-programming is frequent code reviews, giving validation of someones work, and construcitve feedback. This has the advantage of the feedback being self-documenting, and any member of the team can jump in and give their feedback.

In the end, I get excited about technology, and enjoy talking to other engineers about their experiences. I want to learn about peoples goals, and want to do whatever I can to help them achieve success. I simply feel that's eaiser to do in a conversational setting rather than next to a screen.
