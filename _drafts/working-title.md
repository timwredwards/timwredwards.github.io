---
layout: post
title:  "A History of iOS UI Architectures"
categories: []
excerpt_separator: <!--more-->
---

System architecture design in mobile app development in the modern age is crucial, there was a time where simple architectures could get you pretty far, however apps are now so feature-rich, there is simply no way to stay on top of the level of complexity required without using a pattern of organising your code into a set of functional modules with distinct responsibilities. It's for this reason that system design and SOLID principles are becoming increasingly important in mobile app development.

<!--more-->

With the advent of Apple's SwiftUI and Combine reactive programming framework, thsi is only becoming more true. Reactive programming is a totally new paradigm to the way we write apps traditionally (imperitive programming).

System architecture design is a complicated topic, and not something I could cover in one post, however a large part of the complexity in iOS apps particularly, is in UI code. Because of the highly dynamic nature of user interfaces, including touch events, notifications, animations, and synchronising model data, UI code can often get extremely messy within iOS apps, and so a slew of design patterns have cropped up to help us organise this complexity.

It's worth noting that there's been a bit of an obsession with UI patterns in the iOS community, and with lots of engineers trying to find the 'perfect' solution that will fix all their architectural woes, however this is misguided. All design patterns have their advantages and disadvantages, and their effectiveness will depend upon the context in which they are used. Design patterns do have some value as a template or guideline of how to structure your UI code, however they are most powerful when you understand the underlying principles of architectural design, and why these patterns came to exist in the first place. For a more in-depth look at these principles, I highly recommend you read the work of Robert C. Martin, including his 'SOLID' principles, and especially his book "Clean Architecture: A Craftsman's Guide to Software Structure and Design", on which a lot of my architectural design knowledge is founded.

https://en.wikipedia.org/wiki/SOLID
https://www.oreilly.com/library/view/clean-architecture-a/9780134494272/

For now, I will simply outline the existing UI design patterns, the problem they all aim to solve, and their advantages & disadvantages:

# MVC

MVC was born way back in the Smalltalk era as a pattern for building front-end desktop applications. It was later adopted by Apple for use in OSX app development, notably using Cocoa bindings. After Apple released the first iPhone back in 2007, it was natural they would bring MVC to iPhone OS, and encourage it's use as the de-facto UI design pattern.


EXPLAIN AND DIAGRAM



This worked well for a long time, as apps back then were fairly simple in their functional scope, but as the iOS ecosystem grew, apps became more complex, introducing new features like remote notifications, intricate 60fps animations, and new hardware capabilities. This exponentially increased the systematic complexity of mobile apps, to the point where MVC was became unsuitable. For this level of scope, alternatives were needed.

Because of the growing complexity of iOS codebases, engineers were looking for ways of increasing the robustness of their code, and catching regressions when before they got into a production environment. This is when unit-testing and TDD started becoming popular tools for iOS engineers, enforcing their code worked as it should. The problem is, the way Apple implemented MVC is not well suited to 

Advantages
- arguably the most simple architecture to understand, and what most beginners use by dumping everything in the view controller
- Blessed by apple, used in their documentation and code examples, meaning traditionally their API design was based around MVC.

Disadvantages
- Provides no formal structure in a team, kitchen sink syndrome.
- Tightly couples UI and business logic, doesn't scale well in complex apps.
- Hard as shit to unit test as it's hard to mock UI elements.

A lot of people shit on MVC, but can still be used today if done properly.

If you extract a lot of your business logic into a service layer, and your VC is simple, it's much easier to handle.

You can also extract view info to UIViews rather than VCs

You can also put multiple VCs on one screen.

# MVP

EXPLAIN

Advantage
- Still pretty simple compared to MVC
- BC we can keep dumb view, we can test presentation logic

Disadvantages
- Provides some structure, but still kitchen sink syndrome, just moved the problem
- While presentation logic is testable, routing is not

An improvement, but we can do better.

# MVVM

- MVVM introduces the concept of a ViewModel.

- ViewModel binds itself to the ViewController and pushes new data when it's updated, which has boilerplate.

Advantages
- Bindings mean we can propagate changes from business logic layer to UI automatically
- We can convert model data to primitives for views in the VM
- Testing is super simple, just compare the ViewModel data.

Disadvantages
- It's not obvious what to put in it... Data structure? Method calls to services? Bindings?
- It's a really ambiguous architecture and unless you have formalised processes within your team and understand the benefits, you can't use it, which defeats the point.

Testing is starting to become easier, however this is not scalable for complex apps.

# MVVM + RxSwift

An extension of MVVM

RxSwift introduces the reactive programming paradigm as a method of binding the VM to the view

Advantages
- Reduced boilerplate compared to MVVM
- Potential to use reactive programming across the app including service layer.

Disadvantages
- Hard to debug
- Dangerous to change programming paradigm, big irreversible decision.

Because of Combine, this seems to be the way apple is heading.

# VIPER and friends

Included and friends bc there are a lot of complex patterns that do mostly the same thing.

Advantages
- The ultimate separation of concerns
- Provides a formal location for logic
- Very testable, including routing

Disadvantages
- Very verbose, can be hard to parse
- Overkill for simple applications
- Data is still multi-directional through the presenter, not always easy to debug

# The future

- With SwiftUI and combine, Apple has chosen reactive programming.
- SwiftUI solves the single source of truth issue, with bindings.
- Eventually we'll have bindings from CoreData, it's still early days
- Combine is the UI-agnostic equivalent, used for service-layer data binding
- Because we have Apple's blessing with Reactive programming, if I was starting greenfield today I would use RxSwift with MVVM, with a view to move to Combine as soon as iOS 13 is heavily adopted by the user-base, and a long-term view to migrate all UI code to SwiftUI, but we're a long way away from that bc of performance issues and missing functionality.

# Conclusion

Again, stick to solid principles
Future is exciting


![Bad design skills](/images/diagram.png){:width="" class="dark-mode-invert"}
