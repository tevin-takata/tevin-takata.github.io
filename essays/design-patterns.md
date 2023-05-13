---
layout: essay
type: essay
title: "Using Design Patterns"
# All dates must be YYYY-MM-DD format!
date: 2023-04-27
published: false
labels:
  - Software Engineering
  - Design Patterns
---

When a common problem occurs and affects a lot of people, it's only natural to develop similar solutions to resolve each instance of that problem. Design patterns are conceptual solutions to these design problems.

As more software tools come out, many design patterns are not needed anymore, as these tools solve the issue that the design pattern solves, usually more efficiently. But lots of common problems are resolved using design patterns that are very commonplace.

Some common design patterns that I have used are:

## Singleton

Like most design patterns on this list, this is one that I wasn't aware I was using until I learned what it was, only because I was taught it this way.

This is a pattern that essentially uses a class that is instantiated only once. This instance serves as a global variable throughout the entire application.

I have used this pattern as a way of accessing a user or profile collection. This collection can be used by different programs across the entire application, and only have one instance of it, rather than multiple collections.

## Observer

Observer design pattern uses observers to subscribe to certain objects. When something changes in the object, the observer notifies other observers. This pattern is similar to the publish-subscribe pattern, where rather than one observer notifying other observers, a group of publishers send class of information to whatever is a subscriber, whether they're there or not.

This is used in Meteor and can be used to access a collection, since it can notify the subscribers if the collection was accessed.

This also helps in reactive data, since any updates from the publishers can be sent to the subscribers and can update any data in real time.

## Factory

Factory design pattern creates new objects without explicitly creating a new instance of that object. This way, it does not expose the underlying logic and can access different classes to return an object under one factory function.

This design pattern is very common, and I have used before to create multiple instances of objects that share similar classes, like user profiles.

##

Obviously, there are numerous other design patterns that are solutions to common software design problems. These patterns can sometimes evolve overtime to solve more modern problems efficiently. Even though I don't know the names of many of these patterns, I still use some of them very often.