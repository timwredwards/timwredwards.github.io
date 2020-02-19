---
layout: post
title:  "Achieving Success Through Continuous Integration"
categories: [DevOps, Company Culture]
excerpt_separator: <!--more-->
---

Continuous integration (CI) is defined as:

>  "a development practice where developers integrate code into a shared repository frequently, preferably several times a day. Each integration can then be verified by an automated build and automated tests."

<!--more-->

While this definition is vague, I've seen many implementations of CI pipelines across different companies, and it seems there is some confusion about the problem that CI aims to solve.

## The Problem

Some companies see their repository as a dumping ground for code, and their build system as a way of merely automating a test suite, but this misses the point entirely.

CI is a *philosophy*, not a tool. The build systems are the tools; Fastlane, Travis, Bitrise, and even git itself are tools to achieve continuous integration of work within a team.

CI in its purest form simply means keeping all team members synchronised, and is achieved by committing code often and exposing it to the team.

#### Advantages of Continuous Integration

- Because you know everyones work is merged to the primary branch, you can safely pull and avoid nasty merge conflicts.
- The entire team gets exposure to everyones work, raising potential issues earlier, and sparking big-picture discussions, such as architecture and system design.
- It's far easier to review many smaller code diffs than one massive diff, making engineers lives easier.
- There can be unexpected interactions or conflicts between system components, which are only exposed in an integration test. The earlier the components are tested together, the earlier the interaction is discovered. For example, two engineers write code to present modal controllers on separate branches, when they are both merged, the presentation logic breaks.

If some code is not yet open for review, from the teams perspective, it's a liability and should be reviewed as soon as possible. *That* is continuous integration.

## How to achieve Continuous Integration
Making code more CI-friendly can be as simple as breaking down features into smaller modules.

For example, if you're tasked with downloading a JSON file, decoding it, and displaying the result, you could first open a pull-request for the API call, then another for the JSON decoding, then finally another for the UI. This is a great way to get your code integrated into the primary branch sooner, without introducing instability.

Another example is if you're working on a navigation flow, you could systematically write the view controllers and open pull-requests for each, only presenting the new UI when all the other work is finished. This way, all your work has already been reviewed by the time the feature is finished, and there are no nasty massive pull-requests for your team to review.

The ultimate solution is to use remote feature flags, with either an in-house solution, or a behavioural analytics framework such as [Mixpanel](https://mixpanel.com){:target="_blank"}. Many large companies use these tools to decouple their engineering workflow from their feature availability, which is often why you see release notes for these apps as "Bug fixes and other improvements"; It's irrelevant to the end user what's in "this release".


## Continuous Integration in Practise
Understanding and using CI effectively will result in code being committed more frequently, and more pull-requests being opened. As a result, this does mean engineers need to be receptive to new pull-requests and review them as soon as possible. *An open pull-request is a dependency that should be resolved.*

In order to alleviate some of the stresses of CI, make sure to write a build system which is robust and uses generalised tooling such as [Fastlane](https://fastlane.tools){:target="_blank"}.

It's also inadvisable to enforce any overly zealous requirements such as linting. You can display warnings, sure, but failing a build because of something like linting will slow down the feedback loop.

> Perfection is the enemy of progress. - Winston Churchill

## CI in an Organisation

CI can, by extension, also apply to design and product teams:

- Designers can use tools such as [Zeplin](https://zeplin.io){:target="_blank"} to notify engineers of design updates faster, further tightening the feedback loop.

- Product managers can do the same: speak to the team about changes in requirements sooner, don't wait until a sprint planning meeting.

- Testers can run high-level smoke tests or even automated UI tests to raise issues earlier, again tightening the feedback loop.

## Conclusion

Developing high-quality software is an ongoing effort, and I believe continuous integration can earlier expose potential issues in code, raise bugs sooner and help teams perform better, given the correct tools and culture.

Thanks for reading, if you have any questions or comments, please use the contact button at the bottom of the page to get in touch.

Tim
