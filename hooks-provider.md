---
title: 'Provider Pattern and Hooks in React'
date: '2022-11-26'
---

### Patterns

First of all, let's understand what **Design Pattern** means in development enviroments. According to the [Refactoring Guru](https://refactoring.guru/):
> Design patterns are typical solutions to common problems in software design. Each pattern is like a blueprint that you can customize to solve a particular design problem in your code.``

With that in mind, the **Provider Patter** is a solution to organize and facilitate the distribuition of data among many (and in some cases all) components in an application.

There is many forms to share data between components. Passing data using _props_ is one of the most know ways to do that. Nonetheless, this strategies **aren't scalable** when we have a deep tree of components inside the application. It can be complicated to identify the origin of the data and keep then updated in every component when we are dealing whit mutable information.

Using the Provider strategy it's possible to manage this informations through a single provider and use that context to share this set of data between any component that we need.

### Hooks

Talking about **Hooks** it's important to understand why does Hooks exists and accordingly with React documentation we can say that:
> Hooks was introduced in React to solve many problems, some of them were structural problems. Hooks exist in diverse forms and can be applied in many situations and also enabling the creation of Custom Hooks. 

Among the wide variety of Hooks in React like State Hook, Effect Hook, there is the **Context Hook** that can be used to implement our Provider Pattern.

### Provider Pattern and Hooks

Using the Context Hook from React we can create one core file to handle every insertion, update or remove from a set of data and share everything in all components of our application and make it much more simple to _control_ the data flow and let this data properly _updated_ in any place we need.

One great example of data that need to be in almost the entire application is informations about the user that and is also an amazing set of data that can be controlled using **Custom Hooks** to control the user state like:
  - Login
  - Signup
  - Update
  - Deletion

If you want to know more about that strategy working in an application you can check my video about using this pattern in my app Going: https://www.youtube.com/watch?v=PBlAwejJQls