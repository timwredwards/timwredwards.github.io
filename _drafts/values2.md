
---
layout: post
title:  "My Top 15 Software Engineering Principles Part 2: CREATE A NEW TITLE"
categories: [Foo, Bar]
excerpt_separator: <!--more-->
---


Agile Methedologies

Agile is a methedology for software development that encompases a series of core principles to create high-quality sofware and deliver value to project stakeholders faster. There are two main application "frameworks" that aim to formalise Agile methodologies into a process, called Kanban and Scrum.

These are mostly the same, however I believe the key difference is in the way software is delivered. Kanban is on a "continous" process, and relesaes are made when it's determined that vaue has been added to the product.

Scrum on the other hand, is split into time-blocked sprints to allow work on the product, after which software releases are deployed regardless of how much value has been added.

I tend to prefer Scrum as an Agile process framework, as I find it suits mobile application development far better. There is always a certain overhead to deploying an iOS app, with TestFlight, iTunes connect metadata and Apple review times. It's important to factor this time when planning work-loads at the beginning of a sprint, and Scrum allows this. 2 weeks is a good length of time to add value to an application, and perform the release process. Any longer and you comprimise ont he amount of feedback you get from having your app in the open. Any shorter, and you will find yourself spending all your time dealing with deployment rather than adding concrete value to the product.

It's important to note that both Kanban and Scrum are simply templates for a team to adapt and use. Like anything in Software Engineering, it's important to know why frameworks, tools and products exist and undertsand the problem they are trying to solve - only then can you use these tools to their full porential.


Asyncronous communication

Hiring for technology roles is hard, and companies are now looking futher afield to recruit talent, and having employees that work 100% remotely. Many companies are also allowing their employees to work from home 2-3 days a week at home.

Working remotly or out the office can be great for deep working, and has many other advantages for quality of life and flexibility, however it does make communication harder. As someone who's worked in remote environments before, I know first hand how difficult communication can be, as well as other issues such as isolation and lack of social contact.

There are things we can do to make communication in remote sitatuions easier though, through proper use of asyncronous communication methods. Jumping onto a video call is fine, but disrupts work flow and is often unnessecary. Using the correct tools such as project management software, design sharing tools such as Zeplin, and writing high-level documentation can all help. Another trick is to treat messaging clients such as Slack and Google hangouts a little more like email - take real time to consider your messages and any questions you might ask, providing all the nessecary information and bearing in mind the reader may not be present at the time.

This also has the advantage of increasing knowldge transfer between employees, and automatically archiving all important information passing through hands, which is a lifesaver when onboarding a new engineer.

All in all, remote work can be hard, but taking an asyncronous-frist approach can really help in mititage potential misscommunications or fidelity loss.


Code Health

The technology industry moves quickly, and iOS is no exception. Every year there are new frameworks released, Swift sytax is introduced and old API calls are deprecated. Coupled with changing business requirements,this means your codebase will never be static, and any low-level documentation you choose to write for a project will quickly become outdated - and outdated documentaton is even worse than no documentation!

Instead, your code should be self-documenting i.e. It should be easy for someone new reading your code to immediatly understand how different components reference each other and the logic flow of a function. There are entire books written about code health, but generally make sure to group similar levels of abstraction together, choose intelligent, descriptive names for your types and don't overcomplicate things because you can [LINK RULE OF THREE]. Comments are generally not nessecary unless your code is doing something really crazy that warrants external explaination.

Linting [LINK] can also be used to ensure all members of a team are unified on a coding style, enforcing certain coding standards and making code easier to read. Bear in mind there are diminishing returns on linting however, and some flexibility in coding style is inevitable, and enforcing too much may slow engineers down without much benefit.

https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)

Documentation

One type of documentation I truly believe is worth writing is high-level cultural guidelines. It's important as a team to ahve a shared understanding of your approach to problems and communication methods. It's almost like an informal contract, that everyone can refer to in case of ambiguity or conflict.

Note this type of documentaiton is not written by solely the team leader, but is a collaboration of everyones ideals and feelings. If everyone feels their voice is heard and they have a say in the culture of the team, I think it helps everyone feel more involved.

Another style of documentation worth writing are technical refernece sheets for projects, and short tutorials on how to get started and perform actions. An example of this could be a list of dependencies, tools and online platforms your team uses, and a short explaination for each (it's often easy for this information to be lost). Another example is a "getting started" document or "how to deploy".

Pair Programming & Mentorship

Software engineering is about much more than just coding, it's important to have a culture of disucssion where everyone can have their voice heard, lessons can be shared and conflicts can be resolved.

Coding is inherinetly an intimate, involved experience, and requires an envinonrment where you can concentrate on the problem at hand, and the best way to solve this. While pair-programming can have some benefit in assessing someones ability to solve a task, or provide insight into the way someone approaces a problem, I often feel as though it blocks actual productive thought, and stifles creativity.

My suggested alternative would be to host high-level whiteboarding sessions surrounding an issue. Provided everyone has done their due diligence and is well-versed in the topic we are discussions, whiteboarding sessons can be invaluable in apporaching problems from alternative viewpoints and coming up with novel solutions. I would much rather discuss an issue or feature over coffee and a notepad than hunched over a laptop.

Another good alternative to pair-programming is frequent code reviews, giving validation of someones work, and construcitve feedback. This has the advantage of the feedback being self-documenting, and any member of the team can jump in and give their feedback.

In the end, I get excited about technology, and enjoy talking to other engineers about their experiences. I want to learn about peoples goals, and want to do whatever I can to help them achieve success. I simply feel that's eaiser to do in a conversational setting rather than next to a screen.
