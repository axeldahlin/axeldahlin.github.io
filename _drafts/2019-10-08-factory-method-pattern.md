---
title: "The Factory Method Pattern"
date: 2019-07-19T14:01:25+02:00
draft: true
categories: design-patterns
tags: design patterns
layout: post
permalink: /:categories/:title
---



# Problem    
Imagen that you are developing an application. 

At one place in the program you want to create objects from a given
familly of classes. You don't want the client code (in the context
client of an API) to be responsible for which object to create or what
arguments to pass.


In another place in your program you want to create objects from the
same family of classes. As before, this client code should not be
resposible for which objects to create and how to create them. 

In place A and place B you want to create objects from the same family
of classes. But the logic for which object to create and how to create
it needs to be different place A compared to B.


In these two places you want to create object from the same family of
classes. But the logic for which objects to create and what arguements
to pass to the object needs to be diffrent.


# Solution

The soultion is the factory method pattern.

Let's have a look at the definition of the pattern from the book _Head First Design Patterns_.


>"The Factory Method Pattern defines an interface for creating an object,
 but lets subclasses decide which class to instantiate. Factory Method 
 lets a class defer instantiation to subclasses." <br>
>> -Head First Design Patterns

![Factory method pattern](/assets/img/factory-method-pattern.jpg)

If we keep on with the example above the client code in place A would
use **Creator1** to create objects of type **Product**. 

This diagram doesn't show it but in place B there would be a
**Creator2** that also create objects of type **Product**. 

**Creator1** and **Creator2** creates objects of the same type but decides
what kind of **Product** (Product1, Product2, Product3...) and what
argument to pass to the objects dependeing on differnt buisiness logic.

And that is all it is to it! If you get by now, stop reading! If you
need another example to really hammer the concept in and want to see
an example of a project using the pattern, don't for your life stop
reading!

## Real (but silly) example website


[Example](https://www.google.com)

Here in an example written in JavaScript and HTML Canvas. 

Here is the class famillies and their relation:

![Animal factory](/assets/img/animal-factory-method-pattern.png)

All factories return either a **Rat**, **Turtle** or **Rabbit**.

# RandomAnimalFacory

It's totally random which animal it will create and it passes a
randomized value as speed argument.

# JumpingAnimalFactory

The chance of it creating a **Rabbit** is much greater than the other
animals and **Rat** objects jump heiger.

# SlowAnimalFactory

The chance of it creating a **Turtle** is much greater than the other
animals and all animals are passed a low speed argument.
