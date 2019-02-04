---
title: Why reduce tech debt?
date: '2019-02-04T12:00:00.000Z'
---

### What is tech debt?

Let's say you want a car but you don't have money for it. What do you do? One option would be to go to a bank and borrow some cash. Bank gives you the money and you buy a car - today! But now you are in debt. You need to repay all the money back to the bank and also some interest on top of it. The quicker you return money to the bank - the less is the total sum you pay for the car.

It works similarly in software development. You need to complete a feature - today! You do it in a dirty hacky way because you don't have time for proper design and implementation. So you cut some corners today hoping to refactor it later. But refactoring later is going to be more time consuming compared to initial clean implementation, because you'll need to make sense of the mess you've made first.

So technical debt is a metafor - every time you do bad things in code, you are accumulating some debt that will bog you down. Just like with real debt, you can take so much debt that all you'll do is repaying interest - no new work done anymore.

### Why is it bad?

The most obvious reason - it becomes increasingly hard to add features to a codebase that is overburdened with debt. I've worked on a project where it took more then a week to do some simple login form modifications. The code was very brittle and complicated. Before any tweaking you had to understand how everything around that form worked. Your tech debt may grow so big that you'll end up scrapping your codebase and starting a new project. Time is wasted.

Another reason is that tech debt discourages team members. Team is constantly getting blamed for not delivering on time. People in the office joke about code quality of the team. Developers hardly ever write new code - everyone is perpetually stuck in maintenance mode.

### What causes tech debt?

- Tight coupling and lack of modularity. Tightly coupled pieces of code are more brittle and require more maintenance time.

- Dev team doesn't write unit tests. Every time you change code, you are not sure if you broke something or not.

- Inexperienced developers tend to choose quick and easy short-term solutions over long-term ones because they don't know there's a better way.

- Business people pressure dev teams into releasing new features as quickly as possible because the market demands that feature now.

### How do you measure it?

Looks like there are no good ways to measure tech debt. All of them are very imprecise. Here's what people use for tech debt measurument:

- Code complexity metrics
- Tests coverage
- Issues count
- SonarQube reports
- Gut feeling

High code complexity and low tests coverage are usually found in codebases with lots of tech debt. But good results on these metrics don't guarantee low tech debt. Issues count is not really related to tech debt.

SonarQube is software tool that analyzes your codebase, finds code smells and approximates time needed to remediate all of them. It's cool and handy, but in real life we don't need to fix all code smells. Some code has legitimate reasons to be written in a way that seems sub-optimal. Or maybe some badly written piece of code is just a one-off method that will never be changed, so no one will repay that tech debt.

Gut feeling is unquantifiable by definition.

### What can be done?

Although there aren't any decent methods of measuring tech debt, there's no doubt that tech debt exists and should be addressed to avoid slowdowns.

#### Create a tech debt list

One thing you can do is to create a tech debt list. It can be in a form of publicly available Google Docs spreadsheet. This list will hold descriptions of all instances of bad code in your project, so you can plan improvements.

Every time you spot traces of a crime against code clarity, add a new entry to this list and specify:

- Short description
- Time needed to fix
- Impact on codebase / priority of fixing
- Location in code

Talk to your product owner to allocate some percentage of story points in each sprint for fixing these prioritized tech debt items. Hopefully this list will get shorter and shorter over time.

#### Checklists and Definition of Done

You may want to edit your Definition of Done or add checklists to pull request template. Include things like: "Newly incurred technical debt is added to Debt List", "Unit tests are written", "React components do not re-render excessively" or whatever suits your project to reduce newly created tech debt.

#### Write unit tests

Unit tests are one of the primary ways to keep tech debt at bay. Having good unit tests enables refactoring and testable code is generally less complex and thus easier to understand.

#### Modular code

Flexible codebases that can change over time without losing in quality consist of well defined modules. Try to compose your projects with modules that do one thing (Single Responsibility Principle) and are loosely coupled.

#### Share knowledge

If you think you know a better way to do something, try to educate your teammates about it. You can organize a meetup or just gently push your peers in the right direction during code review.

#### Identify tech debt hotspots

Adam Tornhill has an interesting idea about prioritizing tech debt. You should check out his [talk](https://youtu.be/SdUewLCHWvU).

In short: Tech debt that affects your project the most is related to modules that have high complexity and change frequently. Git history can help you find such modules. So addressing these hotspots will greatly reduce your project's debt load.
