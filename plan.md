# Dependency mgmt 3 parts
## Part 1: Dependency mgmt at the code level
- The word dependency mgmt can be scary
- Like many things in tech, it can mean something different depending on the layer of abstraction you're working at
- Depedency mgmt is about organising the references to your dependencies in a way that's extensible and testable.
- Dependency mgmt isn't about reducing absolute dependencies, less dependencies are always better as it makes your code more robust, but dependencies are an inevitable part of software, otherwise if no module talked to anything else, then functionality wouldn't exist.
- In code, it simply means when a type references another type, that's a dependency, if you changed the other type, it would fuck up the first type somehow
- On a code level, this means extracting the responsibility of creating those dependencies to another type.
- In SOLID principles, types should only be responsible for one thing. A type should not be responsible for a) it's primary responsibility and b) creating it's dependencies. That means it's dependencies must be created in another object, and passed to this object. This process is called dependency injection.
- Dependency injection can be done a number of ways, but the most common is constructor injection. This is good bc it enfoces no optionals, and you can always be sure an object has everyhting it needs to function.
- There is also property-based injection which is more annoying or dangerous if you use !.
- There is also parameter based injection which can be useful for passing factories, however can be very verbose and annoying.

## Part 2: Dependency mgmt at an architectural level
- On a project level, this means organising types into well constructed frameworks, so different functionality can be imported on an as-needed basis rather than importing everything from web services to font helpers just to write a simple app.
- This also means you can reuse domain-specific frameworks accross targets, and even your entire company.
- It also means not using 3rd party dependencies. iOS moves quickly, and they can break if not well maintained. Could your company maintain this lib if needed? You need to understand the entire framework, only include it if it's well maintained, is going to save you actual time, not increase project complexity or fuck up onboarding (RxSwift), and you could take it over if needed.
- Bring exernal services into your webapi, manage keys and usage, and reduce client complexity. Thin client is good if possible.

## Part 3: Dependency mgmt at company level
- Dependencies are not just in code or across frameworks, they can also be in the architecture and culture of the company.
- Whenever a team member needs something from another team member, that's a Dependency.
- For example:
- Testers need the newest build (both internal and external, even external testers are unknowingly witholding value if they don't have the latest beta)
- Engineer needs designs
- Design needs copyrighting
- Copyrighting needs C-level approval
- etc.
- TODO: Update provide async comms stuff here
- Reference agile etc. Do some reading.
- Structure your work to allow parralelism.
- Never allow someone else to be blocked.
- Automate as much as possible. If the answer to a question can be automated, do it. Always be striving to improve the companies workflow.
- Seem to remember: treating meetings seriously and having notes before. And making notes for afterwards, document meetings properly.
- Rely on async comms better, properly structure your questons to each other and don't expect a rely now, do something else.
- Have dedicated team-members for domains.
	- CI and devops
	- Testing
	- Code quality
	- Deployment
- Context is important. Depends on the stakeholders.
- Use high level documentation.
- Use universal terminiology. Doesn't matter if it's technical, as long as everyone understands it. If they dont? Help explain. Document this also.
- Everything is getting more cultural, be aware and don't use culture specific language or idioms.
- Be efficient and direct.

# iOS ARCHITECTURE IN 2020
- MVC + cocoabindings
- Why MVC worked at the time
- Why MVC doesn't work now
- MVP, an improvement
- MVP, kitchen sink syndrome
- MVVM, also kitchen sink syndrome
- MVVM and RxSwift, better but hard to debug, and who wants dependencies? (link to dependency reduction)
- VIPER for separation of concerns, but some problems.
- VIP for unidirectional data, same problems as VIPER
- SwiftUI + Combine, back to MVVM. Bindings solve the source-of-truth problem.
- I would not use Combine now, I would switch to RxSwift until iOS 13 is adopted.

# Mobile engineers thinking they are special
- iOS and android both think their os is better
- Same as Mac vs Windows vs Linux, console vs pc gamers.
- I've worked in companies where the front-end teams literally never talked to each other.
- Worse still, when it's engineering vs everyone else.
- Why is this bad
- Frameworks are both opaque and have restrictions, not a bad thing in terms of security but indirectly encourages tribal behaviour, this also comes across to engineering.
- A lot of engineers, especially juniors don't understand the social dynamics of a comapny, and that you're a team. In a company with a healthy culture, if your collegeues succeed, you succeed.
- Writing business logic twice or three times sucks but is sometimes required. There's no convincable cross-platform solution yet. React-native sucks, writing c++ libraries sucks, hosting a local web server is slow and introduces threading issues. There is talk of kotlin cross-platform frameworks but this is still in it's early stages.
- Even with a thin client based stack, this has it's disadvantages, mostly speed. And there will always be cross-platform code.
- Writing cross-platform use-cases and behavioural / unit tests is possible and useful. The ios, android and web teams should be working closely to sync-up their business logic so if bugs arise, tests can be added to all platforms and everyone benefits.
- Bugs come up earlier
- Tests are written
- Entire stack becomes more robust
- Centralized knowlwedge is reduced, meaning if someone leaves it's less of a biggie
- Also, it's easier for everyone to understand the environment of a problem.
- Also, shared terminology is good for comms.

# Continous integration

Notes:
CI is a philosophy
Build systems are a tool

Advantages:
Your branch won't go out of date with the primary branch, no merge hell
Your team gets exposure to the status of your work, brings up architeectural big issues
Way easier to code review a smaller diff
Unseen interactions between two components can cause problems. Sooner this stuff is integrated together the sooner these bugs arise.
This applies to development, testing and deploment.

How to make CI a reality?:
Break large features into chunks.
Some modules don't have to be touched.
View Controllers don't have to be presented.
API wrappers and services don't have to be called.
These can be unit tested, code reviewed, merged and deployed without being used.
Even better, have remote feature flags. Completely seperate development and deployment from feature releases.

Of course, this means more code reviews.
This is good, but more overhead for the team.
A code review waiting is a dependency that needs to be resolved. Help your team members and review.

CI can also apply to design and product teams:
Get incremental designs to engineers and provide notifications (Zeplin etc.) when updates occur.
Same for product, consistently expose the needs of the shareholders, don't wait until sprint-planning.
Same for manual testers, run smoke tests or high-level automated UI tests to raise issues earlier.

Remember: high-quality software is a continious effort, and the more synced an organisation is the better.

# Async comms
TODO:
- What is it
- Why is it good
- Why is it bad
- Companies fuck it up constantly
- Read doc you made for hibooks

Useful when you're in different places
Has value even in-office, for allowing flexibility and quality of life
Automatically archives info - good for reference onboarding

Never let someone else be blocked
Write high-level documentation, tools used, best practises etc. You don't want it to have to change
Unit tests and documentation  help compensate for lack of shared understanding
Have engineering domains in the team, see other article
Have formal development process in place, don't rely on word-of-mouth
Weekly engineering reports, high level knowledge for company wide
Weekly engineering sync-up, everyone brings up points and discuss internally
Proper on-boarding checklist

Use async tools when possible, long slack messages, documentation and design, zeplin etc.
Use long messages, explain clearly and deeply, provide all the info needed. It might also help you understand the issue.
Don't expect a reply at once, try to encourage parralelism in your workflow, have multiple things to do.
Use simple language, avoid locallised jargon.
Change your language context based on who you're speaking too. Technical / product / other etc.
Have a shared domain language. Favourites / Liked / Bookmarked / Wishlist etc.
Meetings: do you really need one?
Be aware of time zone differences and work-loads.
Write an adgenda of stuff to discuss
If one of you are on laptops, everyone should be on laptops. It levels the playing field.
Write actions, decisions, points of interest. Document this in public documentation. This is a reminder and also documentaiton for absent members.


# Future Ideas
- Logging vs error propogation on iOS
- Testing architecture and mocking

