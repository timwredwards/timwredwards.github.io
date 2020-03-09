---
layout: post
title:  "My Top Software Engineering Principles - Part One: Technical Concepts"
categories: [Testing, DevOps]
excerpt_separator: <!--more-->
---

Writing high-quality software for any platform is tough, and iOS is no exception. Mobile app development is a strange hybrid of front-end, back-end and embedded systems engineering - you need to understand animation and view constraints, databases and concurrency, and also memory and CPU management, to name a few.

This is especially true in today's world of hyper-complex mobile applications - gone are the days of simple flashlight apps and gimmicks, the iOS applications of today often contain dozens of features, have access to more hardware capabilities and handle more external environments than any other platform (see: Germanys flaky 3G network!).

<!--more-->

So it's not simple to create an app, especially one that scales well to millions of users and is stable and extensible enough to handle changing business requirements. To cope with this level of complexity, engineers will always have a set of principles or preconceptions they carry with them throughout their career. Some ideas may stay forever, while some may only last a few years before being replaced with new information. Not every engineer will formalise these principles, however, every engineer will have a unique way in which they approach a problem.

This is the first in my three-part attempt to document my principles, and how I approach iOS projects, companies and the tech industry as a whole. It's a collection of concepts I believe are important in creating high-quality software, and without them, I would be quite lost.

## 1) SOLID Principles

Software Engineering at its core is problem-solving. How it differs from more "academic" subjects such as Mathematics or Physics is the level of creativity involved in how those problems can be solved. In Software Engineering, each solution has advantages and disadvantages, and it's up to the engineer to decide which is the more appropriate route to take. No solution is more objectively "correct" than another (in most instances!) and context determines which solution is most effective in that environment.

Software engineers communicate the merits and downsides of each solution using a set of shared principles, which have been tried-and-tested to improve the quality of software. A good example of those are [SOLID](https://en.wikipedia.org/wiki/SOLID){:target="_blank"}, which while slightly outdated due to it's strong links to object-oriented programming paradigms, are still useful in Swift development to create software which is modular, extensible and robust.

By having a codebase that is modularised and split into layers, the advantages are numerous:

- It's easier for new engineers to parse the code and understand how the system fits together as a whole.
- It's easier for existing engineers to know where to find a particular component or reference.
- It's easier to unit test the codebase through proper dependency injection and mocking of components.
- It's easier and safer to extend functionality, as edits will touch less components than otherwise.

All of this means apps are easier to understand, extend and scale.

## 2) Architecture Design and UI Patterns

UI patterns are the formal application of architectural design theory to mobile applications. They are essentially structured blueprints of how to layout modules in a mobile application, most specifically on the UI layer.

UI patterns are generally attractive to developers because they provide an obvious place to store different sets of logic, without having to consider architectural best practices every single time. A good example is VIPER - it's immediately obvious where all View, Interaction and Presentation logic belongs.

Unfortunately within the iOS community, there seems to be an over-reliance on UI patterns and folks using them as a crutch for lack of architectural knowledge, rather than a jumping-off point for a custom design. It's convenient to have a set of pre-made architectural templates you can pick off the shelf while developing an app, but in reality, it's much more complex than that. All UI patterns will have their positives and negatives - some will have more components but be more rigid (VIPER) while others will have fewer components but be more flexible (MVC, MVVM).

Ultimately, while UI patterns can be useful, they are inherently subjective, and designing an architecture for your application is entirely contextual. If you're going to use them, it's important to have a solid base understanding of the architectural design and why these patterns exist in the first place.

The one situation in which I'd say some kind of formalised UI pattern is necessary is when working as part of a larger team - it's essential to have a domain design language, and architecture is part of that. It doesn't matter which pattern it is, but there needs to be a shared understanding of what everyone is talking about when they are in the same room.

## 3) Unit-Testing

Developing robust software is hard - everything can be working fine on your machine, but fall apart when it's deployed to a production environment, causing crashes and ugly App-Store reviews, as well as losing you users and money. There's so much that can go wrong when developing software, it's important to have some kind of safeguard to give us a baseline level of confidence that the work we've submitted isn't liable to fail. That's where testing comes in.

Automated testing on Apple platforms is a relatively new idea, and not particularly well documented in the Apple developer archives. Regardless, it's something which can save some serious headaches if done correctly. By running our code against a suite of unit tests, we can verify logic is behaving as it should.

I think there is a misconception in Software Engineering in general that 100% code coverage is the golden goose, and every team should strive to hit it. I disagree - unit-testing is hard work and requires extra resources from your team, and so it's important to be selective about which parts to test. I'd recommend layering your application into several distinct layers, one UI application layer for every platform you want to support (iOS, macOS, tvOS etc), and a series of frameworks containing different logical abstractions. For example, the top Framework could contain high-level business logic, and you could have sub-frameworks for manipulating text, audio, RESTful APIs, databases etc. By separating your logic like this, you only need to hit a high percentage of code coverage for the layers that contain crucial logic.

This separation of code into layered Frameworks is good practise anyway, and will make your code easier to read, and more reusable across projects or even teams within a company!

## 4) Continous Integration

No code is written in a vacuum, and everything you write will affect your team, your company and your users. When creating software as part of an engineering team, it's crucial to be as synchronised as possible, to avoid miscommunication and blockers.

[Continuous Integration](https://en.wikipedia.org/wiki/Continuous_integration){:target="_blank"} (CI) is a philosophy that encourages engineers to get their code merged into a primary branch of work as soon as possible. This primary branch is locked, and all code must go through a review from other engineers. It's so easy to make a mistake while programming that's only caught when someone else takes a look and enforcing reviews from other engineers means bugs are caught earlier and the quality of the software increases.

This also has the advantage of giving everyone on the team exposure to each other's work, sparking high-level architectural discussions earlier and keeping everyone up to date.

## 5) Continous Deployment

Creating high-quality software is all about feedback. The faster feedback is received by the company from users, the faster they can iterate about their user's needs and wants. This plays into the Agile methodology, but for now, I'm talking simply about [continous deployment](https://en.wikipedia.org/wiki/Continuous_deployment).

After a build is released, and users begin to update, you immediately start to get feedback in the form of crash reports and analytical data if you're using a CRM tool such as Leanplum or Localytics. This data can be used by the product owners of the company to make intelligent business and product decisions. The more often this happens, the more guided the company is by their users, and the higher your chances of success.

Traditionally, application updates on most platforms were released when features were completed and bug fixes had been performed. In the current age of highly-complex multi-featured mobile applications, this has changed. Now, apps are often released on a strict rolling basis of 2-4 weeks, and features are enabled or disabled using an online config or A / B testing suite. This is often why you'll simply see "Bug fixes and improvements" in the release notes of some app updates - it's simply impossible for them to describe what's in that release because it's decoupled from the current feature-set.

## Conclusion

Hopefully, in this article I've provided some insight into my working style - iOS development is not simple by any means, but by utilising the ideas here, amongst others, it becomes easier to manage the level of complexity required by today's mobile applications.

In the next part of this article, I will be focusing on a higher level of abstraction - discussing ideas at the team and company level, such as Agile methodologies, code health and mentorship.

[Click here for part two](/principles-two)
