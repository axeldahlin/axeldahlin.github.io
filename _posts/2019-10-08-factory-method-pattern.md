---
title: "The Factory Method Pattern"
date: 2019-08-11T14:01:25+02:00
categories: design-patterns
tags: design patterns
layout: post
permalink: /:categories/:title
---

# Problem

Pretend that you are developing an application. 

In one place in the program you want to create objects from a given
family of classes. You don't want the client code (in the context
client of an objects API) to be responsible for which objects to create or what
arguments to pass to them.


In another place in your program you want to create objects from the
same family of classes. As before, the client code in this place should not be
responsible for which objects to create and how to create them. 

In both place A and place B you want to create objects from the same
family of classes. But the logic for which object to create and what
arguments to pass to the objects needs to be different in place A
compared to B.


# Solution

The solution is the factory method pattern.

Let's have a look at the definition of the pattern from the book _Head First Design Patterns_.

>"The Factory Method Pattern defines an interface for creating an object,
 but lets subclasses decide which class to instantiate. Factory Method 
 lets a class defer instantiation to subclasses." <br>
>> -Head First Design Patterns

![Factory method pattern](/assets/img/factory-method-pattern.jpg)

If we keep with the example above, the client code in place A would
use **Creator1** to create objects of type **Product**. 

This diagram doesn't show it, but in place B there would be a
**Creator2** that also create objects of type **Product**. 

**Creator1** and **Creator2** creates objects from the same family of
classes but decides what kind of **Product** (e.g Product1, Product2,
Product3...) and what argument to pass with different business logic.

And that's it!

## Real (but silly) example website

<a href="https://axeldahlin.github.io/canvas-factory-method-example/"
target="_blank">Canvas Factory Pattern Example</a>

This example is written in JavaScript and HTML Canvas. 

Here is the class families and their relation:

![Animal factory](/assets/img/animal-factory-method-pattern.png)

In the real code these classes extends an **Animal** class instead of
implementing an **IAnimal** interface, since JavaScript doesn't have
interfaces.

All factories return either **Rat**, **Turtle** or **Rabbit**. But
the chance of what class that will be created and what paramters are passed
are different.

# RandomAnimalFacory

The animal that will be created is totally randomized and it is passed
a randomized speed value.

# JumpingAnimalFactory

The chance of it creating a **Rabbit** is much greater than the other
animals and **Rat** objects jumps higher.

**Turtles** are still not jumping, sorry turtles. 

# SlowAnimalFactory

The chance of it creating a **Turtle** is much greater than the other
animals and all animals are passed a low speed argument.

